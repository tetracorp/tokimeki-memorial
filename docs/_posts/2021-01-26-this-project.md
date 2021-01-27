---
layout: post
title: "About this project"
categories: about
---

_Tokimeki Memorial_ is a highly influential Japanese video game originally
released in 1994 for the NEC PC Engine CD-ROM platform in 1994, and later
released under the the title _Tokimeki Memorial: Forever With You_ for the Sony
Playstation in 1995, Sega Saturn in 1996, and PC in 1997.

This website, _Exploring Tokimeki Memorial_, is a project which aims to
reverse-engineer this game, primarily the 1995 PlayStation release, in order to
shed light on its obscure game mechanics and aid future analysis and translation
projects.

## Why this project?

On 1 January 2021, Tim Rogers of Action Button published an in-depth nearly six
hour long
[review of Tokimeki Memorial](https://www.youtube.com/watch?v=xb-DtICmPTY),
condensing down hundreds of hours of work into the definitive English-language
gameplay analysis of the game. The game's depth was such that on subsequent
playthroughs he continued to discover previously unknown game mechanics.

About a week later, it occurred to me that analysis of 1990s video games for
undocumented game mechanics was similar to
[earlier projects](https://tetracorp.github.io) of mine. I decided to examine
the PlayStation release of _Tokimeki Memorial: Forever With You_ in the same
manner.

## Goals

My aims for this project are less ambitious than earlier my earlier projects
examining the Commodore Amiga games [K240](https://tetracorp.github.io/k240/)
and the [Dungeons of Avalon](https://tetracorp.github.io/dungeons-of-avalon/)
series, which aimed to fully analyze those games. My reasons for this are as
follows:

1. Tokimeki Memorial is deceptively massive and more complex than it first
   appears. While the main executable for the PlayStation version is only 674
   KB, it also has twenty-six 192 KB overlay files which contain further
   executable code, and which can be swapped in and out of memory as required,
   bringing the total program size to at least 5.6 MB. This was obviously
   necessary to fit the program within the PlayStation's 2 MB of RAM, but it
   significantly complicates code analysis.
2. This game was highly succesful, and a certain amount of analysis has already
   been performed by others since its initial release. The benefit of a new
   complete analysis is limited.
3. Tokimeki Memorial released on several platforms, and in multiple revisions.
   A truly complete analysis would require multiple separate dissassemblies,
   each platform involving different tools and methods (for example, while there
   are disassemblers for the PC Engine's
   [HuC6280](https://en.wikipedia.org/wiki/Hudson_Soft_HuC6280) CPU, it is not
   supported by Ghidra).

However, with that in mind, my goals are as follows:

1. To analyze the game's core functionality, with the aim of documenting game
   mechanics and potentially discovering new unknown features, for the benefit
   of players and those interested in the game.
2. To provide a resource for future users attempting to reverse-engineer
   games for the original PlayStation (PSX), especially future analysis of
   _Tokimeki Memorial_.
3. To provide documentation which may make a future fan translation of _Tokimeki
   Memorial_ possible.

Except where otherwise specified, all information on this site refers to the
PlayStation version of the game, _Tokimeki Memorial: Forever With You_.

See the [main index](https://tetracorp.github.io/tokimeki-memorial) for a list
of the project's findings to date.
