---
layout: post
title: "Konami Code (WIP)"
categories: game-mechanics
---

At several places in _Tokimeki Memorial_ for PSX, the player can input the
Konami Code (up, up, down, down, left, right, left, right, cross, circle).

1. Table of Contents
{:toc}

### Technical specifications and references

The partial [debug symbols dump](../data/debug-symbols-dump.html) reveals one
function and four variables:

    8004ECB8  konami_command_check

    800C6F94  konami_command
    800C6FE4  konami_command_tag
    800C6FE8  konami_command_flag
    800C6FEC  konami_command_timer

This is evidence that Japanese developers at Konami internally referred to the
Konami Code as the _Konami command_ in 1995. Here is the decompiled source code
for the konami command check:

~~~c
void konami_command_check(void){
  uint uVar1;
  
  if (konami_command_flag == '\0') {
    uVar1 = konami_command_tag + 1 & 0xff;
    if (pad2buttons == (&konami_command)[konami_command_tag]) {
      konami_command_tag = (byte)uVar1;
      if (0x11 < uVar1) {
        konami_command_flag = '\x01';
      }
      konami_command_timer = '\x10';
    }
    konami_command_timer = konami_command_timer + -1;
    if (konami_command_timer == '\0') {
      konami_command_tag = 0;
    }
  }
  else {
    konami_command_timer = konami_command_timer + '\x01';
    if (konami_command_timer == '\0') {
      konami_command_tag = 0;
      konami_command_flag = 0;
      return;
    }
  }
  return;
}
~~~

`konami_command` defines the bytes which must appear on controller 2 to trigger
the `konami_command_flag`:

    00 10 00 00   ; D-pad up
    00 00 00 00   ; 
    00 10 00 00   ; D-pad up
    00 00 00 00   ; 
    00 40 00 00   ; D-pad down
    00 00 00 00   ; 
    00 40 00 00   ; D-pad down
    00 00 00 00   ; 
    00 80 00 00   ; D-pad left
    00 00 00 00   ; 
    00 20 00 00   ; D-pad right
    00 00 00 00   ; 
    00 80 00 00   ; D-pad left
    00 00 00 00   ; 
    00 20 00 00   ; D-pad right
    00 00 00 00   ; 
    40 00 00 00   ; Cross
    20 00 00 00   ; Circle
    00 00 00 00   ; 
    00 00 00 00   ; 

### Name entry (unknown effect)

The Konami code appears to be something you can enter as a starting name,
although I have yet to locate the exact code which handles it. Three consecutive
sets of SJIS strings in `exedir/name_ext` reference cheat codes entered as a set
of names:

    こなみまん        ; konamiman

    みんな            ; minna ("everyone")
    仲良し            ; nakayoshi ("friendly")

    上上              ; up up
    下下              ; down down
    左右左右×         ; left right left right X

    ↑↑
    ↓↓
    ←→←→×

Setting your nickname to "Konamiman" is a known cheat code to start all stats to
573, while setting your name to Minna Nakayoshi maxes out your friendship with
all girls.

The other strings are references to the Konami code, which appear to be intended
to set as name and nickname. Entering the surname ↑↑, forename, ↓↓, and nickname
←→←→× (using the multiplication symbol x), will increase all starting stats to
999 (including Stress). I cannot determine the effect of entering the name in
kanji;
[this wiki entry](https://konami.fandom.com/ja/wiki/%E3%82%B3%E3%83%8A%E3%83%9F%E3%82%B3%E3%83%9E%E3%83%B3%E3%83%89)
says something about reducing all starting stats to 0.

### Skip intro video

Other than the `konami_commmand_check` function, there are two functions in the
main executable which read check `konami_command_flag`: one on the intro, and
one in the magazine. There's a third reference which just resets it to zero
after the intro. There are also other references in other overlay files, which I
have yet to fully explore.

There's a rumour that entering the Konami code during the intro causes Shiori to
say "suki desu". This isn't true, although there is a separate way to trigger
that event (see [Shiori says "suki desu"](shiori-suki-desu.html)).

However, there is indeed a check for the Konami code in the intro section, after
you hit "game start" on the title screen. In testing, it appears to just skip
the intro. This is probably convenient for game testers.

~~~c
  if (konami_command_flag != '\0') {
    cursor_disp_switch(0);
    PlayVoiceLine(0x7f);
    goto_step(0x11);
    goto_sub_step(1);
    PlayVoiceLine(0x501);
  }
~~~

In the Playstation the Best re-release, this check has actually been modified to
make two additional checks. The first line now reads:

~~~c
  if (((konami_command_flag != '\0') && (iVar1 = FUN_80045288(), iVar1 == 1)) && (1 < DAT_800e7389)) {
~~~

I have yet to discover what the additional checks are. However, the function is
still the same; it just skips the intro video.

### Magazine

The konami mentioned in a text string `p_mes9`, referenced by
`magazine_class_init`:

> 情報誌を見ながら、コナミ コマンドを入力すると…。 ↑↑↓↓←→←→×○）

Translation:

> While reading the magazine, input the Konami Command with... ↑↑↓↓←→←→×○

I don't know the circumstances under which it was displayed. However, it refers
to a functionality in the magazine. An array of fourteen strings are referenced
here:

1. ページの中央・現在の位置 赤・身体　黄・感情 緑・知性　のリズム）
2. バイオリズム・２ 青い線を横切るときは 調子が悪い）
3. バイオリズム・３ 青い線から遠いとき調子が良い 同じ距離なら上のほうが良い）
4. 電話を使って女の子に直接、 電話をかけることができる）
5. このステレオ ラジオ放送があんまりよく 聞こえないんだよな）
6. ゲームをクリアすると、 その女の子のマスコット人形が 手に入る）
7. マスコットは Ｒ１押しながら…移動 Ｒ２押しながら…紐を伸ばす）
8. そういえば、このゲームの 説明書を机に置いたような）
9. ２Ｐ（○×△□同時） 　→１Ｐ○連打）
10. □ボタンで好みの カーソルが選べます）
11. セレクトボタンで メニューモードが変更できます）
12. ２Ｐスタートボタン ＳＤキャラのアニメスピード 変更）
13. ゲームをクリアしても あわてないこと）
14. 『袖竜』には『防御』）

Translation:

1. Middle of page: current position. Red: Physical. Yellow: Emotional. Green:
Intelligence rhythm.
2. Biorhythm #2: When you cross the blue line, you are in poor form.
3. Biorhythm #3: When far from the blue line, you are doing well. An equal
   distance from the top is good.
4. You can call a girl directly using the phone.
5. This stereo radio broadcast is practically inaudiable.
6. When you clear the game, you obtain a mascot doll of that girl.
7. If you press R1, the mascot moves. Press R2 to pull the string.
8. Now that you mention it, this is like placing the game's instruction manual
   on your desk.
9. Press Circle, Cross, Triangle, and Square together on the second controller
   to enable autofire on Circle on the first controller.
10. Press the Square button to change the cursor to your liking.
11. Press the Select button to change menu mode.
12. Press Start on the second controller to change the the SD character
    animation speed.
13. When you beat the game, don't rush.
14. For "Soderyuu", "defense".

In testing, I haven't succeeded at triggering these phrases. The Tokimeki
Memorial Dictionary (a Japanese wiki) says that it should be input on the first
controller, selecting the magazine with the final Circle button.
