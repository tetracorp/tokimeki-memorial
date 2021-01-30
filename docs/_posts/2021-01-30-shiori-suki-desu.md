---
layout: post
title: "Shiori says \"Suki desu\""
categories: game-mechanics
---

In the opening narration to _Tokimeki Memorial: Forever With You_, Fujisaki
Shiori's final words beneath the tree are silent. 

There are, however, circumstances under which they will be unsilenced. Despite
rumours, it's not the [Konami Code](konami-code.html), but there is a cheat to
trigger it.

1. Table of Contents
{:toc}

### How to have Shiori say "suki desu"

At the point in the opening where Fujisaki Shiori confesses under the tree, hold
any button on a controller plugged into the second port. Shiori's line "suki
desu" will be unmuted.

### Code analysis

The opening section function, located in the overlay file `exedir/name_ent.exn`,
has the following excerpt at the point immediately after Shiori speaks under the
tree. She says "anata ga...", then her last words are normally silenced (though,
given her description of how people confess under the tree, the viewer can
probably guess).

At the point the game performs this check:

~~~c
    if (0x10 < c_girl) {
      c_girl = (c_girl & 0xf) + 0x10;
    }
    if ((c_girl == 0x10) || (cVar5 = step?_800ef86d, pad2buttons >> 0x10 != 0)) {
      c_girl = 0x10;
      SetVoiceLine(0x3aa,0x70003b5,0xf);
      gfx_8004e9bc();
      Dialog(0xffffff70,0x44,0,"す・き・で・す",0);
      FUN_8004ecac(1);
      FUN_8004ed64(0,0);
      PlayVoiceLine(0x300);
      cVar5 = step?_800ef86d;
    }
~~~

What happens here is that during the opening narration (Shiori's narration after
the title screen but before the fully animated opening FMV), the dialog for the
entire scene is actually subtitled, but for some reason it's not displayed. We
can see that it Shiori's last words are subtitled as 「す・き・で・す」,
"su-ki-de-su".

The quoted section of code begins with a check if the current girl is set to
0x10 hexadecimal, or decimal #16. This current girl variable is set while
speaking to a character, either in person or on the phone, and includes male
characters you can speak to like Yoshio. For completeness, here's the list:

- 00: Fujisaki Shiori
- 01: Kisaragi Mio
- 02: Himoo Yuina
- 03: Katagiri Ayako
- 04: Nijino Saki
- 05: Koshiki Yukari
- 06: Kiyokawa Nozomi
- 07: Mira Kagami
- 08: Asahina Yuuko
- 09: Mikihara Megumi
- 10: Saotome Yumi (Yoshio's sister)
- 11: Tatebayashi Miharu
- 12: Ijuuin Rei
- 13: Saotome Yoshio
- 14: Sotoi Yukinojou (Ijuin family butler)
- 15: Player (used when alone; name string is written in hiragana, ぷれいや)
- FF: unset

Note that there is no girl #16. I suspect that this is a special value which
only triggers when you successfully clear Shiori in the game. Waiting to view
the title intro afterward would then have Shiori voice the line "suki desu".
However, I have not currently tested this.

However, the check also triggers when buttons on controller 2 are pressed. This
memory location stores the current controller input as a 32-bit value with the
leftmost two bytes storing the buttons as one bit each, where a 1 means pressed
and a 0 means not pressed.

 Hex    | Bit | Controller  |  Mouse
--------|-----|-------------|-----------
 0x0001 |  0  | Select      | 
 0x0002 |  1  | L3          | 
 0x0004 |  2  | R3          | 
 0x0008 |  3  | Start       | 
 0x0010 |  4  | D-pad Up    | 
 0x0020 |  5  | D-pad Right | 
 0x0040 |  6  | D-pad Down  | 
 0x0080 |  7  | D-pad Left  | 
--------|-----|-------------|-----------
 0x0100 |  8  | L2          | 
 0x0200 |  9  | R2          | 
 0x0400 | 10  | L1          | Right click
 0x0800 | 11  | R1          | Left click
 0x1000 | 12  | △           | 
 0x2000 | 13  | ○           | 
 0x4000 | 14  | x           | 
 0x8000 | 15  | □           | 

Shifting the 32-bit value right 16 times will evaluate to zero only if none of
these are pressed. In other words, holding any of these buttons on the second
controller will trigger the voice line.

In my estimation, this is obviously a debug feature to test the voice line
without requiring the playtester to actually complete the game. 

I previously observed a glitch which I can't remember how to replicate, where it
will skip the visual for "anata ga" but still play the audio, so that it
incorrectly syncs the audio for "anata ga" to the visual for "suki desu" and
then continues to the opening FMV as normal.

### Addendum: Subtitles

The following subtitles appear in the code for Shiori's intro narration:

    始まりがあれば終わりがあるように、
    出会いがあればまた、別れもあるのです。
    永遠に続く二人の関係、
    それはどんなに幸せなことでしょう。
    ここ、きらめき高校には、
    一つの伝説があります。
    校庭のはずれにある一本の古木。
    そのたもとで卒業の日に、
    女の子からの告白で生まれた
    恋人達は、永遠に幸せな関係に
    なれるという伝説が…
    あなたが…、
    す・き・で・す

The following subtitles to the opening FMV also appear in the code (they're not
hardcoded into the FMV, but play as dialog):

    好きとか　嫌いとか
    最初に言い出したのは　誰なのかしら
    駆け抜けてゆく　私のメモリアル
    今日も鏡のまえで　髪をとかして　
    ピンクのリップは　Ｓｗｅｅｔ　Ｍａｇｉｃ
    とっておきのコロン
    さ・さ・や・き　キ・ラ・メ・キ
    ド・キ・ド・キ　大好き
    あなただけに見つめてほしい
    Ｔａｋｅ　ｔｈｅ　Ｃｈａｎｃｅ
    仕上げは上出来
    Ｔｅｌｌ　Ｙｏｕｒ　Ｈｅａｒｔ
    準備はＯＫ
    素敵な予感　そよ風に乗せ
    Ｔｒｙ　Ｙｏｕｒ　ＬＵＣＫ
    制服のリボン
    Ｔｅｌｌ　Ｙｏｕｒ　Ｌｏｖｅ
    結び直したら
    今日こそ言えそう
    Ｌｏｖｅ　ｍｅ　ｐｌｅａｓｅ‥‥‥
