---
layout: post
title: "Effects of Shiori's birthday"
categories: game-mechanics
---

After asking the player to enter their own name, date of birth, and blood type,
_Tokimeki Memorial: Forever With You_ takes the perhaps unusual step of asking
you to select classmate Fujisaki Shiori's date of birth and blood type as well.
This has several mechanical effects.

1. Table of Contents
{:toc}

## Invalid dates

You can't set either the player or Shiori's birthday to Feb 29. While 1996 is a
leap year, the game won't let you have only one birthday in the entire game.

Naturally, you can't set either birthday to invalid dates (Feb 30, Feb 31, Apr
31, Jun 31, Sep 31, or Nov 31). If you try, it will automatically set it to the
last valid day of that month.

## Club

Shiori's birthday determines which club she will join. This feature was already
well known, with the exact formula even appearing in English in
[QLai's FAQ](https://gamefaqs.gamespot.com/ps/573657-tokimeki-memorial-forever-with-you/faqs/4668)
v1.2 as far back as 13 December 1996.

The particular code appears in `exedir/name_ext.exn`:

~~~ c
uVar3 = (((birthday_shiori << 0x17) >> 0x1b) * 3 + (birthday_shiori & 0xf)) % 0xb;
club_800ee92a = (byte)(uVar3 << 4) | club_800ee92a & 0xf;
printf("FUJISAKI CLUB %x\n",uVar3);
bVar1 = (&DAT_name_ext__8014d03c)
        [((uint)(birthday_player << 0x15) >> 0x1e) * 4 + ((birthday_shiori << 0x15) >> 0x1e)];
printf("aisyo %d \n");
~~~

A side-effect is that there is a slightly uneven distribution of which club
Shiori will join. There are 32 days which will cause Shiori to join the drama
and swimming club (8.77% each), 33 days to join the art, brass band, computer,
literature, or soccer club (9.04% each) and 45 days on which she will join the
baseball, basketball, science or tennis club (9.32% each).

Note the unusual way birthdates are stored. It would be easy to store the day
and month in separate bytes, but instead they're stored in one half byte each.
Shiori's default birthday of 14 Feb is stored as 0xE2, or binary 0b11100010,
split into 0b1110 (14) and 0b0010 (2). Of course, since four bits have only
16 possible values, days above 15 result in an overflow of 01 to the next byte
(PSX CPU is MIPS little-endian). Note how the calculation in line 1 works by
shifting 23 bits left to cut off all but the top eight bits, then shifting 27
right to cut off the bottom four bits.

The particular calculation can be simplified to `(month + (3 * day)) mod 11`,
as correctly stated in QLai's 1996 FAQ. Interestingly, QLai states that the PC
Engine version places the date and month the opposite way around in the
calculation; I wonder if this swap is a bug or intentional.

Note also the use of `printf` statements; these are normally never seen when
playing on an actual PlayStation, but you can see them in the debug output of an
emulator.

For players, if you want Shiori to join a specific club, the complete list of
dates of birth to select for Shiori is as follows:

Art
: Jan: 1, 12, 23
: Feb: 8, 19
: Mar: 4, 15, 26
: Apr: 11, 22
: May: 7, 18, 29
: Jun: 3, 14, 25
: Jul: 10, 21
: Aug: 6, 17, 28
: Sep: 2, 13, 24
: Oct: 9, 20, 31
: Nov: 5, 16, 27
: Dec: 1, 12, 23

Baseball
: Jan: 9, 20, 31
: Feb: 5, 16, 27
: Mar: 1, 12, 23
: Apr: 8, 19, 30
: May: 4, 15, 26
: Jun: 11, 22
: Jul: 7, 18, 29
: Aug: 3, 14, 25
: Sep: 10, 21
: Oct: 6, 17, 28
: Nov: 2, 13, 24
: Dec: 9, 20, 31

Basketball
: Jan: 3, 14, 25
: Feb: 10, 21
: Mar: 6, 17, 28
: Apr: 2, 13, 24
: May: 9, 20, 31
: Jun: 5, 16, 27
: Jul: 1, 12, 23
: Aug: 8, 19, 30
: Sep: 4, 15, 26
: Oct: 11, 22
: Nov: 7, 18, 29
: Dec: 3, 14, 25

Brass band
: Jan: 5, 16, 27
: Feb: 1, 12, 23
: Mar: 8, 19, 30
: Apr: 4, 15, 26
: May: 11, 22
: Jun: 7, 18, 29
: Jul: 3, 14, 25
: Aug: 10, 21
: Sep: 6, 17, 28
: Oct: 2, 13, 24
: Nov: 9, 20
: Dec: 5, 16, 27

Computer
: Jan: 8, 19, 30
: Feb: 4, 15, 26
: Mar: 11, 22
: Apr: 7, 18, 29
: May: 3, 14, 25
: Jun: 10, 21
: Jul: 6, 17, 28
: Aug: 2, 13, 24
: Sep: 9, 20
: Oct: 5, 16, 27
: Nov: 1, 12, 23
: Dec: 8, 19, 30

Drama
: Jan: 11, 22
: Feb: 7, 18
: Mar: 3, 14, 25
: Apr: 10, 21
: May: 6, 17, 28
: Jun: 2, 13, 24
: Jul: 9, 20, 31
: Aug: 5, 16, 27
: Sep: 1, 12, 23
: Oct: 8, 19, 30
: Nov: 4, 15, 26
: Dec: 11, 22

Literature
: Jan: 7, 18, 29
: Feb: 3, 14, 25
: Mar: 10, 21
: Apr: 6, 17, 28
: May: 2, 13, 24
: Jun: 9, 20
: Jul: 5, 16, 27
: Aug: 1, 12, 23
: Sep: 8, 19, 30
: Oct: 4, 15, 26
: Nov: 11, 22
: Dec: 7, 18, 29

Science
: Jan: 4, 15, 26
: Feb: 11, 22
: Mar: 7, 18, 29
: Apr: 3, 14, 25
: May: 10, 21
: Jun: 6, 17, 28
: Jul: 2, 13, 24
: Aug: 9, 20, 31
: Sep: 5, 16, 27
: Oct: 1, 12, 23
: Nov: 8, 19, 30
: Dec: 4, 15, 26

Soccer
: Jan: 2, 13, 24
: Feb: 9, 20
: Mar: 5, 16, 27
: Apr: 1, 12, 23
: May: 8, 19, 30
: Jun: 4, 15, 26
: Jul: 11, 22
: Aug: 7, 18, 29
: Sep: 3, 14, 25
: Oct: 10, 21
: Nov: 6, 17, 28
: Dec: 2, 13, 24

Swimming
: Jan: 10, 21
: Feb: 6, 17, 28
: Mar: 2, 13, 24
: Apr: 9, 20
: May: 5, 16, 27
: Jun: 1, 12, 23
: Jul: 8, 19, 30
: Aug: 4, 15, 26
: Sep: 11, 22
: Oct: 7, 18, 29
: Nov: 3, 14, 25
: Dec: 10, 21

Tennis
: Jan: 6, 17, 28
: Feb: 2, 13, 24
: Mar: 9, 20, 31
: Apr: 5, 16, 27
: May: 1, 12, 23
: Jun: 8, 19, 30
: Jul: 4, 15, 26
: Aug: 11, 22
: Sep: 7, 18, 29
: Oct: 3, 14, 25
: Nov: 10, 21
: Dec: 6, 17, 28

## Same birthday check

The game actually checks if the player and Shiori have the same birthday. This
was widely known even at the time, since there's a unique birthday event. Of
course, since the player and Shiori are _osananajimi_, if they had the same
birthday then they would have shared birthday events in the past.

Still, here's the relevant code from the main game executable:

~~~ c
undefined4 fujisaki_2nin_birth_check(void){
  undefined4 result;
  int iVar1;
  uint uVar2;
  undefined auStack52 [32];
  undefined auStack20 [20];
  
  get_grp(auStack20,auStack52);
  if (((birthday_player & 0xf) == (birthday_shiori & 0xf)) &&
     ((birthday_player << 0x17) >> 0x1b == (birthday_shiori << 0x17) >> 0x1b)) {
    if ((current_month == '\x03') || ((current_month == '\x04' && (current_day < 4)))) {
      iVar1 = reserved_date(current_year,current_month,current_day);
      if (iVar1 < 1) {
        iVar1 = birth_day_check(0xf); // 0xf = player
        if (iVar1 == 1) {
          uVar2 = get_g_zyotai_s(0);  // 0 = shiori
          result = 0;
          if ((uVar2 & 0x80) != 0) {
            result = 1;
          }
        }
        else {
          result = 0;
        }
      }
      else {
        result = 0;
      }
    }
    else {
      result = 0;
    }
  }
  else {
    result = 0;
  }
  return result;
}
~~~

Several of these function names are pulled from `exedir/o.bin`, a leftover
object file. This means the game's developers called this function
`fujisaki_2nin_birth_check`, where "2nin" probably means 「二人」, meaning two
people or a couple, more commonly read "futari". The function names
`get_grp`, `reserved_date`, `birth_day_check` and get_g_zyotai_s` are also from
the object file.

The check is only passed if:

1. Shiori and the player have the same birth month
2. Shiori and the player have the same birth day
3. The current day is between Mar 1 and Apr 3 inclusive
4. You don't have a date scheduled today
5. It is currently the player's birthday
6. Bit 7 of `get_g_zyotai_s` for Shiori is set (todo: determine significance of
   this function)

## Other

There are other references to Shiori's birthday which I've yet to decode.
