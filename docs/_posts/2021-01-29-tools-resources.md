---
layout: post
title: "Tools and resources for PSX reverse-engineering"
categories: methods
---

The following is a list of tools and documents useful for analyzing, modding or
translating PlayStation games. Many of them are conveniently available in Linux
by a package manager like `apt`.

1. Table of Contents
{:toc}

### PSX file format conversion tools

[jPSXdec](https://github.com/m35/jpsxdec)
: Audio/video convertor which can extract PSX file formats from a disc image
: and build an index of file locations. Converts XA, STR, TIM.
[psxsdk](https://github.com/simias/psxsdk)
: Unofficial SDK for creating PlayStation games. Includes source for some
: conversion tools for PSX formats (ISO/BIN, WAV/VAG. TIM/BMP).

### CD-ROM tools

[PSXImager](https://github.com/cebix/psximager)
: Three tools: psxrip (extract files and disc metadata from BIN/CUE),
: psxbuild (creates a disc image), and psxinject (modify a disc image).
: Unfortunately doesn't provide a build, and has difficulty with some images.
AcetoneISO
: Linux tool to mount, extract and burn single-track ISO and BIN.
[PowerISO](https://www.poweriso.com/)
: Commercial Windows/Linux CD-ROM authoring tool.
ccd2iso
: Linux tool to convert IMG to ISO.
iat
: Linux tool to convert various formats to ISO.
bchunk
: Linux tool to convert BIN/CUE to ISO and CD audio to WAV.
: Supports PSX 2336-byte chunk tracks.
isoinfo
: Linux tool to list contents of ISO files.
[binmerge](https://github.com/putnam/binmerge)
: Python script to combine a multi-track BIN/CUE into one.

### Disassemblers and decompilers

[Ghidra](https://ghidra-sre.org/)
: NSA's disassembler/decompiler, released to the public in 2019.
[Radare2](https://www.radare.org/)
: Free and open-source disassembly tool.
[IDA Pro](https://www.hex-rays.com/products/ida/)
: Commercial decompiler. There's a
: [free](https://www.hex-rays.com/products/ida/support/download_freeware/)
: version but it only supports x86/64 and not MIPS (PSX).
[ghidra_psx_ldr](https://github.com/lab313ru/ghidra_psx_ldr)
: PSX executable add-on for Ghidra.
[This Dust Remembers What It Once Was](https://www.beneaththewaves.net/Software/This_Dust_Remembers_What_It_Once_Was.html)
: Tools for aiding PSX analysis with Ghidra.
: Convert PSX-EXE to ELF and parse PsyQ .SYM files.

### Emulators and debuggers

[Mednafen](https://mednafen.github.io/documentation/psx.html)
: Emulator with a powerful debugger.
[No$psx](https://problemkaputt.de/psx.htm)
: PSX emulator and debugger.
[ePSXe](https://www.epsxe.com/)
: PSX emulator.

### Documentation

[Nocash PSX Specifications](https://problemkaputt.de/psx-spx.htm)
: Description of PSX systems from the author of an emulator.
[Everything You Have Always Wanted to Know about the Playstation But Were Afraid to Ask v1.1](
https://www.raphnet.net/electronique/psx_adaptor/Playstation.txt)
: A collection of documentation about the PSX hardware and history from 2000
: (originally [here](https://web.archive.org/web/20011211221846/http://www.execpc.com/~halkun/PSX/index.html)).
[Introduction to Hacking the Sony Playstation One](https://www.retroreversing.com/ps1/)
: RetroReversing's articles on the PSX.
[Net Yaroze Startup Guide](https://psx.arthus.net/sdk/NetYaroze/Net%20Yaroze%20Official%20-%20Startup%20Guide.pdf)
: Documentation for the official Net Yaroze PSX devkit.

### Development and miscellaneous

[Romhacking.net PSX Utilities](https://www.romhacking.net/?page=utilities&category=&platform=17&game=&author=&os=&level=&perpage=200&title=&desc=&utilsearch=Go)
: A list of PSX utilities for various platforms.
[psx.arthus.net](https://psx.arthus.net/)
: A collection of PSX development resources.
[PSX Links](https://ps1.consoledev.net/)
: Another collection of documentation and resources.
[loveemu labo's PSX articles](https://loveemu.hatenablog.com/archive/category/PSX)
: Some articles.
