---
layout: post
title: "Files changed between revisions"
categories: data
---

Releases of _Tokimeki Memorial: Forever With You_ for PSX after the original
print run changed various files. Since normal file listings are not accessible
in later printings of the disc, a creative approach has to be taken to compare
files. This analysis reveals that various files have changed between revisions.

See also [File date list and analysis](file-dates.html).

1. Table of Contents
{:toc}

### Preface: Method

The main executable of _Tokimeki Memorial_ accesses files by referencing the
disc sector, rather than the filename. In the original release, the file index
is accessible anyway, allowing the filenames to be viewed in a normal PC.
Subsequent printings appear to have a corruption in the file index, perhaps
intentionally to foil casual piracy or cheating.

However, the files appear to be located in the same sectors. This means applying
the index for the original disc to the later ones gives us a chance to recover
the files for comparison to the originals.

A tool called [jPSXdec](https://github.com/m35/jpsxdec), intended for extracting
FMV from PSX discs, has the side-effect of producing an index which maps any
known filenames to disc sectors. By replacing the .BIN with another and loading
the same index file, it's possible to extract the same files to the same names,
assuming they are still the same filesize and in the same locations.

### Original release Rev 1 v110 => Limited edition v110 (31 Aug 1995)

No changes. All files are identical, except for the CD-ROM disc metadata.

### Rev 1 v110 => Rev 2 v125 (17 Nov 1995)

The following files changed:

    psx.exe
    openxa.str
    konamic3.str
    cdrom/bs/d_12_02.bs
    cdrom/bs/d_24_03.bs
    cdrom/bunka/bun_fu.bin
    cdrom/bunka/ko_s6.bin
    cdrom/exedir/bunkaken.exn
    cdrom/exedir/bunkasai.exn
    cdrom/exedir/bunka_sd.exn
    cdrom/exedir/date2.exn
    cdrom/exedir/date.exn
    cdrom/exedir/ending.exn
    cdrom/exedir/en_nichi.exn
    cdrom/exedir/etc.exn
    cdrom/exedir/geko.exn
    cdrom/exedir/kangei.exn
    cdrom/exedir/master.exn
    cdrom/exedir/name_ent.exn
    cdrom/exedir/olh.exn
    cdrom/exedir/omimai.exn
    cdrom/exedir/option.exn
    cdrom/exedir/rensyu.exn
    cdrom/exedir/rpg_bat.exn
    cdrom/exedir/shougatu.exn
    cdrom/exedir/shugaku.exn
    cdrom/exedir/taco.exn
    cdrom/exedir/taiiku.exn
    cdrom/exedir/tel.exn
    cdrom/exedir/tt.exn
    cdrom/exedir/valen.exn
    cdrom/fukutest/joho.nbn
    cdrom/fukutest/option.nbn
    cdrom/fukutest/staff_r.nbn
    cdrom/serifu/date_ka.bin
    cdrom/serifu/date_mi.bin
    cdrom/serifu/date_ni.bin
    cdrom/serifu/ending.bin
    cdrom/serifu/event_as.bin
    cdrom/serifu/event_ka.bin
    cdrom/serifu/event_kg.bin
    cdrom/serifu/event_ni.bin
    cdrom/serifu/gasshuku.bin
    cdrom/serifu/shugaku.bin
    cdrom/serifu/white.bin
    cdrom/serifu/xmas.bin
    cdrom/shiai/siai_tx.bin
    cdrom/taiiku/kari.bin
    cdrom/taiiku/taopd.bin
    cdrom/taiiku/tasetu.bin
    cdrom/tara_obj/karakasi.bin
    cdrom/vab_seq/koku_vol.vh
    cdrom/xa_g/asahina.xa
    cdrom/xa_g/bgm378.xa
    cdrom/xa_g/etc.xa
    cdrom/xa_g/fujisaki.xa
    cdrom/xa_g/himoo.xa
    cdrom/xa_g/kagami.xa
    cdrom/xa_g/katagiri.xa
    cdrom/xa_g/kisaragi.xa
    cdrom/xa_g/kiyokawa.xa
    cdrom/xa_g/koshiki.xa
    cdrom/xa_g/mikihara.xa
    cdrom/xa_g/nijino.xa
    cdrom/xa_g/yoshio.xa
    cdrom/xa_g/yumi.xa

This list of changes omits several files which read as unchanged except that
they're padded with zeroes. Many of these are `.bs` files which appear to be
padded to some round number of bytes, either as an artifact of the file read
process or perhaps for some technical reason.

Nearly all the overlays in `exedir` are changed. The only ones which haven't are
`event.exn` and `gaozi.exn`. The leftover object file `o.bin` is still
unchanged, suggesting that it's an accidental leftover from an old version.

The extraction method doesn't allow for examining file dates. However, for those
files in the root directory, files which changed have retained their original
file date. This suggests that the staff member who authored the disc provided
updates by modifying the original disc image without changing its metadata. It
also suggests that, if we could read the metadata (which appears to still exist,
it's just somehow corrupted or unreadable), it's plausible that the file dates
would not have changed.

### Rev 2 v125 => Rev 4 v143 (31 Mar 1996)

The following files changed between V125 and V143:

    psx.exe
    cdrom/exedir/bunka_sd.exn
    cdrom/exedir/bunkaken.exn
    cdrom/exedir/bunkasai.exn
    cdrom/exedir/date.exn
    cdrom/exedir/date2.exn
    cdrom/exedir/en_nichi.exn
    cdrom/exedir/ending.exn
    cdrom/exedir/etc.exn
    cdrom/exedir/geko.exn
    cdrom/exedir/kangei.exn
    cdrom/exedir/master.exn
    cdrom/exedir/name_ent.exn
    cdrom/exedir/olh.exn
    cdrom/exedir/omimai.exn
    cdrom/exedir/option.exn
    cdrom/exedir/rensyu.exn
    cdrom/exedir/rpg_bat.exn
    cdrom/exedir/shougatu.exn
    cdrom/exedir/shugaku.exn
    cdrom/exedir/taco.exn
    cdrom/exedir/taiiku.exn
    cdrom/exedir/tel.exn
    cdrom/exedir/tt.exn
    cdrom/exedir/valen.exn
    cdrom/master/tear.bin

Again, files whose only changes are zero-padding are omitted from the changes
list. The files `event.exn` and `gaozi.exn` are still unchanged.

### Rev4 v v.143 => PlayStation the Best (25 Dec 1997)

This version looks like it may be a new CD image burned from scratch from the
set of files, given changes like file dates and punctuation in the metadata
name. The following files have changed:

    cdrom/bunka/twinbee.bin
    cdrom/en_game/kingyo.bin
    cdrom/en_game/shateki.bin
    cdrom/exedir/bunkaken.exn
    cdrom/exedir/bunkasai.exn
    cdrom/exedir/bunka_sd.exn
    cdrom/exedir/date2.exn
    cdrom/exedir/date.exn
    cdrom/exedir/ending.exn
    cdrom/exedir/en_nichi.exn
    cdrom/exedir/etc.exn
    cdrom/exedir/geko.exn
    cdrom/exedir/kangei.exn
    cdrom/exedir/master.exn
    cdrom/exedir/name_ent.exn
    cdrom/exedir/olh.exn
    cdrom/exedir/omimai.exn
    cdrom/exedir/option.exn
    cdrom/exedir/rensyu.exn
    cdrom/exedir/rpg_bat.exn
    cdrom/exedir/shougatu.exn
    cdrom/exedir/shugaku.exn
    cdrom/exedir/taco.exn
    cdrom/exedir/taiiku.exn
    cdrom/exedir/tel.exn
    cdrom/exedir/tt.exn
    cdrom/exedir/valen.exn

A file size modification appears to have occurred in `cdrom/taiiku/kasetu.bin`.
This and every file alphabetically after it on the disc are detecting as
modified, which probably means that this file was changed in size and as a
result all files after it in the disc are actually moved in position. The sector
count is also apparently 14 blocks smaller (298,500 instead of 298,514). It's
possible that some files located after `cdrom/taiiku/kasetu.bin` have been
modified.

It may be notable that `event.exn` and `gaozi.exn` remain unchanged from the
original release.

The main exe has been renamed from `PSX.EXE` to `SLPM_86.053`, and `system.cnf`
has been updated to reflect that.

### Other releases

While there was a 2003 PSone re-release (SLPM-87300), I don't have a copy of
that version.
