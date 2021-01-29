---
layout: post
title: "What is decompilation?"
categories: methods
---

The following is a complete newbie introduction to the concept of disassembly or
decompilation of software. If you already understand this, skip to
[Decompiling PSX games with Ghidra](decompiling-psx-games.html).

### Compiling

In general, programs are written in a _programming language_, which must first
be converted into _machine code_ (essentially the computer's native language) so
that a computer can run it. The main type of tool which performs this conversion
is called a _compiler_.

It's also possible to write in something very close to machine code, using a
type of programming language known as an _assembly language_, which is converted
into machine code using a program called an _assembler_. This is more difficult
to understand and program in, but in the mid-1990s and earlier, assembly
language was commonly used in game development to optimize games for the
relatively limited hardware of the day.

For most commercial videogames, we only have the executable machine code, not
the original _source code_ as written by the programmer. Recently, some
companies have
[released the source code](https://en.wikipedia.org/wiki/List_of_commercial_video_games_with_later_released_source_code)
to ancient video games, but it still happens rarely.

### Disassembly

It may happen that we wish to examine how a program works. Many videogames have
features which are non-obvious in their functionality and and not fully
described in the game's official documentation. However, machine code is
difficult to interpret, and what we want is the human-readable source code.

One solution is a _disassembler_, a tool which will turn a program into assembly
language. For games originally written in assembly language, this is effectively
recreating the original source code. However, there are a number of limitations
with this approach.

1. The compilation or assembly process usually strips all comments, variable
names, and function names from the program. The original programmers used these
to understand the meaning of the program, but the CPU doesn't use them, so
they're usually deliberately stripped from the final program to save memory.
This means our disassembly will have no variable names.
2. The process of disassembly is not perfect. Programs contain both _code_
(machine code instructions) and _data_ (numbers, variables, text, etc), and it
is not always obvious to the decompiler whether any given byte is code or data.
3. For languages written in something other than assembly language, disassembly
will still only give you assembly language.

### Decompilation

For games which were originally written in a high-level compiled language like C
(which was commonly used for game development in the late 1990s), we ideally
want to recreate the original source code in that language.

A tool known as a _decompiler_ will reverse the program back into C or another
high-level language, making reasonable estimates as to what the source code
would need to have produced the machine code. This is an advanced feature, and
it's not trivial to do.

Like disassembly, however, we are still limited by the information available in
the main executable. There are no variable names. An advanced tool like Ghidra
can make reasonable estimates as to what is a function, what is a string, and so
on, based on the way these addresses are used in the program, but it's still not
perfect and requires manual tweaking. Also, you're still not going to get
variable names or comments.

The main advantage of a decompiler is that it usually produces C, rather than
assembly language. Assembly language is challenging to learn and different for
every CPU. C is relatively standard across CPUs and easier to read, and even if
you're not familiar with C you may be familiar with another C-influenced
language like JavaScript or PHP.

### Symbol table

In some cases, however, developers of commercial games have left the variable
names and function names in the finished program in some form. This is usually
an accident, but it's a boon to anyone trying to reverse-engineer the game.

This set is referred to as a _symbol table_ or a set of _debug symbols_, and
often included either in the original executable or a separate file.

They are usually left in during the game's development to aid programmers
attempting to debug the program, but the finished version of the game will
typically remove them. In cases where the developers have left them in,
disassemblers and decompilers can read the file.

Lists of games known to have left debug symbols in appear in the articles
[Playstation 1 Games with Debug Symbols](https://www.retroreversing.com/ps1-debug-symbols)
and
[PS2 Games With DebugSymbols](https://tcrf.net/User:Kojin/PS2_Games_With_Debug_Symbols).

---

Next: [Reverse-engineering PSX game with Ghidra](decompiling-psx-games.html)
