---
layout: post
title: "Reverse-engineering PSX games with Ghidra"
categories: methods
---

This is a collection of information I've found while researching PlayStation
(PSX) reverse-engineering. If you're unfamiliar with the basic idea of
reverse-engineering, first see [What is
decompilation?](what-is-decompilation.html).

### Reading PlayStation discs

PlayStation discs are recorded in stnadard ISO 9660 CD-ROM format and can be
read in a PC in the normal manner. Disc image files (e.g. .ISO, .BIN/CUE) can be
mounted or extracted with software like AcetoneISO or PowerISO. However, there
are sometimes obstacles:

1. Some files may be effectively hidden. The PsyQ API used by most PSX games can
read files from disc based on a numeric sector location (LBN) rather than
filename, but to a PC they're unlisted.
2. It is thought that some PSX discs were intentionally created with disc errors
(bad blocks) as an anti-piracy measure to prevent copying.
3. Some software for reading disc images has trouble with multi-track discs. You
may have to do some quirk like load the .BIN for the first track into
AcetoneISO, or combine multiple .BINs with
[binmerge](https://github.com/putnam/binmerge), or make a fake .cue file that
only includes the first track.

However, at least two key files are usually easily readable: `system.cnf`, which
will tell you the filename of the main game executable; and the executable file
itself, which will usually be named either `PSX.EXE` or something like
`SLPM_86.053`. This is the file needed for executable analysis.

### Beginning an executable analysis with Ghidra

[Ghidra](https://ghidra-sre.org/) is a piece of reverse-engineering software
developed by the NSA and released for free to the public in 2019. While there
are other similar tools like
[radare2](https://www.radare.org/) and 
[IDA Pro](https://www.hex-rays.com/products/ida/),
Ghidra is both exceptionally powerful and free of cost.

Ghidra can also natively handle the CPU type used by the PSX (the R3000, which
Ghidra will understand as MIPS default 32-bit little-endian). A third-party
plugin called [ghidra_psx_ldr](https://github.com/lab313ru/ghidra_psx_ldr) will
aid in PSX-specific analysis.

Download and unzip [Ghidra](https://ghidra-sre.org/).
Download the
[latest release zip](https://github.com/lab313ru/ghidra_psx_ldr/releases)
of `ghidra_psx_ldr`, and _don't unzip_ it, but instead, put it in Ghidra's
folder. Launch Ghidra for the first time by running  `ghidraRun.bat` on Windows
or `./ghidraRun` on Linux. From the menu select File - Install Extensions and
pick `ghidra_psx_ldr`.

Create a new non-shared project (File - New Project). Click on the project entry
in the list and click the green dragon icon to open the Code Browser. From this
new window, select File - Import (or press I) and select the PlayStation
executable file you got from the disc.

You should now be given the option to run Auto-Analyze on the program. If you
choose not to do this for some reason, you can run it later from the Analysis
menu, or press A. Auto-Analyze will take some time to generate a disassembly.
When it's done, hit CTRL-S to save. For future reference, note that save will
block undo history.

A lot of the default open windows aren't important here. The main ones you want
open are the Symbol Tree (lists variable and function names), Listing (shows
MIPS dissassembly) and Decompile (shows C). Other windows are just taking up
space right now.

### Making sense of disassembly

You now have several tens of thousands of lines of MIPS assembly language,
probably with few or no variable and function names set. This can be daunting,
especially if you're not familiar with MIPS assembly.

First, consider the assembly layout. An excerpt:

                         **************************************************************
                         *                          FUNCTION                          *
                         **************************************************************
                         undefined myrand()
                           assume gp = 0x800f0d90
         undefined         v0:1           <RETURN>
                         myrand
    800425d0 0f 80 03 3c     lui        v1,0x800f
         assume gp = <UNKNOWN>
    800425d4 f0 01 63 8c     lw         v1,offset rng_800f01f0(v1)                       = ??
    800425d8 0f 80 01 3c     lui        at,0x800f
    800425dc 77 03 62 24     addiu      v0,v1,0x377
    800425e0 08 00 e0 03     jr         ra
    800425e4 f0 01 22 ac     _sw        v0,offset rng_800f01f0(at)                       = ??

"FUNCTION" here is a comment signifying that Ghidra believes this is the start
of a function, likely because auto-analysis noticed a jump instruction to this
location elsewhere in the code).

`undefined myrand()` gives the function name. Almost always this will instead be
a default name like FUN_800425d0, because the executable did not retain its
proper name. When you eventually work out what a function or variable does, you
can click on its name and hit "L" on the keyboard to enter a label, and the
name change will take effect throughout the program.

If a function begins pre-identified, you can usually thank `ghidra_psx_ldr` for
recognizing it as a reference to one of the PsyQ standard library functions from
the PSX devkit. These can be a critical starting point for uncovering game
functions. For example, tracing references to the standard `rand` function can
identify game mechanics using randomness; `print` can reveal debug output;
and `write` in a PSX game is essentially always writing to memory card, which
can lead you to the memory sections containing variables which which maintain
aspects of long-term game state.

Each line of code begins with an eight-digit number (e.g. `800425d0`). This is
the byte location in memory where this instruction is located. PSX software
often addresses memory starting at 0x80000000 rather than zero, but both refer
to the same physical memory, e.g. 0x800425d0 and 0x000425d0 address the same
memory (see [Memory Map](https://problemkaputt.de/psx-spx.htm#memorymap) at the
Nocash PSX Specifications page for the technical details).

The next section in each line contains four sets of two digits. These are the
four bytes located in that one 32-bit _word_. This might be one instruction, or
one four-byte variable, or whatever.

Next is the instruction as represented in assembly language. It may be more
useful in most cases to examine the Decompile window instead, which shows you
the function in C.

Another useful key is to hit the semicolon key ; to insert a comment. You can
set comments either in the disassembly or the decompile window.

### Identifying code and data

Ghidra is reasonably good at identifying code correctly, but not perfect. Since
all it has in the executable are raw bytes, it may sometimes fail to correctly
identify a section as code, or mistake its data type.

If you have a hunch that a chunk of unrecognized data might be code, select the
first byte and hit D to disassemble. Sometimes, this is actually a function,
perhaps one that isn't directly called from anywhere. Hit F to turn it into a
function. If this turns out to be a mistake (e.g. the resulting "code" is not
right), just Ctrl-Z your way back to how things used to be. You can also hit C
to turn an identified section back into unidentified bytes.

You can also right-click a line, select Data, and pick a datatype to identify
as. This is good for picking out strings. Japanese games in particular often use
Shift-JIS encoding which Ghidra won't automatically pick up. Right-click any
string, go to Data - Settings and set the charset to Shift-JIS. Even better,
Data - Default Settings will set this for all strings.

Ghidra even lets you enter a translation for a string. You can translate at a
site like [WWWJDIC](https://www.edrdg.org/cgi-bin/wwwjdic/wwwjdic).

### Following code flow

If you encounter a function or instruction variable, you can go to it by
double clicking on it, or moving the text cursor there and hitting Enter. You
can return to your previous position by hitting Left in the toolbar or Alt+Left
on the keyboard.

A function may have an XREF section at the top right. This is a list of
other functions which call it. You can also see a list of references to a
variable or function by selecting it and hitting Ctrl-Shift-F. A useful approach
is to start with something you can understand (a string or named function),
trace what functions use it, work out how those functions work, and so on.

Each label you can place gives a piece of the puzzle which can aid you in
understanding later code.

### Examining memory live with a debugger

Although `ghidra_psx_ldr` has a debugger, at time of writing it's currently
limited in functionality. The emulator Mednafen has a much more powerful
[debugger](https://mednafen.github.io/documentation/debugger.html)
which will let you observe and modify memory in real time.

Set up Mednafen and run it with a GUI like Mednaffe. Launch a game (it accepts
.BIN/CUE files, even ones which don't read correctly on a PC). If you have
trouble with the controller (and I recommend configuring an actual controller,
which will let you enter inputs while the debugger screen is up), follow these
instructions:

1. Start any game.
2. Press all the controller buttons and d-pad directions, twirl all analog
sticks to the maximum, and press all shoulder buttons.
3. Hit F3 to recenter the controllers.
4. Use Alt-Shift-1 to start controller configuration, and press buttons as
directed.

This controller setup only has to be done once.

Now, hit Alt-D to load the debugger. The 
[Mednafen debugger documentation](https://mednafen.github.io/documentation/debugger.html)
will give you full information on the controls for the debugger, but the
important ones are that Alt-1 will show you the CPU, S will stop or step to the
next instruction, R will resume, and Alt-3 will show memory. This view updates
in real time.

While in the memory screen, hit G and type an address to go there. The addresses
used by Mednafen match up with the ones in Ghidra, except they start with 0
instead of 8. You can watch known variables change in real-time. You can also
hit D to dump memory to a file for later analysis. Dump from 0 to 200000
(hexadecimal), which will give you 2MB.

### Additional executable files (overlays)

The PSX only has 2MB of RAM and 1MB of VRAM, which limits the maximum program
size to 2MB. Unlike cartridge-based systems, where the CPU can address the ROM
directly, CD-based consoles had to load into RAM first, hence loading times.
For a lot of PlayStation games this was sufficient, but for complex games it may
not be enough.

The solution is the PsyQ _overlay_ system, where chunks of the program are saved
in separate files, which the main executable can load and unload as necessary.
For example, _Tokimeki Memorial_ has something like 4.9 MB of optional code
in overlays.

Each overlay is intended to be loaded to a fixed location in memory. Discovering
where it is loaded is tricky, but the method which I found to work is as
follows:

1. Hex edit the overlays file and print the first sixteen bytes or so of each.
2. Reach a point in game which loads this code. Dump RAM.
3. Search for those bytes in RAM to find where they are loaded in memory.

Once you know where the overlay is loaded in memory, you can load it into Ghidra
as follows:

1. In the code browser, select File - Add to Program and choose the relevant
binary.
2. Hit "Options". Tick "Overlay", enter a block name, and enter the relevant
base address (remember that for PSX overlays this is probably going to start
with 8 rather than 0).
3. Select Tools - Memory Map (or hit the icon on the toolbar). Select your
overlay and ensure the following are ticked: R, X, Overlay, and Initialized. "X"
is important as it determines executable.
4. Double-click the start address. This should bring it up in the code browser.
5. Analysis - Auto Analysis to decompile with this new code.

A challenge with overlays is that the overlay files are sometimes unlisted in
the CD-ROM structure, since only the main EXE has to be accessible to the
filesystem to boot from. You would have to examine the main executable code to
see what's being loaded to where and and how many bytes. Alternatively, you
might extract it from a memory dump.
