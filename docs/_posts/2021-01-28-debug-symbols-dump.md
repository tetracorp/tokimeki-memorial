---
layout: post
title: "Debug symbols dump"
categories: data
---

A massive boon to reverse-engineering _Tokimeki Memorial: Forever With You_ is
the existence of an object file revealing several of the original function and
variable names. The file is located at `cdrom/exedir/o.bin` and appears in the
SLPS-00064 limited edtion release and SLPS-00065 original revision V110.

Linux "file" command identifies it as "MIPSEL ECOFF executable (impure) -
version 3.18". Using the tool `objdump` from the 
[psxsdk](https://github.com/ChrisRx/psxsdk) project reveals that it contains
debug symbols. They do not match the executable exactly, and appear to be from
an earlier build of the main game executable. This file was probably included by
accident.

1. Table of Contents
{:toc}

### Dump

    MIPSEL ECOFF executable - start=0x80132000 size=603981008 sections=4

    Sections:
     0 .text   len=928  offset=240  0x80132000 0x80132000
     1 .rdata  len=144  offset=1168 0x801323A0 0x801323A0
     2 .data   len=160  offset=1312 0x80132430 0x80132430
     3 .comment   len=603979776 offset=537264128 0x00000000 0x00000000

    Symbols:
    [   0] e 000000008004C000 st 1 sc 5 index=FFFFF     warm_reset_init
    [   1] e 000000008004C0B8 st 1 sc 5 index=FFFFF     draw_and_disp_env_init
    [   2] e 000000008004C2C0 st 1 sc 5 index=FFFFF     print_dr_env
    [   3] e 000000008004C2D4 st 1 sc 5 index=FFFFF     print_di_env
    [   4] e 000000008004C2E8 st 1 sc 5 index=FFFFF     vram_clear
    [   5] e 000000008004C424 st 1 sc 5 index=FFFFF     system_init
    [   6] e 000000008004C6C0 st 1 sc 5 index=FFFFF     prim_init
    [   7] e 000000008004C6F0 st 1 sc 5 index=FFFFF     sprite_init
    [   8] e 000000008004C788 st 1 sc 5 index=FFFFF     bg_init
    [   9] e 000000008004C97C st 1 sc 5 index=FFFFF     game_system_init
    [  10] e 000000008004C9B0 st 1 sc 5 index=FFFFF     _game_work_init_set
    [  11] e 000000008004C9E8 st 1 sc 5 index=FFFFF     debug_data_init
    [  12] e 000000008004CB28 st 1 sc 5 index=FFFFF     game_data_init
    [  13] e 000000008004CC78 st 1 sc 5 index=FFFFF     play_data_init
    [  14] e 000000008004CE98 st 1 sc 5 index=FFFFF     girl_data_init
    [  15] e 000000008004D228 st 1 sc 5 index=FFFFF     etc_data_init
    [  16] e 000000008004D494 st 1 sc 5 index=FFFFF     addr_init_main_rom
    [  17] e 000000008004D49C st 1 sc 5 index=FFFFF     addr_init_main_dat
    [  18] e 000000008004D4B0 st 1 sc 5 index=FFFFF     main
    [  19] e 000000008004D514 st 1 sc 5 index=FFFFF     _main
    [  20] e 000000008004D790 st 1 sc 5 index=FFFFF     girl_data_print
    [  21] e 000000008004DA48 st 1 sc 5 index=FFFFF     swap_env
    [  22] e 000000008004DAE0 st 1 sc 5 index=FFFFF     game_info_disp
    [  23] e 000000008004DBC4 st 1 sc 5 index=FFFFF     vblank_callback
    [  24] e 000000008004DBF0 st 1 sc 5 index=FFFFF     myrand
    [  25] e 000000008004DC08 st 1 sc 5 index=FFFFF     cold_reset_init
    [  26] e 000000008004DC84 st 1 sc 5 index=FFFFF     cashe_f
    [  27] e 000000008004DCB4 st 1 sc 5 index=FFFFF     vblank_ev_set
    [  28] e 000000008004DD30 st 1 sc 5 index=FFFFF     game_main
    [  29] e 000000008004DF6C st 1 sc 5 index=FFFFF     step_up
    [  30] e 000000008004DFDC st 1 sc 5 index=FFFFF     sub_step_up
    [  31] e 000000008004E020 st 1 sc 5 index=FFFFF     sub_sub_step_up
    [  32] e 000000008004E04C st 1 sc 5 index=FFFFF     goto_step
    [  33] e 000000008004E0B8 st 1 sc 5 index=FFFFF     goto_sub_step
    [  34] e 000000008004E0F0 st 1 sc 5 index=FFFFF     goto_sub_sub_step
    [  35] e 000000008004E110 st 1 sc 5 index=FFFFF     check_load_func
    [  36] e 000000008004E194 st 1 sc 5 index=FFFFF     step_display_func
    [  37] e 000000008004E280 st 1 sc 5 index=FFFFF     PadDataRead
    [  38] e 000000008004E3AC st 1 sc 5 index=FFFFF     controller_check
    [  39] e 000000008004E604 st 1 sc 5 index=FFFFF     _pad_data_read_mouse
    [  40] e 000000008004E93C st 1 sc 5 index=FFFFF     MyPadRead
    [  41] e 000000008004E9EC st 1 sc 5 index=FFFFF     _pad_data_read_pad
    [  42] e 000000008004ECB8 st 1 sc 5 index=FFFFF     konami_command_check
    [  43] e 000000008004ED74 st 1 sc 5 index=FFFFF     pause_func
    [  44] e 000000008004ED80 st 1 sc 5 index=FFFFF     vblank_function
    [  45] e 000000008004F130 st 1 sc 5 index=FFFFF     draw2d3d
    [  46] e 000000008004F144 st 1 sc 5 index=FFFFF     back_clear_switch
    [  47] e 000000008004F168 st 1 sc 5 index=FFFFF     load_palette
    [  48] e 000000008004F1D4 st 1 sc 5 index=FFFFF     load_csr_ab
    [  49] e 000000008004F254 st 1 sc 5 index=FFFFF     load_csr_tp
    [  50] e 000000008004F2D8 st 1 sc 5 index=FFFFF     csr_load_vram
    [  51] e 000000008004F3C8 st 1 sc 5 index=FFFFF     palette_load_vram
    [  52] e 000000008004FBB0 st 1 sc 5 index=FFFFF     LoadSquare
    [  53] e 000000008004FBF4 st 1 sc 5 index=FFFFF     MoveSquare
    [  54] e 000000008004FC44 st 1 sc 5 index=FFFFF     StoreSquare
    [  55] e 000000008004FC88 st 1 sc 5 index=FFFFF     show_packet_use_box
    [  56] e 000000008004FF84 st 1 sc 5 index=FFFFF     show_vcnt_info
    [  57] e 0000000080050248 st 1 sc 5 index=FFFFF     move_palette
    [  58] e 00000000800502A0 st 1 sc 5 index=FFFFF     put_sd_error
    [  59] e 00000000800502DC st 1 sc 5 index=FFFFF     print_sd_error
    [  60] e 000000008005034C st 1 sc 5 index=FFFFF     SD_Call
    [  61] e 00000000800503E8 st 1 sc 5 index=FFFFF     seq_switch
    [  62] e 0000000080050480 st 1 sc 5 index=FFFFF     get_seq_state
    [  63] e 0000000080050490 st 1 sc 5 index=FFFFF     get_now_seq
    [  64] e 00000000800504A0 st 1 sc 5 index=FFFFF     pcm_system_reset
    [  65] e 00000000800504FC st 1 sc 5 index=FFFFF     main_pcm_read
    [  66] e 00000000800508E8 st 1 sc 5 index=FFFFF     main_pcm_trans2
    [  67] e 0000000080050A14 st 1 sc 5 index=FFFFF     trans_spu_local
    [  68] e 0000000080050B34 st 1 sc 5 index=FFFFF     main_pcm_trans
    [  69] e 0000000080050CAC st 1 sc 5 index=FFFFF     vab_State
    [  70] e 0000000080050D24 st 1 sc 5 index=FFFFF     current_seq_call
    [  71] e 0000000080050E10 st 1 sc 5 index=FFFFF     now_trans_pointer
    [  72] e 0000000080050E20 st 1 sc 5 index=FFFFF     change_trans_pointer
    [  73] e 0000000080050E2C st 1 sc 5 index=FFFFF     t_cdreadcallback
    [  74] e 0000000080050E3C st 1 sc 5 index=FFFFF     t_cdsynccallback
    [  75] e 0000000080050EA0 st 1 sc 5 index=FFFFF     CDQ_init
    [  76] e 0000000080050EE0 st 1 sc 5 index=FFFFF     cd_command_set
    [  77] e 0000000080050FDC st 1 sc 5 index=FFFFF     Control_CD
    [  78] e 00000000800511F4 st 1 sc 5 index=FFFFF     Control_CD_main
    [  79] e 00000000800519E4 st 1 sc 5 index=FFFFF     get_CD_l_com
    [  80] e 0000000080051A1C st 1 sc 5 index=FFFFF     get_CD_State2
    [  81] e 0000000080051A2C st 1 sc 5 index=FFFFF     get_reads
    [  82] e 0000000080051A3C st 1 sc 5 index=FFFFF     get_CD_State
    [  83] e 0000000080051A4C st 1 sc 5 index=FFFFF     check_head_position
    [  84] e 0000000080051C04 st 1 sc 5 index=FFFFF     get_head_position
    [  85] e 0000000080051C14 st 1 sc 5 index=FFFFF     get_XAsector
    [  86] e 0000000080051C20 st 1 sc 5 index=FFFFF     set_XAsector
    [  87] e 0000000080051C50 st 1 sc 5 index=FFFFF     p_cd2_debugprint
    [  88] e 0000000080051CC8 st 1 sc 5 index=FFFFF     cdcommake_a
    [  89] e 0000000080051CD4 st 1 sc 5 index=FFFFF     cdreaddata
    [  90] e 0000000080051D14 st 1 sc 5 index=FFFFF     cdreaddata2
    [  91] e 0000000080051D58 st 1 sc 5 index=FFFFF     check_sum_check
    [  92] e 0000000080051DD4 st 1 sc 5 index=FFFFF     Control_CD_sub
    [  93] e 0000000080051E1C st 1 sc 5 index=FFFFF     Control_CD_print
    [  94] e 0000000080051F40 st 1 sc 5 index=FFFFF     p_error
    [  95] e 0000000080051FF4 st 1 sc 5 index=FFFFF     keta_n
    [  96] e 00000000800520E8 st 1 sc 5 index=FFFFF     bcd2a
    [  97] e 00000000800521B8 st 1 sc 5 index=FFFFF     make_fan
    [  98] e 000000008005252C st 1 sc 5 index=FFFFF     disp_fan
    [  99] e 0000000080052FC0 st 1 sc 5 index=FFFFF     don_init
    [ 100] e 0000000080052FD0 st 1 sc 5 index=FFFFF     don_move
    [ 101] e 0000000080053130 st 1 sc 5 index=FFFFF     class_set
    [ 102] e 0000000080053D58 st 1 sc 5 index=FFFFF     tpage_buf_clear_all
    [ 103] e 0000000080053DEC st 1 sc 5 index=FFFFF     tpage_buf_clear
    [ 104] e 0000000080053E44 st 1 sc 5 index=FFFFF     _sys_default_tpage_set
    [ 105] e 0000000080053F70 st 1 sc 5 index=FFFFF     load_tpage_buf_lock
    [ 106] e 0000000080054018 st 1 sc 5 index=FFFFF     search_load_tpage_buf_lock
    [ 107] e 0000000080054100 st 1 sc 5 index=FFFFF     search_tpage_multi
    [ 108] e 0000000080054284 st 1 sc 5 index=FFFFF     search_tpage
    [ 109] e 00000000800544EC st 1 sc 5 index=FFFFF     search_tpage8
    [ 110] e 0000000080054754 st 1 sc 5 index=FFFFF     class_switch
    [ 111] e 0000000080054778 st 1 sc 5 index=FFFFF     class_clear
    [ 112] e 00000000800547EC st 1 sc 5 index=FFFFF     class_clear_f
    [ 113] e 000000008005482C st 1 sc 5 index=FFFFF     class_clear_all
    [ 114] e 00000000800548D8 st 1 sc 5 index=FFFFF     class_clear_n
    [ 115] e 0000000080054978 st 1 sc 5 index=FFFFF     get_brightness
    [ 116] e 0000000080054988 st 1 sc 5 index=FFFFF     clear_brightness
    [ 117] e 00000000800549A0 st 1 sc 5 index=FFFFF     set_brightness
    [ 118] e 0000000080054A10 st 1 sc 5 index=FFFFF     set_brightness_d
    [ 119] e 0000000080054A20 st 1 sc 5 index=FFFFF     SetWorkBase
    [ 120] e 0000000080054A50 st 1 sc 5 index=FFFFF     GetWorkBase
    [ 121] e 0000000080054AA0 st 1 sc 5 index=FFFFF     sprite_set_gpu_poly_ft4
    [ 122] e 0000000080054D08 st 1 sc 5 index=FFFFF     goto_tpage
    [ 123] e 0000000080054DB0 st 1 sc 5 index=FFFFF     safe_env
    [ 124] e 0000000080054E1C st 1 sc 5 index=FFFFF     dtd_on_tpage
    [ 125] e 0000000080054EBC st 1 sc 5 index=FFFFF     dtd_on
    [ 126] e 0000000080054F3C st 1 sc 5 index=FFFFF     _sprite_set_light_effect1
    [ 127] e 00000000800553A0 st 1 sc 5 index=FFFFF     _sprite_set_box_shade
    [ 128] e 000000008005594C st 1 sc 5 index=FFFFF     sprite_set_gpu_sprt2
    [ 129] e 0000000080055CA0 st 1 sc 5 index=FFFFF     line_set
    [ 130] e 0000000080055DFC st 1 sc 5 index=FFFFF     box_set
    [ 131] e 0000000080055E50 st 1 sc 5 index=FFFFF     bg_set
    [ 132] e 00000000800560C4 st 1 sc 5 index=FFFFF     mozaiku_show
    [ 133] e 0000000080056460 st 1 sc 5 index=FFFFF     mozaiku_show2
    [ 134] e 0000000080056860 st 1 sc 5 index=FFFFF     spot_light
    [ 135] e 0000000080056C64 st 1 sc 5 index=FFFFF     night_parade_effect
    [ 136] e 0000000080056EE4 st 1 sc 5 index=FFFFF     blur_area
    [ 137] e 0000000080057130 st 1 sc 5 index=FFFFF     white_light
    [ 138] e 00000000800571E0 st 1 sc 5 index=FFFFF     pn_switch
    [ 139] e 000000008005722C st 1 sc 5 index=FFFFF     pn_set
    [ 140] e 0000000080057254 st 1 sc 5 index=FFFFF     get_pn_flag
    [ 141] e 0000000080057264 st 1 sc 5 index=FFFFF     number_font_load
    [ 142] e 000000008005729C st 1 sc 5 index=FFFFF     show_number
    [ 143] e 00000000800572BC st 1 sc 5 index=FFFFF     show_number_col
    [ 144] e 00000000800575F0 st 1 sc 5 index=FFFFF     show_number_hex
    [ 145] e 0000000080057780 st 1 sc 5 index=FFFFF     show_string_e
    [ 146] e 00000000800577A0 st 1 sc 5 index=FFFFF     show_string_e_col
    [ 147] e 00000000800579B0 st 1 sc 5 index=FFFFF     col2mono
    [ 148] e 0000000080057C30 st 1 sc 5 index=FFFFF     printcolor
    [ 149] e 0000000080057C3C st 1 sc 5 index=FFFFF     printrgb
    [ 150] e 0000000080057C48 st 1 sc 5 index=FFFFF     make_color_bar
    [ 151] e 0000000080058078 st 1 sc 5 index=FFFFF     make_color_bar16
    [ 152] e 000000008005867C st 1 sc 5 index=FFFFF     col2sepia
    [ 153] e 00000000800588C0 st 1 sc 5 index=FFFFF     srn_tpage_show
    [ 154] e 0000000080059558 st 1 sc 5 index=FFFFF     srn_vram_set
    [ 155] e 00000000800597F0 st 1 sc 5 index=FFFFF     move_255_line
    [ 156] e 0000000080059898 st 1 sc 5 index=FFFFF     mod_trans_vram
    [ 157] e 0000000080059B88 st 1 sc 5 index=FFFFF     get_fnt
    [ 158] e 0000000080059F94 st 1 sc 5 index=FFFFF     printpix
    [ 159] e 000000008005A074 st 1 sc 5 index=FFFFF     mod_set_gpu
    [ 160] e 000000008005A398 st 1 sc 5 index=FFFFF     mod_set
    [ 161] e 000000008005A6A4 st 1 sc 5 index=FFFFF     srn_set
    [ 162] e 000000008005A8F8 st 1 sc 5 index=FFFFF     srn_init
    [ 163] e 000000008005A9F4 st 1 sc 5 index=FFFFF     mod_init
    [ 164] e 000000008005AAA0 st 1 sc 5 index=FFFFF     k_sys_clear
    [ 165] e 000000008005AC34 st 1 sc 5 index=FFFFF     change_k_w
    [ 166] e 000000008005AC64 st 1 sc 5 index=FFFFF     k_printf
    [ 167] e 000000008005ACE0 st 1 sc 5 index=FFFFF     set_kanji_string
    [ 168] e 000000008005ADDC st 1 sc 5 index=FFFFF     k_disp_start
    [ 169] e 000000008005AE94 st 1 sc 5 index=FFFFF     k_disp_switch
    [ 170] e 000000008005AEC8 st 1 sc 5 index=FFFFF     get_k_work
    [ 171] e 000000008005AEF4 st 1 sc 5 index=FFFFF     get_ksys
    [ 172] e 000000008005AF00 st 1 sc 5 index=FFFFF     set_k_work
    [ 173] e 000000008005AF4C st 1 sc 5 index=FFFFF     k_reset
    [ 174] e 000000008005AFF0 st 1 sc 5 index=FFFFF     k_sub_reset_point_set
    [ 175] e 000000008005B004 st 1 sc 5 index=FFFFF     k_sub_reset
    [ 176] e 000000008005B02C st 1 sc 5 index=FFFFF     k_sub_disp_start
    [ 177] e 000000008005B054 st 1 sc 5 index=FFFFF     k_disp_goto_line_end
    [ 178] e 000000008005B144 st 1 sc 5 index=FFFFF     k_speed_set
    [ 179] e 000000008005B16C st 1 sc 5 index=FFFFF     get_k_speed
    [ 180] e 000000008005B17C st 1 sc 5 index=FFFFF     k_disp_inc
    [ 181] e 000000008005B20C st 1 sc 5 index=FFFFF     check_end_k
    [ 182] e 000000008005B238 st 1 sc 5 index=FFFFF     check_set_k
    [ 183] e 000000008005B248 st 1 sc 5 index=FFFFF     get_now_k
    [ 184] e 000000008005B368 st 1 sc 5 index=FFFFF     disp_string
    [ 185] e 000000008005B7C0 st 1 sc 5 index=FFFFF     load_string
    [ 186] e 000000008005B8BC st 1 sc 5 index=FFFFF     vload_font
    [ 187] e 000000008005BA48 st 1 sc 5 index=FFFFF     melt_font
    [ 188] e 000000008005BC00 st 1 sc 5 index=FFFFF     menu_set
    [ 189] e 000000008005BD14 st 1 sc 5 index=FFFFF     menu_check
    [ 190] e 000000008005BE18 st 1 sc 5 index=FFFFF     menu_check_1
    [ 191] e 000000008005BEFC st 1 sc 5 index=FFFFF     menu_check_2
    [ 192] e 000000008005BFA0 st 1 sc 5 index=FFFFF     menu_bar_select
    [ 193] e 000000008005C690 st 1 sc 5 index=FFFFF     get_near_menu
    [ 194] e 000000008005CD88 st 1 sc 5 index=FFFFF     menu_bar_color
    [ 195] e 000000008005CDDC st 1 sc 5 index=FFFFF     menu_bar_show
    [ 196] e 000000008005CEAC st 1 sc 5 index=FFFFF     x_taku_menu_set
    [ 197] e 000000008005D000 st 1 sc 5 index=FFFFF     x_taku_string_set
    [ 198] e 000000008005D084 st 1 sc 5 index=FFFFF     gnsx
    [ 199] e 000000008005D114 st 1 sc 5 index=FFFFF     sndisp
    [ 200] e 000000008005D298 st 1 sc 5 index=FFFFF     sndi
    [ 201] e 000000008005D6B4 st 1 sc 5 index=FFFFF     set_c_girl
    [ 202] e 000000008005D6C0 st 1 sc 5 index=FFFFF     get_g_name
    [ 203] e 000000008005D790 st 1 sc 5 index=FFFFF     get_p_name
    [ 204] e 000000008005DCF0 st 1 sc 5 index=FFFFF     get_g_zyotai_s
    [ 205] e 000000008005DDD0 st 1 sc 5 index=FFFFF     get_g_zyotai_h
    [ 206] e 000000008005DE64 st 1 sc 5 index=FFFFF     menu_girl_taku_set
    [ 207] e 000000008005E044 st 1 sc 5 index=FFFFF     xa_wait
    [ 208] e 000000008005E288 st 1 sc 5 index=FFFFF     xa_wait2
    [ 209] e 000000008005E2E4 st 1 sc 5 index=FFFFF     xa_set_m
    [ 210] e 000000008005E3E0 st 1 sc 5 index=FFFFF     xa_wait_m
    [ 211] e 000000008005E80C st 1 sc 5 index=FFFFF     get_h_tokimeki
    [ 212] e 000000008005EE4C st 1 sc 5 index=FFFFF     get_h_yuukou
    [ 213] e 000000008005EEC8 st 1 sc 5 index=FFFFF     get_h_tokimeki_table
    [ 214] e 000000008005EF18 st 1 sc 5 index=FFFFF     get_h_yuukou_table
    [ 215] e 000000008005EF68 st 1 sc 5 index=FFFFF     birth_day_check
    [ 216] e 000000008005EF98 st 1 sc 5 index=FFFFF     birth_day_check_days
    [ 217] e 000000008005F024 st 1 sc 5 index=FFFFF     ending_para_check_fuji
    [ 218] e 000000008005F0EC st 1 sc 5 index=FFFFF     ending_para_check_else
    [ 219] e 000000008005F4FC st 1 sc 5 index=FFFFF     get_grp
    [ 220] e 000000008005F610 st 1 sc 5 index=FFFFF     club_undo_check
    [ 221] e 000000008005F648 st 1 sc 5 index=FFFFF     get_club_girl
    [ 222] e 000000008005F730 st 1 sc 5 index=FFFFF     dec_env_set
    [ 223] e 000000008005F78C st 1 sc 5 index=FFFFF     decdct
    [ 224] e 000000008005F8E0 st 1 sc 5 index=FFFFF     card_ev_set
    [ 225] e 000000008005F928 st 1 sc 5 index=FFFFF     Sw_Start
    [ 226] e 000000008005FA0C st 1 sc 5 index=FFFFF     Hw_Start
    [ 227] e 000000008005FAF0 st 1 sc 5 index=FFFFF     Sw_Test
    [ 228] e 000000008005FBB8 st 1 sc 5 index=FFFFF     Sw_Clear
    [ 229] e 000000008005FC10 st 1 sc 5 index=FFFFF     Hw_Test
    [ 230] e 000000008005FCDC st 1 sc 5 index=FFFFF     Hw_Clear
    [ 231] e 000000008005FD34 st 1 sc 5 index=FFFFF     Hw_Stop
    [ 232] e 000000008005FD9C st 1 sc 5 index=FFFFF     start_card
    [ 233] e 000000008005FE14 st 1 sc 5 index=FFFFF     stop_card
    [ 234] e 000000008005FE90 st 1 sc 5 index=FFFFF     goto_cs
    [ 235] e 000000008005FEAC st 1 sc 5 index=FFFFF     Control_CARD_main
    [ 236] e 0000000080061338 st 1 sc 5 index=FFFFF     make_file
    [ 237] e 00000000800613C4 st 1 sc 5 index=FFFFF     delete_file
    [ 238] e 000000008006145C st 1 sc 5 index=FFFFF     loadfile
    [ 239] e 00000000800615A0 st 1 sc 5 index=FFFFF     savefile
    [ 240] e 000000008006184C st 1 sc 5 index=FFFFF     find_card
    [ 241] e 0000000080061920 st 1 sc 5 index=FFFFF     system_check
    [ 242] e 000000008006195C st 1 sc 5 index=FFFFF     card_check
    [ 243] e 00000000800619C4 st 1 sc 5 index=FFFFF     card_w_clear
    [ 244] e 00000000800619EC st 1 sc 5 index=FFFFF     cardfile_init
    [ 245] e 0000000080061C14 st 1 sc 5 index=FFFFF     sys0w2card
    [ 246] e 0000000080061F2C st 1 sc 5 index=FFFFF     card2sys0w
    [ 247] e 0000000080062138 st 1 sc 5 index=FFFFF     sysw2card
    [ 248] e 000000008006259C st 1 sc 5 index=FFFFF     card_check_sum_check
    [ 249] e 00000000800626A4 st 1 sc 5 index=FFFFF     card2sysw
    [ 250] e 0000000080062CA8 st 1 sc 5 index=FFFFF     get_file_name
    [ 251] e 0000000080062EB0 st 1 sc 5 index=FFFFF     vram_test
    [ 252] e 0000000080063260 st 1 sc 5 index=FFFFF     exit_function
    [ 253] e 0000000080063350 st 1 sc 5 index=FFFFF     set_movie_offset
    [ 254] e 0000000080063374 st 1 sc 5 index=FFFFF     strInit
    [ 255] e 00000000800633FC st 1 sc 5 index=FFFFF     strSetDefDecEnv
    [ 256] e 00000000800634EC st 1 sc 5 index=FFFFF     strCallback
    [ 257] e 000000008006376C st 1 sc 5 index=FFFFF     strNextVlc
    [ 258] e 0000000080063818 st 1 sc 5 index=FFFFF     strNext
    [ 259] e 0000000080063A08 st 1 sc 5 index=FFFFF     strSync
    [ 260] e 0000000080063A9C st 1 sc 5 index=FFFFF     strKickCD
    [ 261] e 0000000080063B08 st 1 sc 5 index=FFFFF     movie_main
    [ 262] e 0000000080063FD0 st 1 sc 5 index=FFFFF     song_base_set
    [ 263] e 0000000080064074 st 1 sc 5 index=FFFFF     song_set
    [ 264] e 00000000800642A0 st 1 sc 5 index=FFFFF     set_dec_bri
    [ 265] e 00000000800642AC st 1 sc 5 index=FFFFF     get_last_gamen_mode
    [ 266] e 00000000800642BC st 1 sc 5 index=FFFFF     dec_bg_reset
    [ 267] e 0000000080064308 st 1 sc 5 index=FFFFF     dec_bg_show_switch
    [ 268] e 0000000080064328 st 1 sc 5 index=FFFFF     dec_bg_show_set
    [ 269] e 000000008006433C st 1 sc 5 index=FFFFF     dec_bg_cd_read
    [ 270] e 000000008006442C st 1 sc 5 index=FFFFF     dec_bg_init
    [ 271] e 0000000080064528 st 1 sc 5 index=FFFFF     vram_full_move
    [ 272] e 00000000800645F8 st 1 sc 5 index=FFFFF     goto_step_bg_out
    [ 273] e 00000000800647DC st 1 sc 5 index=FFFFF     dec_bg_show
    [ 274] e 0000000080064CA8 st 1 sc 5 index=FFFFF     set_tbg_bri
    [ 275] e 0000000080064CB4 st 1 sc 5 index=FFFFF     bg_show_girl_out
    [ 276] e 0000000080065324 st 1 sc 5 index=FFFFF     bg_change
    [ 277] e 0000000080065CB0 st 1 sc 5 index=FFFFF     initView
    [ 278] e 0000000080065D30 st 1 sc 5 index=FFFFF     initLight
    [ 279] e 0000000080065E40 st 1 sc 5 index=FFFFF     initCoordinate
    [ 280] e 0000000080065E9C st 1 sc 5 index=FFFFF     initModelingData_init
    [ 281] e 0000000080065F2C st 1 sc 5 index=FFFFF     initModelingData
    [ 282] e 0000000080065FC8 st 1 sc 5 index=FFFFF     all_object_disp_off
    [ 283] e 0000000080066014 st 1 sc 5 index=FFFFF     swap_env3
    [ 284] e 0000000080066058 st 1 sc 5 index=FFFFF     set_256_mode
    [ 285] e 000000008006612C st 1 sc 5 index=FFFFF     set_512_mode
    [ 286] e 0000000080066200 st 1 sc 5 index=FFFFF     class_3d_set
    [ 287] e 00000000800664B8 st 1 sc 5 index=FFFFF     class_clear_3d
    [ 288] e 0000000080066530 st 1 sc 5 index=FFFFF     MouseState
    [ 289] e 00000000800665C0 st 1 sc 5 index=FFFFF     InitMouse
    [ 290] e 00000000800665D0 st 1 sc 5 index=FFFFF     RangeMouse
    [ 291] e 0000000080066628 st 1 sc 5 index=FFFFF     SenseMouse
    [ 292] e 000000008006663C st 1 sc 5 index=FFFFF     SetMouse
    [ 293] e 0000000080066680 st 1 sc 5 index=FFFFF     MouseRead
    [ 294] e 0000000080066840 st 1 sc 5 index=FFFFF     _load_vram
    [ 295] e 00000000800668C0 st 1 sc 5 index=FFFFF     default_data_vram_load
    [ 296] e 00000000800668E8 st 1 sc 5 index=FFFFF     main_data_vram_load
    [ 297] e 0000000080066B00 st 1 sc 5 index=FFFFF     default_data_read_cd
    [ 298] e 0000000080066C14 st 1 sc 5 index=FFFFF     tokimeki_default_chara_init
    [ 299] e 0000000080066D98 st 1 sc 5 index=FFFFF     load_vram
    [ 300] e 0000000080066E30 st 1 sc 5 index=FFFFF     game_mode
    [ 301] e 0000000080066F20 st 1 sc 5 index=FFFFF     game_mode_init_all
    [ 302] e 0000000080066FFC st 1 sc 5 index=FFFFF     game_mode_init
    [ 303] e 00000000800670D0 st 1 sc 5 index=FFFFF     game_mode_init0
    [ 304] e 0000000080067130 st 1 sc 5 index=FFFFF     game_mode_init0_wait
    [ 305] e 0000000080067158 st 1 sc 5 index=FFFFF     game_mode_cal_font_load
    [ 306] e 0000000080067230 st 1 sc 5 index=FFFFF     game_mode_init1
    [ 307] e 000000008006766C st 1 sc 5 index=FFFFF     dec_evening_read
    [ 308] e 00000000800676E8 st 1 sc 5 index=FFFFF     game_mode_cdread
    [ 309] e 0000000080067738 st 1 sc 5 index=FFFFF     sunday_evening_icon_phase
    [ 310] e 00000000800677C8 st 1 sc 5 index=FFFFF     byouki_show
    [ 311] e 00000000800678B8 st 1 sc 5 index=FFFFF     game_mode_main
    [ 312] e 000000008006790C st 1 sc 5 index=FFFFF     hitsuji_check
    [ 313] e 00000000800679A0 st 1 sc 5 index=FFFFF     olh_check
    [ 314] e 0000000080067A3C st 1 sc 5 index=FFFFF     radio_check
    [ 315] e 0000000080067AE4 st 1 sc 5 index=FFFFF     radio_check_m
    [ 316] e 0000000080067B8C st 1 sc 5 index=FFFFF     mascot_speech_check_m
    [ 317] e 0000000080067C84 st 1 sc 5 index=FFFFF     mascot_speech_check
    [ 318] e 0000000080067D48 st 1 sc 5 index=FFFFF     game_mode_main0
    [ 319] e 0000000080067DA8 st 1 sc 5 index=FFFFF     icon_check
    [ 320] e 0000000080067FB4 st 1 sc 5 index=FFFFF     callendar_disp
    [ 321] e 000000008006801C st 1 sc 5 index=FFFFF     callendar_disp_init
    [ 322] e 000000008006808C st 1 sc 5 index=FFFFF     callendar_disp_main
    [ 323] e 00000000800680FC st 1 sc 5 index=FFFFF     callendar_disp_exit
    [ 324] e 0000000080068124 st 1 sc 5 index=FFFFF     data_save_load
    [ 325] e 0000000080068230 st 1 sc 5 index=FFFFF     data_save_load_init
    [ 326] e 0000000080068360 st 1 sc 5 index=FFFFF     data_save_load_mem_card_check
    [ 327] e 0000000080068430 st 1 sc 5 index=FFFFF     data_save_load_main
    [ 328] e 00000000800684E8 st 1 sc 5 index=FFFFF     data_save_init
    [ 329] e 0000000080068680 st 1 sc 5 index=FFFFF     data_save
    [ 330] e 000000008006879C st 1 sc 5 index=FFFFF     data_save_exit
    [ 331] e 00000000800687E4 st 1 sc 5 index=FFFFF     data_load_init
    [ 332] e 000000008006896C st 1 sc 5 index=FFFFF     data_load
    [ 333] e 0000000080068A64 st 1 sc 5 index=FFFFF     data_load_exit
    [ 334] e 0000000080068B98 st 1 sc 5 index=FFFFF     mem_card_wait
    [ 335] e 0000000080068BD0 st 1 sc 5 index=FFFFF     system_config
    [ 336] e 0000000080068E68 st 1 sc 5 index=FFFFF     system_config_init
    [ 337] e 0000000080068FA0 st 1 sc 5 index=FFFFF     system_moji_set
    [ 338] e 000000008006910C st 1 sc 5 index=FFFFF     system_config_root_menu
    [ 339] e 0000000080069230 st 1 sc 5 index=FFFFF     system_config_moji_speed_init
    [ 340] e 0000000080069364 st 1 sc 5 index=FFFFF     system_config_moji_speed
    [ 341] e 00000000800694B0 st 1 sc 5 index=FFFFF     system_config_moji_speed_exit
    [ 342] e 00000000800694F0 st 1 sc 5 index=FFFFF     system_config_icon_mode_init
    [ 343] e 0000000080069624 st 1 sc 5 index=FFFFF     system_config_icon_mode
    [ 344] e 00000000800697E4 st 1 sc 5 index=FFFFF     system_config_icon_mode_exit
    [ 345] e 0000000080069824 st 1 sc 5 index=FFFFF     system_config_mouse_mode_init
    [ 346] e 0000000080069958 st 1 sc 5 index=FFFFF     system_config_mouse_mode
    [ 347] e 0000000080069A20 st 1 sc 5 index=FFFFF     system_config_mouse_mode_exit
    [ 348] e 0000000080069A60 st 1 sc 5 index=FFFFF     system_config_mouse_botton_mode_init
    [ 349] e 0000000080069B78 st 1 sc 5 index=FFFFF     system_config_mouse_botton_mode
    [ 350] e 0000000080069C7C st 1 sc 5 index=FFFFF     system_config_mouse_botton_mode_exit
    [ 351] e 0000000080069CBC st 1 sc 5 index=FFFFF     system_config_mouse_click_mode_init
    [ 352] e 0000000080069DD4 st 1 sc 5 index=FFFFF     system_config_mouse_click_mode
    [ 353] e 0000000080069ED8 st 1 sc 5 index=FFFFF     system_config_mouse_click_mode_exit
    [ 354] e 0000000080069F18 st 1 sc 5 index=FFFFF     system_config_mouse_click_speed_init
    [ 355] e 000000008006A068 st 1 sc 5 index=FFFFF     system_config_mouse_click_speed
    [ 356] e 000000008006A170 st 1 sc 5 index=FFFFF     system_config_mouse_click_speed_exit
    [ 357] e 000000008006A1B0 st 1 sc 5 index=FFFFF     system_config_pad_mode_init
    [ 358] e 000000008006A364 st 1 sc 5 index=FFFFF     system_config_pad_mode
    [ 359] e 000000008006A5D0 st 1 sc 5 index=FFFFF     system_config_pad_mode_exit
    [ 360] e 000000008006A610 st 1 sc 5 index=FFFFF     system_config_cursor_speed_init
    [ 361] e 000000008006A7D8 st 1 sc 5 index=FFFFF     system_config_cursor_speed
    [ 362] e 000000008006AA68 st 1 sc 5 index=FFFFF     system_config_cursor_speed_exit
    [ 363] e 000000008006AAA8 st 1 sc 5 index=FFFFF     system_config_sound_mode_init
    [ 364] e 000000008006ABDC st 1 sc 5 index=FFFFF     system_config_sound_mode
    [ 365] e 000000008006AD78 st 1 sc 5 index=FFFFF     system_config_sound_mode_exit
    [ 366] e 000000008006ADB8 st 1 sc 5 index=FFFFF     system_config_exit
    [ 367] e 000000008006ADE0 st 1 sc 5 index=FFFFF     system_mascot_init
    [ 368] e 000000008006AFF4 st 1 sc 5 index=FFFFF     system_mascot_select
    [ 369] e 000000008006B0C8 st 1 sc 5 index=FFFFF     system_mascot_exit
    [ 370] e 000000008006B0E8 st 1 sc 5 index=FFFFF     join_club
    [ 371] e 000000008006B190 st 1 sc 5 index=FFFFF     join_club_init
    [ 372] e 000000008006B1D0 st 1 sc 5 index=FFFFF     join_club_select
    [ 373] e 000000008006B2CC st 1 sc 5 index=FFFFF     join_club_message
    [ 374] e 000000008006B4EC st 1 sc 5 index=FFFFF     join_club_exit
    [ 375] e 000000008006B514 st 1 sc 5 index=FFFFF     uwasa_set
    [ 376] e 000000008006B62C st 1 sc 5 index=FFFFF     uwasa_init
    [ 377] e 000000008006B680 st 1 sc 5 index=FFFFF     uwasa_main0
    [ 378] e 000000008006B6D4 st 1 sc 5 index=FFFFF     uwasa_exit0
    [ 379] e 000000008006B6F4 st 1 sc 5 index=FFFFF     uwasa0
    [ 380] e 000000008006B748 st 1 sc 5 index=FFFFF     uwasa_main
    [ 381] e 000000008006B7D0 st 1 sc 5 index=FFFFF     pre_xmas_init
    [ 382] e 000000008006B8B0 st 1 sc 5 index=FFFFF     pre_xmas
    [ 383] e 000000008006B904 st 1 sc 5 index=FFFFF     pre_xmas_main
    [ 384] e 000000008006B98C st 1 sc 5 index=FFFFF     get_nenga_girl
    [ 385] e 000000008006BB30 st 1 sc 5 index=FFFFF     pre_syogatu_init0
    [ 386] e 000000008006BBE4 st 1 sc 5 index=FFFFF     pre_syogatu_init1
    [ 387] e 000000008006BC6C st 1 sc 5 index=FFFFF     pre_syogatu_init2
    [ 388] e 000000008006BCBC st 1 sc 5 index=FFFFF     pre_syogatu_init3
    [ 389] e 000000008006BD1C st 1 sc 5 index=FFFFF     pre_syogatu_init
    [ 390] e 000000008006BDB4 st 1 sc 5 index=FFFFF     pre_syogatu0
    [ 391] e 000000008006BF64 st 1 sc 5 index=FFFFF     pre_syogatu1
    [ 392] e 000000008006C100 st 1 sc 5 index=FFFFF     pre_syogatu
    [ 393] e 000000008006C154 st 1 sc 5 index=FFFFF     pre_syogatu_main
    [ 394] e 000000008006C1E4 st 1 sc 5 index=FFFFF     put_yes_string
    [ 395] e 000000008006C228 st 1 sc 5 index=FFFFF     put_no_string
    [ 396] e 000000008006C26C st 1 sc 5 index=FFFFF     file_select_number_show
    [ 397] e 000000008006C418 st 1 sc 5 index=FFFFF     girl_mark_animation
    [ 398] e 000000008006C61C st 1 sc 5 index=FFFFF     girl_mark_set
    [ 399] e 000000008006C6E4 st 1 sc 5 index=FFFFF     message_kind_change
    [ 400] e 000000008006C768 st 1 sc 5 index=FFFFF     message_disp
    [ 401] e 000000008006C7F8 st 1 sc 5 index=FFFFF     album_message_set
    [ 402] e 000000008006CA48 st 1 sc 5 index=FFFFF     clear_kaisu_show
    [ 403] e 000000008006CF60 st 1 sc 5 index=FFFFF     hyouka_show
    [ 404] e 000000008006CF88 st 1 sc 5 index=FFFFF     parameter_file_show
    [ 405] e 000000008006D2E8 st 1 sc 5 index=FFFFF     now_game_info_disp
    [ 406] e 000000008006D410 st 1 sc 5 index=FFFFF     now_select_mode_disp
    [ 407] e 000000008006D540 st 1 sc 5 index=FFFFF     now_select_album_disp
    [ 408] e 000000008006D8B4 st 1 sc 5 index=FFFFF     touzyou_fan_disp
    [ 409] e 000000008006DA40 st 1 sc 5 index=FFFFF     file_select_init0
    [ 410] e 000000008006DC04 st 1 sc 5 index=FFFFF     file_select_init1
    [ 411] e 000000008006DD6C st 1 sc 5 index=FFFFF     file_select_init2
    [ 412] e 000000008006E1E8 st 1 sc 5 index=FFFFF     file_select_start_card
    [ 413] e 000000008006E260 st 1 sc 5 index=FFFFF     file_select_init
    [ 414] e 000000008006E2C8 st 1 sc 5 index=FFFFF     file_select_init_card0
    [ 415] e 000000008006E330 st 1 sc 5 index=FFFFF     file_select_init_card1
    [ 416] e 000000008006E3A8 st 1 sc 5 index=FFFFF     file_select_init_card2
    [ 417] e 000000008006E418 st 1 sc 5 index=FFFFF     file_select_init_card3
    [ 418] e 000000008006E448 st 1 sc 5 index=FFFFF     file_select_init_card4
    [ 419] e 000000008006E50C st 1 sc 5 index=FFFFF     file_select_init_card5
    [ 420] e 000000008006E580 st 1 sc 5 index=FFFFF     file_select_init_card6
    [ 421] e 000000008006E640 st 1 sc 5 index=FFFFF     file_select_init_card7
    [ 422] e 000000008006E678 st 1 sc 5 index=FFFFF     file_select_init_card
    [ 423] e 000000008006E734 st 1 sc 5 index=FFFFF     file_select_main0
    [ 424] e 000000008006E7C8 st 1 sc 5 index=FFFFF     swap_card
    [ 425] e 000000008006E820 st 1 sc 5 index=FFFFF     file_select_main1
    [ 426] e 000000008006E8F0 st 1 sc 5 index=FFFFF     file_select_main2
    [ 427] e 000000008006EA34 st 1 sc 5 index=FFFFF     set_cursor
    [ 428] e 000000008006EAB4 st 1 sc 5 index=FFFFF     file_select_main20
    [ 429] e 000000008006EB10 st 1 sc 5 index=FFFFF     file_select_main21
    [ 430] e 000000008006EC70 st 1 sc 5 index=FFFFF     mode_change_check
    [ 431] e 000000008006ED5C st 1 sc 5 index=FFFFF     file_select_main22
    [ 432] e 000000008006EDF8 st 1 sc 5 index=FFFFF     file_select_main23
    [ 433] e 000000008006EE4C st 1 sc 5 index=FFFFF     file_select_main24
    [ 434] e 000000008006EEB4 st 1 sc 5 index=FFFFF     file_select_main40
    [ 435] e 000000008006EF94 st 1 sc 5 index=FFFFF     file_select_main41
    [ 436] e 000000008006EFE0 st 1 sc 5 index=FFFFF     file_select_main42
    [ 437] e 000000008006F048 st 1 sc 5 index=FFFFF     file_select_main43
    [ 438] e 000000008006F070 st 1 sc 5 index=FFFFF     file_select_main44
    [ 439] e 000000008006F0F4 st 1 sc 5 index=FFFFF     file_select_main45
    [ 440] e 000000008006F200 st 1 sc 5 index=FFFFF     file_select_main46
    [ 441] e 000000008006F284 st 1 sc 5 index=FFFFF     file_select_main47
    [ 442] e 000000008006F2B4 st 1 sc 5 index=FFFFF     file_select_main48
    [ 443] e 000000008006F378 st 1 sc 5 index=FFFFF     file_select_main49
    [ 444] e 000000008006F3C4 st 1 sc 5 index=FFFFF     file_select_main4a
    [ 445] e 000000008006F448 st 1 sc 5 index=FFFFF     file_select_main4b
    [ 446] e 000000008006F4A4 st 1 sc 5 index=FFFFF     file_select_main4c
    [ 447] e 000000008006F560 st 1 sc 5 index=FFFFF     file_select_main4d
    [ 448] e 000000008006F61C st 1 sc 5 index=FFFFF     file_select_main4e
    [ 449] e 000000008006F668 st 1 sc 5 index=FFFFF     file_select_new
    [ 450] e 000000008006F6EC st 1 sc 5 index=FFFFF     file_select_new1
    [ 451] e 000000008006F724 st 1 sc 5 index=FFFFF     file_select_new2
    [ 452] e 000000008006F78C st 1 sc 5 index=FFFFF     file_select_new3
    [ 453] e 000000008006F8B4 st 1 sc 5 index=FFFFF     file_select_new4
    [ 454] e 000000008006F9C0 st 1 sc 5 index=FFFFF     file_select_new5
    [ 455] e 000000008006FA0C st 1 sc 5 index=FFFFF     file_select_new6
    [ 456] e 000000008006FA9C st 1 sc 5 index=FFFFF     file_select_new7
    [ 457] e 000000008006FBF8 st 1 sc 5 index=FFFFF     file_select_copy
    [ 458] e 000000008006FC7C st 1 sc 5 index=FFFFF     file_select_copy1
    [ 459] e 000000008006FDAC st 1 sc 5 index=FFFFF     file_select_copy2
    [ 460] e 000000008006FEF8 st 1 sc 5 index=FFFFF     file_select_copy3
    [ 461] e 0000000080070020 st 1 sc 5 index=FFFFF     file_select_copy4
    [ 462] e 000000008007012C st 1 sc 5 index=FFFFF     file_select_copy5
    [ 463] e 0000000080070290 st 1 sc 5 index=FFFFF     file_select_copy6
    [ 464] e 0000000080070444 st 1 sc 5 index=FFFFF     file_select_delete
    [ 465] e 00000000800704C8 st 1 sc 5 index=FFFFF     file_select_delete1
    [ 466] e 00000000800705F0 st 1 sc 5 index=FFFFF     file_select_delete2
    [ 467] e 00000000800706FC st 1 sc 5 index=FFFFF     file_select_delete3
    [ 468] e 0000000080070750 st 1 sc 5 index=FFFFF     file_select_delete4
    [ 469] e 00000000800707E4 st 1 sc 5 index=FFFFF     file_select_delete5
    [ 470] e 0000000080070824 st 1 sc 5 index=FFFFF     file_select_delete6
    [ 471] e 000000008007087C st 1 sc 5 index=FFFFF     file_select_main
    [ 472] e 0000000080070CB0 st 1 sc 5 index=FFFFF     file_select_err
    [ 473] e 0000000080070D98 st 1 sc 5 index=FFFFF     file_select_xa_call
    [ 474] e 0000000080070F74 st 1 sc 5 index=FFFFF     file_select_goto_game
    [ 475] e 0000000080070FA4 st 1 sc 5 index=FFFFF     file_select_exit
    [ 476] e 0000000080070FF8 st 1 sc 5 index=FFFFF     file_select
    [ 477] e 00000000800710E8 st 1 sc 5 index=FFFFF     white_in
    [ 478] e 0000000080071148 st 1 sc 5 index=FFFFF     shadow_file_name
    [ 479] e 0000000080071364 st 1 sc 5 index=FFFFF     _opening_movie
    [ 480] e 000000008007171C st 1 sc 5 index=FFFFF     _pre_opening_init
    [ 481] e 0000000080071C5C st 1 sc 5 index=FFFFF     _pre_opening_1
    [ 482] e 0000000080072BD0 st 1 sc 5 index=FFFFF     fujisaki_speak
    [ 483] e 0000000080072D9C st 1 sc 5 index=FFFFF     fujisaki_wink
    [ 484] e 0000000080072E70 st 1 sc 5 index=FFFFF     _pre_opening_exit
    [ 485] e 0000000080072EC0 st 1 sc 5 index=FFFFF     _pre_opening
    [ 486] e 0000000080072F5C st 1 sc 5 index=FFFFF     opening
    [ 487] e 0000000080072FC0 st 1 sc 5 index=FFFFF     logo
    [ 488] e 0000000080073060 st 1 sc 5 index=FFFFF     title_init_View
    [ 489] e 00000000800730E0 st 1 sc 5 index=FFFFF     title_init_Light
    [ 490] e 0000000080073200 st 1 sc 5 index=FFFFF     title_init_Coordinate
    [ 491] e 000000008007325C st 1 sc 5 index=FFFFF     title_init_ModelingData
    [ 492] e 0000000080073384 st 1 sc 5 index=FFFFF     title_data_read
    [ 493] e 000000008007381C st 1 sc 5 index=FFFFF     title_move_show
    [ 494] e 00000000800738E4 st 1 sc 5 index=FFFFF     title_white_out
    [ 495] e 0000000080073A3C st 1 sc 5 index=FFFFF     title_white_in
    [ 496] e 0000000080073AE8 st 1 sc 5 index=FFFFF     title_move
    [ 497] e 0000000080073B6C st 1 sc 5 index=FFFFF     title_show_init
    [ 498] e 0000000080073D40 st 1 sc 5 index=FFFFF     cursor_select
    [ 499] e 0000000080073E80 st 1 sc 5 index=FFFFF     title_show
    [ 500] e 0000000080073F0C st 1 sc 5 index=FFFFF     cursor_elem
    [ 501] e 0000000080073F40 st 1 sc 5 index=FFFFF     title_elem
    [ 502] e 0000000080073F80 st 1 sc 5 index=FFFFF     title_set
    [ 503] e 0000000080073FFC st 1 sc 5 index=FFFFF     title_goto_else_step
    [ 504] e 00000000800740E0 st 1 sc 5 index=FFFFF     title_fade_out
    [ 505] e 0000000080074158 st 1 sc 5 index=FFFFF     title_out
    [ 506] e 00000000800741BC st 1 sc 5 index=FFFFF     title
    [ 507] e 0000000080074294 st 1 sc 5 index=FFFFF     title_object_rotate
    [ 508] e 0000000080074510 st 1 sc 5 index=FFFFF     bust_up_read
    [ 509] e 0000000080074544 st 1 sc 5 index=FFFFF     bust_up_init
    [ 510] e 0000000080074C7C st 1 sc 5 index=FFFFF     bust_up_face_c
    [ 511] e 0000000080074DC4 st 1 sc 5 index=FFFFF     bust_up_show
    [ 512] e 0000000080075138 st 1 sc 5 index=FFFFF     bustup_speech
    [ 513] e 000000008007516C st 1 sc 5 index=FFFFF     bustup_wink
    [ 514] e 0000000080075190 st 1 sc 5 index=FFFFF     parameter_change
    [ 515] e 00000000800751D8 st 1 sc 5 index=FFFFF     parameter_disp_switch
    [ 516] e 0000000080075280 st 1 sc 5 index=FFFFF     parameter_show_init
    [ 517] e 0000000080075F74 st 1 sc 5 index=FFFFF     parameter_show
    [ 518] e 00000000800761D4 st 1 sc 5 index=FFFFF     hizuke_disp_switch
    [ 519] e 000000008007627C st 1 sc 5 index=FFFFF     hizuke_init
    [ 520] e 0000000080076694 st 1 sc 5 index=FFFFF     hizuke_show
    [ 521] e 00000000800766F0 st 1 sc 5 index=FFFFF     message_disp_switch
    [ 522] e 000000008007672C st 1 sc 5 index=FFFFF     message_window_init
    [ 523] e 00000000800767F0 st 1 sc 5 index=FFFFF     message_window_show
    [ 524] e 000000008007684C st 1 sc 5 index=FFFFF     icon_disp_switch
    [ 525] e 00000000800768F0 st 1 sc 5 index=FFFFF     icon_can_use_set
    [ 526] e 000000008007691C st 1 sc 5 index=FFFFF     get_icon_can_use
    [ 527] e 0000000080076944 st 1 sc 5 index=FFFFF     icon_init
    [ 528] e 0000000080076C1C st 1 sc 5 index=FFFFF     icon_menu_set
    [ 529] e 000000008007704C st 1 sc 5 index=FFFFF     icon_mem_card_switch
    [ 530] e 0000000080077078 st 1 sc 5 index=FFFFF     icon_atari_check
    [ 531] e 0000000080077220 st 1 sc 5 index=FFFFF     icon_show
    [ 532] e 0000000080077564 st 1 sc 5 index=FFFFF     basyo_disp_switch
    [ 533] e 0000000080077728 st 1 sc 5 index=FFFFF     basyo_init2
    [ 534] e 0000000080077750 st 1 sc 5 index=FFFFF     basyo_init
    [ 535] e 0000000080077958 st 1 sc 5 index=FFFFF     basyo_show
    [ 536] e 0000000080078050 st 1 sc 5 index=FFFFF     get_season
    [ 537] e 00000000800780A8 st 1 sc 5 index=FFFFF     get_nf
    [ 538] e 00000000800780F0 st 1 sc 5 index=FFFFF     get_vacation
    [ 539] e 00000000800781B8 st 1 sc 5 index=FFFFF     back_scroll_move
    [ 540] e 0000000080078968 st 1 sc 5 index=FFFFF     back_scroll_init
    [ 541] e 00000000800789E8 st 1 sc 5 index=FFFFF     normal_music_read_init0
    [ 542] e 0000000080078A58 st 1 sc 5 index=FFFFF     normal_music_read_again
    [ 543] e 0000000080078B7C st 1 sc 5 index=FFFFF     normal_music_read_init1
    [ 544] e 0000000080078BB8 st 1 sc 5 index=FFFFF     mascot_disp_switch
    [ 545] e 0000000080078C18 st 1 sc 5 index=FFFFF     mascot_init
    [ 546] e 0000000080078DDC st 1 sc 5 index=FFFFF     mascot_move
    [ 547] e 00000000800791D0 st 1 sc 5 index=FFFFF     event_bust_up_show
    [ 548] e 0000000080079338 st 1 sc 5 index=FFFFF     event_bustup_wink
    [ 549] e 0000000080079360 st 1 sc 5 index=FFFFF     event_bustup_kuchi_ani
    [ 550] e 0000000080079390 st 1 sc 5 index=FFFFF     cal_class_init
    [ 551] e 0000000080079460 st 1 sc 5 index=FFFFF     schedule_mark_on
    [ 552] e 0000000080079BCC st 1 sc 5 index=FFFFF     get_calx_pos
    [ 553] e 0000000080079C24 st 1 sc 5 index=FFFFF     get_caly_pos
    [ 554] e 0000000080079C6C st 1 sc 5 index=FFFFF     cal_font_load
    [ 555] e 0000000080079F18 st 1 sc 5 index=FFFFF     biorhythm_curve
    [ 556] e 000000008007A198 st 1 sc 5 index=FFFFF     cal_show
    [ 557] e 000000008007A2C0 st 1 sc 5 index=FFFFF     cal_base_show
    [ 558] e 000000008007A310 st 1 sc 5 index=FFFFF     appraisal_base_show
    [ 559] e 000000008007A360 st 1 sc 5 index=FFFFF     magazine_base_show
    [ 560] e 000000008007A3B0 st 1 sc 5 index=FFFFF     cal_sprite_disp_switch
    [ 561] e 000000008007A470 st 1 sc 5 index=FFFFF     cal_sprite_init
    [ 562] e 000000008007A7AC st 1 sc 5 index=FFFFF     data_save_load_class_init
    [ 563] e 000000008007A874 st 1 sc 5 index=FFFFF     memory_card_data_set
    [ 564] e 000000008007AB28 st 1 sc 5 index=FFFFF     joho_check
    [ 565] e 000000008007ADAC st 1 sc 5 index=FFFFF     magazine_class_init
    [ 566] e 000000008007B9A4 st 1 sc 5 index=FFFFF     reserved_date
    [ 567] e 000000008007BAEC st 1 sc 5 index=FFFFF     check_date_info
    [ 568] e 000000008007BBA0 st 1 sc 5 index=FFFFF     sort_date_info
    [ 569] e 000000008007C084 st 1 sc 5 index=FFFFF     set_date_info
    [ 570] e 000000008007C108 st 1 sc 5 index=FFFFF     print_date_info
    [ 571] e 000000008007C284 st 1 sc 5 index=FFFFF     join_club_class_init
    [ 572] e 000000008007C530 st 1 sc 5 index=FFFFF     date_light_effect
    [ 573] e 000000008007C670 st 1 sc 5 index=FFFFF     cursor_move
    [ 574] e 000000008007C844 st 1 sc 5 index=FFFFF     cursor_init
    [ 575] e 000000008007C988 st 1 sc 5 index=FFFFF     cursor_disp_switch
    [ 576] e 000000008007C9C4 st 1 sc 5 index=FFFFF     biorhythm_sf_set
    [ 577] e 000000008007CE8C st 1 sc 5 index=FFFFF     biorhythm_sf
    [ 578] e 000000008007CEB8 st 1 sc 5 index=FFFFF     biorhythm_sf2
    [ 579] e 000000008007D284 st 1 sc 5 index=FFFFF     get_pass_days
    [ 580] e 000000008007D2EC st 1 sc 5 index=FFFFF     konami_mark_set
    [ 581] e 000000008007D3D4 st 1 sc 5 index=FFFFF     yazirushi_disp_switch
    [ 582] e 000000008007D4C0 st 1 sc 5 index=FFFFF     move_yazirushi
    [ 583] e 000000008007D520 st 1 sc 5 index=FFFFF     schedule_init
    [ 584] e 000000008007D55C st 1 sc 5 index=FFFFF     _schedule_init
    [ 585] e 000000008007D618 st 1 sc 5 index=FFFFF     last_date_spot_timer_dec
    [ 586] e 000000008007D6D4 st 1 sc 5 index=FFFFF     restore_bgm
    [ 587] e 000000008007D704 st 1 sc 5 index=FFFFF     schedule_icon_disp
    [ 588] e 000000008007D75C st 1 sc 5 index=FFFFF     normal_icon_set
    [ 589] e 000000008007D7E0 st 1 sc 5 index=FFFFF     schedule_buf_clear
    [ 590] e 000000008007D828 st 1 sc 5 index=FFFFF     season_mess_clear
    [ 591] e 000000008007D8B4 st 1 sc 5 index=FFFFF     season_flag_set
    [ 592] e 000000008007D8E0 st 1 sc 5 index=FFFFF     season_last_date_spot_clear
    [ 593] e 000000008007D9C8 st 1 sc 5 index=FFFFF     basyo_flag_set
    [ 594] e 000000008007DD38 st 1 sc 5 index=FFFFF     bukatu_reset
    [ 595] e 000000008007DDC4 st 1 sc 5 index=FFFFF     schedule_weekday
    [ 596] e 000000008007EBE8 st 1 sc 5 index=FFFFF     tate_last_date_check
    [ 597] e 000000008007ECF0 st 1 sc 5 index=FFFFF     touzyou_girl1
    [ 598] e 000000008007F038 st 1 sc 5 index=FFFFF     touzyou_girl2
    [ 599] e 000000008007F374 st 1 sc 5 index=FFFFF     touzyou_girl3
    [ 600] e 000000008007F624 st 1 sc 5 index=FFFFF     get_ouen_girl
    [ 601] e 000000008007FC78 st 1 sc 5 index=FFFFF     tokubetu_judge
    [ 602] e 00000000800807B0 st 1 sc 5 index=FFFFF     geko_judge
    [ 603] e 000000008008096C st 1 sc 5 index=FFFFF     date_sasoi_judge
    [ 604] e 0000000080080BF0 st 1 sc 5 index=FFFFF     schedule_girls_gakko
    [ 605] e 0000000080080D60 st 1 sc 5 index=FFFFF     yuukou_down
    [ 606] e 0000000080080F2C st 1 sc 5 index=FFFFF     syoushin_up
    [ 607] e 0000000080080FAC st 1 sc 5 index=FFFFF     schdeule_girls_param
    [ 608] e 0000000080080FE8 st 1 sc 5 index=FFFFF     schedule_init_exit
    [ 609] e 00000000800810E4 st 1 sc 5 index=FFFFF     schedule_set
    [ 610] e 0000000080081120 st 1 sc 5 index=FFFFF     _schedule_set
    [ 611] e 0000000080081170 st 1 sc 5 index=FFFFF     schedule_bye
    [ 612] e 00000000800811D8 st 1 sc 5 index=FFFFF     parameter_limited
    [ 613] e 0000000080081384 st 1 sc 5 index=FFFFF     mem_card_check
    [ 614] e 00000000800813E8 st 1 sc 5 index=FFFFF     himo_robo_check
    [ 615] e 0000000080081528 st 1 sc 5 index=FFFFF     schedule_analyze
    [ 616] e 00000000800822F8 st 1 sc 5 index=FFFFF     change_joho_look_f
    [ 617] e 0000000080082364 st 1 sc 5 index=FFFFF     cal_inc
    [ 618] e 0000000080082570 st 1 sc 5 index=FFFFF     etc_flag_clear
    [ 619] e 000000008008258C st 1 sc 5 index=FFFFF     kyuuka
    [ 620] e 00000000800825F0 st 1 sc 5 index=FFFFF     _goto_vacation
    [ 621] e 0000000080082758 st 1 sc 5 index=FFFFF     change_month
    [ 622] e 00000000800827BC st 1 sc 5 index=FFFFF     _change_month
    [ 623] e 000000008008284C st 1 sc 5 index=FFFFF     change_month_font_load
    [ 624] e 000000008008292C st 1 sc 5 index=FFFFF     change_month_bgm_read
    [ 625] e 0000000080082968 st 1 sc 5 index=FFFFF     return_schedule
    [ 626] e 00000000800829CC st 1 sc 5 index=FFFFF     kega_check
    [ 627] e 0000000080082A1C st 1 sc 5 index=FFFFF     _kega_check
    [ 628] e 0000000080082B2C st 1 sc 5 index=FFFFF     kega_check1
    [ 629] e 0000000080082F34 st 1 sc 5 index=FFFFF     kega_hassei
    [ 630] e 0000000080083088 st 1 sc 5 index=FFFFF     noiroze_hassei
    [ 631] e 000000008008315C st 1 sc 5 index=FFFFF     sick_hassei
    [ 632] e 0000000080083230 st 1 sc 5 index=FFFFF     kega_kaifuku
    [ 633] e 0000000080083318 st 1 sc 5 index=FFFFF     noiroze_kaifuku
    [ 634] e 0000000080083400 st 1 sc 5 index=FFFFF     sick_kaifuku
    [ 635] e 00000000800834E8 st 1 sc 5 index=FFFFF     kega_exit
    [ 636] e 0000000080083560 st 1 sc 5 index=FFFFF     week_day
    [ 637] e 0000000080083640 st 1 sc 5 index=FFFFF     week_day_exit
    [ 638] e 0000000080083680 st 1 sc 5 index=FFFFF     week_day_init
    [ 639] e 0000000080083700 st 1 sc 5 index=FFFFF     week_day_main
    [ 640] e 0000000080083740 st 1 sc 5 index=FFFFF     get_weekly_bg_sector
    [ 641] e 00000000800837A0 st 1 sc 5 index=FFFFF     week_day_init0
    [ 642] e 000000008008392C st 1 sc 5 index=FFFFF     set_sd
    [ 643] e 0000000080083E34 st 1 sc 5 index=FFFFF     week_day_init1
    [ 644] e 0000000080083FE8 st 1 sc 5 index=FFFFF     week_day_init2
    [ 645] e 00000000800842F4 st 1 sc 5 index=FFFFF     week_day_main0
    [ 646] e 0000000080084434 st 1 sc 5 index=FFFFF     week_day_exit0
    [ 647] e 0000000080084478 st 1 sc 5 index=FFFFF     parameter_up_down
    [ 648] e 0000000080084944 st 1 sc 5 index=FFFFF     vacation_day_init
    [ 649] e 00000000800849C4 st 1 sc 5 index=FFFFF     vacation_day_init0
    [ 650] e 0000000080084B0C st 1 sc 5 index=FFFFF     vacation_day_init1
    [ 651] e 0000000080084C2C st 1 sc 5 index=FFFFF     vacation_day_init2
    [ 652] e 0000000080084E20 st 1 sc 5 index=FFFFF     holiday
    [ 653] e 0000000080084F68 st 1 sc 5 index=FFFFF     holiday_init
    [ 654] e 0000000080084FC0 st 1 sc 5 index=FFFFF     fujisaki_2nin_birth_check
    [ 655] e 00000000800850B4 st 1 sc 5 index=FFFFF     holiday_init_0
    [ 656] e 00000000800854E8 st 1 sc 5 index=FFFFF     holiday_init_1
    [ 657] e 0000000080085530 st 1 sc 5 index=FFFFF     sunday_icon_phase
    [ 658] e 0000000080085604 st 1 sc 5 index=FFFFF     holiday_main
    [ 659] e 0000000080085658 st 1 sc 5 index=FFFFF     holiday_main0
    [ 660] e 0000000080085690 st 1 sc 5 index=FFFFF     phone_check
    [ 661] e 0000000080085970 st 1 sc 5 index=FFFFF     get_holiday_bg_sector
    [ 662] e 00000000800859D0 st 1 sc 5 index=FFFFF     icon_check_h
    [ 663] e 0000000080085CC8 st 1 sc 5 index=FFFFF     get_date_basyo_num
    [ 664] e 0000000080085DFC st 1 sc 5 index=FFFFF     pre_date_init
    [ 665] e 0000000080085F70 st 1 sc 5 index=FFFFF     date_x_taku_set
    [ 666] e 00000000800862C4 st 1 sc 5 index=FFFFF     pre_date_select
    [ 667] e 00000000800863F8 st 1 sc 5 index=FFFFF     pre_date_exit
    [ 668] e 0000000080086518 st 1 sc 5 index=FFFFF     pre_date
    [ 669] e 0000000080086588 st 1 sc 5 index=FFFFF     holiday_normal
    [ 670] e 000000008008661C st 1 sc 5 index=FFFFF     set_sd_holiday
    [ 671] e 0000000080086730 st 1 sc 5 index=FFFFF     holiday_normal_init0
    [ 672] e 00000000800869F0 st 1 sc 5 index=FFFFF     holiday_normal_init1
    [ 673] e 0000000080086B9C st 1 sc 5 index=FFFFF     holiday_normal_main
    [ 674] e 0000000080086E44 st 1 sc 5 index=FFFFF     holiday_magazine
    [ 675] e 0000000080086EB4 st 1 sc 5 index=FFFFF     magazine_init
    [ 676] e 0000000080086F0C st 1 sc 5 index=FFFFF     magazine_main
    [ 677] e 0000000080086F68 st 1 sc 5 index=FFFFF     magazine_exit
    [ 678] e 0000000080086F98 st 1 sc 5 index=FFFFF     holiday_tel
    [ 679] e 000000008008701C st 1 sc 5 index=FFFFF     holiday_tel_init
    [ 680] e 0000000080087094 st 1 sc 5 index=FFFFF     holiday_tel_call
    [ 681] e 0000000080087184 st 1 sc 5 index=FFFFF     holiday_tel_exit
    [ 682] e 000000008008732C st 1 sc 5 index=FFFFF     telephone_class_init
    [ 683] e 0000000080087640 st 1 sc 5 index=FFFFF     holiday_club_init
    [ 684] e 00000000800876A8 st 1 sc 5 index=FFFFF     holiday_club_select
    [ 685] e 00000000800877F8 st 1 sc 5 index=FFFFF     holiday_club_exit
    [ 686] e 000000008008789C st 1 sc 5 index=FFFFF     holiday_taibu_club_exit
    [ 687] e 00000000800878DC st 1 sc 5 index=FFFFF     holiday_club
    [ 688] e 0000000080087960 st 1 sc 5 index=FFFFF     holiday_club_join_exit
    [ 689] e 0000000080087990 st 1 sc 5 index=FFFFF     holiday_club_join
    [ 690] e 0000000080087A20 st 1 sc 5 index=FFFFF     load_exe_bin
    [ 691] e 0000000080087AC0 st 1 sc 5 index=FFFFF     etc_disp
    [ 692] e 0000000080087C38 st 1 sc 5 index=FFFFF     load_func_main
    [ 693] e 0000000080087F80 st 1 sc 5 index=FFFFF     load_func_ok
    [ 694] e 0000000080087FB4 st 1 sc 5 index=FFFFF     load_fucn_check_sum
    [ 695] e 0000000080088010 st 1 sc 5 index=FFFFF     load_func_go
    [ 696] e 00000000800884A8 st 1 sc 5 index=FFFFF     twinbee
    [ 697] e 0000000080088700 st 1 sc 5 index=FFFFF     SD_Call_SD
    [ 698] e 0000000080088724 st 1 sc 5 index=FFFFF     SD_Task
    [ 699] e 0000000080088860 st 1 sc 5 index=FFFFF     SD_HandleVBLVAB
    [ 700] e 000000008008898C st 1 sc 5 index=FFFFF     SD_TransVAB
    [ 701] e 0000000080088A54 st 1 sc 5 index=FFFFF     SD_ISVabAvailable
    [ 702] e 0000000080088AA0 st 1 sc 5 index=FFFFF     SD_XATask
    [ 703] e 0000000080088AF0 st 1 sc 5 index=FFFFF     SD_CheckXASector
    [ 704] e 0000000080088B54 st 1 sc 5 index=FFFFF     SD_IsXAReady
    [ 705] e 0000000080088C30 st 1 sc 5 index=FFFFF     SD_HandleVBL
    [ 706] e 0000000080088CCC st 1 sc 5 index=FFFFF     SD_BranchCTRL
    [ 707] e 0000000080088EA0 st 1 sc 5 index=FFFFF     SD_VABTransfer
    [ 708] e 0000000080088FA0 st 1 sc 5 index=FFFFF     SD_BufferUpdate
    [ 709] e 0000000080089088 st 1 sc 5 index=FFFFF     SD_HandleSys
    [ 710] e 0000000080089100 st 1 sc 5 index=FFFFF     SD_HandleVBLXA
    [ 711] e 0000000080089130 st 1 sc 5 index=FFFFF     SD_HandleXAFadeOut
    [ 712] e 00000000800891E0 st 1 sc 5 index=FFFFF     SD_FinishFadeOutXA
    [ 713] e 000000008008923C st 1 sc 5 index=FFFFF     SD_XACall
    [ 714] e 00000000800893E4 st 1 sc 5 index=FFFFF     SD_XAParamUpdate
    [ 715] e 00000000800894A0 st 1 sc 5 index=FFFFF     SD_PlayXA
    [ 716] e 0000000080089508 st 1 sc 5 index=FFFFF     SD_StopXA
    [ 717] e 0000000080089668 st 1 sc 5 index=FFFFF     SD_FadeXA
    [ 718] e 0000000080089724 st 1 sc 5 index=FFFFF     SD_HandleVBLSEQ
    [ 719] e 000000008008981C st 1 sc 5 index=FFFFF     SD_FinishFadeOutSEQ
    [ 720] e 0000000080089858 st 1 sc 5 index=FFFFF     SD_SEQCall
    [ 721] e 0000000080089940 st 1 sc 5 index=FFFFF     SD_PlaySeq
    [ 722] e 000000008008998C st 1 sc 5 index=FFFFF     SD_SeqGo
    [ 723] e 0000000080089B08 st 1 sc 5 index=FFFFF     SD_StopSeq
    [ 724] e 0000000080089C64 st 1 sc 5 index=FFFFF     SD_FadeSeq
    [ 725] e 0000000080089D0C st 1 sc 5 index=FFFFF     SD_HandleVBLSE
    [ 726] e 0000000080089D14 st 1 sc 5 index=FFFFF     SD_SECall
    [ 727] e 0000000080089D98 st 1 sc 5 index=FFFFF     SD_OtherSECall
    [ 728] e 0000000080089E1C st 1 sc 5 index=FFFFF     SD_SECallInSEQ
    [ 729] e 0000000080089EA0 st 1 sc 5 index=FFFFF     SD_OtherSECallInSEQ
    [ 730] e 0000000080089F24 st 1 sc 5 index=FFFFF     SD_PlaySE
    [ 731] e 0000000080089F60 st 1 sc 5 index=FFFFF     SD_StopSE
    [ 732] e 0000000080089F80 st 1 sc 5 index=FFFFF     SD_FadeSE
    [ 733] e 0000000080089F88 st 1 sc 5 index=FFFFF     SD_AddEvt
    [ 734] e 0000000080089FDC st 1 sc 5 index=FFFFF     SD_FlashEvent
    [ 735] e 0000000080089FE8 st 1 sc 5 index=FFFFF     SD_GetNextEvent
    [ 736] e 000000008008A07C st 1 sc 5 index=FFFFF     SD_KillXA
    [ 737] e 000000008008A0D8 st 1 sc 5 index=FFFFF     SD_KillSPU
    [ 738] e 000000008008A0F8 st 1 sc 5 index=FFFFF     SD_Init
    [ 739] e 000000008008A1BC st 1 sc 5 index=FFFFF     SD_SetVabAdrs
    [ 740] e 000000008008A260 st 1 sc 5 index=FFFFF     SD_GetVabAdrs
    [ 741] e 000000008008A318 st 1 sc 5 index=FFFFF     SD_InitCD
    [ 742] e 000000008008A370 st 1 sc 5 index=FFFFF     SD_InitStruct
    [ 743] e 000000008008A4A8 st 1 sc 5 index=FFFFF     SD_SetSeqAdrs
    [ 744] e 000000008008A52C st 1 sc 5 index=FFFFF     SD_ChnChange
    [ 745] e 000000008008A5E0 st 1 sc 5 index=FFFFF     SD_Reset
    [ 746] e 000000008008A67C st 1 sc 5 index=FFFFF     SD_GetVAB
    [ 747] e 000000008008A6A4 st 1 sc 5 index=FFFFF     SD_DisposeVAB
    [ 748] e 000000008008A748 st 1 sc 5 index=FFFFF     SD_InitCDLevelInfo
    [ 749] e 000000008008A780 st 1 sc 5 index=FFFFF     SD_GetCDLevel
    [ 750] e 000000008008AA60 st 1 sc 5 index=FFFFF     SD_DetectCDPeak
    [ 751] e 000000008008AB64 st 1 sc 5 index=FFFFF     SD_CalcCDAve
    [ 752] e 000000008008AC6C st 1 sc 5 index=FFFFF     getCDlevel
    [ 753] e 000000008008ACB0 st 1 sc 5 index=FFFFF     addr_init_weekly_sd
    [ 754] e 000000008008AD1C st 1 sc 5 index=FFFFF     addr_init_holiday_sd
    [ 755] e 000000008008AD88 st 1 sc 5 index=FFFFF     addr_init_club_sd
    [ 756] e 000000008008ADF8 st 1 sc 5 index=FFFFF     addr_init_else_sd
    [ 757] e 000000008008AE90 st 1 sc 5 index=FFFFF     addr_init_bustup
    [ 758] e 000000008008AED4 st 1 sc 5 index=FFFFF     cdread_callback
    [ 759] e 000000008008AF08 st 1 sc 5 index=FFFFF     normal_date_bg_suddenin
    [ 760] e 000000008008AF3C st 1 sc 5 index=FFFFF     normal_date_bg_suddenout
    [ 761] e 000000008008AF68 st 1 sc 5 index=FFFFF     normal_date_bg_in
    [ 762] e 000000008008AF9C st 1 sc 5 index=FFFFF     normal_date_bg_in_sub
    [ 763] e 000000008008BA58 st 1 sc 5 index=FFFFF     set_tarao_bg
    [ 764] e 000000008008BD54 st 1 sc 5 index=FFFFF     set_tarao_sprt
    [ 765] e 000000008008BE5C st 1 sc 5 index=FFFFF     set_tarao_rect
    [ 766] e 000000008008BF4C st 1 sc 5 index=FFFFF     normal_date_bg_out
    [ 767] e 000000008008BF80 st 1 sc 5 index=FFFFF     normal_date_bg_out_sub
    [ 768] e 000000008008CA2C st 1 sc 5 index=FFFFF     normal_date_girl_in
    [ 769] e 000000008008CA94 st 1 sc 5 index=FFFFF     normal_date_girl_in_init
    [ 770] e 000000008008CB04 st 1 sc 5 index=FFFFF     normal_date_girl_in_main
    [ 771] e 000000008008CBCC st 1 sc 5 index=FFFFF     normal_date_girl_suddenin
    [ 772] e 000000008008CC3C st 1 sc 5 index=FFFFF     normal_date_girl_out
    [ 773] e 000000008008CCA4 st 1 sc 5 index=FFFFF     normal_date_girl_out_init
    [ 774] e 000000008008CCD0 st 1 sc 5 index=FFFFF     normal_date_girl_out_main
    [ 775] e 000000008008CDF8 st 1 sc 5 index=FFFFF     normal_date_girl_suddenout
    [ 776] e 000000008008CEB8 st 1 sc 5 index=FFFFF     normal_date_bg_fadein
    [ 777] e 000000008008CF20 st 1 sc 5 index=FFFFF     normal_date_bggirl_fadein
    [ 778] e 000000008008CFD0 st 1 sc 5 index=FFFFF     normal_date_bg_fadeout
    [ 779] e 000000008008D038 st 1 sc 5 index=FFFFF     normal_date_bggirl_fadeout
    [ 780] e 000000008008D148 st 1 sc 5 index=FFFFF     normal_date_move_place
    [ 781] e 000000008008D1A8 st 1 sc 5 index=FFFFF     normal_date_move_place_init
    [ 782] e 000000008008D1F8 st 1 sc 5 index=FFFFF     normal_date_move_place_main
    [ 783] e 000000008008D304 st 1 sc 5 index=FFFFF     place_init
    [ 784] e 000000008008D338 st 1 sc 5 index=FFFFF     place_init2
    [ 785] e 000000008008D36C st 1 sc 5 index=FFFFF     change_dec_bg
    [ 786] e 000000008008D394 st 1 sc 5 index=FFFFF     dec_init
    [ 787] e 000000008008D420 st 1 sc 5 index=FFFFF     bg_read_sub2
    [ 788] e 000000008008D494 st 1 sc 5 index=FFFFF     check_k_scroll
    [ 789] e 000000008008D5A0 st 1 sc 5 index=FFFFF     wait_sub_sub
    [ 790] e 000000008008D5E4 st 1 sc 5 index=FFFFF     set_window_message
    [ 791] e 000000008008F5B0 st 1 sc 5 index=FFFFF     seek_stop_xa
    [ 792] e 000000008008F610 st 1 sc 5 index=FFFFF     set_kanji_win_string
    [ 793] e 0000000080090BE4 st 1 sc 5 index=FFFFF     speak_sub
    [ 794] e 000000008009119C st 1 sc 5 index=FFFFF     make_three_select
    [ 795] e 00000000800912F8 st 1 sc 5 index=FFFFF     junban_init
    [ 796] e 00000000800913B4 st 1 sc 5 index=FFFFF     normal_date_three_select
    [ 797] e 0000000080091414 st 1 sc 5 index=FFFFF     normal_date_three_select_init
    [ 798] e 00000000800914BC st 1 sc 5 index=FFFFF     normal_date_three_select_main
    [ 799] e 00000000800915B8 st 1 sc 5 index=FFFFF     normal_date_two_select
    [ 800] e 0000000080091618 st 1 sc 5 index=FFFFF     normal_date_two_select_init
    [ 801] e 00000000800916AC st 1 sc 5 index=FFFFF     normal_date_two_select_main
    [ 802] e 000000008009177C st 1 sc 5 index=FFFFF     normal_date_face_change_continue
    [ 803] e 00000000800917C4 st 1 sc 5 index=FFFFF     hidden_face_change_continue
    [ 804] e 0000000080091804 st 1 sc 5 index=FFFFF     normal_date_face_change0
    [ 805] e 0000000080091834 st 1 sc 5 index=FFFFF     normal_date_face_change1
    [ 806] e 0000000080091864 st 1 sc 5 index=FFFFF     normal_date_face_change2
    [ 807] e 0000000080091894 st 1 sc 5 index=FFFFF     normal_date_face_change3
    [ 808] e 00000000800918C4 st 1 sc 5 index=FFFFF     normal_date_face_change4
    [ 809] e 00000000800918F4 st 1 sc 5 index=FFFFF     hidden_face_change0
    [ 810] e 000000008009191C st 1 sc 5 index=FFFFF     hidden_face_change1
    [ 811] e 0000000080091944 st 1 sc 5 index=FFFFF     hidden_face_change2
    [ 812] e 000000008009196C st 1 sc 5 index=FFFFF     hidden_face_change3
    [ 813] e 0000000080091994 st 1 sc 5 index=FFFFF     hidden_face_change4
    [ 814] e 00000000800919BC st 1 sc 5 index=FFFFF     face_change
    [ 815] e 00000000800919E8 st 1 sc 5 index=FFFFF     bust_up_init2
    [ 816] e 0000000080091B48 st 1 sc 5 index=FFFFF     bust_up_init3
    [ 817] e 0000000080091C7C st 1 sc 5 index=FFFFF     bust_up_show2
    [ 818] e 0000000080091E84 st 1 sc 5 index=FFFFF     dec_bg_show2
    [ 819] e 0000000080091F38 st 1 sc 5 index=FFFFF     hizuke_hide
    [ 820] e 0000000080091F60 st 1 sc 5 index=FFFFF     hizuke_appear
    [ 821] e 0000000080091F88 st 1 sc 5 index=FFFFF     read_bustup
    [ 822] e 00000000800925B4 st 1 sc 5 index=FFFFF     read_bustup_uniform
    [ 823] e 0000000080092988 st 1 sc 5 index=FFFFF     read_bustup_swimsuit
    [ 824] e 0000000080092ABC st 1 sc 5 index=FFFFF     bustup_return
    [ 825] e 0000000080092ADC st 1 sc 5 index=FFFFF     return_step
    [ 826] e 0000000080092B24 st 1 sc 5 index=FFFFF     k_disp_inc2
    [ 827] e 0000000080092B9C st 1 sc 5 index=FFFFF     yosi_trans
    [ 828] e 0000000080092BC8 st 1 sc 5 index=FFFFF     change_yoshio
    [ 829] e 0000000080092BF0 st 1 sc 5 index=FFFFF     change_girl
    [ 830] e 0000000080092C1C st 1 sc 5 index=FFFFF     pg_name_init
    [ 831] e 0000000080092CAC st 1 sc 5 index=FFFFF     select_girl
    [ 832] e 0000000080092D0C st 1 sc 5 index=FFFFF     select_girl2
    [ 833] e 0000000080092D6C st 1 sc 5 index=FFFFF     select_girl_init
    [ 834] e 0000000080092FFC st 1 sc 5 index=FFFFF     select_girl_main
    [ 835] e 00000000800930F8 st 1 sc 5 index=FFFFF     sprite_brightness
    [ 836] e 0000000080093128 st 1 sc 5 index=FFFFF     day_plus
    [ 837] e 000000008009319C st 1 sc 5 index=FFFFF     check_para_limit
    [ 838] e 00000000800932AC st 1 sc 5 index=FFFFF     set_yajirusi
    [ 839] e 0000000080093394 st 1 sc 5 index=FFFFF     bustup_mouse_on
    [ 840] e 00000000800933B8 st 1 sc 5 index=FFFFF     load_ful
    [ 841] e 00000000800935FC st 1 sc 5 index=FFFFF     load_opd
    [ 842] e 0000000080093754 st 1 sc 5 index=FFFFF     event_char_onoff
    [ 843] e 0000000080093858 st 1 sc 5 index=FFFFF     ev_fadein
    [ 844] e 00000000800938D0 st 1 sc 5 index=FFFFF     ev_fadeout
    [ 845] e 0000000080093964 st 1 sc 5 index=FFFFF     event_face0
    [ 846] e 0000000080093994 st 1 sc 5 index=FFFFF     event_face1
    [ 847] e 00000000800939C8 st 1 sc 5 index=FFFFF     event_face2
    [ 848] e 00000000800939FC st 1 sc 5 index=FFFFF     event_face3
    [ 849] e 0000000080093A30 st 1 sc 5 index=FFFFF     event_face_kuchi0
    [ 850] e 0000000080093A58 st 1 sc 5 index=FFFFF     event_face_kuchi1
    [ 851] e 0000000080093A80 st 1 sc 5 index=FFFFF     event_kuchi_ani_no
    [ 852] e 0000000080093AB0 st 1 sc 5 index=FFFFF     event_kuchi_ani_yes
    [ 853] e 0000000080093AE0 st 1 sc 5 index=FFFFF     ev_me_on
    [ 854] e 0000000080093B10 st 1 sc 5 index=FFFFF     ev_me_on_continue
    [ 855] e 0000000080093B44 st 1 sc 5 index=FFFFF     _sprite_set_box_shade_tarao
    [ 856] e 0000000080093D28 st 1 sc 5 index=FFFFF     clear_work_tarao
    [ 857] e 0000000080093DA4 st 1 sc 5 index=FFFFF     don_init2
    [ 858] e 0000000080093DCC st 1 sc 5 index=FFFFF     don_wait
    [ 859] e 0000000080093E14 st 1 sc 5 index=FFFFF     normal_date_speak_1line
    [ 860] e 0000000080093EA4 st 1 sc 5 index=FFFFF     normal_date_speak_012
    [ 861] e 0000000080093F1C st 1 sc 5 index=FFFFF     normal_date_speak
    [ 862] e 0000000080093F98 st 1 sc 5 index=FFFFF     vram_bustup_clear
    [ 863] e 0000000080093FF8 st 1 sc 5 index=FFFFF     date_alubum_para_set
    [ 864] e 0000000080094130 st 1 sc 5 index=FFFFF     bust_up_face
    [ 865] e 0000000080094290 st 1 sc 5 index=FFFFF     Graph_Init
    [ 866] e 0000000080094388 st 1 sc 5 index=FFFFF     Vblnk_Timer_Init
    [ 867] e 00000000800943A4 st 1 sc 5 index=FFFFF     Vblnk_Timer
    [ 868] e 00000000800943C4 st 1 sc 5 index=FFFFF     Scroll
    [ 869] e 00000000800946BC st 1 sc 5 index=FFFFF     Rot_2D
    [ 870] e 0000000080094788 st 1 sc 5 index=FFFFF     Fade_Out_Init
    [ 871] e 00000000800947A8 st 1 sc 5 index=FFFFF     Fade_Out_Main
    [ 872] e 0000000080094808 st 1 sc 5 index=FFFFF     Fade_In_Init
    [ 873] e 0000000080094828 st 1 sc 5 index=FFFFF     Fade_In_Main
    [ 874] e 000000008009488C st 1 sc 5 index=FFFFF     Yubi
    [ 875] e 00000000800948DC st 1 sc 5 index=FFFFF     Default_Disp
    [ 876] e 0000000080094934 st 1 sc 5 index=FFFFF     Shiori_Case_Of_Mine
    [ 877] e 0000000080094A0C st 1 sc 5 index=FFFFF     Ev_Class_W_Switch
    [ 878] e 0000000080094A48 st 1 sc 5 index=FFFFF     Get_Serifu
    [ 879] e 0000000080094A6C st 1 sc 5 index=FFFFF     bust_up_read_myu
    [ 880] e 0000000080094B84 st 1 sc 5 index=FFFFF     pcm_read_myu
    [ 881] e 0000000080094BD0 st 1 sc 5 index=FFFFF     DecDCTReset
    [ 882] e 0000000080094C04 st 1 sc 5 index=FFFFF     DecDCTBufSize
    [ 883] e 0000000080094C10 st 1 sc 5 index=FFFFF     DecDCTvlc
    [ 884] e 0000000080094C50 st 1 sc 5 index=FFFFF     DecDCTin
    [ 885] e 0000000080094CD0 st 1 sc 5 index=FFFFF     DecDCTout
    [ 886] e 0000000080094CF0 st 1 sc 5 index=FFFFF     DecDCTinSync
    [ 887] e 0000000080094D10 st 1 sc 5 index=FFFFF     DecDCToutSync
    [ 888] e 0000000080095190 st 1 sc 5 index=FFFFF     MDEC_vlc
    [ 889] e 00000000800953E0 st 1 sc 5 index=FFFFF     MDEC_vlc2
    [ 890] e 00000000800957A0 st 1 sc 5 index=FFFFF     ivlc_dct_dc_size
    [ 891] e 0000000080095990 st 1 sc 5 index=FFFFF     CdInit
    [ 892] e 0000000080095A0C st 1 sc 5 index=FFFFF     CdInitFileSystem
    [ 893] e 0000000080095AF0 st 1 sc 5 index=FFFFF     CdReset
    [ 894] e 0000000080095B10 st 1 sc 5 index=FFFFF     CdSync
    [ 895] e 0000000080095B30 st 1 sc 5 index=FFFFF     CdReady
    [ 896] e 0000000080095B50 st 1 sc 5 index=FFFFF     CdReadSync
    [ 897] e 0000000080095B70 st 1 sc 5 index=FFFFF     CdSetDebug
    [ 898] e 0000000080095B84 st 1 sc 5 index=FFFFF     CdComstr
    [ 899] e 0000000080095BB8 st 1 sc 5 index=FFFFF     CdIntstr
    [ 900] e 0000000080095BEC st 1 sc 5 index=FFFFF     CdSyncCallback
    [ 901] e 0000000080095C00 st 1 sc 5 index=FFFFF     CdReadyCallback
    [ 902] e 0000000080095C14 st 1 sc 5 index=FFFFF     CdReadCallback
    [ 903] e 0000000080095D48 st 1 sc 5 index=FFFFF     CdControl
    [ 904] e 0000000080095D6C st 1 sc 5 index=FFFFF     CdControlF
    [ 905] e 0000000080095D94 st 1 sc 5 index=FFFFF     CdControlB
    [ 906] e 0000000080095DE0 st 1 sc 5 index=FFFFF     CdGetSector
    [ 907] e 0000000080095E00 st 1 sc 5 index=FFFFF     CdRead
    [ 908] e 0000000080095EE8 st 1 sc 5 index=FFFFF     CdMix
    [ 909] e 0000000080095F08 st 1 sc 5 index=FFFFF     CdRead2
    [ 910] e 0000000080095F70 st 1 sc 5 index=FFFFF     CdIntToPos
    [ 911] e 00000000800960AC st 1 sc 5 index=FFFFF     CdPosToInt
    [ 912] e 0000000080096160 st 1 sc 5 index=FFFFF     StSetRing
    [ 913] e 00000000800961B4 st 1 sc 5 index=FFFFF     StClearRing
    [ 914] e 0000000080096200 st 1 sc 5 index=FFFFF     StUnSetRing
    [ 915] e 0000000080096238 st 1 sc 5 index=FFFFF     data_ready_callback
    [ 916] e 000000008009629C st 1 sc 5 index=FFFFF     StSetStream
    [ 917] e 0000000080096300 st 1 sc 5 index=FFFFF     StSetEmulate
    [ 918] e 0000000080096370 st 1 sc 5 index=FFFFF     StFreeRing
    [ 919] e 0000000080096474 st 1 sc 5 index=FFFFF     StGetNext
    [ 920] e 0000000080096524 st 1 sc 5 index=FFFFF     StSetMask
    [ 921] e 0000000080096540 st 1 sc 5 index=FFFFF     StCdInterrupt
    [ 922] e 00000000800970B8 st 1 sc 5 index=FFFFF     StSetChannel
    [ 923] e 00000000800970E0 st 1 sc 5 index=FFFFF     CdSearchFile
    [ 924] e 00000000800980C0 st 1 sc 5 index=FFFFF     CD_sync
    [ 925] e 0000000080098170 st 1 sc 5 index=FFFFF     CD_ready
    [ 926] e 00000000800981FC st 1 sc 5 index=FFFFF     CD_cw
    [ 927] e 000000008009846C st 1 sc 5 index=FFFFF     CD_vol
    [ 928] e 0000000080098518 st 1 sc 5 index=FFFFF     CD_init
    [ 929] e 0000000080098618 st 1 sc 5 index=FFFFF     CD_readm
    [ 930] e 0000000080098730 st 1 sc 5 index=FFFFF     CD_readsync
    [ 931] e 0000000080098928 st 1 sc 5 index=FFFFF     CD_read
    [ 932] e 0000000080098A50 st 1 sc 5 index=FFFFF     CD_set_test_parmnum
    [ 933] e 0000000080098A68 st 1 sc 5 index=FFFFF     _96_vec
    [ 934] e 0000000080098BB0 st 1 sc 5 index=FFFFF     SsSetMVol
    [ 935] e 0000000080098D24 st 1 sc 5 index=FFFFF     SsInit
    [ 936] e 0000000080098D44 st 1 sc 5 index=FFFFF     SsInitHot
    [ 937] e 0000000080098D64 st 1 sc 5 index=FFFFF     SsSetTableSize
    [ 938] e 0000000080098F04 st 1 sc 5 index=FFFFF     SsSetTickMode
    [ 939] e 0000000080099274 st 1 sc 5 index=FFFFF     SsStart
    [ 940] e 0000000080099294 st 1 sc 5 index=FFFFF     SsStart2
    [ 941] e 00000000800992B4 st 1 sc 5 index=FFFFF     SsEnd
    [ 942] e 000000008009931C st 1 sc 5 index=FFFFF     SsQuit
    [ 943] e 0000000080099340 st 1 sc 5 index=FFFFF     SsSetSerialAttr
    [ 944] e 0000000080099410 st 1 sc 5 index=FFFFF     SsSetSerialVol
    [ 945] e 00000000800995E0 st 1 sc 5 index=FFFFF     SsVabTransCompleted
    [ 946] e 0000000080099610 st 1 sc 5 index=FFFFF     SsVabOpenHead
    [ 947] e 0000000080099640 st 1 sc 5 index=FFFFF     SsVabOpenHeadSticky
    [ 948] e 0000000080099670 st 1 sc 5 index=FFFFF     SsVabFakeHead
    [ 949] e 0000000080099AB0 st 1 sc 5 index=FFFFF     SsVabTransBody
    [ 950] e 0000000080099B80 st 1 sc 5 index=FFFFF     SsSeqSetVol
    [ 951] e 0000000080099BB8 st 1 sc 5 index=FFFFF     SsSepSetVol
    [ 952] e 0000000080099BF4 st 1 sc 5 index=FFFFF     Snd_SetVol
    [ 953] e 0000000080099C70 st 1 sc 5 index=FFFFF     SsUtReverbOn
    [ 954] e 0000000080099C90 st 1 sc 5 index=FFFFF     SsUtReverbOff
    [ 955] e 0000000080099CB0 st 1 sc 5 index=FFFFF     SsUtSetReverbType
    [ 956] e 0000000080099D0C st 1 sc 5 index=FFFFF     SsUtGetReverbType
    [ 957] e 0000000080099D1C st 1 sc 5 index=FFFFF     SsUtSetReverbDepth
    [ 958] e 0000000080099DE0 st 1 sc 5 index=FFFFF     SsUtSetReverbFeedback
    [ 959] e 0000000080099E20 st 1 sc 5 index=FFFFF     SsUtSetReverbDelay
    [ 960] e 0000000080099E60 st 1 sc 5 index=FFFFF     SsSeqOpen
    [ 961] e 0000000080099F0C st 1 sc 5 index=FFFFF     SsSepOpen
    [ 962] e 000000008009A030 st 1 sc 5 index=FFFFF     SsUtGetVabHdr
    [ 963] e 000000008009A110 st 1 sc 5 index=FFFFF     SsSeqPlay
    [ 964] e 000000008009A148 st 1 sc 5 index=FFFFF     SsSepPlay
    [ 965] e 000000008009A184 st 1 sc 5 index=FFFFF     SsPlayBack
    [ 966] e 000000008009A240 st 1 sc 5 index=FFFFF     Snd_SetPlayMode
    [ 967] e 000000008009A340 st 1 sc 5 index=FFFFF     SsSeqStop
    [ 968] e 000000008009A3D4 st 1 sc 5 index=FFFFF     SsSepStop
    [ 969] e 000000008009A490 st 1 sc 5 index=FFFFF     Snd_stop
    [ 970] e 000000008009A5A0 st 1 sc 5 index=FFFFF     SsSeqClose
    [ 971] e 000000008009A704 st 1 sc 5 index=FFFFF     SsSepClose
    [ 972] e 000000008009A870 st 1 sc 5 index=FFFFF     SsSeqPause
    [ 973] e 000000008009A900 st 1 sc 5 index=FFFFF     SsSepPause
    [ 974] e 000000008009A9C0 st 1 sc 5 index=FFFFF     SsSeqReplay
    [ 975] e 000000008009AA38 st 1 sc 5 index=FFFFF     SsSepReplay
    [ 976] e 000000008009AAE0 st 1 sc 5 index=FFFFF     SsVoKeyOff
    [ 977] e 000000008009AB20 st 1 sc 5 index=FFFFF     SsVoKeyOn
    [ 978] e 000000008009BDDC st 1 sc 5 index=FFFFF     SsUtVibrateOn
    [ 979] e 000000008009BE10 st 1 sc 5 index=FFFFF     SsUtVibrateOff
    [ 980] e 000000008009BE34 st 1 sc 5 index=FFFFF     SpuVmInit
    [ 981] e 000000008009C124 st 1 sc 5 index=FFFFF     SpuVmNoiseOnWithAdsr
    [ 982] e 000000008009C1B4 st 1 sc 5 index=FFFFF     SpuVmNoiseOff
    [ 983] e 000000008009C244 st 1 sc 5 index=FFFFF     SpuVmNoiseOn
    [ 984] e 000000008009C270 st 1 sc 5 index=FFFFF     SpuVmPitchBend
    [ 985] e 000000008009C530 st 1 sc 5 index=FFFFF     SpuVmFlush
    [ 986] e 000000008009C818 st 1 sc 5 index=FFFFF     SpuVmKeyOn
    [ 987] e 000000008009CC08 st 1 sc 5 index=FFFFF     SpuVmKeyOff
    [ 988] e 000000008009CD48 st 1 sc 5 index=FFFFF     SpuVmSeKeyOn
    [ 989] e 000000008009CE3C st 1 sc 5 index=FFFFF     SpuVmSeKeyOff
    [ 990] e 000000008009CE70 st 1 sc 5 index=FFFFF     KeyOnCheck
    [ 991] e 000000008009CE78 st 1 sc 5 index=FFFFF     SpuVmSetSeqVol
    [ 992] e 000000008009D008 st 1 sc 5 index=FFFFF     SpuVmGetSeqVol
    [ 993] e 000000008009D06C st 1 sc 5 index=FFFFF     SpuVmGetSeqLVol
    [ 994] e 000000008009D0A4 st 1 sc 5 index=FFFFF     SpuVmGetSeqRVol
    [ 995] e 000000008009D0DC st 1 sc 5 index=FFFFF     SpuVmGetSeqPan
    [ 996] e 000000008009D124 st 1 sc 5 index=FFFFF     SpuVmSeqKeyOff
    [ 997] e 000000008009D1B4 st 1 sc 5 index=FFFFF     SpuVmSetProgVol
    [ 998] e 000000008009D228 st 1 sc 5 index=FFFFF     SpuVmGetProgVol
    [ 999] e 000000008009D27C st 1 sc 5 index=FFFFF     SpuVmSetProgPan
    [1000] e 000000008009D2F0 st 1 sc 5 index=FFFFF     SpuVmGetProgPan
    [1001] e 000000008009D344 st 1 sc 5 index=FFFFF     SsUtKeyOn
    [1002] e 000000008009D730 st 1 sc 5 index=FFFFF     SsUtKeyOff
    [1003] e 000000008009D840 st 1 sc 5 index=FFFFF     SsUtKeyOnV
    [1004] e 000000008009DBE8 st 1 sc 5 index=FFFFF     SsUtKeyOffV
    [1005] e 000000008009DC58 st 1 sc 5 index=FFFFF     SsUtPitchBend
    [1006] e 000000008009DC94 st 1 sc 5 index=FFFFF     SsUtChangePitch
    [1007] e 000000008009DDCC st 1 sc 5 index=FFFFF     SsUtChangeADSR
    [1008] e 000000008009DE94 st 1 sc 5 index=FFFFF     SsUtGetDetVVol
    [1009] e 000000008009DEEC st 1 sc 5 index=FFFFF     SsUtSetDetVVol
    [1010] e 000000008009DF50 st 1 sc 5 index=FFFFF     SsUtGetVVol
    [1011] e 000000008009E008 st 1 sc 5 index=FFFFF     SsUtSetVVol
    [1012] e 000000008009E090 st 1 sc 5 index=FFFFF     SsUtAutoVol
    [1013] e 000000008009E0AC st 1 sc 5 index=FFFFF     SsUtAutoPan
    [1014] e 000000008009E0C8 st 1 sc 5 index=FFFFF     SsUtAllKeyOff
    [1015] e 000000008009E210 st 1 sc 5 index=FFFFF     SsSetReservedVoice
    [1016] e 000000008009E250 st 1 sc 5 index=FFFFF     SsSetAutoKeyOffMode
    [1017] e 000000008009E260 st 1 sc 5 index=FFFFF     SsSetMono
    [1018] e 000000008009E270 st 1 sc 5 index=FFFFF     SsSetStereo
    [1019] e 000000008009E280 st 1 sc 5 index=FFFFF     SsVabClose
    [1020] e 000000008009E2FC st 1 sc 5 index=FFFFF     SsVabOpen
    [1021] e 000000008009E360 st 1 sc 5 index=FFFFF     SsSeqCalledTbyT
    [1022] e 000000008009E5A0 st 1 sc 5 index=FFFFF     InitSoundSeq
    [1023] e 000000008009E8C0 st 1 sc 5 index=FFFFF     InitSoundSep
    [1024] e 000000008009EC40 st 1 sc 5 index=FFFFF     SpuVmVSetUp
    [1025] e 000000008009ED10 st 1 sc 5 index=FFFFF     Snd_play
    [1026] e 000000008009ED40 st 1 sc 5 index=FFFFF     Snd_crescendo
    [1027] e 000000008009F1A0 st 1 sc 5 index=FFFFF     Snd_decrescendo
    [1028] e 000000008009F600 st 1 sc 5 index=FFFFF     Snd_tempo
    [1029] e 000000008009F7D0 st 1 sc 5 index=FFFFF     Snd_pause
    [1030] e 000000008009F85C st 1 sc 5 index=FFFFF     Snd_nextpause
    [1031] e 000000008009F8C0 st 1 sc 5 index=FFFFF     Snd_replay
    [1032] e 000000008009F920 st 1 sc 5 index=FFFFF     SeqPlay
    [1033] e 000000008009FA24 st 1 sc 5 index=FFFFF     GetSeqData
    [1034] e 000000008009FCBC st 1 sc 5 index=FFFFF     NoteOn
    [1035] e 000000008009FDC0 st 1 sc 5 index=FFFFF     SetProgramChange
    [1036] e 000000008009FE2C st 1 sc 5 index=FFFFF     SetControlChange
    [1037] e 00000000800A010C st 1 sc 5 index=FFFFF     ContModulation
    [1038] e 00000000800A0228 st 1 sc 5 index=FFFFF     ContPortaTime
    [1039] e 00000000800A0344 st 1 sc 5 index=FFFFF     ContPortamento
    [1040] e 00000000800A04E8 st 1 sc 5 index=FFFFF     ContResetAll
    [1041] e 00000000800A059C st 1 sc 5 index=FFFFF     ContNrpn1
    [1042] e 00000000800A06C0 st 1 sc 5 index=FFFFF     ContNrpn2
    [1043] e 00000000800A07E8 st 1 sc 5 index=FFFFF     ContRpn1
    [1044] e 00000000800A0854 st 1 sc 5 index=FFFFF     ContRpn2
    [1045] e 00000000800A08C0 st 1 sc 5 index=FFFFF     ContDataEntry
    [1046] e 00000000800A0E88 st 1 sc 5 index=FFFFF     Snd_setVabAttr
    [1047] e 00000000800A11E0 st 1 sc 5 index=FFFFF     SetPitchBend
    [1048] e 00000000800A1280 st 1 sc 5 index=FFFFF     GetMetaEvent
    [1049] e 00000000800A15C0 st 1 sc 5 index=FFFFF     ReadDeltaValue
    [1050] e 00000000800A1670 st 1 sc 5 index=FFFFF     SpuVmDamperOff
    [1051] e 00000000800A1680 st 1 sc 5 index=FFFFF     SpuVmDamperOn
    [1052] e 00000000800A1690 st 1 sc 5 index=FFFFF     SsUtGetProgAtr
    [1053] e 00000000800A17A0 st 1 sc 5 index=FFFFF     SsUtGetVagAtr
    [1054] e 00000000800A19E0 st 1 sc 5 index=FFFFF     SsUtSetVagAtr
    [1055] e 00000000800A1BB0 st 1 sc 5 index=FFFFF     SsUtResolveADSR
    [1056] e 00000000800A1C0C st 1 sc 5 index=FFFFF     SsUtBuildADSR
    [1057] e 00000000800A1CA0 st 1 sc 5 index=FFFFF     Snd_nextseq
    [1058] e 00000000800A1DD0 st 1 sc 5 index=FFFFF     SpuClearReverbWorkArea
    [1059] e 00000000800A1F20 st 1 sc 5 index=FFFFF     SpuIsTransferCompleted
    [1060] e 00000000800A1FD0 st 1 sc 5 index=FFFFF     _spu_setInTransfer
    [1061] e 00000000800A1FF8 st 1 sc 5 index=FFFFF     _spu_getInTransfer
    [1062] e 00000000800A2010 st 1 sc 5 index=FFFFF     SpuSetTransferStartAddr
    [1063] e 00000000800A2060 st 1 sc 5 index=FFFFF     SpuRead
    [1064] e 00000000800A211C st 1 sc 5 index=FFFFF     _spu_init
    [1065] e 00000000800A2364 st 1 sc 5 index=FFFFF     _spu_close
    [1066] e 00000000800A238C st 1 sc 5 index=FFFFF     _spu_open
    [1067] e 00000000800A2400 st 1 sc 5 index=FFFFF     _spu_write
    [1068] e 00000000800A2648 st 1 sc 5 index=FFFFF     _spu_read
    [1069] e 00000000800A26FC st 1 sc 5 index=FFFFF     _spu_w
    [1070] e 00000000800A2824 st 1 sc 5 index=FFFFF     _spu_r
    [1071] e 00000000800A2928 st 1 sc 5 index=FFFFF     _spu_r_
    [1072] e 00000000800A29D8 st 1 sc 5 index=FFFFF     _spu_ioctl
    [1073] e 00000000800A3D20 st 1 sc 5 index=FFFFF     SysSpu_setRegister
    [1074] e 00000000800A3D3C st 1 sc 5 index=FFFFF     SysSpu_getRegister
    [1075] e 00000000800A3E3C st 1 sc 5 index=FFFFF     SpuInit
    [1076] e 00000000800A3E5C st 1 sc 5 index=FFFFF     SpuInitHot
    [1077] e 00000000800A3E7C st 1 sc 5 index=FFFFF     SpuStart
    [1078] e 00000000800A3EF4 st 1 sc 5 index=FFFFF     SpuQuit
    [1079] e 00000000800A424C st 1 sc 5 index=FFFFF     SpuInitMalloc
    [1080] e 00000000800A42BC st 1 sc 5 index=FFFFF     SpuMalloc
    [1081] e 00000000800A48D8 st 1 sc 5 index=FFFFF     SpuMallocWithStartAddr
    [1082] e 00000000800A4B7C st 1 sc 5 index=FFFFF     _SpuIsInAllocateArea
    [1083] e 00000000800A4BE8 st 1 sc 5 index=FFFFF     _SpuIsInAllocateArea_
    [1084] e 00000000800A4C10 st 1 sc 5 index=FFFFF     SpuFree
    [1085] e 00000000800A4C88 st 1 sc 5 index=FFFFF     _print
    [1086] e 00000000800A4D40 st 1 sc 5 index=FFFFF     SpuSetTransferMode
    [1087] e 00000000800A4DA0 st 1 sc 5 index=FFFFF     SpuWrite
    [1088] e 00000000800A4E00 st 1 sc 5 index=FFFFF     SpuSetReverb
    [1089] e 00000000800A4EE0 st 1 sc 5 index=FFFFF     SpuSetReverbModeParam
    [1090] e 00000000800A53C0 st 1 sc 5 index=FFFFF     GsInitGraph
    [1091] e 00000000800A5558 st 1 sc 5 index=FFFFF     GsInitGraph2
    [1092] e 00000000800A582C st 1 sc 5 index=FFFFF     GsSortClear
    [1093] e 00000000800A5920 st 1 sc 5 index=FFFFF     GsGetActiveBuff
    [1094] e 00000000800A5930 st 1 sc 5 index=FFFFF     GsSetDrawBuffOffset
    [1095] e 00000000800A59D0 st 1 sc 5 index=FFFFF     GsDefDispBuff
    [1096] e 00000000800A5A80 st 1 sc 5 index=FFFFF     GsInit3D
    [1097] e 00000000800A5AF0 st 1 sc 5 index=FFFFF     GsInitVcount
    [1098] e 00000000800A5B30 st 1 sc 5 index=FFFFF     GsSetWorkBase
    [1099] e 00000000800A5B40 st 1 sc 5 index=FFFFF     GsClearOt
    [1100] e 00000000800A5BA0 st 1 sc 5 index=FFFFF     GsGetVcount
    [1101] e 00000000800A5BD0 st 1 sc 5 index=FFFFF     GsSortSprite
    [1102] e 00000000800A6190 st 1 sc 5 index=FFFFF     GsSortFastSprite
    [1103] e 00000000800A6370 st 1 sc 5 index=FFFFF     GsSortBg
    [1104] e 00000000800A6C60 st 1 sc 5 index=FFFFF     GsSetRefView2
    [1105] e 00000000800A7220 st 1 sc 5 index=FFFFF     GsGetLws
    [1106] e 00000000800A74E0 st 1 sc 5 index=FFFFF     GsInitCoordinate2
    [1107] e 00000000800A755C st 1 sc 5 index=FFFFF     GsInitCoord2param
    [1108] e 00000000800A7588 st 1 sc 5 index=FFFFF     GsSetLsMatrix
    [1109] e 00000000800A75B4 st 1 sc 5 index=FFFFF     GsSetLightMatrix
    [1110] e 00000000800A764C st 1 sc 5 index=FFFFF     GsSetLightMatrix2
    [1111] e 00000000800A767C st 1 sc 5 index=FFFFF     GsMulCoord0
    [1112] e 00000000800A770C st 1 sc 5 index=FFFFF     GsMulCoord2
    [1113] e 00000000800A778C st 1 sc 5 index=FFFFF     GsMulCoord3
    [1114] e 00000000800A780C st 1 sc 5 index=FFFFF     print_matrix
    [1115] e 00000000800A787C st 1 sc 5 index=FFFFF     print_vector
    [1116] e 00000000800A78B0 st 1 sc 5 index=FFFFF     GsGetLs
    [1117] e 00000000800A7B60 st 1 sc 5 index=FFFFF     GsLinkObject4
    [1118] e 00000000800A7CA0 st 1 sc 5 index=FFFFF     GsSortObject4
    [1119] e 00000000800A9300 st 1 sc 5 index=FFFFF     GsGetWorkBase
    [1120] e 00000000800A9310 st 1 sc 5 index=FFFFF     GsClearVcount
    [1121] e 00000000800A9340 st 1 sc 5 index=FFFFF     GsSwapDispBuff
    [1122] e 00000000800A9400 st 1 sc 5 index=FFFFF     GsDrawOt
    [1123] e 00000000800A9430 st 1 sc 5 index=FFFFF     GsSetProjection
    [1124] e 00000000800A9450 st 1 sc 5 index=FFFFF     GsSetNearClip
    [1125] e 00000000800A9460 st 1 sc 5 index=FFFFF     GsSetFarClip
    [1126] e 00000000800A9470 st 1 sc 5 index=FFFFF     GsSetFlatLight
    [1127] e 00000000800A9B50 st 1 sc 5 index=FFFFF     GsSetAmbient
    [1128] e 00000000800A9B80 st 1 sc 5 index=FFFFF     GsSetLightMode
    [1129] e 00000000800A9C10 st 1 sc 5 index=FFFFF     GsMapModelingData
    [1130] e 00000000800A9CA0 st 1 sc 5 index=FFFFF     gte_init
    [1131] e 00000000800A9CE0 st 1 sc 5 index=FFFFF     GsSetDrawBuffClip
    [1132] e 00000000800A9D90 st 1 sc 5 index=FFFFF     GsLinkObject2
    [1133] e 00000000800A9DA8 st 1 sc 5 index=FFFFF     GsSortObject2
    [1134] e 00000000800AA084 st 1 sc 5 index=FFFFF     GsLinkObject
    [1135] e 00000000800AA154 st 1 sc 5 index=FFFFF     GsSortObject
    [1136] e 00000000800AA464 st 1 sc 5 index=FFFFF     Gslight_normal
    [1137] e 00000000800AA620 st 1 sc 5 index=FFFFF     Gslight_normal_fog
    [1138] e 00000000800AA7E8 st 1 sc 5 index=FFFFF     Gslight_mate
    [1139] e 00000000800AA9C0 st 1 sc 5 index=FFFFF     Gslight_mate_fog
    [1140] e 00000000800AAB98 st 1 sc 5 index=FFFFF     gte_flat_mat3
    [1141] e 00000000800AABA0 st 1 sc 5 index=FFFFF     gte_texture_flat_mat3
    [1142] e 00000000800AABA8 st 1 sc 5 index=FFFFF     gte_gouraud_mat3
    [1143] e 00000000800AABB0 st 1 sc 5 index=FFFFF     gte_texture_gouraud_mat3
    [1144] e 00000000800AABB8 st 1 sc 5 index=FFFFF     gte_flat_mat_fog3
    [1145] e 00000000800AABC0 st 1 sc 5 index=FFFFF     gte_texture_flat_mat_fog3
    [1146] e 00000000800AABC8 st 1 sc 5 index=FFFFF     gte_gouraud_mat_fog3
    [1147] e 00000000800AABD0 st 1 sc 5 index=FFFFF     gte_texture_gouraud_mat_fog3
    [1148] e 00000000800AABE0 st 1 sc 5 index=FFFFF     _make_packet
    [1149] e 00000000800AAC80 st 1 sc 5 index=FFFFF     gte_rotate_z_matrix
    [1150] e 00000000800AAD50 st 1 sc 5 index=FFFFF     gte_scale_matrix
    [1151] e 00000000800AAEC0 st 1 sc 5 index=FFFFF     _mk_spr_packet
    [1152] e 00000000800AAF00 st 1 sc 5 index=FFFFF     _mk_xpndsp
    [1153] e 00000000800AB248 st 1 sc 5 index=FFFFF     _mk_normsp
    [1154] e 00000000800AB510 st 1 sc 5 index=FFFFF     Gssub_make_matrix
    [1155] e 00000000800AB5E0 st 1 sc 5 index=FFFFF     GsGetLw
    [1156] e 00000000800AB820 st 1 sc 5 index=FFFFF     GsInitCoordinate
    [1157] e 00000000800AB868 st 1 sc 5 index=FFFFF     GsSetRefView
    [1158] e 00000000800ABC88 st 1 sc 5 index=FFFFF     GsGetObjLw
    [1159] e 00000000800AC2E4 st 1 sc 5 index=FFFFF     GsGetObjLight
    [1160] e 00000000800AC37C st 1 sc 5 index=FFFFF     GsGetObjMatrix
    [1161] e 00000000800AC4F0 st 1 sc 5 index=FFFFF     gte_apply_matrixl
    [1162] e 00000000800AC640 st 1 sc 5 index=FFFFF     gte_apply_matrixll
    [1163] e 00000000800AC7C0 st 1 sc 5 index=FFFFF     gte_rotate_y_matrix
    [1164] e 00000000800AC890 st 1 sc 5 index=FFFFF     gte_rotate_x_matrix
    [1165] e 00000000800AC988 st 1 sc 5 index=FFFFF     ResetGraph
    [1166] e 00000000800ACB48 st 1 sc 5 index=FFFFF     SetGraphReverse
    [1167] e 00000000800ACC10 st 1 sc 5 index=FFFFF     SetGraphDebug
    [1168] e 00000000800ACC70 st 1 sc 5 index=FFFFF     GetGraphType
    [1169] e 00000000800ACC80 st 1 sc 5 index=FFFFF     GetGraphDebug
    [1170] e 00000000800ACC90 st 1 sc 5 index=FFFFF     DrawSyncCallback
    [1171] e 00000000800ACCA4 st 1 sc 5 index=FFFFF     SetDispMask
    [1172] e 00000000800ACCE8 st 1 sc 5 index=FFFFF     DrawSync
    [1173] e 00000000800ACD18 st 1 sc 5 index=FFFFF     ClearImage
    [1174] e 00000000800ACD6C st 1 sc 5 index=FFFFF     LoadImage
    [1175] e 00000000800ACDA8 st 1 sc 5 index=FFFFF     StoreImage
    [1176] e 00000000800ACDE4 st 1 sc 5 index=FFFFF     MoveImage
    [1177] e 00000000800ACE54 st 1 sc 5 index=FFFFF     ClearOTag
    [1178] e 00000000800ACEA8 st 1 sc 5 index=FFFFF     ClearOTagR
    [1179] e 00000000800ACEE0 st 1 sc 5 index=FFFFF     DrawPrim
    [1180] e 00000000800ACF64 st 1 sc 5 index=FFFFF     DrawOTag
    [1181] e 00000000800ACFBC st 1 sc 5 index=FFFFF     PutDrawEnv
    [1182] e 00000000800AD080 st 1 sc 5 index=FFFFF     GetDrawEnv
    [1183] e 00000000800AD0E0 st 1 sc 5 index=FFFFF     PutDispEnv
    [1184] e 00000000800AD46C st 1 sc 5 index=FFFFF     GetDispEnv
    [1185] e 00000000800AD4CC st 1 sc 5 index=FFFFF     SetTexWindow
    [1186] e 00000000800AD504 st 1 sc 5 index=FFFFF     SetDrawArea
    [1187] e 00000000800AD574 st 1 sc 5 index=FFFFF     SetDrawOffset
    [1188] e 00000000800AD5B4 st 1 sc 5 index=FFFFF     SetPriority
    [1189] e 00000000800AD5E0 st 1 sc 5 index=FFFFF     SetDrawMode
    [1190] e 00000000800AD634 st 1 sc 5 index=FFFFF     SetDrawEnv
    [1191] e 00000000800AEEF4 st 1 sc 5 index=FFFFF     GetTPage
    [1192] e 00000000800AEF88 st 1 sc 5 index=FFFFF     GetClut
    [1193] e 00000000800AEFA0 st 1 sc 5 index=FFFFF     DumpTPage
    [1194] e 00000000800AF030 st 1 sc 5 index=FFFFF     DumpClut
    [1195] e 00000000800AF070 st 1 sc 5 index=FFFFF     NextPrim
    [1196] e 00000000800AF08C st 1 sc 5 index=FFFFF     IsEndPrim
    [1197] e 00000000800AF0A8 st 1 sc 5 index=FFFFF     AddPrim
    [1198] e 00000000800AF0E4 st 1 sc 5 index=FFFFF     AddPrims
    [1199] e 00000000800AF120 st 1 sc 5 index=FFFFF     CatPrim
    [1200] e 00000000800AF144 st 1 sc 5 index=FFFFF     TermPrim
    [1201] e 00000000800AF15C st 1 sc 5 index=FFFFF     SetSemiTrans
    [1202] e 00000000800AF188 st 1 sc 5 index=FFFFF     SetShadeTex
    [1203] e 00000000800AF1B4 st 1 sc 5 index=FFFFF     SetPolyF3
    [1204] e 00000000800AF1C8 st 1 sc 5 index=FFFFF     SetPolyFT3
    [1205] e 00000000800AF1DC st 1 sc 5 index=FFFFF     SetPolyG3
    [1206] e 00000000800AF1F0 st 1 sc 5 index=FFFFF     SetPolyGT3
    [1207] e 00000000800AF204 st 1 sc 5 index=FFFFF     SetPolyF4
    [1208] e 00000000800AF218 st 1 sc 5 index=FFFFF     SetPolyFT4
    [1209] e 00000000800AF22C st 1 sc 5 index=FFFFF     SetPolyG4
    [1210] e 00000000800AF240 st 1 sc 5 index=FFFFF     SetPolyGT4
    [1211] e 00000000800AF254 st 1 sc 5 index=FFFFF     SetSprt8
    [1212] e 00000000800AF268 st 1 sc 5 index=FFFFF     SetSprt16
    [1213] e 00000000800AF27C st 1 sc 5 index=FFFFF     SetSprt
    [1214] e 00000000800AF290 st 1 sc 5 index=FFFFF     SetTile1
    [1215] e 00000000800AF2A4 st 1 sc 5 index=FFFFF     SetTile8
    [1216] e 00000000800AF2B8 st 1 sc 5 index=FFFFF     SetTile16
    [1217] e 00000000800AF2CC st 1 sc 5 index=FFFFF     SetTile
    [1218] e 00000000800AF2E0 st 1 sc 5 index=FFFFF     SetBlockFill
    [1219] e 00000000800AF2F4 st 1 sc 5 index=FFFFF     SetLineF2
    [1220] e 00000000800AF308 st 1 sc 5 index=FFFFF     SetLineG2
    [1221] e 00000000800AF31C st 1 sc 5 index=FFFFF     SetLineF3
    [1222] e 00000000800AF33C st 1 sc 5 index=FFFFF     SetLineG3
    [1223] e 00000000800AF35C st 1 sc 5 index=FFFFF     SetLineF4
    [1224] e 00000000800AF37C st 1 sc 5 index=FFFFF     SetLineG4
    [1225] e 00000000800AF39C st 1 sc 5 index=FFFFF     MargePrim
    [1226] e 00000000800AF3D0 st 1 sc 5 index=FFFFF     DumpDrawEnv
    [1227] e 00000000800AF500 st 1 sc 5 index=FFFFF     DumpDispEnv
    [1228] e 00000000800AF5B0 st 1 sc 5 index=FFFFF     LoadTPage
    [1229] e 00000000800AF698 st 1 sc 5 index=FFFFF     LoadClut
    [1230] e 00000000800AF6FC st 1 sc 5 index=FFFFF     SetDefDrawEnv
    [1231] e 00000000800AF788 st 1 sc 5 index=FFFFF     SetDefDispEnv
    [1232] e 00000000800AF88C st 1 sc 5 index=FFFFF     DrawOTagIO
    [1233] e 00000000800AF934 st 1 sc 5 index=FFFFF     DumpOTag
    [1234] e 00000000800AFA7C st 1 sc 5 index=FFFFF     CheckPrim
    [1235] e 00000000800AFB10 st 1 sc 5 index=FFFFF     InitGeom
    [1236] e 00000000800AFB78 st 1 sc 5 index=FFFFF     LoadAverage12
    [1237] e 00000000800AFBC8 st 1 sc 5 index=FFFFF     LoadAverage0
    [1238] e 00000000800AFC18 st 1 sc 5 index=FFFFF     LoadAverageShort12
    [1239] e 00000000800AFCA0 st 1 sc 5 index=FFFFF     LoadAverageShort0
    [1240] e 00000000800AFD28 st 1 sc 5 index=FFFFF     LoadAverageByte
    [1241] e 00000000800AFD84 st 1 sc 5 index=FFFFF     LoadAverageCol
    [1242] e 00000000800AFDF8 st 1 sc 5 index=FFFFF     VectorNormal
    [1243] e 00000000800AFEC0 st 1 sc 5 index=FFFFF     VectorNormalS
    [1244] e 00000000800AFF88 st 1 sc 5 index=FFFFF     SquareRoot0
    [1245] e 00000000800B000C st 1 sc 5 index=FFFFF     SquareRoot12
    [1246] e 00000000800B00A0 st 1 sc 5 index=FFFFF     InvSquareRoot
    [1247] e 00000000800B012C st 1 sc 5 index=FFFFF     gteMIMefunc
    [1248] e 00000000800B01AC st 1 sc 5 index=FFFFF     InterpolShort
    [1249] e 00000000800B0224 st 1 sc 5 index=FFFFF     InterpolByte
    [1250] e 00000000800B0270 st 1 sc 5 index=FFFFF     rsin
    [1251] e 00000000800B02C0 st 1 sc 5 index=FFFFF     sin_1
    [1252] e 00000000800B036C st 1 sc 5 index=FFFFF     rcos
    [1253] e 00000000800B043C st 1 sc 5 index=FFFFF     SetFogFar
    [1254] e 00000000800B0498 st 1 sc 5 index=FFFFF     SetFogNear
    [1255] e 00000000800B04FC st 1 sc 5 index=FFFFF     EigenMatrix
    [1256] e 00000000800B08CC st 1 sc 5 index=FFFFF     IsIdMatrix
    [1257] e 00000000800B09A0 st 1 sc 5 index=FFFFF     TransposeMatrix
    [1258] e 00000000800B09F0 st 1 sc 5 index=FFFFF     RotMatrix
    [1259] e 00000000800B0C7C st 1 sc 5 index=FFFFF     RotMatrixYXZ
    [1260] e 00000000800B0F08 st 1 sc 5 index=FFFFF     RotMatrixZYX
    [1261] e 00000000800B1194 st 1 sc 5 index=FFFFF     RotMatrixX
    [1262] e 00000000800B132C st 1 sc 5 index=FFFFF     RotMatrixY
    [1263] e 00000000800B14C4 st 1 sc 5 index=FFFFF     RotMatrixZ
    [1264] e 00000000800B16D0 st 1 sc 5 index=FFFFF     CompMatrix
    [1265] e 00000000800B1830 st 1 sc 5 index=FFFFF     MulMatrix0
    [1266] e 00000000800B193C st 1 sc 5 index=FFFFF     MulRotMatrix0
    [1267] e 00000000800B1A20 st 1 sc 5 index=FFFFF     MulMatrix
    [1268] e 00000000800B1B2C st 1 sc 5 index=FFFFF     MulMatrix2
    [1269] e 00000000800B1C38 st 1 sc 5 index=FFFFF     MulRotMatrix
    [1270] e 00000000800B1D20 st 1 sc 5 index=FFFFF     SetMulMatrix
    [1271] e 00000000800B1E30 st 1 sc 5 index=FFFFF     ApplyMatrix
    [1272] e 00000000800B1E80 st 1 sc 5 index=FFFFF     ApplyMatrixSV
    [1273] e 00000000800B1EDC st 1 sc 5 index=FFFFF     ApplyMatrixLV
    [1274] e 00000000800B203C st 1 sc 5 index=FFFFF     ApplyRotMatrix
    [1275] e 00000000800B206C st 1 sc 5 index=FFFFF     TransMatrix
    [1276] e 00000000800B2090 st 1 sc 5 index=FFFFF     ScaleMatrix
    [1277] e 00000000800B21B4 st 1 sc 5 index=FFFFF     ScaleMatrixL
    [1278] e 00000000800B22D8 st 1 sc 5 index=FFFFF     SetRotMatrix
    [1279] e 00000000800B2308 st 1 sc 5 index=FFFFF     SetLightMatrix
    [1280] e 00000000800B2338 st 1 sc 5 index=FFFFF     SetColorMatrix
    [1281] e 00000000800B2368 st 1 sc 5 index=FFFFF     SetTransMatrix
    [1282] e 00000000800B2388 st 1 sc 5 index=FFFFF     PushMatrix
    [1283] e 00000000800B2428 st 1 sc 5 index=FFFFF     PopMatrix
    [1284] e 00000000800B24C8 st 1 sc 5 index=FFFFF     ReadRotMatrix
    [1285] e 00000000800B2510 st 1 sc 5 index=FFFFF     ReadLightMatrix
    [1286] e 00000000800B2558 st 1 sc 5 index=FFFFF     ReadColorMatrix
    [1287] e 00000000800B25A0 st 1 sc 5 index=FFFFF     SetVertex0
    [1288] e 00000000800B25B0 st 1 sc 5 index=FFFFF     SetVertex1
    [1289] e 00000000800B25C0 st 1 sc 5 index=FFFFF     SetVertex2
    [1290] e 00000000800B25D0 st 1 sc 5 index=FFFFF     SetVertexTri
    [1291] e 00000000800B25F0 st 1 sc 5 index=FFFFF     SetRGBcd
    [1292] e 00000000800B25FC st 1 sc 5 index=FFFFF     SetRGBfifo
    [1293] e 00000000800B2610 st 1 sc 5 index=FFFFF     SetIR123
    [1294] e 00000000800B2624 st 1 sc 5 index=FFFFF     SetIR0
    [1295] e 00000000800B2630 st 1 sc 5 index=FFFFF     SetBackColor
    [1296] e 00000000800B2650 st 1 sc 5 index=FFFFF     SetFarColor
    [1297] e 00000000800B2670 st 1 sc 5 index=FFFFF     SetSZfifo3
    [1298] e 00000000800B2684 st 1 sc 5 index=FFFFF     SetSZfifo4
    [1299] e 00000000800B269C st 1 sc 5 index=FFFFF     SetSXSYfifo
    [1300] e 00000000800B26B0 st 1 sc 5 index=FFFFF     SetRii
    [1301] e 00000000800B26C4 st 1 sc 5 index=FFFFF     SetMAC123
    [1302] e 00000000800B26D8 st 1 sc 5 index=FFFFF     SetData32
    [1303] e 00000000800B26E4 st 1 sc 5 index=FFFFF     SetGeomOffset
    [1304] e 00000000800B26FC st 1 sc 5 index=FFFFF     SetGeomScreen
    [1305] e 00000000800B2708 st 1 sc 5 index=FFFFF     SetDQA
    [1306] e 00000000800B2714 st 1 sc 5 index=FFFFF     SetDQB
    [1307] e 00000000800B2720 st 1 sc 5 index=FFFFF     ReadOTZ
    [1308] e 00000000800B272C st 1 sc 5 index=FFFFF     ReadIR0
    [1309] e 00000000800B2738 st 1 sc 5 index=FFFFF     ReadIR123
    [1310] e 00000000800B274C st 1 sc 5 index=FFFFF     ReadSZ2
    [1311] e 00000000800B2758 st 1 sc 5 index=FFFFF     ReadSZfifo3
    [1312] e 00000000800B276C st 1 sc 5 index=FFFFF     ReadSZfifo4
    [1313] e 00000000800B2784 st 1 sc 5 index=FFFFF     ReadSXSYfifo
    [1314] e 00000000800B2798 st 1 sc 5 index=FFFFF     ReadRGBfifo
    [1315] e 00000000800B27AC st 1 sc 5 index=FFFFF     ReadMac0
    [1316] e 00000000800B27B8 st 1 sc 5 index=FFFFF     ReadMAC123
    [1317] e 00000000800B27CC st 1 sc 5 index=FFFFF     ReadORGB
    [1318] e 00000000800B27FC st 1 sc 5 index=FFFFF     ReadLZC
    [1319] e 00000000800B2808 st 1 sc 5 index=FFFFF     ReadFLAG
    [1320] e 00000000800B2814 st 1 sc 5 index=FFFFF     ReadGeomOffset
    [1321] e 00000000800B2834 st 1 sc 5 index=FFFFF     ReadGeomScreen
    [1322] e 00000000800B2840 st 1 sc 5 index=FFFFF     RotTransPersN
    [1323] e 00000000800B2894 st 1 sc 5 index=FFFFF     RotTransPers3N
    [1324] e 00000000800B2910 st 1 sc 5 index=FFFFF     RotTransPers4
    [1325] e 00000000800B2988 st 1 sc 5 index=FFFFF     RotAverage3
    [1326] e 00000000800B29E0 st 1 sc 5 index=FFFFF     RotAverage4
    [1327] e 00000000800B2A5C st 1 sc 5 index=FFFFF     RotNclip
    [1328] e 00000000800B2A88 st 1 sc 5 index=FFFFF     RotNclip3
    [1329] e 00000000800B2B0C st 1 sc 5 index=FFFFF     RotNclip4
    [1330] e 00000000800B2BBC st 1 sc 5 index=FFFFF     RotAverageNclip3
    [1331] e 00000000800B2C44 st 1 sc 5 index=FFFFF     RotAverageNclip3_1
    [1332] e 00000000800B2CE4 st 1 sc 5 index=FFFFF     RotAverageNclip4
    [1333] e 00000000800B2D94 st 1 sc 5 index=FFFFF     RotColorDpq
    [1334] e 00000000800B2DE0 st 1 sc 5 index=FFFFF     RotColorDpq3
    [1335] e 00000000800B2E78 st 1 sc 5 index=FFFFF     RotAverageNclipColorDpq3
    [1336] e 00000000800B2F40 st 1 sc 5 index=FFFFF     RotAverageNclipColorCol3
    [1337] e 00000000800B3008 st 1 sc 5 index=FFFFF     RotColorMatDpq
    [1338] e 00000000800B3070 st 1 sc 5 index=FFFFF     ColorMatDpq
    [1339] e 00000000800B30B0 st 1 sc 5 index=FFFFF     ColorMatCol
    [1340] e 00000000800B30F0 st 1 sc 5 index=FFFFF     GsTMDfastNF3
    [1341] e 00000000800B322C st 1 sc 5 index=FFFFF     GsTMDfastF3NL
    [1342] e 00000000800B336C st 1 sc 5 index=FFFFF     GsTMDfastF3L
    [1343] e 00000000800B34B4 st 1 sc 5 index=FFFFF     GsTMDfastF3LFG
    [1344] e 00000000800B3600 st 1 sc 5 index=FFFFF     GsTMDfastNF4
    [1345] e 00000000800B3768 st 1 sc 5 index=FFFFF     GsTMDfastF4NL
    [1346] e 00000000800B38D4 st 1 sc 5 index=FFFFF     GsTMDfastF4L
    [1347] e 00000000800B3A4C st 1 sc 5 index=FFFFF     GsTMDfastF4LFG
    [1348] e 00000000800B3BD0 st 1 sc 5 index=FFFFF     GsTMDfastNG3
    [1349] e 00000000800B3D18 st 1 sc 5 index=FFFFF     GsTMDfastG3NL
    [1350] e 00000000800B3E58 st 1 sc 5 index=FFFFF     GsTMDfastG3L
    [1351] e 00000000800B3FE8 st 1 sc 5 index=FFFFF     GsTMDfastG3LFG
    [1352] e 00000000800B4180 st 1 sc 5 index=FFFFF     GsTMDfastTNF3
    [1353] e 00000000800B42EC st 1 sc 5 index=FFFFF     GsTMDfastTF3NL
    [1354] e 00000000800B4450 st 1 sc 5 index=FFFFF     GsTMDfastTF3L
    [1355] e 00000000800B45C0 st 1 sc 5 index=FFFFF     GsTMDfastTF3LFG
    [1356] e 00000000800B4730 st 1 sc 5 index=FFFFF     GsTMDfastTNG3
    [1357] e 00000000800B48A8 st 1 sc 5 index=FFFFF     GsTMDfastTG3NL
    [1358] e 00000000800B4A04 st 1 sc 5 index=FFFFF     GsTMDfastTG3L
    [1359] e 00000000800B4BB8 st 1 sc 5 index=FFFFF     GsTMDfastTG3LFG
    [1360] e 00000000800B4D70 st 1 sc 5 index=FFFFF     GsTMDfastNG4
    [1361] e 00000000800B4EF0 st 1 sc 5 index=FFFFF     GsTMDfastG4NL
    [1362] e 00000000800B5064 st 1 sc 5 index=FFFFF     GsTMDfastG4L
    [1363] e 00000000800B5244 st 1 sc 5 index=FFFFF     GsTMDfastG4LFG
    [1364] e 00000000800B5430 st 1 sc 5 index=FFFFF     GsTMDfastTNF4
    [1365] e 00000000800B55D0 st 1 sc 5 index=FFFFF     GsTMDfastTF4NL
    [1366] e 00000000800B576C st 1 sc 5 index=FFFFF     GsTMDfastTF4L
    [1367] e 00000000800B5918 st 1 sc 5 index=FFFFF     GsTMDfastTF4LFG
    [1368] e 00000000800B5AD0 st 1 sc 5 index=FFFFF     GsTMDfastTNG4
    [1369] e 00000000800B5C8C st 1 sc 5 index=FFFFF     GsTMDfastTG4NL
    [1370] e 00000000800B5E24 st 1 sc 5 index=FFFFF     GsTMDfastTG4L
    [1371] e 00000000800B6030 st 1 sc 5 index=FFFFF     GsTMDfastTG4LFG
    [1372] e 00000000800B6240 st 1 sc 5 index=FFFFF     GsTMDdivF3L
    [1373] e 00000000800B646C st 1 sc 5 index=FFFFF     GsTMDdivF3LFG
    [1374] e 00000000800B6698 st 1 sc 5 index=FFFFF     GsTMDdivF3NL
    [1375] e 00000000800B6880 st 1 sc 5 index=FFFFF     GsTMDdivNF3
    [1376] e 00000000800B6A60 st 1 sc 5 index=FFFFF     DivideF3
    [1377] e 00000000800B6BB0 st 1 sc 5 index=FFFFF     GsTMDdivF4L
    [1378] e 00000000800B6E10 st 1 sc 5 index=FFFFF     GsTMDdivF4LFG
    [1379] e 00000000800B7074 st 1 sc 5 index=FFFFF     GsTMDdivF4NL
    [1380] e 00000000800B72A4 st 1 sc 5 index=FFFFF     GsTMDdivNF4
    [1381] e 00000000800B74D4 st 1 sc 5 index=FFFFF     DivideF4
    [1382] e 00000000800B7660 st 1 sc 5 index=FFFFF     GsTMDdivG3L
    [1383] e 00000000800B7898 st 1 sc 5 index=FFFFF     GsTMDdivG3LFG
    [1384] e 00000000800B7AD0 st 1 sc 5 index=FFFFF     GsTMDdivG3NL
    [1385] e 00000000800B7CC8 st 1 sc 5 index=FFFFF     GsTMDdivNG3
    [1386] e 00000000800B7EC0 st 1 sc 5 index=FFFFF     DivideG3
    [1387] e 00000000800B8040 st 1 sc 5 index=FFFFF     GsTMDdivTF3L
    [1388] e 00000000800B82A8 st 1 sc 5 index=FFFFF     GsTMDdivTF3LFG
    [1389] e 00000000800B8510 st 1 sc 5 index=FFFFF     GsTMDdivTF3NL
    [1390] e 00000000800B8734 st 1 sc 5 index=FFFFF     GsTMDdivTNF3
    [1391] e 00000000800B8950 st 1 sc 5 index=FFFFF     DivideFT3
    [1392] e 00000000800B8AF0 st 1 sc 5 index=FFFFF     GsTMDdivTG3L
    [1393] e 00000000800B8D64 st 1 sc 5 index=FFFFF     GsTMDdivTG3LFG
    [1394] e 00000000800B8FD8 st 1 sc 5 index=FFFFF     GsTMDdivTG3NL
    [1395] e 00000000800B9204 st 1 sc 5 index=FFFFF     GsTMDdivTNG3
    [1396] e 00000000800B943C st 1 sc 5 index=FFFFF     DivideGT3
    [1397] e 00000000800B9610 st 1 sc 5 index=FFFFF     GsTMDdivG4L
    [1398] e 00000000800B98B4 st 1 sc 5 index=FFFFF     GsTMDdivG4LFG
    [1399] e 00000000800B9B64 st 1 sc 5 index=FFFFF     GsTMDdivG4NL
    [1400] e 00000000800B9DB8 st 1 sc 5 index=FFFFF     GsTMDdivNG4
    [1401] e 00000000800BA00C st 1 sc 5 index=FFFFF     DivideG4
    [1402] e 00000000800BA1E0 st 1 sc 5 index=FFFFF     GsTMDdivTF4L
    [1403] e 00000000800BA478 st 1 sc 5 index=FFFFF     GsTMDdivTF4LFG
    [1404] e 00000000800BA714 st 1 sc 5 index=FFFFF     GsTMDdivTF4NL
    [1405] e 00000000800BA990 st 1 sc 5 index=FFFFF     GsTMDdivTNF4
    [1406] e 00000000800BAC08 st 1 sc 5 index=FFFFF     DivideFT4
    [1407] e 00000000800BAE00 st 1 sc 5 index=FFFFF     GsTMDdivTG4L
    [1408] e 00000000800BB0E4 st 1 sc 5 index=FFFFF     GsTMDdivTG4LFG
    [1409] e 00000000800BB3D0 st 1 sc 5 index=FFFFF     GsTMDdivTG4NL
    [1410] e 00000000800BB654 st 1 sc 5 index=FFFFF     GsTMDdivTNG4
    [1411] e 00000000800BB8F4 st 1 sc 5 index=FFFFF     DivideGT4
    [1412] e 00000000800BBB30 st 1 sc 5 index=FFFFF     gte_scope_f3
    [1413] e 00000000800BBC4C st 1 sc 5 index=FFFFF     gte_scope_tf3
    [1414] e 00000000800BBD50 st 1 sc 5 index=FFFFF     gte_scope_g3
    [1415] e 00000000800BBE70 st 1 sc 5 index=FFFFF     gte_scope_tg3
    [1416] e 00000000800BBF90 st 1 sc 5 index=FFFFF     gte_flat3
    [1417] e 00000000800BC08C st 1 sc 5 index=FFFFF     gte_texture_flat3
    [1418] e 00000000800BC1AC st 1 sc 5 index=FFFFF     gte_gouraud3
    [1419] e 00000000800BC2F8 st 1 sc 5 index=FFFFF     gte_texture_gouraud3
    [1420] e 00000000800BC45C st 1 sc 5 index=FFFFF     gte_flat_fog3
    [1421] e 00000000800BC550 st 1 sc 5 index=FFFFF     gte_texture_flat_fog3
    [1422] e 00000000800BC670 st 1 sc 5 index=FFFFF     gte_gouraud_fog3
    [1423] e 00000000800BC7B0 st 1 sc 5 index=FFFFF     gte_texture_gouraud_fog3
    [1424] e 00000000800BC914 st 1 sc 5 index=FFFFF     gte_scope_tf4_B
    [1425] e 00000000800BCA88 st 1 sc 5 index=FFFFF     gte_scope_tf4
    [1426] e 00000000800BCBE0 st 1 sc 5 index=FFFFF     RotTransPers
    [1427] e 00000000800BCC0C st 1 sc 5 index=FFFFF     RotTransPers3
    [1428] e 00000000800BCC60 st 1 sc 5 index=FFFFF     RotTrans
    [1429] e 00000000800BCC88 st 1 sc 5 index=FFFFF     RotTrans0
    [1430] e 00000000800BCCB0 st 1 sc 5 index=FFFFF     LocalLight
    [1431] e 00000000800BCCD4 st 1 sc 5 index=FFFFF     LightColor
    [1432] e 00000000800BCCFC st 1 sc 5 index=FFFFF     DpqColorLight
    [1433] e 00000000800BCD24 st 1 sc 5 index=FFFFF     DpqColor
    [1434] e 00000000800BCD40 st 1 sc 5 index=FFFFF     DpqColor3
    [1435] e 00000000800BCD7C st 1 sc 5 index=FFFFF     Intpl
    [1436] e 00000000800BCDA0 st 1 sc 5 index=FFFFF     Square12
    [1437] e 00000000800BCDC8 st 1 sc 5 index=FFFFF     Square0
    [1438] e 00000000800BCDF0 st 1 sc 5 index=FFFFF     NormalColor
    [1439] e 00000000800BCE0C st 1 sc 5 index=FFFFF     NormalColor3
    [1440] e 00000000800BCE48 st 1 sc 5 index=FFFFF     NormalColorDpq
    [1441] e 00000000800BCE6C st 1 sc 5 index=FFFFF     NormalColorDpq3
    [1442] e 00000000800BCEB4 st 1 sc 5 index=FFFFF     NormalColorCol
    [1443] e 00000000800BCED4 st 1 sc 5 index=FFFFF     NormalColorCol3
    [1444] e 00000000800BCF18 st 1 sc 5 index=FFFFF     ColorDpq
    [1445] e 00000000800BCF40 st 1 sc 5 index=FFFFF     ColorCol
    [1446] e 00000000800BCF64 st 1 sc 5 index=FFFFF     NormalClip
    [1447] e 00000000800BCF88 st 1 sc 5 index=FFFFF     NormalClipS
    [1448] e 00000000800BCF98 st 1 sc 5 index=FFFFF     AverageZ3
    [1449] e 00000000800BCFB8 st 1 sc 5 index=FFFFF     AverageSZ3
    [1450] e 00000000800BCFC8 st 1 sc 5 index=FFFFF     AverageZ4
    [1451] e 00000000800BCFEC st 1 sc 5 index=FFFFF     AverageSZ4
    [1452] e 00000000800BCFFC st 1 sc 5 index=FFFFF     OuterProduct12
    [1453] e 00000000800BD054 st 1 sc 5 index=FFFFF     OuterProduct0
    [1454] e 00000000800BD0AC st 1 sc 5 index=FFFFF     Lzc
    [1455] e 00000000800BD0D0 st 1 sc 5 index=FFFFF     RCpolyF3
    [1456] e 00000000800BD0D8 st 1 sc 5 index=FFFFF     RCpolyF3A
    [1457] e 00000000800BD440 st 1 sc 5 index=FFFFF     RCpolyF4
    [1458] e 00000000800BD448 st 1 sc 5 index=FFFFF     RCpolyF4A
    [1459] e 00000000800BD8C0 st 1 sc 5 index=FFFFF     RCpolyG3
    [1460] e 00000000800BD8C8 st 1 sc 5 index=FFFFF     RCpolyG3A
    [1461] e 00000000800BDCD0 st 1 sc 5 index=FFFFF     RCpolyFT3
    [1462] e 00000000800BDCD8 st 1 sc 5 index=FFFFF     RCpolyFT3A
    [1463] e 00000000800BE0D0 st 1 sc 5 index=FFFFF     RCpolyGT3
    [1464] e 00000000800BE0D8 st 1 sc 5 index=FFFFF     RCpolyGT3A
    [1465] e 00000000800BE570 st 1 sc 5 index=FFFFF     RCpolyG4
    [1466] e 00000000800BE578 st 1 sc 5 index=FFFFF     RCpolyG4A
    [1467] e 00000000800BEAC0 st 1 sc 5 index=FFFFF     RCpolyFT4
    [1468] e 00000000800BEAC8 st 1 sc 5 index=FFFFF     RCpolyFT4A
    [1469] e 00000000800BEFE8 st 1 sc 5 index=FFFFF     RCpolyGT4
    [1470] e 00000000800BEFF0 st 1 sc 5 index=FFFFF     RCpolyGT4A
    [1471] e 00000000800BF610 st 1 sc 5 index=FFFFF     ResetCallback
    [1472] e 00000000800BF640 st 1 sc 5 index=FFFFF     InterruptCallback
    [1473] e 00000000800BF670 st 1 sc 5 index=FFFFF     DMACallback
    [1474] e 00000000800BF6A0 st 1 sc 5 index=FFFFF     VSyncCallback
    [1475] e 00000000800BF6D0 st 1 sc 5 index=FFFFF     StopCallback
    [1476] e 00000000800BF700 st 1 sc 5 index=FFFFF     CheckCallback
    [1477] e 00000000800BFA80 st 1 sc 5 index=FFFFF     VSync
    [1478] e 00000000800BFC10 st 1 sc 5 index=FFFFF     DecDCTinCallback
    [1479] e 00000000800BFC34 st 1 sc 5 index=FFFFF     DecDCToutCallback
    [1480] e 00000000800BFC58 st 1 sc 5 index=FFFFF     CdDataCallback
    [1481] e 00000000800BFC7C st 1 sc 5 index=FFFFF     SpuDataCallback
    [1482] e 00000000800BFCA0 st 1 sc 5 index=FFFFF     PioDataCallback
    [1483] e 00000000800BFCC4 st 1 sc 5 index=FFFFF     CdCallback
    [1484] e 00000000800BFCE8 st 1 sc 5 index=FFFFF     SpuCallback
    [1485] e 00000000800BFD0C st 1 sc 5 index=FFFFF     PioCallback
    [1486] e 00000000800BFD30 st 1 sc 5 index=FFFFF     PadInit
    [1487] e 00000000800BFD84 st 1 sc 5 index=FFFFF     PadRead
    [1488] e 00000000800BFDB0 st 1 sc 5 index=FFFFF     PadStop
    [1489] e 00000000800BFDD0 st 1 sc 5 index=FFFFF     VBLNKInit
    [1490] e 00000000800BFE44 st 1 sc 5 index=FFFFF     VBLNKStop
    [1491] e 00000000800BFF20 st 1 sc 5 index=FFFFF     DMAInit
    [1492] e 00000000800BFF80 st 1 sc 5 index=FFFFF     DMAStop
    [1493] e 00000000800C01B0 st 1 sc 5 index=FFFFF     InitCARD
    [1494] e 00000000800C01C0 st 1 sc 5 index=FFFFF     StartCARD
    [1495] e 00000000800C01D0 st 1 sc 5 index=FFFFF     _bu_init
    [1496] e 00000000800C01E0 st 1 sc 5 index=FFFFF     _card_auto
    [1497] e 00000000800C01F0 st 1 sc 5 index=FFFFF     _card_info
    [1498] e 00000000800C0200 st 1 sc 5 index=FFFFF     _card_load
    [1499] e 00000000800C0210 st 1 sc 5 index=FFFFF     _card_clear
    [1500] e 00000000800C0240 st 1 sc 5 index=FFFFF     _card_status
    [1501] e 00000000800C0250 st 1 sc 5 index=FFFFF     _new_card
    [1502] e 00000000800C0260 st 1 sc 5 index=FFFFF     _card_write
    [1503] e 00000000800C0270 st 1 sc 5 index=FFFFF     printf
    [1504] e 00000000800C0280 st 1 sc 5 index=FFFFF     bzero
    [1505] e 00000000800C0290 st 1 sc 5 index=FFFFF     strcpy
    [1506] e 00000000800C02A0 st 1 sc 5 index=FFFFF     memcpy
    [1507] e 00000000800C02B0 st 1 sc 5 index=FFFFF     abs
    [1508] e 00000000800C02C0 st 1 sc 5 index=FFFFF     rand
    [1509] e 00000000800C02D0 st 1 sc 5 index=FFFFF     strlen
    [1510] e 00000000800C02E0 st 1 sc 5 index=FFFFF     strncpy
    [1511] e 00000000800C02F0 st 1 sc 5 index=FFFFF     strcat
    [1512] e 00000000800C0300 st 1 sc 5 index=FFFFF     strncat
    [1513] e 00000000800C0310 st 1 sc 5 index=FFFFF     srand
    [1514] e 00000000800C0320 st 1 sc 5 index=FFFFF     sprintf
    [1515] e 00000000800C10A0 st 1 sc 5 index=FFFFF     strcmp
    [1516] e 00000000800C10B0 st 1 sc 5 index=FFFFF     exit
    [1517] e 00000000800C10C0 st 1 sc 5 index=FFFFF     strncmp
    [1518] e 00000000800C10D0 st 1 sc 5 index=FFFFF     bcopy
    [1519] e 00000000800C10E0 st 1 sc 5 index=FFFFF     setjmp
    [1520] e 00000000800C10F0 st 1 sc 5 index=FFFFF     memchr
    [1521] e 00000000800C1100 st 1 sc 5 index=FFFFF     memmove
    [1522] e 00000000800C1110 st 1 sc 5 index=FFFFF     SetSp
    [1523] e 00000000800C1120 st 1 sc 5 index=FFFFF     InitHeap
    [1524] e 00000000800C1130 st 1 sc 5 index=FFFFF     GetGp
    [1525] e 00000000800C1140 st 1 sc 5 index=FFFFF     InitPAD
    [1526] e 00000000800C1150 st 1 sc 5 index=FFFFF     StartPAD
    [1527] e 00000000800C1160 st 1 sc 5 index=FFFFF     ChangeClearPAD
    [1528] e 00000000800C1170 st 1 sc 5 index=FFFFF     EnterCriticalSection
    [1529] e 00000000800C1180 st 1 sc 5 index=FFFFF     FlushCache
    [1530] e 00000000800C1190 st 1 sc 5 index=FFFFF     ExitCriticalSection
    [1531] e 00000000800C11A0 st 1 sc 5 index=FFFFF     OpenEvent
    [1532] e 00000000800C11B0 st 1 sc 5 index=FFFFF     EnableEvent
    [1533] e 00000000800C11C0 st 1 sc 5 index=FFFFF     SetRCnt
    [1534] e 00000000800C125C st 1 sc 5 index=FFFFF     GetRCnt
    [1535] e 00000000800C1294 st 1 sc 5 index=FFFFF     StartRCnt
    [1536] e 00000000800C12C8 st 1 sc 5 index=FFFFF     StopRCnt
    [1537] e 00000000800C12FC st 1 sc 5 index=FFFFF     ResetRCnt
    [1538] e 00000000800C1330 st 1 sc 5 index=FFFFF     GetSp
    [1539] e 00000000800C1340 st 1 sc 5 index=FFFFF     TestEvent
    [1540] e 00000000800C1350 st 1 sc 5 index=FFFFF     CloseEvent
    [1541] e 00000000800C1360 st 1 sc 5 index=FFFFF     format
    [1542] e 00000000800C1370 st 1 sc 5 index=FFFFF     close
    [1543] e 00000000800C1380 st 1 sc 5 index=FFFFF     open
    [1544] e 00000000800C1390 st 1 sc 5 index=FFFFF     delete
    [1545] e 00000000800C13A0 st 1 sc 5 index=FFFFF     read
    [1546] e 00000000800C13B0 st 1 sc 5 index=FFFFF     write
    [1547] e 00000000800C13C0 st 1 sc 5 index=FFFFF     _96_init
    [1548] e 00000000800C13D0 st 1 sc 5 index=FFFFF     LoadExec
    [1549] e 00000000800C13E0 st 1 sc 5 index=FFFFF     _96_remove
    [1550] e 00000000800C13F0 st 1 sc 5 index=FFFFF     DeliverEvent
    [1551] e 00000000800C1400 st 1 sc 5 index=FFFFF     DisableEvent
    [1552] e 00000000800C1410 st 1 sc 5 index=FFFFF     GPU_cw
    [1553] e 00000000800C1420 st 1 sc 5 index=FFFFF     ReturnFromException
    [1554] e 00000000800C1430 st 1 sc 5 index=FFFFF     HookEntryInt
    [1555] e 00000000800C1440 st 1 sc 5 index=FFFFF     PAD_init
    [1556] e 00000000800C1450 st 1 sc 5 index=FFFFF     PAD_dr
    [1557] e 00000000800C1460 st 1 sc 5 index=FFFFF     StopPAD
    [1558] e 00000000800C1470 st 1 sc 5 index=FFFFF     ChangeClearRCnt
    [1559] e 00000000800C6860 st 1 sc 5 index=FFFFF     suuzi0
    [1560] e 00000000800C6864 st 1 sc 5 index=FFFFF     suuzi1
    [1561] e 00000000800C6868 st 1 sc 5 index=FFFFF     suuzi2
    [1562] e 00000000800C686C st 1 sc 5 index=FFFFF     suuzi3
    [1563] e 00000000800C6870 st 1 sc 5 index=FFFFF     suuzi4
    [1564] e 00000000800C6874 st 1 sc 5 index=FFFFF     suuzi5
    [1565] e 00000000800C6878 st 1 sc 5 index=FFFFF     suuzi6
    [1566] e 00000000800C687C st 1 sc 5 index=FFFFF     suuzi7
    [1567] e 00000000800C6880 st 1 sc 5 index=FFFFF     suuzi8
    [1568] e 00000000800C6884 st 1 sc 5 index=FFFFF     suuzi9
    [1569] e 00000000800C6888 st 1 sc 5 index=FFFFF     suuzi10
    [1570] e 00000000800C6890 st 1 sc 5 index=FFFFF     suuzi11
    [1571] e 00000000800C6898 st 1 sc 5 index=FFFFF     suuzi12
    [1572] e 00000000800C68A0 st 1 sc 5 index=FFFFF     suuzi13
    [1573] e 00000000800C68A8 st 1 sc 5 index=FFFFF     suuzi14
    [1574] e 00000000800C68B0 st 1 sc 5 index=FFFFF     suuzi15
    [1575] e 00000000800C68B8 st 1 sc 5 index=FFFFF     suuzi16
    [1576] e 00000000800C68C0 st 1 sc 5 index=FFFFF     suuzi_0org
    [1577] e 00000000800C6904 st 1 sc 5 index=FFFFF     suuzi
    [1578] e 00000000800C6908 st 1 sc 5 index=FFFFF     com_name_tai
    [1579] e 00000000800C6910 st 1 sc 5 index=FFFFF     com_name_bun
    [1580] e 00000000800C6918 st 1 sc 5 index=FFFFF     com_name_ri
    [1581] e 00000000800C6920 st 1 sc 5 index=FFFFF     com_name_gei
    [1582] e 00000000800C6928 st 1 sc 5 index=FFFFF     com_name_un
    [1583] e 00000000800C6930 st 1 sc 5 index=FFFFF     com_name_zat
    [1584] e 00000000800C6938 st 1 sc 5 index=FFFFF     com_name_you
    [1585] e 00000000800C6940 st 1 sc 5 index=FFFFF     com_name_kon
    [1586] e 00000000800C6948 st 1 sc 5 index=FFFFF     com_name_str
    [1587] e 00000000800C6954 st 1 sc 5 index=FFFFF     com_name
    [1588] e 00000000800C6978 st 1 sc 5 index=FFFFF     date_name_0
    [1589] e 00000000800C6984 st 1 sc 5 index=FFFFF     date_name_1
    [1590] e 00000000800C6998 st 1 sc 5 index=FFFFF     date_name_2
    [1591] e 00000000800C69A8 st 1 sc 5 index=FFFFF     date_name_3
    [1592] e 00000000800C69B0 st 1 sc 5 index=FFFFF     date_name_4
    [1593] e 00000000800C69B8 st 1 sc 5 index=FFFFF     date_name_5
    [1594] e 00000000800C69C0 st 1 sc 5 index=FFFFF     date_name_6
    [1595] e 00000000800C69D0 st 1 sc 5 index=FFFFF     date_name_7
    [1596] e 00000000800C69D8 st 1 sc 5 index=FFFFF     date_name_8
    [1597] e 00000000800C69E0 st 1 sc 5 index=FFFFF     date_name_9
    [1598] e 00000000800C69F0 st 1 sc 5 index=FFFFF     date_name_10
    [1599] e 00000000800C6A00 st 1 sc 5 index=FFFFF     date_name_11
    [1600] e 00000000800C6A0C st 1 sc 5 index=FFFFF     date_name_12
    [1601] e 00000000800C6A14 st 1 sc 5 index=FFFFF     date_name_13
    [1602] e 00000000800C6A20 st 1 sc 5 index=FFFFF     date_name_14
    [1603] e 00000000800C6A28 st 1 sc 5 index=FFFFF     date_name_15
    [1604] e 00000000800C6A38 st 1 sc 5 index=FFFFF     date_name_16
    [1605] e 00000000800C6A40 st 1 sc 5 index=FFFFF     date_name_17
    [1606] e 00000000800C6A44 st 1 sc 5 index=FFFFF     date_name_18
    [1607] e 00000000800C6A4C st 1 sc 5 index=FFFFF     date_name_19
    [1608] e 00000000800C6A58 st 1 sc 5 index=FFFFF     date_name_20
    [1609] e 00000000800C6A64 st 1 sc 5 index=FFFFF     date_name
    [1610] e 00000000800C6AB8 st 1 sc 5 index=FFFFF     tc_name_0
    [1611] e 00000000800C6AC4 st 1 sc 5 index=FFFFF     tc_name_1
    [1612] e 00000000800C6AD0 st 1 sc 5 index=FFFFF     tc_name_2
    [1613] e 00000000800C6ADC st 1 sc 5 index=FFFFF     tc_name_3
    [1614] e 00000000800C6AE8 st 1 sc 5 index=FFFFF     tc_name_4
    [1615] e 00000000800C6AF4 st 1 sc 5 index=FFFFF     tc_name_5
    [1616] e 00000000800C6B00 st 1 sc 5 index=FFFFF     tc_name_6
    [1617] e 00000000800C6B08 st 1 sc 5 index=FFFFF     tc_name_7
    [1618] e 00000000800C6B10 st 1 sc 5 index=FFFFF     tc_name_8
    [1619] e 00000000800C6B1C st 1 sc 5 index=FFFFF     tc_name_9
    [1620] e 00000000800C6B28 st 1 sc 5 index=FFFFF     tc_name_10
    [1621] e 00000000800C6B34 st 1 sc 5 index=FFFFF     tc_name_11
    [1622] e 00000000800C6B40 st 1 sc 5 index=FFFFF     tc_name_12
    [1623] e 00000000800C6B4C st 1 sc 5 index=FFFFF     tc_name_13
    [1624] e 00000000800C6B58 st 1 sc 5 index=FFFFF     tc_name_14
    [1625] e 00000000800C6B64 st 1 sc 5 index=FFFFF     tc_name_15
    [1626] e 00000000800C6B70 st 1 sc 5 index=FFFFF     tc_name
    [1627] e 00000000800C6BB0 st 1 sc 5 index=FFFFF     tc_sname_0
    [1628] e 00000000800C6BB8 st 1 sc 5 index=FFFFF     tc_sname_1
    [1629] e 00000000800C6BC0 st 1 sc 5 index=FFFFF     tc_sname_2
    [1630] e 00000000800C6BC8 st 1 sc 5 index=FFFFF     tc_sname_3
    [1631] e 00000000800C6BD0 st 1 sc 5 index=FFFFF     tc_sname_4
    [1632] e 00000000800C6BD8 st 1 sc 5 index=FFFFF     tc_sname_5
    [1633] e 00000000800C6BE0 st 1 sc 5 index=FFFFF     tc_sname_6
    [1634] e 00000000800C6BE8 st 1 sc 5 index=FFFFF     tc_sname_7
    [1635] e 00000000800C6BEC st 1 sc 5 index=FFFFF     tc_sname_8
    [1636] e 00000000800C6BF4 st 1 sc 5 index=FFFFF     tc_sname_9
    [1637] e 00000000800C6BFC st 1 sc 5 index=FFFFF     tc_sname_10
    [1638] e 00000000800C6C04 st 1 sc 5 index=FFFFF     tc_sname_11
    [1639] e 00000000800C6C0C st 1 sc 5 index=FFFFF     tc_sname_12
    [1640] e 00000000800C6C14 st 1 sc 5 index=FFFFF     tc_sname_13
    [1641] e 00000000800C6C1C st 1 sc 5 index=FFFFF     tc_sname_14
    [1642] e 00000000800C6C24 st 1 sc 5 index=FFFFF     tc_sname_15
    [1643] e 00000000800C6C2C st 1 sc 5 index=FFFFF     tc_sname
    [1644] e 00000000800C6C6C st 1 sc 5 index=FFFFF     kun
    [1645] e 00000000800C6C70 st 1 sc 5 index=FFFFF     san
    [1646] e 00000000800C6C78 st 1 sc 5 index=FFFFF     non
    [1647] e 00000000800C6C7C st 1 sc 5 index=FFFFF     space
    [1648] e 00000000800C6C80 st 1 sc 5 index=FFFFF     xass
    [1649] e 00000000800C6CC0 st 1 sc 5 index=FFFFF     girl_vh
    [1650] e 00000000800C6D00 st 1 sc 5 index=FFFFF     girl_vb
    [1651] e 00000000800C6D40 st 1 sc 5 index=FFFFF     girl_seq
    [1652] e 00000000800C6D80 st 1 sc 5 index=FFFFF     cal_dat
    [1653] e 00000000800C6D84 st 1 sc 5 index=FFFFF     f_main07
    [1654] e 00000000800C6D88 st 1 sc 5 index=FFFFF     stadium_data
    [1655] e 00000000800C6DB0 st 1 sc 5 index=FFFFF     telephone_kigou
    [1656] e 00000000800C6E0C st 1 sc 5 index=FFFFF     aisatu_sector
    [1657] e 00000000800C6E74 st 1 sc 5 index=FFFFF     aisatu_sector2
    [1658] e 00000000800C6EDC st 1 sc 5 index=FFFFF     bukatu_name0
    [1659] e 00000000800C6EE4 st 1 sc 5 index=FFFFF     bukatu_name1
    [1660] e 00000000800C6EEC st 1 sc 5 index=FFFFF     bukatu_name2
    [1661] e 00000000800C6EF4 st 1 sc 5 index=FFFFF     bukatu_name3
    [1662] e 00000000800C6EFC st 1 sc 5 index=FFFFF     bukatu_name4
    [1663] e 00000000800C6F04 st 1 sc 5 index=FFFFF     bukatu_name5
    [1664] e 00000000800C6F0C st 1 sc 5 index=FFFFF     bukatu_name6
    [1665] e 00000000800C6F14 st 1 sc 5 index=FFFFF     bukatu_name7
    [1666] e 00000000800C6F20 st 1 sc 5 index=FFFFF     bukatu_name8
    [1667] e 00000000800C6F28 st 1 sc 5 index=FFFFF     bukatu_name9
    [1668] e 00000000800C6F30 st 1 sc 5 index=FFFFF     bukatu_name10
    [1669] e 00000000800C6F38 st 1 sc 5 index=FFFFF     bukatu_name11
    [1670] e 00000000800C6F40 st 1 sc 5 index=FFFFF     bukatu_name_table
    [1671] e 00000000800C6F70 st 1 sc 5 index=FFFFF     card_file_name
    [1672] e 00000000800C6F90 st 1 sc 5 index=FFFFF     pad_mode
    [1673] e 00000000800C6F94 st 1 sc 5 index=FFFFF     konami_command
    [1674] e 00000000800C6FE4 st 1 sc 5 index=FFFFF     konami_command_tag
    [1675] e 00000000800C6FE8 st 1 sc 5 index=FFFFF     konami_command_flag
    [1676] e 00000000800C6FEC st 1 sc 5 index=FFFFF     konami_command_timer
    [1677] e 00000000800C6FF0 st 1 sc 5 index=FFFFF     gs_vcnt
    [1678] e 00000000800C7010 st 1 sc 5 index=FFFFF     trans_flag
    [1679] e 00000000800C7014 st 1 sc 5 index=FFFFF     msflag
    [1680] e 00000000800C7018 st 1 sc 5 index=FFFFF     same_se
    [1681] e 00000000800C701C st 1 sc 5 index=FFFFF     same_seq
    [1682] e 00000000800C7020 st 1 sc 5 index=FFFFF     last_m_se
    [1683] e 00000000800C7024 st 1 sc 5 index=FFFFF     last_m_seq
    [1684] e 00000000800C7028 st 1 sc 5 index=FFFFF     last_s_se
    [1685] e 00000000800C702C st 1 sc 5 index=FFFFF     last_s_seq
    [1686] e 00000000800C7030 st 1 sc 5 index=FFFFF     seq_on_off
    [1687] e 00000000800C7034 st 1 sc 5 index=FFFFF     seq_info
    [1688] e 00000000800C7038 st 1 sc 5 index=FFFFF     cur_seq_num
    [1689] e 00000000800C703C st 1 sc 5 index=FFFFF     trans_wait_counter
    [1690] e 00000000800C7040 st 1 sc 5 index=FFFFF     sd_err_flag
    [1691] e 00000000800C7050 st 1 sc 5 index=FFFFF     cd_check_level
    [1692] e 00000000800C7054 st 1 sc 5 index=FFFFF     cdsectors
    [1693] e 00000000800C7058 st 1 sc 5 index=FFFFF     last_sector
    [1694] e 00000000800C705C st 1 sc 5 index=FFFFF     XAsector
    [1695] e 00000000800C7070 st 1 sc 5 index=FFFFF     night_x1
    [1696] e 00000000800C7074 st 1 sc 5 index=FFFFF     night_x2
    [1697] e 00000000800C7078 st 1 sc 5 index=FFFFF     night_x3
    [1698] e 00000000800C707C st 1 sc 5 index=FFFFF     night_y1
    [1699] e 00000000800C7080 st 1 sc 5 index=FFFFF     night_y2
    [1700] e 00000000800C7084 st 1 sc 5 index=FFFFF     night_y3
    [1701] e 00000000800C7090 st 1 sc 5 index=FFFFF     print_flag
    [1702] e 00000000800C70C0 st 1 sc 5 index=FFFFF     ko_move_ok
    [1703] e 00000000800C70C4 st 1 sc 5 index=FFFFF     s_count
    [1704] e 00000000800C70D0 st 1 sc 5 index=FFFFF     k_work
    [1705] e 00000000800C7250 st 1 sc 5 index=FFFFF     ksys
    [1706] e 00000000800C725C st 1 sc 5 index=FFFFF     sjis_col
    [1707] e 00000000800C729C st 1 sc 5 index=FFFFF     sjis_col_s
    [1708] e 00000000800C72DC st 1 sc 5 index=FFFFF     sjis_data
    [1709] e 00000000800C73A0 st 1 sc 5 index=FFFFF     x_taku_y
    [1710] e 00000000800C73B0 st 1 sc 5 index=FFFFF     tokimeki_hosei_table
    [1711] e 00000000800C73C0 st 1 sc 5 index=FFFFF     tokimeki_check_table
    [1712] e 00000000800C73D0 st 1 sc 5 index=FFFFF     tokimeki_check_pattern
    [1713] e 00000000800C73E0 st 1 sc 5 index=FFFFF     girl_l
    [1714] e 00000000800C7448 st 1 sc 5 index=FFFFF     para_sl
    [1715] e 00000000800C7450 st 1 sc 5 index=FFFFF     yuukou_hosei_table
    [1716] e 00000000800C7460 st 1 sc 5 index=FFFFF     grp_tbl
    [1717] e 00000000800C75F0 st 1 sc 5 index=FFFFF     fuji_para_tbl
    [1718] e 00000000800C75F8 st 1 sc 5 index=FFFFF     SYOUSIN_BAIRITU
    [1719] e 00000000800C7604 st 1 sc 5 index=FFFFF     PARA_GA
    [1720] e 00000000800C7610 st 1 sc 5 index=FFFFF     PARA_GB
    [1721] e 00000000800C761C st 1 sc 5 index=FFFFF     END_PLUS_POINT
    [1722] e 00000000800C762C st 1 sc 5 index=FFFFF     STRESS_TABLE
    [1723] e 00000000800C7640 st 1 sc 5 index=FFFFF     icon_col
    [1724] e 00000000800C77E0 st 1 sc 5 index=FFFFF     icon_image0
    [1725] e 00000000800C7960 st 1 sc 5 index=FFFFF     icon_image1
    [1726] e 00000000800C7AE0 st 1 sc 5 index=FFFFF     icon_image2
    [1727] e 00000000800C7C60 st 1 sc 5 index=FFFFF     icon_image3
    [1728] e 00000000800C7DE0 st 1 sc 5 index=FFFFF     icon_image4
    [1729] e 00000000800C7F60 st 1 sc 5 index=FFFFF     icon_image5
    [1730] e 00000000800C80E0 st 1 sc 5 index=FFFFF     icon_image6
    [1731] e 00000000800C8260 st 1 sc 5 index=FFFFF     icon_image7
    [1732] e 00000000800C83E0 st 1 sc 5 index=FFFFF     icon_image8
    [1733] e 00000000800C8560 st 1 sc 5 index=FFFFF     icon_image9
    [1734] e 00000000800C86E0 st 1 sc 5 index=FFFFF     icon_imagea
    [1735] e 00000000800C8860 st 1 sc 5 index=FFFFF     icon_imageb
    [1736] e 00000000800C89E0 st 1 sc 5 index=FFFFF     icon_imagec
    [1737] e 00000000800C8B60 st 1 sc 5 index=FFFFF     icon_image
    [1738] e 00000000800C8BA0 st 1 sc 5 index=FFFFF     frame_cnt
    [1739] e 00000000800C8BA4 st 1 sc 5 index=FFFFF     max_frame
    [1740] e 00000000800C8BA8 st 1 sc 5 index=FFFFF     movie_ofx
    [1741] e 00000000800C8BAC st 1 sc 5 index=FFFFF     movie_ofy
    [1742] e 00000000800C8BB0 st 1 sc 5 index=FFFFF     rgb_mode
    [1743] e 00000000800C8BB4 st 1 sc 5 index=FFFFF     next_line
    [1744] e 00000000800C8BD0 st 1 sc 5 index=FFFFF     dec_bg_sector
    [1745] e 00000000800C8BE8 st 1 sc 5 index=FFFFF     now_dec_bg_show
    [1746] e 00000000800C8BEC st 1 sc 5 index=FFFFF     last_gamen_mode
    [1747] e 00000000800C8BF0 st 1 sc 5 index=FFFFF     full_move_timer
    [1748] e 00000000800C8BF4 st 1 sc 5 index=FFFFF     tbg_bri
    [1749] e 00000000800C8C00 st 1 sc 5 index=FFFFF     season_main_e_bg_sector
    [1750] e 00000000800C8C10 st 1 sc 5 index=FFFFF     season_main_n_bg_sector
    [1751] e 00000000800C8C20 st 1 sc 5 index=FFFFF     radio_sector
    [1752] e 00000000800C8C60 st 1 sc 5 index=FFFFF     radio_sector_m
    [1753] e 00000000800C8CB0 st 1 sc 5 index=FFFFF     now_select_menu
    [1754] e 00000000800C8CB4 st 1 sc 5 index=FFFFF     message_kind
    [1755] e 00000000800C8CB8 st 1 sc 5 index=FFFFF     src_album
    [1756] e 00000000800C8CBC st 1 sc 5 index=FFFFF     dst_album
    [1757] e 00000000800C8CC0 st 1 sc 5 index=FFFFF     cardsys0
    [1758] e 00000000800C8CC4 st 1 sc 5 index=FFFFF     fan_size
    [1759] e 00000000800C8CC8 st 1 sc 5 index=FFFFF     fan_x_pos
    [1760] e 00000000800C8CCC st 1 sc 5 index=FFFFF     fan_y_pos
    [1761] e 00000000800C8CD0 st 1 sc 5 index=FFFFF     fan_x_speed
    [1762] e 00000000800C8CD4 st 1 sc 5 index=FFFFF     fan_y_speed
    [1763] e 00000000800C8CD8 st 1 sc 5 index=FFFFF     debug_step
    [1764] e 00000000800C8CDC st 1 sc 5 index=FFFFF     yes_string0
    [1765] e 00000000800C8CF4 st 1 sc 5 index=FFFFF     yes_string
    [1766] e 00000000800C8CF8 st 1 sc 5 index=FFFFF     no_string0
    [1767] e 00000000800C8D10 st 1 sc 5 index=FFFFF     no_string
    [1768] e 00000000800C8D14 st 1 sc 5 index=FFFFF     migi_string
    [1769] e 00000000800C8D18 st 1 sc 5 index=FFFFF     hidari_string
    [1770] e 00000000800C8D30 st 1 sc 5 index=FFFFF     no_memcard
    [1771] e 00000000800C8DA8 st 1 sc 5 index=FFFFF     save_error
    [1772] e 00000000800C8E20 st 1 sc 5 index=FFFFF     cant_read_memcard
    [1773] e 00000000800C8E98 st 1 sc 5 index=FFFFF     cant_read_cd0
    [1774] e 00000000800C8F10 st 1 sc 5 index=FFFFF     cant_read_cd1
    [1775] e 00000000800C8F80 st 1 sc 5 index=FFFFF     morning_sector
    [1776] e 00000000800C9050 st 1 sc 5 index=FFFFF     vol_max
    [1777] e 00000000800C9054 st 1 sc 5 index=FFFFF     now_icon
    [1778] e 00000000800C9058 st 1 sc 5 index=FFFFF     now_icon_timer
    [1779] e 00000000800C905C st 1 sc 5 index=FFFFF     icon_xy_b
    [1780] e 00000000800C909C st 1 sc 5 index=FFFFF     icon_xy_a
    [1781] e 00000000800C90DC st 1 sc 5 index=FFFFF     basyo_len
    [1782] e 00000000800C90E0 st 1 sc 5 index=FFFFF     cal_color
    [1783] e 00000000800C9180 st 1 sc 5 index=FFFFF     season_timer
    [1784] e 00000000800C9184 st 1 sc 5 index=FFFFF     bg_scroll_x
    [1785] e 00000000800C9188 st 1 sc 5 index=FFFFF     bg_scroll_y
    [1786] e 00000000800C918C st 1 sc 5 index=FFFFF     back_bg_pri
    [1787] e 00000000800C9190 st 1 sc 5 index=FFFFF     season_seq
    [1788] e 00000000800C91A0 st 1 sc 5 index=FFFFF     season_vh
    [1789] e 00000000800C91B0 st 1 sc 5 index=FFFFF     season_vb
    [1790] e 00000000800C91C0 st 1 sc 5 index=FFFFF     mascot_kind
    [1791] e 00000000800C91D0 st 1 sc 5 index=FFFFF     iv2ic
    [1792] e 00000000800C91EC st 1 sc 5 index=FFFFF     concert_names
    [1793] e 00000000800C92CC st 1 sc 5 index=FFFFF     concert_kind_f
    [1794] e 00000000800C92DC st 1 sc 5 index=FFFFF     cinema_name
    [1795] e 00000000800C93BC st 1 sc 5 index=FFFFF     cinema_kind
    [1796] e 00000000800C93CC st 1 sc 5 index=FFFFF     message_newspot
    [1797] e 00000000800C9464 st 1 sc 5 index=FFFFF     message_main
    [1798] e 00000000800C99E0 st 1 sc 5 index=FFFFF     p_mes0
    [1799] e 00000000800C9A4C st 1 sc 5 index=FFFFF     p_mes1
    [1800] e 00000000800C9A94 st 1 sc 5 index=FFFFF     p_mes2
    [1801] e 00000000800C9AAC st 1 sc 5 index=FFFFF     p_mes3
    [1802] e 00000000800C9B0C st 1 sc 5 index=FFFFF     p_mes4
    [1803] e 00000000800C9B28 st 1 sc 5 index=FFFFF     p_mes5
    [1804] e 00000000800C9B64 st 1 sc 5 index=FFFFF     p_mes6
    [1805] e 00000000800C9B78 st 1 sc 5 index=FFFFF     p_mes7
    [1806] e 00000000800C9B90 st 1 sc 5 index=FFFFF     p_mes8
    [1807] e 00000000800C9C00 st 1 sc 5 index=FFFFF     p_mes9
    [1808] e 00000000800C9C34 st 1 sc 5 index=FFFFF     p_mes10
    [1809] e 00000000800C9CA0 st 1 sc 5 index=FFFFF     p_mes11
    [1810] e 00000000800C9CC4 st 1 sc 5 index=FFFFF     p_mes12
    [1811] e 00000000800C9CD0 st 1 sc 5 index=FFFFF     player_message
    [1812] e 00000000800C9D10 st 1 sc 5 index=FFFFF     date_light_x
    [1813] e 00000000800C9D24 st 1 sc 5 index=FFFFF     date_light_iso
    [1814] e 00000000800C9D38 st 1 sc 5 index=FFFFF     pat_pat
    [1815] e 00000000800C9D3C st 1 sc 5 index=FFFFF     sum_month
    [1816] e 00000000800C9D60 st 1 sc 5 index=FFFFF     first_girl
    [1817] e 00000000800C9D64 st 1 sc 5 index=FFFFF     border
    [1818] e 00000000800C9D80 st 1 sc 5 index=FFFFF     sd_bg_sector
    [1819] e 00000000800C9DA0 st 1 sc 5 index=FFFFF     club_bg_sector
    [1820] e 00000000800C9DCC st 1 sc 5 index=FFFFF     main_sd_sector
    [1821] e 00000000800C9E30 st 1 sc 5 index=FFFFF     club_sd_sector
    [1822] e 00000000800C9EB0 st 1 sc 5 index=FFFFF     club_sd_data_s
    [1823] e 00000000800C9EC8 st 1 sc 5 index=FFFFF     club_sd_data_w
    [1824] e 00000000800C9EE0 st 1 sc 5 index=FFFFF     sd_data_s
    [1825] e 00000000800C9EF0 st 1 sc 5 index=FFFFF     sd_data_w
    [1826] e 00000000800C9F00 st 1 sc 5 index=FFFFF     toki_para_d
    [1827] e 00000000800C9F48 st 1 sc 5 index=FFFFF     toki_para_club_d
    [1828] e 00000000800C9FB0 st 1 sc 5 index=FFFFF     tel_check_tag
    [1829] e 00000000800C9FB4 st 1 sc 5 index=FFFFF     sd_h_bg_sector
    [1830] e 00000000800C9FD4 st 1 sc 5 index=FFFFF     demachiawase
    [1831] e 00000000800C9FE8 st 1 sc 5 index=FFFFF     sd_h_data_s
    [1832] e 00000000800C9FF0 st 1 sc 5 index=FFFFF     sd_h_data_w
    [1833] e 00000000800C9FF8 st 1 sc 5 index=FFFFF     main_h_sd_sector
    [1834] e 00000000800CA030 st 1 sc 5 index=FFFFF     lf_mode
    [1835] e 00000000800CA034 st 1 sc 5 index=FFFFF     lf_step
    [1836] e 00000000800CA038 st 1 sc 5 index=FFFFF     lf_sector_size
    [1837] e 00000000800CA03C st 1 sc 5 index=FFFFF     lf_addr
    [1838] e 00000000800CA040 st 1 sc 5 index=FFFFF     lf_cd_sector
    [1839] e 00000000800CA050 st 1 sc 5 index=FFFFF     sjissce
    [1840] e 00000000800D92CC st 1 sc 5 index=FFFFF     o_asobi_rom_table
    [1841] e 00000000800D92D4 st 1 sc 5 index=FFFFF     o_asobi_pattern_table
    [1842] e 00000000800D9310 st 1 sc 5 index=FFFFF     o_asobi_animation_table
    [1843] e 00000000800D9314 st 1 sc 5 index=FFFFF     o_asobi_max_animation
    [1844] e 00000000800D9318 st 1 sc 5 index=FFFFF     o_asobi_opd_info
    [1845] e 00000000800D9320 st 1 sc 5 index=FFFFF     c_main_col
    [1846] e 00000000800DC8E0 st 1 sc 5 index=FFFFF     BUNKEI
    [1847] e 00000000800DC8F4 st 1 sc 5 index=FFFFF     RIKEI
    [1848] e 00000000800DC908 st 1 sc 5 index=FFFFF     GEIJYUTU
    [1849] e 00000000800DC91C st 1 sc 5 index=FFFFF     UNDOU
    [1850] e 00000000800DC930 st 1 sc 5 index=FFFFF     BUKATU
    [1851] e 00000000800DC950 st 1 sc 5 index=FFFFF     ASOBI
    [1852] e 00000000800DC964 st 1 sc 5 index=FFFFF     YOUSI
    [1853] e 00000000800DC978 st 1 sc 5 index=FFFFF     NERU
    [1854] e 00000000800DC998 st 1 sc 5 index=FFFFF     DENWA
    [1855] e 00000000800DC9A4 st 1 sc 5 index=FFFFF     DATE
    [1856] e 00000000800DC9B8 st 1 sc 5 index=FFFFF     JYOUHOU
    [1857] e 00000000800DC9CC st 1 sc 5 index=FFFFF     SYSTEM
    [1858] e 00000000800DC9E0 st 1 sc 5 index=FFFFF     CALENDAR
    [1859] e 00000000800DC9F4 st 1 sc 5 index=FFFFF     MEMORY
    [1860] e 00000000800DCA10 st 1 sc 5 index=FFFFF     SAVETYUU
    [1861] e 00000000800DCA24 st 1 sc 5 index=FFFFF     YOKUJITU
    [1862] e 00000000800DCA30 st 1 sc 5 index=FFFFF     o_main_rom_table
    [1863] e 00000000800DCA5C st 1 sc 5 index=FFFFF     o_main_pattern_table
    [1864] e 00000000800DCD14 st 1 sc 5 index=FFFFF     o_main_animation_table
    [1865] e 00000000800DCD54 st 1 sc 5 index=FFFFF     o_main_max_animation
    [1866] e 00000000800DCD58 st 1 sc 5 index=FFFFF     o_main_opd_info
    [1867] e 00000000800DCD60 st 1 sc 5 index=FFFFF     byouki_csr
    [1868] e 00000000800DD060 st 1 sc 5 index=FFFFF     byouki_col
    [1869] e 00000000800DD260 st 1 sc 5 index=FFFFF     sd_adr
    [1870] e 00000000800DD2F8 st 1 sc 5 index=FFFFF     sd_h_adr
    [1871] e 00000000800DD348 st 1 sc 5 index=FFFFF     sdc_adr
    [1872] e 00000000800DD408 st 1 sc 5 index=FFFFF     sde_adr
    [1873] e 00000000800DD420 st 1 sc 5 index=FFFFF     a_rom_table
    [1874] e 00000000800DD424 st 1 sc 5 index=FFFFF     a_pattern_table
    [1875] e 00000000800DD428 st 1 sc 5 index=FFFFF     a_animation_table
    [1876] e 00000000800DD42C st 1 sc 5 index=FFFFF     a_max_animation
    [1877] e 00000000800DD430 st 1 sc 5 index=FFFFF     a_col
    [1878] e 00000000800DD434 st 1 sc 5 index=FFFFF     now_s
    [1879] e 00000000800DD438 st 1 sc 5 index=FFFFF     now_s_in
    [1880] e 00000000800DD43C st 1 sc 5 index=FFFFF     ss_s
    [1881] e 00000000800DD440 st 1 sc 5 index=FFFFF     ss_s_kind
    [1882] e 00000000800DD444 st 1 sc 5 index=FFFFF     sss_so
    [1883] e 00000000800DD448 st 1 sc 5 index=FFFFF     now_serifu
    [1884] e 00000000800DD44C st 1 sc 5 index=FFFFF     now_serifu_in
    [1885] e 00000000800DD450 st 1 sc 5 index=FFFFF     now_serifuev
    [1886] e 00000000800DD454 st 1 sc 5 index=FFFFF     now_serifuev_in
    [1887] e 00000000800DD458 st 1 sc 5 index=FFFFF     now_serifue
    [1888] e 00000000800DD45C st 1 sc 5 index=FFFFF     now_serifue_in
    [1889] e 00000000800DD460 st 1 sc 5 index=FFFFF     ss_serifu
    [1890] e 00000000800DD464 st 1 sc 5 index=FFFFF     ss_serifu_kind
    [1891] e 00000000800DD468 st 1 sc 5 index=FFFFF     sss_sound
    [1892] e 00000000800DD46C st 1 sc 5 index=FFFFF     p_name
    [1893] e 00000000800DD474 st 1 sc 5 index=FFFFF     pp_name
    [1894] e 00000000800DD47C st 1 sc 5 index=FFFFF     p_name2
    [1895] e 00000000800DD488 st 1 sc 5 index=FFFFF     g_name
    [1896] e 00000000800DD490 st 1 sc 5 index=FFFFF     g_name2
    [1897] e 00000000800DD49C st 1 sc 5 index=FFFFF     ba_string
    [1898] e 00000000800DD4DC st 1 sc 5 index=FFFFF     ba_string2
    [1899] e 00000000800DD51C st 1 sc 5 index=FFFFF     kao
    [1900] e 00000000800DD524 st 1 sc 5 index=FFFFF     kao2
    [1901] e 00000000800DD52C st 1 sc 5 index=FFFFF     imp
    [1902] e 00000000800DD534 st 1 sc 5 index=FFFFF     ans
    [1903] e 00000000800DD53C st 1 sc 5 index=FFFFF     shu_name
    [1904] e 00000000800DD548 st 1 sc 5 index=FFFFF     oname
    [1905] e 00000000800DD550 st 1 sc 5 index=FFFFF     wname
    [1906] e 00000000800DD55C st 1 sc 5 index=FFFFF     aname
    [1907] e 00000000800DD580 st 1 sc 5 index=FFFFF     mname
    [1908] e 00000000800DD5A4 st 1 sc 5 index=FFFFF     junban
    [1909] e 00000000800DD5A8 st 1 sc 5 index=FFFFF     sound_seek_wait
    [1910] e 00000000800DD5AC st 1 sc 5 index=FFFFF     sound_seek_time
    [1911] e 00000000800DD5B0 st 1 sc 5 index=FFFFF     girl_appear
    [1912] e 00000000800DD5BC st 1 sc 5 index=FFFFF     scroll_exist
    [1913] e 00000000800DD5C0 st 1 sc 5 index=FFFFF     last_x_y
    [1914] e 00000000800DD5C4 st 1 sc 5 index=FFFFF     xcut
    [1915] e 00000000800DD5C8 st 1 sc 5 index=FFFFF     yajirusi_timer
    [1916] e 00000000800DD5CC st 1 sc 5 index=FFFFF     shugaku_place
    [1917] e 00000000800DD5D0 st 1 sc 5 index=FFFFF     ss_serifu_shugaku
    [1918] e 00000000800DD5D4 st 1 sc 5 index=FFFFF     ss_serifu_shugaku_kind
    [1919] e 00000000800DD5D8 st 1 sc 5 index=FFFFF     sss_sound_shugaku
    [1920] e 00000000800DD5DC st 1 sc 5 index=FFFFF     now_serifu_shugaku
    [1921] e 00000000800DD5E0 st 1 sc 5 index=FFFFF     now_serifu_shugaku_in
    [1922] e 00000000800DD5E4 st 1 sc 5 index=FFFFF     with_yoshi
    [1923] e 00000000800DD5E8 st 1 sc 5 index=FFFFF     move_in
    [1924] e 00000000800DD5EC st 1 sc 5 index=FFFFF     date_place
    [1925] e 00000000800DD5F0 st 1 sc 5 index=FFFFF     basho_num
    [1926] e 00000000800DD5F4 st 1 sc 5 index=FFFFF     menu_x
    [1927] e 00000000800DD60C st 1 sc 5 index=FFFFF     menu_y
    [1928] e 00000000800DD624 st 1 sc 5 index=FFFFF     menu_w
    [1929] e 00000000800DD63C st 1 sc 5 index=FFFFF     menu_h
    [1930] e 00000000800DD670 st 1 sc 5 index=FFFFF     mdec_iq
    [1931] e 00000000800DD6F4 st 1 sc 5 index=FFFFF     mdec_coef
    [1932] e 00000000800DD7C0 st 1 sc 5 index=FFFFF     DCL_DVLC
    [1933] e 00000000800DDFC0 st 1 sc 5 index=FFFFF     DCC_DVLC
    [1934] e 00000000800DE7C0 st 1 sc 5 index=FFFFF     CF_DVLC
    [1935] e 00000000800EE7C0 st 1 sc 5 index=FFFFF     CF2_DVLC
    [1936] e 00000000800EF8C0 st 1 sc 5 index=FFFFF     CD_debug
    [1937] e 00000000800EF8C4 st 1 sc 5 index=FFFFF     CD_isopen
    [1938] e 00000000800EF8C8 st 1 sc 5 index=FFFFF     CD_comstr
    [1939] e 00000000800EF93C st 1 sc 5 index=FFFFF     CD_intstr
    [1940] e 00000000800EFE10 st 1 sc 5 index=FFFFF     _spu_zerobuf
    [1941] e 00000000800F0230 st 1 sc 5 index=FFFFF     _spu_rev_startaddr
    [1942] e 00000000800F0258 st 1 sc 5 index=FFFFF     _spu_rev_workareasize
    [1943] e 00000000800F05C8 st 1 sc 5 index=FFFFF     GPU_printf
    [1944] e 00000000800F09B0 st 1 sc 5 index=FFFFF     rsin_tbl
    [1945] e 00000000800F11B0 st 1 sc 5 index=FFFFF     rcossin_tbl
    [1946] e 00000000800F55C0 st 1 sc 5 index=FFFFF     Vcount
    [1947] e 00000000800F9AE0 st 1 sc 5 index=FFFFF     sys
    [1948] e 00000000800FB550 st 1 sc 5 index=FFFFF     sys0
    [1949] e 00000000800FBDB0 st 1 sc 5 index=FFFFF     padbuf0
    [1950] e 00000000800FBDF0 st 1 sc 5 index=FFFFF     padbuf1
    [1951] e 00000000800FBE30 st 1 sc 5 index=FFFFF     WorldOT
    [1952] e 00000000800FBE60 st 1 sc 5 index=FFFFF     OTTags
    [1953] e 00000000800FC660 st 1 sc 5 index=FFFFF     GpuPacketArea
    [1954] e 0000000080106660 st 1 sc 5 index=FFFFF     out_packet2
    [1955] e 0000000080128660 st 1 sc 5 index=FFFFF     activeBuff
    [1956] e 0000000080128664 st 1 sc 5 index=FFFFF     cursor_flag
    [1957] e 0000000080128668 st 1 sc 5 index=FFFFF     VB
    [1958] e 000000008012866C st 1 sc 5 index=FFFFF     CE0
    [1959] e 0000000080128670 st 1 sc 5 index=FFFFF     CE1
    [1960] e 0000000080128674 st 1 sc 5 index=FFFFF     CE2
    [1961] e 0000000080128678 st 1 sc 5 index=FFFFF     CE3
    [1962] e 000000008012867C st 1 sc 5 index=FFFFF     CEH0
    [1963] e 0000000080128680 st 1 sc 5 index=FFFFF     CEH1
    [1964] e 0000000080128684 st 1 sc 5 index=FFFFF     CEH2
    [1965] e 0000000080128688 st 1 sc 5 index=FFFFF     CEH3
    [1966] e 0000000080128690 st 1 sc 5 index=FFFFF     class_w
    [1967] e 000000008012B110 st 1 sc 5 index=FFFFF     srn_w
    [1968] e 000000008012B160 st 1 sc 5 index=FFFFF     mod_w
    [1969] e 000000008012B190 st 1 sc 5 index=FFFFF     Sprites
    [1970] e 000000008012BA90 st 1 sc 5 index=FFFFF     Bg
    [1971] e 000000008012BAE0 st 1 sc 5 index=FFFFF     Map
    [1972] e 000000008012BB00 st 1 sc 5 index=FFFFF     Cell
    [1973] e 000000008012BF00 st 1 sc 5 index=FFFFF     C_index
    [1974] e 000000008012C000 st 1 sc 5 index=FFFFF     object
    [1975] e 000000008012C230 st 1 sc 5 index=FFFFF     view
    [1976] e 000000008012C250 st 1 sc 5 index=FFFFF     pslt
    [1977] e 000000008012C280 st 1 sc 5 index=FFFFF     fogp
    [1978] e 000000008012C290 st 1 sc 5 index=FFFFF     coord
    [1979] e 000000008012CD80 st 1 sc 5 index=FFFFF     daen_obj
    [1980] e 000000008012CDB0 st 1 sc 5 index=FFFFF     work_tarao
    [1981] e 000000008012CEB0 st 1 sc 5 index=FFFFF     work_miura
    [1982] e 000000008012CFB0 st 1 sc 5 index=FFFFF     work_takak
    [1983] e 000000008012D0B0 st 1 sc 5 index=FFFFF     work_yamag
    [1984] e 000000008012D1B0 st 1 sc 5 index=FFFFF     work_fuku
    [1985] e 000000008012D1F0 st 1 sc 5 index=FFFFF     load_func
    [1986] e 000000008012D200 st 1 sc 5 index=FFFFF     card
    [1987] e 000000008012F200 st 1 sc 5 index=FFFFF     set_gp
    [1988] e 000000008012F204 st 1 sc 5 index=FFFFF     old_sp
    [1989] e 000000008012F208 st 1 sc 5 index=FFFFF     now_packet_end
    [1990] e 000000008012F20C st 1 sc 5 index=FFFFF     now_packet_end2
    [1991] e 000000008012F210 st 1 sc 5 index=FFFFF     cd_read_end
    [1992] e 000000008012F218 st 1 sc 5 index=FFFFF     rcdresult
    [1993] e 000000008012F220 st 1 sc 5 index=FFFFF     scdresult
    [1994] e 000000008012F228 st 1 sc 5 index=FFFFF     ccdresult
    [1995] e 000000008012F230 st 1 sc 5 index=FFFFF     now_active_area
    [1996] e 000000008012F234 st 1 sc 5 index=FFFFF     don_timer
    [1997] e 000000008012F238 st 1 sc 5 index=FFFFF     POSITION
    [1998] e 000000008012F240 st 1 sc 5 index=FFFFF     string_buff
    [1999] e 000000008012F840 st 1 sc 5 index=FFFFF     now_xa1
    [2000] e 000000008012F844 st 1 sc 5 index=FFFFF     now_xa2
    [2001] e 000000008012F848 st 1 sc 5 index=FFFFF     now_xa_num
    [2002] e 000000008012F84C st 1 sc 5 index=FFFFF     now_xa_on
    [2003] e 000000008012F850 st 1 sc 5 index=FFFFF     mdec_bs
    [2004] e 000000008012F854 st 1 sc 5 index=FFFFF     mdec_rl
    [2005] e 000000008012F858 st 1 sc 5 index=FFFFF     mdec_image
    [2006] e 000000008012F85C st 1 sc 5 index=FFFFF     fd
    [2007] e 000000008012F860 st 1 sc 5 index=FFFFF     vtw
    [2008] e 000000008012F870 st 1 sc 5 index=FFFFF     m
    [2009] e 000000008012F878 st 1 sc 5 index=FFFFF     StCdIntrFlag
    [2010] e 000000008012F880 st 1 sc 5 index=FFFFF     dec_bg_brightness
    [2011] e 000000008012F890 st 1 sc 5 index=FFFFF     GsIDMATRIX
    [2012] e 000000008012F8B0 st 1 sc 5 index=FFFFF     vol_mean
    [2013] e 000000008012F8C0 st 1 sc 5 index=FFFFF     icon_xy
    [2014] e 000000008012F900 st 1 sc 5 index=FFFFF     icon_can_use
    [2015] e 000000008012F910 st 1 sc 5 index=FFFFF     basyo_timer
    [2016] e 000000008012F914 st 1 sc 5 index=FFFFF     mascot
    [2017] e 000000008012F918 st 1 sc 5 index=FFFFF     mascot_hi
    [2018] e 000000008012F919 st 1 sc 5 index=FFFFF     mascot_cw
    [2019] e 000000008012F91C st 1 sc 5 index=FFFFF     sd_col
    [2020] e 000000008012F920 st 1 sc 5 index=FFFFF     sd_pattern_table
    [2021] e 000000008012F924 st 1 sc 5 index=FFFFF     sd_animation_table
    [2022] e 000000008012F928 st 1 sc 5 index=FFFFF     sd_rom_table
    [2023] e 000000008012F92C st 1 sc 5 index=FFFFF     tel_check
    [2024] e 000000008012F933 st 1 sc 5 index=FFFFF     twinbee_mode
    [2025] e 000000008012F940 st 1 sc 5 index=FFFFF     gSDEvt
    [2026] e 000000008012F990 st 1 sc 5 index=FFFFF     gSDInfo
    [2027] e 000000008012F9E0 st 1 sc 5 index=FFFFF     gSDHeadAdrs
    [2028] e 000000008012F9F0 st 1 sc 5 index=FFFFF     gSDBodyAdrs
    [2029] e 000000008012FA00 st 1 sc 5 index=FFFFF     gSDBodyLAdrs
    [2030] e 000000008012FA10 st 1 sc 5 index=FFFFF     gSDBodySize
    [2031] e 000000008012FA20 st 1 sc 5 index=FFFFF     gSDSeqAdrs
    [2032] e 000000008012FAA0 st 1 sc 5 index=FFFFF     gSDSeqReverb
    [2033] e 000000008012FAE0 st 1 sc 5 index=FFFFF     gSDCDLevelInfo
    [2034] e 000000008012FAF0 st 1 sc 5 index=FFFFF     gSDCDLevel
    [2035] e 000000008012FEF0 st 1 sc 5 index=FFFFF     gSDSeqTable
    [2036] e 0000000080130048 st 1 sc 5 index=FFFFF     dc_y
    [2037] e 0000000080130050 st 1 sc 5 index=FFFFF     dc_cr
    [2038] e 0000000080130058 st 1 sc 5 index=FFFFF     dc_cb
    [2039] e 0000000080130060 st 1 sc 5 index=FFFFF     dc_type
    [2040] e 0000000080130068 st 1 sc 5 index=FFFFF     dec_used
    [2041] e 0000000080130070 st 1 sc 5 index=FFFFF     dec_pt
    [2042] e 0000000080130078 st 1 sc 5 index=FFFFF     bs_curt
    [2043] e 0000000080130080 st 1 sc 5 index=FFFFF     CD_cbsync
    [2044] e 0000000080130088 st 1 sc 5 index=FFFFF     CD_cbready
    [2045] e 0000000080130090 st 1 sc 5 index=FFFFF     CD_cbread
    [2046] e 0000000080130098 st 1 sc 5 index=FFFFF     RingAddr
    [2047] e 00000000801300A0 st 1 sc 5 index=FFFFF     FinalSector
    [2048] e 00000000801300A8 st 1 sc 5 index=FFFFF     RingBase
    [2049] e 00000000801300B0 st 1 sc 5 index=FFFFF     MarkCallback
    [2050] e 00000000801308B0 st 1 sc 5 index=FFFFF     VBLANK_MINUS
    [2051] e 00000000801308B8 st 1 sc 5 index=FFFFF     _snd_openflag
    [2052] e 00000000801308C0 st 1 sc 5 index=FFFFF     _snd_ev_flag
    [2053] e 00000000801308C8 st 1 sc 5 index=FFFFF     _snd_seq_s_max
    [2054] e 00000000801308D0 st 1 sc 5 index=FFFFF     _snd_seq_t_max
    [2055] e 00000000801308E0 st 1 sc 5 index=FFFFF     _ss_score
    [2056] e 0000000080130960 st 1 sc 5 index=FFFFF     _snd_seq_no_tick
    [2057] e 0000000080130968 st 1 sc 5 index=FFFFF     _snd_seq_tick_mode
    [2058] e 0000000080130970 st 1 sc 5 index=FFFFF     _svm_vab_used
    [2059] e 0000000080130980 st 1 sc 5 index=FFFFF     _svm_vab_count
    [2060] e 0000000080130990 st 1 sc 5 index=FFFFF     _svm_vab_vh
    [2061] e 00000000801309D0 st 1 sc 5 index=FFFFF     _svm_vh
    [2062] e 00000000801309D8 st 1 sc 5 index=FFFFF     kMaxPrograms
    [2063] e 00000000801309E0 st 1 sc 5 index=FFFFF     _svm_vab_pg
    [2064] e 0000000080130A20 st 1 sc 5 index=FFFFF     _svm_pg
    [2065] e 0000000080130A30 st 1 sc 5 index=FFFFF     _svm_vab_tn
    [2066] e 0000000080130A70 st 1 sc 5 index=FFFFF     _svm_tn
    [2067] e 0000000080130A80 st 1 sc 5 index=FFFFF     _svm_brr_start_addr
    [2068] e 0000000080130AC0 st 1 sc 5 index=FFFFF     _svm_vab_start
    [2069] e 0000000080130B00 st 1 sc 5 index=FFFFF     _svm_vab_total
    [2070] e 0000000080130B40 st 1 sc 5 index=FFFFF     _svm_rattr
    [2071] e 0000000080130B58 st 1 sc 5 index=FFFFF     spuVmMaxVoice
    [2072] e 0000000080130B60 st 1 sc 5 index=FFFFF     _svm_cur
    [2073] e 0000000080130B80 st 1 sc 5 index=FFFFF     _svm_stereo_mono
    [2074] e 0000000080130B88 st 1 sc 5 index=FFFFF     _svm_orev1
    [2075] e 0000000080130B90 st 1 sc 5 index=FFFFF     _svm_orev2
    [2076] e 0000000080130B98 st 1 sc 5 index=FFFFF     _svm_okon1
    [2077] e 0000000080130BA0 st 1 sc 5 index=FFFFF     _svm_okon2
    [2078] e 0000000080130BA8 st 1 sc 5 index=FFFFF     _svm_okof1
    [2079] e 0000000080130BB0 st 1 sc 5 index=FFFFF     _svm_okof2
    [2080] e 0000000080130BB8 st 1 sc 5 index=FFFFF     _svm_damper
    [2081] e 0000000080130BC0 st 1 sc 5 index=FFFFF     _svm_vcf
    [2082] e 0000000080130BC8 st 1 sc 5 index=FFFFF     _svm_auto_kof_mode
    [2083] e 0000000080130BD0 st 1 sc 5 index=FFFFF     _svm_vg
    [2084] e 0000000080130BD8 st 1 sc 5 index=FFFFF     _spu_fd
    [2085] e 0000000080130BE0 st 1 sc 5 index=FFFFF     _spu_trans_mode
    [2086] e 0000000080130BE8 st 1 sc 5 index=FFFFF     _spu_inTransfer
    [2087] e 0000000080130BF0 st 1 sc 5 index=FFFFF     _spu_EVdma
    [2088] e 0000000080130BF8 st 1 sc 5 index=FFFFF     _spu_transferCallback
    [2089] e 0000000080130C00 st 1 sc 5 index=FFFFF     _spu_rev_attr
    [2090] e 0000000080130C18 st 1 sc 5 index=FFFFF     _spu_rev_flag
    [2091] e 0000000080130C20 st 1 sc 5 index=FFFFF     _spu_rev_reserve_wa
    [2092] e 0000000080130C28 st 1 sc 5 index=FFFFF     _spu_rev_offsetaddr
    [2093] e 0000000080130C30 st 1 sc 5 index=FFFFF     _spu_keystat
    [2094] e 0000000080130C38 st 1 sc 5 index=FFFFF     _spu_keyon_bit
    [2095] e 0000000080130C40 st 1 sc 5 index=FFFFF     _spu_keyoff_bit
    [2096] e 0000000080130C50 st 1 sc 5 index=FFFFF     _spu_voice_centerNote
    [2097] e 0000000080130C80 st 1 sc 5 index=FFFFF     _spu_keyevent_time
    [2098] e 0000000080130C88 st 1 sc 5 index=FFFFF     PSDIDX
    [2099] e 0000000080130C90 st 1 sc 5 index=FFFFF     GsDRAWENV
    [2100] e 0000000080130CF0 st 1 sc 5 index=FFFFF     GsDISPENV
    [2101] e 0000000080130D08 st 1 sc 5 index=FFFFF     PSDGPU
    [2102] e 0000000080130D10 st 1 sc 5 index=FFFFF     HWD0
    [2103] e 0000000080130D18 st 1 sc 5 index=FFFFF     VWD0
    [2104] e 0000000080130D20 st 1 sc 5 index=FFFFF     GsIDMATRIX2
    [2105] e 0000000080130D40 st 1 sc 5 index=FFFFF     GsLIGHTWSMATRIX
    [2106] e 0000000080130D60 st 1 sc 5 index=FFFFF     _LC
    [2107] e 0000000080130D80 st 1 sc 5 index=FFFFF     PSDBASEX
    [2108] e 0000000080130D88 st 1 sc 5 index=FFFFF     PSDBASEY
    [2109] e 0000000080130D90 st 1 sc 5 index=FFFFF     CLIP2
    [2110] e 0000000080130D98 st 1 sc 5 index=FFFFF     PSDOFSX
    [2111] e 0000000080130DA0 st 1 sc 5 index=FFFFF     PSDOFSY
    [2112] e 0000000080130DB0 st 1 sc 5 index=FFFFF     GsDSTACK
    [2113] e 00000000801312B0 st 1 sc 5 index=FFFFF     GsWSMATRIX
    [2114] e 00000000801312D0 st 1 sc 5 index=FFFFF     GsLIGHT_MODE
    [2115] e 00000000801312D8 st 1 sc 5 index=FFFFF     GsCLIP3far
    [2116] e 00000000801312E0 st 1 sc 5 index=FFFFF     GsCLIP3near
    [2117] e 00000000801312E8 st 1 sc 5 index=FFFFF     GsOUT_PACKET_P
    [2118] e 00000000801312F0 st 1 sc 5 index=FFFFF     DSTACK
    [2119] e 0000000080131370 st 1 sc 5 index=FFFFF     GsMATE_C
    [2120] e 0000000080131378 st 1 sc 5 index=FFFFF     GsLMODE
    [2121] e 0000000080131380 st 1 sc 5 index=FFFFF     GsNDIV
    [2122] e 0000000080131388 st 1 sc 5 index=FFFFF     GsLIGNR
    [2123] e 0000000080131390 st 1 sc 5 index=FFFFF     GsLIOFF
    [2124] e 0000000080131398 st 1 sc 5 index=FFFFF     GsDISPON
    [2125] e 00000000801313A0 st 1 sc 5 index=FFFFF     GsZOVER
    [2126] e 00000000801313A8 st 1 sc 5 index=FFFFF     GsBACKC
    [2127] e 00000000801313B0 st 1 sc 5 index=FFFFF     GsTRATE
    [2128] e 00000000801313B8 st 1 sc 5 index=FFFFF     GsTON
    [2129] e 00000000801313C0 st 1 sc 5 index=FFFFF     GsLIGHT_FUNC
    [2130] e 00000000801313D0 st 1 sc 5 index=FFFFF     GsLSMATRIX
    [2131] e 00000000801313F0 st 1 sc 5 index=FFFFF     PadIdentifier
    [2132] e 0000000080132000 st 6 sc 1 index=FFFFF     olh_main
    [2133] e 0000000080132070 st 6 sc 1 index=FFFFF     olh_init
    [2134] e 000000008013222C st 6 sc 1 index=FFFFF     olh
    [2135] e 000000008013231C st 6 sc 1 index=FFFFF     olh_exit
    [2136] e 0000000080132430 st 1 sc 2 index=FFFFF     menu0
    [2137] e 0000000080132440 st 1 sc 2 index=FFFFF     menu1
    [2138] e 0000000080132450 st 1 sc 2 index=FFFFF     menu2
    [2139] e 0000000080132460 st 1 sc 2 index=FFFFF     menu3
    [2140] e 0000000080132470 st 1 sc 2 index=FFFFF     menu4
    [2141] e 0000000080132480 st 1 sc 2 index=FFFFF     menu5
    [2142] e 0000000080132490 st 1 sc 2 index=FFFFF     menu6
    [2143] e 00000000801324A0 st 1 sc 2 index=FFFFF     menu7
    [2144] e 00000000801324B0 st 1 sc 2 index=FFFFF     olh_menu
    [2145] e 000000008013233C st 6 sc 1 index=FFFFF     move_menu_title

Some code appears at the end when using `objdump -d`. I'm not sure of its
significance but have included it for completeness.

~~~assembly
olh_main:
        lui     $v1, 0x8010
        lbu     $v1, -21559($v1)
        addiu   $sp, $sp, 0xFFD8
        beq     $v1, $zero, 32
        sw      $ra, 0x14($sp)
        addiu   $at, $zero, 0x1
        beq     $v1, $at, 36
        addiu   $at, $zero, 0x2
        beq     $v1, $at, 44
        nop
        beq     $zero, $zero, 44
        nop
        jal     0x132070
        nop
        beq     $zero, $zero, 28
        nop
        jal     0x13222C
        nop
        beq     $zero, $zero, 12
        nop
        jal     0x13231C
        nop
        jal     0x7C670
        nop
        lw      $ra, 0x14($sp)
        addiu   $sp, $sp, 0x28
        jr      $ra
        nop
olh_init:
        addiu   $sp, $sp, 0xFF40
        sw      $ra, 0x44($sp)
        sw      $fp, 0x40($sp)
        sw      $s7, 0x3C($sp)
        sw      $s6, 0x38($sp)
        sw      $s5, 0x34($sp)
        sw      $s4, 0x30($sp)
        sw      $s3, 0x2C($sp)
        sw      $s2, 0x28($sp)
        sw      $s1, 0x24($sp)
        jal     0x5AAA0
        sw      $s0, 0x20($sp)
        jal     0x5482C
        or      $a0, $zero, $zero
        jal     0x4F144
        addiu   $a0, $zero, 0x1
        addiu   $v0, $zero, 0x64
        lui     $at, 0x8010
        sb      $v0, -25833($at)
        lui     $at, 0x8010
        sb      $v0, -25834($at)
        lui     $at, 0x8010
        lui     $a3, 0x8013
        addiu   $a3, $a3, 0x23A0
        sb      $v0, -25832($at)
        addiu   $a0, $zero, 0xFF60
        addiu   $a1, $zero, 0xFFB0
        addiu   $a2, $zero, 0xF
        jal     0x5ACE0
        sw      $zero, 0x10($sp)
        lui     $a3, 0x8013
        addiu   $a3, $a3, 0x23B4
        or      $a0, $zero, $zero
        addiu   $a1, $zero, 0xFFB0
        addiu   $a2, $zero, 0x1
        jal     0x5ACE0
        sw      $zero, 0x10($sp)
        lui     $a3, 0x8013
        addiu   $a3, $a3, 0x23C8
        addiu   $a0, $zero, 0xA0
        addiu   $a1, $zero, 0xFFB0
        addiu   $a2, $zero, 0x2
        jal     0x5ACE0
        sw      $zero, 0x10($sp)
        lui     $a3, 0x8013
        addiu   $a3, $a3, 0x23DC
        addiu   $a0, $zero, 0x140
        addiu   $a1, $zero, 0xFFB0
        or      $a2, $zero, $zero
        jal     0x5ACE0
        sw      $zero, 0x10($sp)
        lui     $s2, 0x8013
        addiu   $s2, $s2, 0x24B0
        addiu   $s0, $sp, 0xA4
        addiu   $s1, $sp, 0x94
        addiu   $s3, $sp, 0x84
        addiu   $s4, $sp, 0x74
        addiu   $fp, $zero, 0x10
        addiu   $s7, $zero, 0x80
        addiu   $s6, $zero, 0x4E
        addiu   $s5, $zero, 0xFFC0
        sh      $s5, 0($s0)
        sh      $s6, 0($s1)
        sh      $s7, 0($s3)
        sh      $fp, 0($s4)
        lh      $a1, 0($s1)
        lh      $a0, 0($s0)
        lw      $a3, 0($s2)
        sw      $zero, 0x10($sp)
        jal     0x5ACE0
        addiu   $a2, $zero, 0xF
        lui     $t6, 0x8013
        addiu   $t6, $t6, 0x24D0
        addiu   $s2, $s2, 0x4
        addiu   $s0, $s0, 0x2
        addiu   $s1, $s1, 0x2
        addiu   $s3, $s3, 0x2
        bne     $s2, $t6, -68
        addiu   $s4, $s4, 0x2
        addiu   $t7, $sp, 0x84
        addiu   $t8, $sp, 0x74
        sw      $t8, 0x14($sp)
        sw      $t7, 0x10($sp)
        or      $a0, $zero, $zero
        addiu   $a1, $zero, 0x8
        addiu   $a2, $sp, 0xA4
        jal     0x5BC00
        addiu   $a3, $sp, 0x94
        lui     $a3, 0x8013
        addiu   $a3, $a3, 0x23F0
        addiu   $a0, $zero, 0xFF9C
        addiu   $a1, $zero, 0x50
        addiu   $a2, $zero, 0xF
        jal     0x5ACE0
        sw      $zero, 0x10($sp)
        jal     0x5ADDC
        or      $a0, $v0, $zero
        jal     0x4DFDC
        nop
        lw      $ra, 0x44($sp)
        lw      $s0, 0x20($sp)
        lw      $s1, 0x24($sp)
        lw      $s2, 0x28($sp)
        lw      $s3, 0x2C($sp)
        lw      $s4, 0x30($sp)
        lw      $s5, 0x34($sp)
        lw      $s6, 0x38($sp)
        lw      $s7, 0x3C($sp)
        lw      $fp, 0x40($sp)
        jr      $ra
        addiu   $sp, $sp, 0xC0
olh:
        addiu   $sp, $sp, 0xFFD8
        lui     $a1, 0x8013
        lui     $a2, 0x8013
        sw      $ra, 0x14($sp)
        lh      $a2, -31046($a2)
        lh      $a1, -31050($a1)
        jal     0x5BD14
        addiu   $a0, $zero, 0x1
        jal     0x5CDDC
        addiu   $a0, $zero, 0x1
        jal     0x5BFA0
        addiu   $a0, $zero, 0x1
        lui     $t6, 0x8010
        lbu     $t6, -21677($t6)
        nop
        sltiu   $at, $t6, 0x8
        beq     $at, $zero, 148
        sll     $t6, $t6, 2
        lui     $at, 0x8013
        addu    $at, $at, $t6
        lw      $t6, 0x2408($at)
        nop
        jr      $t6
        nop
        jal     0x4E0B8
        addiu   $a0, $zero, 0x10
        beq     $zero, $zero, 108
        nop
        jal     0x4E0B8
        addiu   $a0, $zero, 0x20
        beq     $zero, $zero, 92
        nop
        jal     0x4E0B8
        addiu   $a0, $zero, 0x30
        beq     $zero, $zero, 76
        nop
        jal     0x4E0B8
        addiu   $a0, $zero, 0x40
        beq     $zero, $zero, 60
        nop
        jal     0x4E0B8
        addiu   $a0, $zero, 0x50
        beq     $zero, $zero, 44
        nop
        jal     0x4E0B8
        addiu   $a0, $zero, 0x60
        beq     $zero, $zero, 28
        nop
        jal     0x4E0B8
        addiu   $a0, $zero, 0x70
        beq     $zero, $zero, 12
        nop
        jal     0x4E0B8
        addiu   $a0, $zero, 0x3
        jal     0x13233C
        nop
        lw      $ra, 0x14($sp)
        addiu   $sp, $sp, 0x28
        jr      $ra
        nop
olh_exit:
        addiu   $sp, $sp, 0xFFD8
        sw      $ra, 0x14($sp)
        jal     0x4E04C
        addiu   $a0, $zero, 0x41
        lw      $ra, 0x14($sp)
        addiu   $sp, $sp, 0x28
        jr      $ra
        nop
move_menu_title:
        addiu   $sp, $sp, 0xFFD0
        sw      $s1, 0x18($sp)
        sw      $s0, 0x14($sp)
        sw      $ra, 0x1C($sp)
        or      $s0, $zero, $zero
        addiu   $s1, $zero, 0x4
        jal     0x5AEC8
        or      $a0, $s0, $zero
        lh      $t6, 0($v0)
        addiu   $s0, $s0, 0x1
        addiu   $t7, $t6, 0xFFFE
        bne     $s0, $s1, -24
        sh      $t7, 0($v0)
        lh      $v1, 0($v0)
        nop
        slti    $at, $v1, 0xFE20
        beq     $at, $zero, 8
        addiu   $t8, $v1, 0x280
        sh      $t8, 0($v0)
        lw      $ra, 0x1C($sp)
        lw      $s0, 0x14($sp)
        lw      $s1, 0x18($sp)
        jr      $ra
        addiu   $sp, $sp, 0x30
        nop
        swl     $v0, -14718($gp)
        swl     $v0, -8318($gp)
        swc0    $s3, -15224($a0)
        nop
        swl     $v0, -14718($gp)
        swl     $v0, -8318($gp)
        swc0    $s3, -15224($a0)
        nop
        swl     $v0, -14718($gp)
        swl     $v0, -8318($gp)
        swc0    $s3, -15224($a0)
        nop
        swl     $v0, -14718($gp)
        swl     $v0, -8318($gp)
        swc0    $s3, -15224($a0)
        nop
        nop
        lwc1    $v0, -3710($t4)
        sb      $v0, -19582($s4)
        nop
        lb      $s3, 0x228C($zero)
        lb      $s3, 0x229C($zero)
        lb      $s3, 0x22AC($zero)
        lb      $s3, 0x22BC($zero)
        lb      $s3, 0x22CC($zero)
        lb      $s3, 0x22DC($zero)
        lb      $s3, 0x22EC($zero)
        lb      $s3, 0x22FC($zero)
        nop
        nop
        lb      $v1, 0x6583($a0)
        swc2    $s2, -8816($a0)
        nop
        lb      $v1, -32381($s4)
        sra     $t5, $zero, 2
        sra     $t4, $zero, 30
        lwl     $v1, 0x4983($s4)
        lb      $v1, 0x5983($a0)
        nop
        lwl     $v1, 0x5C83($gp)
        nop
        nop
        sra     $s0, $zero, 2
        nop
        lwc0    $v0, -23923($t4)
        swc2    $t7, -17022($s4)
        break   0x21E
        nop
        lwc2    $v0, -32637($t4)
        swc2    $v0, -8298($t4)
        nop
        lb      $s3, 0x2430($zero)
        lb      $s3, 0x2440($zero)
        lb      $s3, 0x2450($zero)
        lb      $s3, 0x2460($zero)
        lb      $s3, 0x2470($zero)
        lb      $s3, 0x2480($zero)
        lb      $s3, 0x2490($zero)
        lb      $s3, 0x24A0($zero)
~~~

### Calculated variable data

This table gives the address of each function/variable start, and the number of
bytes until the next function, in decimal, hex, and in bytes divided by four
(i.e. 32-bit lines of assembly as they appear in Ghidra, useful for eyeballing
lenghts of functions for identification).

While these don't match the executable precisely, they provided a useful
starting point for identifying functions and variables based on their length and
the order they appear in the file.

Address    | Len (d)| Len (h)| Lines  | Name
-----------|-------:|-------:|-------:|------------------------
0x8004c000 |  184   | 0xb8   | 46     | `warm_reset_init`
0x8004c0b8 |  520   | 0x208  | 130    | `draw_and_disp_env_init`
0x8004c2c0 |  20    | 0x14   | 5      | `print_dr_env`
0x8004c2d4 |  20    | 0x14   | 5      | `print_di_env`
0x8004c2e8 |  316   | 0x13c  | 79     | `vram_clear`
0x8004c424 |  668   | 0x29c  | 167    | `system_init`
0x8004c6c0 |  48    | 0x30   | 12     | `prim_init`
0x8004c6f0 |  152   | 0x98   | 38     | `sprite_init`
0x8004c788 |  500   | 0x1f4  | 125    | `bg_init`
0x8004c97c |  52    | 0x34   | 13     | `game_system_init`
0x8004c9b0 |  56    | 0x38   | 14     | `_game_work_init_set`
0x8004c9e8 |  320   | 0x140  | 80     | `debug_data_init`
0x8004cb28 |  336   | 0x150  | 84     | `game_data_init`
0x8004cc78 |  544   | 0x220  | 136    | `play_data_init`
0x8004ce98 |  912   | 0x390  | 228    | `girl_data_init`
0x8004d228 |  620   | 0x26c  | 155    | `etc_data_init`
0x8004d494 |  8     | 0x8    | 2      | `addr_init_main_rom`
0x8004d49c |  20    | 0x14   | 5      | `addr_init_main_dat`
0x8004d4b0 |  100   | 0x64   | 25     | `main`
0x8004d514 |  636   | 0x27c  | 159    | `_main`
0x8004d790 |  696   | 0x2b8  | 174    | `girl_data_print`
0x8004da48 |  152   | 0x98   | 38     | `swap_env`
0x8004dae0 |  228   | 0xe4   | 57     | `game_info_disp`
0x8004dbc4 |  44    | 0x2c   | 11     | `vblank_callback`
0x8004dbf0 |  24    | 0x18   | 6      | `myrand`
0x8004dc08 |  124   | 0x7c   | 31     | `cold_reset_init`
0x8004dc84 |  48    | 0x30   | 12     | `cashe_f`
0x8004dcb4 |  124   | 0x7c   | 31     | `vblank_ev_set`
0x8004dd30 |  572   | 0x23c  | 143    | `game_main`
0x8004df6c |  112   | 0x70   | 28     | `step_up`
0x8004dfdc |  68    | 0x44   | 17     | `sub_step_up`
0x8004e020 |  44    | 0x2c   | 11     | `sub_sub_step_up`
0x8004e04c |  108   | 0x6c   | 27     | `goto_step`
0x8004e0b8 |  56    | 0x38   | 14     | `goto_sub_step`
0x8004e0f0 |  32    | 0x20   | 8      | `goto_sub_sub_step`
0x8004e110 |  132   | 0x84   | 33     | `check_load_func`
0x8004e194 |  236   | 0xec   | 59     | `step_display_func`
0x8004e280 |  300   | 0x12c  | 75     | `PadDataRead`
0x8004e3ac |  600   | 0x258  | 150    | `controller_check`
0x8004e604 |  824   | 0x338  | 206    | `_pad_data_read_mouse`
0x8004e93c |  176   | 0xb0   | 44     | `MyPadRead`
0x8004e9ec |  716   | 0x2cc  | 179    | `_pad_data_read_pad`
0x8004ecb8 |  188   | 0xbc   | 47     | `konami_command_check`
0x8004ed74 |  12    | 0xc    | 3      | `pause_func`
0x8004ed80 |  944   | 0x3b0  | 236    | `vblank_function`
0x8004f130 |  20    | 0x14   | 5      | `draw2d3d`
0x8004f144 |  36    | 0x24   | 9      | `back_clear_switch`
0x8004f168 |  108   | 0x6c   | 27     | `load_palette`
0x8004f1d4 |  128   | 0x80   | 32     | `load_csr_ab`
0x8004f254 |  132   | 0x84   | 33     | `load_csr_tp`
0x8004f2d8 |  240   | 0xf0   | 60     | `csr_load_vram`
0x8004f3c8 |  2024  | 0x7e8  | 506    | `palette_load_vram`
0x8004fbb0 |  68    | 0x44   | 17     | `LoadSquare`
0x8004fbf4 |  80    | 0x50   | 20     | `MoveSquare`
0x8004fc44 |  68    | 0x44   | 17     | `StoreSquare`
0x8004fc88 |  764   | 0x2fc  | 191    | `show_packet_use_box`
0x8004ff84 |  708   | 0x2c4  | 177    | `show_vcnt_info`
0x80050248 |  88    | 0x58   | 22     | `move_palette`
0x800502a0 |  60    | 0x3c   | 15     | `put_sd_error`
0x800502dc |  112   | 0x70   | 28     | `print_sd_error`
0x8005034c |  156   | 0x9c   | 39     | `SD_Call`
0x800503e8 |  152   | 0x98   | 38     | `seq_switch`
0x80050480 |  16    | 0x10   | 4      | `get_seq_state`
0x80050490 |  16    | 0x10   | 4      | `get_now_seq`
0x800504a0 |  92    | 0x5c   | 23     | `pcm_system_reset`
0x800504fc |  1004  | 0x3ec  | 251    | `main_pcm_read`
0x800508e8 |  300   | 0x12c  | 75     | `main_pcm_trans2`
0x80050a14 |  288   | 0x120  | 72     | `trans_spu_local`
0x80050b34 |  376   | 0x178  | 94     | `main_pcm_trans`
0x80050cac |  120   | 0x78   | 30     | `vab_State`
0x80050d24 |  236   | 0xec   | 59     | `current_seq_call`
0x80050e10 |  16    | 0x10   | 4      | `now_trans_pointer`
0x80050e20 |  12    | 0xc    | 3      | `change_trans_pointer`
0x80050e2c |  16    | 0x10   | 4      | `t_cdreadcallback`
0x80050e3c |  100   | 0x64   | 25     | `t_cdsynccallback`
0x80050ea0 |  64    | 0x40   | 16     | `CDQ_init`
0x80050ee0 |  252   | 0xfc   | 63     | `cd_command_set`
0x80050fdc |  536   | 0x218  | 134    | `Control_CD`
0x800511f4 |  2032  | 0x7f0  | 508    | `Control_CD_main`
0x800519e4 |  56    | 0x38   | 14     | `get_CD_l_com`
0x80051a1c |  16    | 0x10   | 4      | `get_CD_State2`
0x80051a2c |  16    | 0x10   | 4      | `get_reads`
0x80051a3c |  16    | 0x10   | 4      | `get_CD_State`
0x80051a4c |  440   | 0x1b8  | 110    | `check_head_position`
0x80051c04 |  16    | 0x10   | 4      | `get_head_position`
0x80051c14 |  12    | 0xc    | 3      | `get_XAsector`
0x80051c20 |  48    | 0x30   | 12     | `set_XAsector`
0x80051c50 |  120   | 0x78   | 30     | `p_cd2_debugprint`
0x80051cc8 |  12    | 0xc    | 3      | `cdcommake_a`
0x80051cd4 |  64    | 0x40   | 16     | `cdreaddata`
0x80051d14 |  68    | 0x44   | 17     | `cdreaddata2`
0x80051d58 |  124   | 0x7c   | 31     | `check_sum_check`
0x80051dd4 |  72    | 0x48   | 18     | `Control_CD_sub`
0x80051e1c |  292   | 0x124  | 73     | `Control_CD_print`
0x80051f40 |  180   | 0xb4   | 45     | `p_error`
0x80051ff4 |  244   | 0xf4   | 61     | `keta_n`
0x800520e8 |  208   | 0xd0   | 52     | `bcd2a`
0x800521b8 |  884   | 0x374  | 221    | `make_fan`
0x8005252c |  2708  | 0xa94  | 677    | `disp_fan`
0x80052fc0 |  16    | 0x10   | 4      | `don_init`
0x80052fd0 |  352   | 0x160  | 88     | `don_move`
0x80053130 |  3112  | 0xc28  | 778    | `class_set`
0x80053d58 |  148   | 0x94   | 37     | `tpage_buf_clear_all`
0x80053dec |  88    | 0x58   | 22     | `tpage_buf_clear`
0x80053e44 |  300   | 0x12c  | 75     | `_sys_default_tpage_set`
0x80053f70 |  168   | 0xa8   | 42     | `load_tpage_buf_lock`
0x80054018 |  232   | 0xe8   | 58     | `search_load_tpage_buf_lock`
0x80054100 |  388   | 0x184  | 97     | `search_tpage_multi`
0x80054284 |  616   | 0x268  | 154    | `search_tpage`
0x800544ec |  616   | 0x268  | 154    | `search_tpage8`
0x80054754 |  36    | 0x24   | 9      | `class_switch`
0x80054778 |  116   | 0x74   | 29     | `class_clear`
0x800547ec |  64    | 0x40   | 16     | `class_clear_f`
0x8005482c |  172   | 0xac   | 43     | `class_clear_all`
0x800548d8 |  160   | 0xa0   | 40     | `class_clear_n`
0x80054978 |  16    | 0x10   | 4      | `get_brightness`
0x80054988 |  24    | 0x18   | 6      | `clear_brightness`
0x800549a0 |  112   | 0x70   | 28     | `set_brightness`
0x80054a10 |  16    | 0x10   | 4      | `set_brightness_d`
0x80054a20 |  48    | 0x30   | 12     | `SetWorkBase`
0x80054a50 |  80    | 0x50   | 20     | `GetWorkBase`
0x80054aa0 |  616   | 0x268  | 154    | `sprite_set_gpu_poly_ft4`
0x80054d08 |  168   | 0xa8   | 42     | `goto_tpage`
0x80054db0 |  108   | 0x6c   | 27     | `safe_env`
0x80054e1c |  160   | 0xa0   | 40     | `dtd_on_tpage`
0x80054ebc |  128   | 0x80   | 32     | `dtd_on`
0x80054f3c |  1124  | 0x464  | 281    | `_sprite_set_light_effect1`
0x800553a0 |  1452  | 0x5ac  | 363    | `_sprite_set_box_shade`
0x8005594c |  852   | 0x354  | 213    | `sprite_set_gpu_sprt2`
0x80055ca0 |  348   | 0x15c  | 87     | `line_set`
0x80055dfc |  84    | 0x54   | 21     | `box_set`
0x80055e50 |  628   | 0x274  | 157    | `bg_set`
0x800560c4 |  924   | 0x39c  | 231    | `mozaiku_show`
0x80056460 |  1024  | 0x400  | 256    | `mozaiku_show2`
0x80056860 |  1028  | 0x404  | 257    | `spot_light`
0x80056c64 |  640   | 0x280  | 160    | `night_parade_effect`
0x80056ee4 |  588   | 0x24c  | 147    | `blur_area`
0x80057130 |  176   | 0xb0   | 44     | `white_light`
0x800571e0 |  76    | 0x4c   | 19     | `pn_switch`
0x8005722c |  40    | 0x28   | 10     | `pn_set`
0x80057254 |  16    | 0x10   | 4      | `get_pn_flag`
0x80057264 |  56    | 0x38   | 14     | `number_font_load`
0x8005729c |  32    | 0x20   | 8      | `show_number`
0x800572bc |  820   | 0x334  | 205    | `show_number_col`
0x800575f0 |  400   | 0x190  | 100    | `show_number_hex`
0x80057780 |  32    | 0x20   | 8      | `show_string_e`
0x800577a0 |  528   | 0x210  | 132    | `show_string_e_col`
0x800579b0 |  640   | 0x280  | 160    | `col2mono`
0x80057c30 |  12    | 0xc    | 3      | `printcolor`
0x80057c3c |  12    | 0xc    | 3      | `printrgb`
0x80057c48 |  1072  | 0x430  | 268    | `make_color_bar`
0x80058078 |  1540  | 0x604  | 385    | `make_color_bar16`
0x8005867c |  580   | 0x244  | 145    | `col2sepia`
0x800588c0 |  3224  | 0xc98  | 806    | `srn_tpage_show`
0x80059558 |  664   | 0x298  | 166    | `srn_vram_set`
0x800597f0 |  168   | 0xa8   | 42     | `move_255_line`
0x80059898 |  752   | 0x2f0  | 188    | `mod_trans_vram`
0x80059b88 |  1036  | 0x40c  | 259    | `get_fnt`
0x80059f94 |  224   | 0xe0   | 56     | `printpix`
0x8005a074 |  804   | 0x324  | 201    | `mod_set_gpu`
0x8005a398 |  780   | 0x30c  | 195    | `mod_set`
0x8005a6a4 |  596   | 0x254  | 149    | `srn_set`
0x8005a8f8 |  252   | 0xfc   | 63     | `srn_init`
0x8005a9f4 |  172   | 0xac   | 43     | `mod_init`
0x8005aaa0 |  404   | 0x194  | 101    | `k_sys_clear`
0x8005ac34 |  48    | 0x30   | 12     | `change_k_w`
0x8005ac64 |  124   | 0x7c   | 31     | `k_printf`
0x8005ace0 |  252   | 0xfc   | 63     | `set_kanji_string`
0x8005addc |  184   | 0xb8   | 46     | `k_disp_start`
0x8005ae94 |  52    | 0x34   | 13     | `k_disp_switch`
0x8005aec8 |  44    | 0x2c   | 11     | `get_k_work`
0x8005aef4 |  12    | 0xc    | 3      | `get_ksys`
0x8005af00 |  76    | 0x4c   | 19     | `set_k_work`
0x8005af4c |  164   | 0xa4   | 41     | `k_reset`
0x8005aff0 |  20    | 0x14   | 5      | `k_sub_reset_point_set`
0x8005b004 |  40    | 0x28   | 10     | `k_sub_reset`
0x8005b02c |  40    | 0x28   | 10     | `k_sub_disp_start`
0x8005b054 |  240   | 0xf0   | 60     | `k_disp_goto_line_end`
0x8005b144 |  40    | 0x28   | 10     | `k_speed_set`
0x8005b16c |  16    | 0x10   | 4      | `get_k_speed`
0x8005b17c |  144   | 0x90   | 36     | `k_disp_inc`
0x8005b20c |  44    | 0x2c   | 11     | `check_end_k`
0x8005b238 |  16    | 0x10   | 4      | `check_set_k`
0x8005b248 |  288   | 0x120  | 72     | `get_now_k`
0x8005b368 |  1112  | 0x458  | 278    | `disp_string`
0x8005b7c0 |  252   | 0xfc   | 63     | `load_string`
0x8005b8bc |  396   | 0x18c  | 99     | `vload_font`
0x8005ba48 |  440   | 0x1b8  | 110    | `melt_font`
0x8005bc00 |  276   | 0x114  | 69     | `menu_set`
0x8005bd14 |  260   | 0x104  | 65     | `menu_check`
0x8005be18 |  228   | 0xe4   | 57     | `menu_check_1`
0x8005befc |  164   | 0xa4   | 41     | `menu_check_2`
0x8005bfa0 |  1776  | 0x6f0  | 444    | `menu_bar_select`
0x8005c690 |  1784  | 0x6f8  | 446    | `get_near_menu`
0x8005cd88 |  84    | 0x54   | 21     | `menu_bar_color`
0x8005cddc |  208   | 0xd0   | 52     | `menu_bar_show`
0x8005ceac |  340   | 0x154  | 85     | `x_taku_menu_set`
0x8005d000 |  132   | 0x84   | 33     | `x_taku_string_set`
0x8005d084 |  144   | 0x90   | 36     | `gnsx`
0x8005d114 |  388   | 0x184  | 97     | `sndisp`
0x8005d298 |  1052  | 0x41c  | 263    | `sndi`
0x8005d6b4 |  12    | 0xc    | 3      | `set_c_girl`
0x8005d6c0 |  208   | 0xd0   | 52     | `get_g_name`
0x8005d790 |  1376  | 0x560  | 344    | `get_p_name`
0x8005dcf0 |  224   | 0xe0   | 56     | `get_g_zyotai_s`
0x8005ddd0 |  148   | 0x94   | 37     | `get_g_zyotai_h`
0x8005de64 |  480   | 0x1e0  | 120    | `menu_girl_taku_set`
0x8005e044 |  580   | 0x244  | 145    | `xa_wait`
0x8005e288 |  92    | 0x5c   | 23     | `xa_wait2`
0x8005e2e4 |  252   | 0xfc   | 63     | `xa_set_m`
0x8005e3e0 |  1068  | 0x42c  | 267    | `xa_wait_m`
0x8005e80c |  1600  | 0x640  | 400    | `get_h_tokimeki`
0x8005ee4c |  124   | 0x7c   | 31     | `get_h_yuukou`
0x8005eec8 |  80    | 0x50   | 20     | `get_h_tokimeki_table`
0x8005ef18 |  80    | 0x50   | 20     | `get_h_yuukou_table`
0x8005ef68 |  48    | 0x30   | 12     | `birth_day_check`
0x8005ef98 |  140   | 0x8c   | 35     | `birth_day_check_days`
0x8005f024 |  200   | 0xc8   | 50     | `ending_para_check_fuji`
0x8005f0ec |  1040  | 0x410  | 260    | `ending_para_check_else`
0x8005f4fc |  276   | 0x114  | 69     | `get_grp`
0x8005f610 |  56    | 0x38   | 14     | `club_undo_check`
0x8005f648 |  232   | 0xe8   | 58     | `get_club_girl`
0x8005f730 |  92    | 0x5c   | 23     | `dec_env_set`
0x8005f78c |  340   | 0x154  | 85     | `decdct`
0x8005f8e0 |  72    | 0x48   | 18     | `card_ev_set`
0x8005f928 |  228   | 0xe4   | 57     | `Sw_Start`
0x8005fa0c |  228   | 0xe4   | 57     | `Hw_Start`
0x8005faf0 |  200   | 0xc8   | 50     | `Sw_Test`
0x8005fbb8 |  88    | 0x58   | 22     | `Sw_Clear`
0x8005fc10 |  204   | 0xcc   | 51     | `Hw_Test`
0x8005fcdc |  88    | 0x58   | 22     | `Hw_Clear`
0x8005fd34 |  104   | 0x68   | 26     | `Hw_Stop`
0x8005fd9c |  120   | 0x78   | 30     | `start_card`
0x8005fe14 |  124   | 0x7c   | 31     | `stop_card`
0x8005fe90 |  28    | 0x1c   | 7      | `goto_cs`
0x8005feac |  5260  | 0x148c | 1315   | `Control_CARD_main`
0x80061338 |  140   | 0x8c   | 35     | `make_file`
0x800613c4 |  152   | 0x98   | 38     | `delete_file`
0x8006145c |  324   | 0x144  | 81     | `loadfile`
0x800615a0 |  684   | 0x2ac  | 171    | `savefile`
0x8006184c |  212   | 0xd4   | 53     | `find_card`
0x80061920 |  60    | 0x3c   | 15     | `system_check`
0x8006195c |  104   | 0x68   | 26     | `card_check`
0x800619c4 |  40    | 0x28   | 10     | `card_w_clear`
0x800619ec |  552   | 0x228  | 138    | `cardfile_init`
0x80061c14 |  792   | 0x318  | 198    | `sys0w2card`
0x80061f2c |  524   | 0x20c  | 131    | `card2sys0w`
0x80062138 |  1124  | 0x464  | 281    | `sysw2card`
0x8006259c |  264   | 0x108  | 66     | `card_check_sum_check`
0x800626a4 |  1540  | 0x604  | 385    | `card2sysw`
0x80062ca8 |  520   | 0x208  | 130    | `get_file_name`
0x80062eb0 |  944   | 0x3b0  | 236    | `vram_test`
0x80063260 |  240   | 0xf0   | 60     | `exit_function`
0x80063350 |  36    | 0x24   | 9      | `set_movie_offset`
0x80063374 |  136   | 0x88   | 34     | `strInit`
0x800633fc |  240   | 0xf0   | 60     | `strSetDefDecEnv`
0x800634ec |  640   | 0x280  | 160    | `strCallback`
0x8006376c |  172   | 0xac   | 43     | `strNextVlc`
0x80063818 |  496   | 0x1f0  | 124    | `strNext`
0x80063a08 |  148   | 0x94   | 37     | `strSync`
0x80063a9c |  108   | 0x6c   | 27     | `strKickCD`
0x80063b08 |  1224  | 0x4c8  | 306    | `movie_main`
0x80063fd0 |  164   | 0xa4   | 41     | `song_base_set`
0x80064074 |  556   | 0x22c  | 139    | `song_set`
0x800642a0 |  12    | 0xc    | 3      | `set_dec_bri`
0x800642ac |  16    | 0x10   | 4      | `get_last_gamen_mode`
0x800642bc |  76    | 0x4c   | 19     | `dec_bg_reset`
0x80064308 |  32    | 0x20   | 8      | `dec_bg_show_switch`
0x80064328 |  20    | 0x14   | 5      | `dec_bg_show_set`
0x8006433c |  240   | 0xf0   | 60     | `dec_bg_cd_read`
0x8006442c |  252   | 0xfc   | 63     | `dec_bg_init`
0x80064528 |  208   | 0xd0   | 52     | `vram_full_move`
0x800645f8 |  484   | 0x1e4  | 121    | `goto_step_bg_out`
0x800647dc |  1228  | 0x4cc  | 307    | `dec_bg_show`
0x80064ca8 |  12    | 0xc    | 3      | `set_tbg_bri`
0x80064cb4 |  1648  | 0x670  | 412    | `bg_show_girl_out`
0x80065324 |  2444  | 0x98c  | 611    | `bg_change`
0x80065cb0 |  128   | 0x80   | 32     | `initView`
0x80065d30 |  272   | 0x110  | 68     | `initLight`
0x80065e40 |  92    | 0x5c   | 23     | `initCoordinate`
0x80065e9c |  144   | 0x90   | 36     | `initModelingData_init`
0x80065f2c |  156   | 0x9c   | 39     | `initModelingData`
0x80065fc8 |  76    | 0x4c   | 19     | `all_object_disp_off`
0x80066014 |  68    | 0x44   | 17     | `swap_env3`
0x80066058 |  212   | 0xd4   | 53     | `set_256_mode`
0x8006612c |  212   | 0xd4   | 53     | `set_512_mode`
0x80066200 |  696   | 0x2b8  | 174    | `class_3d_set`
0x800664b8 |  120   | 0x78   | 30     | `class_clear_3d`
0x80066530 |  144   | 0x90   | 36     | `MouseState`
0x800665c0 |  16    | 0x10   | 4      | `InitMouse`
0x800665d0 |  88    | 0x58   | 22     | `RangeMouse`
0x80066628 |  20    | 0x14   | 5      | `SenseMouse`
0x8006663c |  68    | 0x44   | 17     | `SetMouse`
0x80066680 |  448   | 0x1c0  | 112    | `MouseRead`
0x80066840 |  128   | 0x80   | 32     | `_load_vram`
0x800668c0 |  40    | 0x28   | 10     | `default_data_vram_load`
0x800668e8 |  536   | 0x218  | 134    | `main_data_vram_load`
0x80066b00 |  276   | 0x114  | 69     | `default_data_read_cd`
0x80066c14 |  388   | 0x184  | 97     | `tokimeki_default_chara_init`
0x80066d98 |  152   | 0x98   | 38     | `load_vram`
0x80066e30 |  240   | 0xf0   | 60     | `game_mode`
0x80066f20 |  220   | 0xdc   | 55     | `game_mode_init_all`
0x80066ffc |  212   | 0xd4   | 53     | `game_mode_init`
0x800670d0 |  96    | 0x60   | 24     | `game_mode_init0`
0x80067130 |  40    | 0x28   | 10     | `game_mode_init0_wait`
0x80067158 |  216   | 0xd8   | 54     | `game_mode_cal_font_load`
0x80067230 |  1084  | 0x43c  | 271    | `game_mode_init1`
0x8006766c |  124   | 0x7c   | 31     | `dec_evening_read`
0x800676e8 |  80    | 0x50   | 20     | `game_mode_cdread`
0x80067738 |  144   | 0x90   | 36     | `sunday_evening_icon_phase`
0x800677c8 |  240   | 0xf0   | 60     | `byouki_show`
0x800678b8 |  84    | 0x54   | 21     | `game_mode_main`
0x8006790c |  148   | 0x94   | 37     | `hitsuji_check`
0x800679a0 |  156   | 0x9c   | 39     | `olh_check`
0x80067a3c |  168   | 0xa8   | 42     | `radio_check`
0x80067ae4 |  168   | 0xa8   | 42     | `radio_check_m`
0x80067b8c |  248   | 0xf8   | 62     | `mascot_speech_check_m`
0x80067c84 |  196   | 0xc4   | 49     | `mascot_speech_check`
0x80067d48 |  96    | 0x60   | 24     | `game_mode_main0`
0x80067da8 |  524   | 0x20c  | 131    | `icon_check`
0x80067fb4 |  104   | 0x68   | 26     | `callendar_disp`
0x8006801c |  112   | 0x70   | 28     | `callendar_disp_init`
0x8006808c |  112   | 0x70   | 28     | `callendar_disp_main`
0x800680fc |  40    | 0x28   | 10     | `callendar_disp_exit`
0x80068124 |  268   | 0x10c  | 67     | `data_save_load`
0x80068230 |  304   | 0x130  | 76     | `data_save_load_init`
0x80068360 |  208   | 0xd0   | 52     | `data_save_load_mem_card_check`
0x80068430 |  184   | 0xb8   | 46     | `data_save_load_main`
0x800684e8 |  408   | 0x198  | 102    | `data_save_init`
0x80068680 |  284   | 0x11c  | 71     | `data_save`
0x8006879c |  72    | 0x48   | 18     | `data_save_exit`
0x800687e4 |  392   | 0x188  | 98     | `data_load_init`
0x8006896c |  248   | 0xf8   | 62     | `data_load`
0x80068a64 |  308   | 0x134  | 77     | `data_load_exit`
0x80068b98 |  56    | 0x38   | 14     | `mem_card_wait`
0x80068bd0 |  664   | 0x298  | 166    | `system_config`
0x80068e68 |  312   | 0x138  | 78     | `system_config_init`
0x80068fa0 |  364   | 0x16c  | 91     | `system_moji_set`
0x8006910c |  292   | 0x124  | 73     | `system_config_root_menu`
0x80069230 |  308   | 0x134  | 77     | `system_config_moji_speed_init`
0x80069364 |  332   | 0x14c  | 83     | `system_config_moji_speed`
0x800694b0 |  64    | 0x40   | 16     | `system_config_moji_speed_exit`
0x800694f0 |  308   | 0x134  | 77     | `system_config_icon_mode_init`
0x80069624 |  448   | 0x1c0  | 112    | `system_config_icon_mode`
0x800697e4 |  64    | 0x40   | 16     | `system_config_icon_mode_exit`
0x80069824 |  308   | 0x134  | 77     | `system_config_mouse_mode_init`
0x80069958 |  200   | 0xc8   | 50     | `system_config_mouse_mode`
0x80069a20 |  64    | 0x40   | 16     | `system_config_mouse_mode_exit`
0x80069a60 |  280   | 0x118  | 70     | `system_config_mouse_botton_mode_init`
0x80069b78 |  260   | 0x104  | 65     | `system_config_mouse_botton_mode`
0x80069c7c |  64    | 0x40   | 16     | `system_config_mouse_botton_mode_exit`
0x80069cbc |  280   | 0x118  | 70     | `system_config_mouse_click_mode_init`
0x80069dd4 |  260   | 0x104  | 65     | `system_config_mouse_click_mode`
0x80069ed8 |  64    | 0x40   | 16     | `system_config_mouse_click_mode_exit`
0x80069f18 |  336   | 0x150  | 84     | `system_config_mouse_click_speed_init`
0x8006a068 |  264   | 0x108  | 66     | `system_config_mouse_click_speed`
0x8006a170 |  64    | 0x40   | 16     | `system_config_mouse_click_speed_exit`
0x8006a1b0 |  436   | 0x1b4  | 109    | `system_config_pad_mode_init`
0x8006a364 |  620   | 0x26c  | 155    | `system_config_pad_mode`
0x8006a5d0 |  64    | 0x40   | 16     | `system_config_pad_mode_exit`
0x8006a610 |  456   | 0x1c8  | 114    | `system_config_cursor_speed_init`
0x8006a7d8 |  656   | 0x290  | 164    | `system_config_cursor_speed`
0x8006aa68 |  64    | 0x40   | 16     | `system_config_cursor_speed_exit`
0x8006aaa8 |  308   | 0x134  | 77     | `system_config_sound_mode_init`
0x8006abdc |  412   | 0x19c  | 103    | `system_config_sound_mode`
0x8006ad78 |  64    | 0x40   | 16     | `system_config_sound_mode_exit`
0x8006adb8 |  40    | 0x28   | 10     | `system_config_exit`
0x8006ade0 |  532   | 0x214  | 133    | `system_mascot_init`
0x8006aff4 |  212   | 0xd4   | 53     | `system_mascot_select`
0x8006b0c8 |  32    | 0x20   | 8      | `system_mascot_exit`
0x8006b0e8 |  168   | 0xa8   | 42     | `join_club`
0x8006b190 |  64    | 0x40   | 16     | `join_club_init`
0x8006b1d0 |  252   | 0xfc   | 63     | `join_club_select`
0x8006b2cc |  544   | 0x220  | 136    | `join_club_message`
0x8006b4ec |  40    | 0x28   | 10     | `join_club_exit`
0x8006b514 |  280   | 0x118  | 70     | `uwasa_set`
0x8006b62c |  84    | 0x54   | 21     | `uwasa_init`
0x8006b680 |  84    | 0x54   | 21     | `uwasa_main0`
0x8006b6d4 |  32    | 0x20   | 8      | `uwasa_exit0`
0x8006b6f4 |  84    | 0x54   | 21     | `uwasa0`
0x8006b748 |  136   | 0x88   | 34     | `uwasa_main`
0x8006b7d0 |  224   | 0xe0   | 56     | `pre_xmas_init`
0x8006b8b0 |  84    | 0x54   | 21     | `pre_xmas`
0x8006b904 |  136   | 0x88   | 34     | `pre_xmas_main`
0x8006b98c |  420   | 0x1a4  | 105    | `get_nenga_girl`
0x8006bb30 |  180   | 0xb4   | 45     | `pre_syogatu_init0`
0x8006bbe4 |  136   | 0x88   | 34     | `pre_syogatu_init1`
0x8006bc6c |  80    | 0x50   | 20     | `pre_syogatu_init2`
0x8006bcbc |  96    | 0x60   | 24     | `pre_syogatu_init3`
0x8006bd1c |  152   | 0x98   | 38     | `pre_syogatu_init`
0x8006bdb4 |  432   | 0x1b0  | 108    | `pre_syogatu0`
0x8006bf64 |  412   | 0x19c  | 103    | `pre_syogatu1`
0x8006c100 |  84    | 0x54   | 21     | `pre_syogatu`
0x8006c154 |  144   | 0x90   | 36     | `pre_syogatu_main`
0x8006c1e4 |  68    | 0x44   | 17     | `put_yes_string`
0x8006c228 |  68    | 0x44   | 17     | `put_no_string`
0x8006c26c |  428   | 0x1ac  | 107    | `file_select_number_show`
0x8006c418 |  516   | 0x204  | 129    | `girl_mark_animation`
0x8006c61c |  200   | 0xc8   | 50     | `girl_mark_set`
0x8006c6e4 |  132   | 0x84   | 33     | `message_kind_change`
0x8006c768 |  144   | 0x90   | 36     | `message_disp`
0x8006c7f8 |  592   | 0x250  | 148    | `album_message_set`
0x8006ca48 |  1304  | 0x518  | 326    | `clear_kaisu_show`
0x8006cf60 |  40    | 0x28   | 10     | `hyouka_show`
0x8006cf88 |  864   | 0x360  | 216    | `parameter_file_show`
0x8006d2e8 |  296   | 0x128  | 74     | `now_game_info_disp`
0x8006d410 |  304   | 0x130  | 76     | `now_select_mode_disp`
0x8006d540 |  884   | 0x374  | 221    | `now_select_album_disp`
0x8006d8b4 |  396   | 0x18c  | 99     | `touzyou_fan_disp`
0x8006da40 |  452   | 0x1c4  | 113    | `file_select_init0`
0x8006dc04 |  360   | 0x168  | 90     | `file_select_init1`
0x8006dd6c |  1148  | 0x47c  | 287    | `file_select_init2`
0x8006e1e8 |  120   | 0x78   | 30     | `file_select_start_card`
0x8006e260 |  104   | 0x68   | 26     | `file_select_init`
0x8006e2c8 |  104   | 0x68   | 26     | `file_select_init_card0`
0x8006e330 |  120   | 0x78   | 30     | `file_select_init_card1`
0x8006e3a8 |  112   | 0x70   | 28     | `file_select_init_card2`
0x8006e418 |  48    | 0x30   | 12     | `file_select_init_card3`
0x8006e448 |  196   | 0xc4   | 49     | `file_select_init_card4`
0x8006e50c |  116   | 0x74   | 29     | `file_select_init_card5`
0x8006e580 |  192   | 0xc0   | 48     | `file_select_init_card6`
0x8006e640 |  56    | 0x38   | 14     | `file_select_init_card7`
0x8006e678 |  188   | 0xbc   | 47     | `file_select_init_card`
0x8006e734 |  148   | 0x94   | 37     | `file_select_main0`
0x8006e7c8 |  88    | 0x58   | 22     | `swap_card`
0x8006e820 |  208   | 0xd0   | 52     | `file_select_main1`
0x8006e8f0 |  324   | 0x144  | 81     | `file_select_main2`
0x8006ea34 |  128   | 0x80   | 32     | `set_cursor`
0x8006eab4 |  92    | 0x5c   | 23     | `file_select_main20`
0x8006eb10 |  352   | 0x160  | 88     | `file_select_main21`
0x8006ec70 |  236   | 0xec   | 59     | `mode_change_check`
0x8006ed5c |  156   | 0x9c   | 39     | `file_select_main22`
0x8006edf8 |  84    | 0x54   | 21     | `file_select_main23`
0x8006ee4c |  104   | 0x68   | 26     | `file_select_main24`
0x8006eeb4 |  224   | 0xe0   | 56     | `file_select_main40`
0x8006ef94 |  76    | 0x4c   | 19     | `file_select_main41`
0x8006efe0 |  104   | 0x68   | 26     | `file_select_main42`
0x8006f048 |  40    | 0x28   | 10     | `file_select_main43`
0x8006f070 |  132   | 0x84   | 33     | `file_select_main44`
0x8006f0f4 |  268   | 0x10c  | 67     | `file_select_main45`
0x8006f200 |  132   | 0x84   | 33     | `file_select_main46`
0x8006f284 |  48    | 0x30   | 12     | `file_select_main47`
0x8006f2b4 |  196   | 0xc4   | 49     | `file_select_main48`
0x8006f378 |  76    | 0x4c   | 19     | `file_select_main49`
0x8006f3c4 |  132   | 0x84   | 33     | `file_select_main4a`
0x8006f448 |  92    | 0x5c   | 23     | `file_select_main4b`
0x8006f4a4 |  188   | 0xbc   | 47     | `file_select_main4c`
0x8006f560 |  188   | 0xbc   | 47     | `file_select_main4d`
0x8006f61c |  76    | 0x4c   | 19     | `file_select_main4e`
0x8006f668 |  132   | 0x84   | 33     | `file_select_new`
0x8006f6ec |  56    | 0x38   | 14     | `file_select_new1`
0x8006f724 |  104   | 0x68   | 26     | `file_select_new2`
0x8006f78c |  296   | 0x128  | 74     | `file_select_new3`
0x8006f8b4 |  268   | 0x10c  | 67     | `file_select_new4`
0x8006f9c0 |  76    | 0x4c   | 19     | `file_select_new5`
0x8006fa0c |  144   | 0x90   | 36     | `file_select_new6`
0x8006fa9c |  348   | 0x15c  | 87     | `file_select_new7`
0x8006fbf8 |  132   | 0x84   | 33     | `file_select_copy`
0x8006fc7c |  304   | 0x130  | 76     | `file_select_copy1`
0x8006fdac |  332   | 0x14c  | 83     | `file_select_copy2`
0x8006fef8 |  296   | 0x128  | 74     | `file_select_copy3`
0x80070020 |  268   | 0x10c  | 67     | `file_select_copy4`
0x8007012c |  356   | 0x164  | 89     | `file_select_copy5`
0x80070290 |  436   | 0x1b4  | 109    | `file_select_copy6`
0x80070444 |  132   | 0x84   | 33     | `file_select_delete`
0x800704c8 |  296   | 0x128  | 74     | `file_select_delete1`
0x800705f0 |  268   | 0x10c  | 67     | `file_select_delete2`
0x800706fc |  84    | 0x54   | 21     | `file_select_delete3`
0x80070750 |  148   | 0x94   | 37     | `file_select_delete4`
0x800707e4 |  64    | 0x40   | 16     | `file_select_delete5`
0x80070824 |  88    | 0x58   | 22     | `file_select_delete6`
0x8007087c |  1076  | 0x434  | 269    | `file_select_main`
0x80070cb0 |  232   | 0xe8   | 58     | `file_select_err`
0x80070d98 |  476   | 0x1dc  | 119    | `file_select_xa_call`
0x80070f74 |  48    | 0x30   | 12     | `file_select_goto_game`
0x80070fa4 |  84    | 0x54   | 21     | `file_select_exit`
0x80070ff8 |  240   | 0xf0   | 60     | `file_select`
0x800710e8 |  96    | 0x60   | 24     | `white_in`
0x80071148 |  540   | 0x21c  | 135    | `shadow_file_name`
0x80071364 |  952   | 0x3b8  | 238    | `_opening_movie`
0x8007171c |  1344  | 0x540  | 336    | `_pre_opening_init`
0x80071c5c |  3956  | 0xf74  | 989    | `_pre_opening_1`
0x80072bd0 |  460   | 0x1cc  | 115    | `fujisaki_speak`
0x80072d9c |  212   | 0xd4   | 53     | `fujisaki_wink`
0x80072e70 |  80    | 0x50   | 20     | `_pre_opening_exit`
0x80072ec0 |  156   | 0x9c   | 39     | `_pre_opening`
0x80072f5c |  100   | 0x64   | 25     | `opening`
0x80072fc0 |  160   | 0xa0   | 40     | `logo`
0x80073060 |  128   | 0x80   | 32     | `title_init_View`
0x800730e0 |  288   | 0x120  | 72     | `title_init_Light`
0x80073200 |  92    | 0x5c   | 23     | `title_init_Coordinate`
0x8007325c |  296   | 0x128  | 74     | `title_init_ModelingData`
0x80073384 |  1176  | 0x498  | 294    | `title_data_read`
0x8007381c |  200   | 0xc8   | 50     | `title_move_show`
0x800738e4 |  344   | 0x158  | 86     | `title_white_out`
0x80073a3c |  172   | 0xac   | 43     | `title_white_in`
0x80073ae8 |  132   | 0x84   | 33     | `title_move`
0x80073b6c |  468   | 0x1d4  | 117    | `title_show_init`
0x80073d40 |  320   | 0x140  | 80     | `cursor_select`
0x80073e80 |  140   | 0x8c   | 35     | `title_show`
0x80073f0c |  52    | 0x34   | 13     | `cursor_elem`
0x80073f40 |  64    | 0x40   | 16     | `title_elem`
0x80073f80 |  124   | 0x7c   | 31     | `title_set`
0x80073ffc |  228   | 0xe4   | 57     | `title_goto_else_step`
0x800740e0 |  120   | 0x78   | 30     | `title_fade_out`
0x80074158 |  100   | 0x64   | 25     | `title_out`
0x800741bc |  216   | 0xd8   | 54     | `title`
0x80074294 |  636   | 0x27c  | 159    | `title_object_rotate`
0x80074510 |  52    | 0x34   | 13     | `bust_up_read`
0x80074544 |  1848  | 0x738  | 462    | `bust_up_init`
0x80074c7c |  328   | 0x148  | 82     | `bust_up_face_c`
0x80074dc4 |  884   | 0x374  | 221    | `bust_up_show`
0x80075138 |  52    | 0x34   | 13     | `bustup_speech`
0x8007516c |  36    | 0x24   | 9      | `bustup_wink`
0x80075190 |  72    | 0x48   | 18     | `parameter_change`
0x800751d8 |  168   | 0xa8   | 42     | `parameter_disp_switch`
0x80075280 |  3316  | 0xcf4  | 829    | `parameter_show_init`
0x80075f74 |  608   | 0x260  | 152    | `parameter_show`
0x800761d4 |  168   | 0xa8   | 42     | `hizuke_disp_switch`
0x8007627c |  1048  | 0x418  | 262    | `hizuke_init`
0x80076694 |  92    | 0x5c   | 23     | `hizuke_show`
0x800766f0 |  60    | 0x3c   | 15     | `message_disp_switch`
0x8007672c |  196   | 0xc4   | 49     | `message_window_init`
0x800767f0 |  92    | 0x5c   | 23     | `message_window_show`
0x8007684c |  164   | 0xa4   | 41     | `icon_disp_switch`
0x800768f0 |  44    | 0x2c   | 11     | `icon_can_use_set`
0x8007691c |  40    | 0x28   | 10     | `get_icon_can_use`
0x80076944 |  728   | 0x2d8  | 182    | `icon_init`
0x80076c1c |  1072  | 0x430  | 268    | `icon_menu_set`
0x8007704c |  44    | 0x2c   | 11     | `icon_mem_card_switch`
0x80077078 |  424   | 0x1a8  | 106    | `icon_atari_check`
0x80077220 |  836   | 0x344  | 209    | `icon_show`
0x80077564 |  452   | 0x1c4  | 113    | `basyo_disp_switch`
0x80077728 |  40    | 0x28   | 10     | `basyo_init2`
0x80077750 |  520   | 0x208  | 130    | `basyo_init`
0x80077958 |  1784  | 0x6f8  | 446    | `basyo_show`
0x80078050 |  88    | 0x58   | 22     | `get_season`
0x800780a8 |  72    | 0x48   | 18     | `get_nf`
0x800780f0 |  200   | 0xc8   | 50     | `get_vacation`
0x800781b8 |  1968  | 0x7b0  | 492    | `back_scroll_move`
0x80078968 |  128   | 0x80   | 32     | `back_scroll_init`
0x800789e8 |  112   | 0x70   | 28     | `normal_music_read_init0`
0x80078a58 |  292   | 0x124  | 73     | `normal_music_read_again`
0x80078b7c |  60    | 0x3c   | 15     | `normal_music_read_init1`
0x80078bb8 |  96    | 0x60   | 24     | `mascot_disp_switch`
0x80078c18 |  452   | 0x1c4  | 113    | `mascot_init`
0x80078ddc |  1012  | 0x3f4  | 253    | `mascot_move`
0x800791d0 |  360   | 0x168  | 90     | `event_bust_up_show`
0x80079338 |  40    | 0x28   | 10     | `event_bustup_wink`
0x80079360 |  48    | 0x30   | 12     | `event_bustup_kuchi_ani`
0x80079390 |  208   | 0xd0   | 52     | `cal_class_init`
0x80079460 |  1900  | 0x76c  | 475    | `schedule_mark_on`
0x80079bcc |  88    | 0x58   | 22     | `get_calx_pos`
0x80079c24 |  72    | 0x48   | 18     | `get_caly_pos`
0x80079c6c |  684   | 0x2ac  | 171    | `cal_font_load`
0x80079f18 |  640   | 0x280  | 160    | `biorhythm_curve`
0x8007a198 |  296   | 0x128  | 74     | `cal_show`
0x8007a2c0 |  80    | 0x50   | 20     | `cal_base_show`
0x8007a310 |  80    | 0x50   | 20     | `appraisal_base_show`
0x8007a360 |  80    | 0x50   | 20     | `magazine_base_show`
0x8007a3b0 |  192   | 0xc0   | 48     | `cal_sprite_disp_switch`
0x8007a470 |  828   | 0x33c  | 207    | `cal_sprite_init`
0x8007a7ac |  200   | 0xc8   | 50     | `data_save_load_class_init`
0x8007a874 |  692   | 0x2b4  | 173    | `memory_card_data_set`
0x8007ab28 |  644   | 0x284  | 161    | `joho_check`
0x8007adac |  3064  | 0xbf8  | 766    | `magazine_class_init`
0x8007b9a4 |  328   | 0x148  | 82     | `reserved_date`
0x8007baec |  180   | 0xb4   | 45     | `check_date_info`
0x8007bba0 |  1252  | 0x4e4  | 313    | `sort_date_info`
0x8007c084 |  132   | 0x84   | 33     | `set_date_info`
0x8007c108 |  380   | 0x17c  | 95     | `print_date_info`
0x8007c284 |  684   | 0x2ac  | 171    | `join_club_class_init`
0x8007c530 |  320   | 0x140  | 80     | `date_light_effect`
0x8007c670 |  468   | 0x1d4  | 117    | `cursor_move`
0x8007c844 |  324   | 0x144  | 81     | `cursor_init`
0x8007c988 |  60    | 0x3c   | 15     | `cursor_disp_switch`
0x8007c9c4 |  1224  | 0x4c8  | 306    | `biorhythm_sf_set`
0x8007ce8c |  44    | 0x2c   | 11     | `biorhythm_sf`
0x8007ceb8 |  972   | 0x3cc  | 243    | `biorhythm_sf2`
0x8007d284 |  104   | 0x68   | 26     | `get_pass_days`
0x8007d2ec |  232   | 0xe8   | 58     | `konami_mark_set`
0x8007d3d4 |  236   | 0xec   | 59     | `yazirushi_disp_switch`
0x8007d4c0 |  96    | 0x60   | 24     | `move_yazirushi`
0x8007d520 |  60    | 0x3c   | 15     | `schedule_init`
0x8007d55c |  188   | 0xbc   | 47     | `_schedule_init`
0x8007d618 |  188   | 0xbc   | 47     | `last_date_spot_timer_dec`
0x8007d6d4 |  48    | 0x30   | 12     | `restore_bgm`
0x8007d704 |  88    | 0x58   | 22     | `schedule_icon_disp`
0x8007d75c |  132   | 0x84   | 33     | `normal_icon_set`
0x8007d7e0 |  72    | 0x48   | 18     | `schedule_buf_clear`
0x8007d828 |  140   | 0x8c   | 35     | `season_mess_clear`
0x8007d8b4 |  44    | 0x2c   | 11     | `season_flag_set`
0x8007d8e0 |  232   | 0xe8   | 58     | `season_last_date_spot_clear`
0x8007d9c8 |  880   | 0x370  | 220    | `basyo_flag_set`
0x8007dd38 |  140   | 0x8c   | 35     | `bukatu_reset`
0x8007ddc4 |  3620  | 0xe24  | 905    | `schedule_weekday`
0x8007ebe8 |  264   | 0x108  | 66     | `tate_last_date_check`
0x8007ecf0 |  840   | 0x348  | 210    | `touzyou_girl1`
0x8007f038 |  828   | 0x33c  | 207    | `touzyou_girl2`
0x8007f374 |  688   | 0x2b0  | 172    | `touzyou_girl3`
0x8007f624 |  1620  | 0x654  | 405    | `get_ouen_girl`
0x8007fc78 |  2872  | 0xb38  | 718    | `tokubetu_judge`
0x800807b0 |  444   | 0x1bc  | 111    | `geko_judge`
0x8008096c |  644   | 0x284  | 161    | `date_sasoi_judge`
0x80080bf0 |  368   | 0x170  | 92     | `schedule_girls_gakko`
0x80080d60 |  460   | 0x1cc  | 115    | `yuukou_down`
0x80080f2c |  128   | 0x80   | 32     | `syoushin_up`
0x80080fac |  60    | 0x3c   | 15     | `schdeule_girls_param`
0x80080fe8 |  252   | 0xfc   | 63     | `schedule_init_exit`
0x800810e4 |  60    | 0x3c   | 15     | `schedule_set`
0x80081120 |  80    | 0x50   | 20     | `_schedule_set`
0x80081170 |  104   | 0x68   | 26     | `schedule_bye`
0x800811d8 |  428   | 0x1ac  | 107    | `parameter_limited`
0x80081384 |  100   | 0x64   | 25     | `mem_card_check`
0x800813e8 |  320   | 0x140  | 80     | `himo_robo_check`
0x80081528 |  3536  | 0xdd0  | 884    | `schedule_analyze`
0x800822f8 |  108   | 0x6c   | 27     | `change_joho_look_f`
0x80082364 |  524   | 0x20c  | 131    | `cal_inc`
0x80082570 |  28    | 0x1c   | 7      | `etc_flag_clear`
0x8008258c |  100   | 0x64   | 25     | `kyuuka`
0x800825f0 |  360   | 0x168  | 90     | `_goto_vacation`
0x80082758 |  100   | 0x64   | 25     | `change_month`
0x800827bc |  144   | 0x90   | 36     | `_change_month`
0x8008284c |  224   | 0xe0   | 56     | `change_month_font_load`
0x8008292c |  60    | 0x3c   | 15     | `change_month_bgm_read`
0x80082968 |  100   | 0x64   | 25     | `return_schedule`
0x800829cc |  80    | 0x50   | 20     | `kega_check`
0x80082a1c |  272   | 0x110  | 68     | `_kega_check`
0x80082b2c |  1032  | 0x408  | 258    | `kega_check1`
0x80082f34 |  340   | 0x154  | 85     | `kega_hassei`
0x80083088 |  212   | 0xd4   | 53     | `noiroze_hassei`
0x8008315c |  212   | 0xd4   | 53     | `sick_hassei`
0x80083230 |  232   | 0xe8   | 58     | `kega_kaifuku`
0x80083318 |  232   | 0xe8   | 58     | `noiroze_kaifuku`
0x80083400 |  232   | 0xe8   | 58     | `sick_kaifuku`
0x800834e8 |  120   | 0x78   | 30     | `kega_exit`
0x80083560 |  224   | 0xe0   | 56     | `week_day`
0x80083640 |  64    | 0x40   | 16     | `week_day_exit`
0x80083680 |  128   | 0x80   | 32     | `week_day_init`
0x80083700 |  64    | 0x40   | 16     | `week_day_main`
0x80083740 |  96    | 0x60   | 24     | `get_weekly_bg_sector`
0x800837a0 |  396   | 0x18c  | 99     | `week_day_init0`
0x8008392c |  1288  | 0x508  | 322    | `set_sd`
0x80083e34 |  436   | 0x1b4  | 109    | `week_day_init1`
0x80083fe8 |  780   | 0x30c  | 195    | `week_day_init2`
0x800842f4 |  320   | 0x140  | 80     | `week_day_main0`
0x80084434 |  68    | 0x44   | 17     | `week_day_exit0`
0x80084478 |  1228  | 0x4cc  | 307    | `parameter_up_down`
0x80084944 |  128   | 0x80   | 32     | `vacation_day_init`
0x800849c4 |  328   | 0x148  | 82     | `vacation_day_init0`
0x80084b0c |  288   | 0x120  | 72     | `vacation_day_init1`
0x80084c2c |  500   | 0x1f4  | 125    | `vacation_day_init2`
0x80084e20 |  328   | 0x148  | 82     | `holiday`
0x80084f68 |  88    | 0x58   | 22     | `holiday_init`
0x80084fc0 |  244   | 0xf4   | 61     | `fujisaki_2nin_birth_check`
0x800850b4 |  1076  | 0x434  | 269    | `holiday_init_0`
0x800854e8 |  72    | 0x48   | 18     | `holiday_init_1`
0x80085530 |  212   | 0xd4   | 53     | `sunday_icon_phase`
0x80085604 |  84    | 0x54   | 21     | `holiday_main`
0x80085658 |  56    | 0x38   | 14     | `holiday_main0`
0x80085690 |  736   | 0x2e0  | 184    | `phone_check`
0x80085970 |  96    | 0x60   | 24     | `get_holiday_bg_sector`
0x800859d0 |  760   | 0x2f8  | 190    | `icon_check_h`
0x80085cc8 |  308   | 0x134  | 77     | `get_date_basyo_num`
0x80085dfc |  372   | 0x174  | 93     | `pre_date_init`
0x80085f70 |  852   | 0x354  | 213    | `date_x_taku_set`
0x800862c4 |  308   | 0x134  | 77     | `pre_date_select`
0x800863f8 |  288   | 0x120  | 72     | `pre_date_exit`
0x80086518 |  112   | 0x70   | 28     | `pre_date`
0x80086588 |  148   | 0x94   | 37     | `holiday_normal`
0x8008661c |  276   | 0x114  | 69     | `set_sd_holiday`
0x80086730 |  704   | 0x2c0  | 176    | `holiday_normal_init0`
0x800869f0 |  428   | 0x1ac  | 107    | `holiday_normal_init1`
0x80086b9c |  680   | 0x2a8  | 170    | `holiday_normal_main`
0x80086e44 |  112   | 0x70   | 28     | `holiday_magazine`
0x80086eb4 |  88    | 0x58   | 22     | `magazine_init`
0x80086f0c |  92    | 0x5c   | 23     | `magazine_main`
0x80086f68 |  48    | 0x30   | 12     | `magazine_exit`
0x80086f98 |  132   | 0x84   | 33     | `holiday_tel`
0x8008701c |  120   | 0x78   | 30     | `holiday_tel_init`
0x80087094 |  240   | 0xf0   | 60     | `holiday_tel_call`
0x80087184 |  424   | 0x1a8  | 106    | `holiday_tel_exit`
0x8008732c |  788   | 0x314  | 197    | `telephone_class_init`
0x80087640 |  104   | 0x68   | 26     | `holiday_club_init`
0x800876a8 |  336   | 0x150  | 84     | `holiday_club_select`
0x800877f8 |  164   | 0xa4   | 41     | `holiday_club_exit`
0x8008789c |  64    | 0x40   | 16     | `holiday_taibu_club_exit`
0x800878dc |  132   | 0x84   | 33     | `holiday_club`
0x80087960 |  48    | 0x30   | 12     | `holiday_club_join_exit`
0x80087990 |  144   | 0x90   | 36     | `holiday_club_join`
0x80087a20 |  160   | 0xa0   | 40     | `load_exe_bin`
0x80087ac0 |  376   | 0x178  | 94     | `etc_disp`
0x80087c38 |  840   | 0x348  | 210    | `load_func_main`
0x80087f80 |  52    | 0x34   | 13     | `load_func_ok`
0x80087fb4 |  92    | 0x5c   | 23     | `load_fucn_check_sum`
0x80088010 |  1176  | 0x498  | 294    | `load_func_go`
0x800884a8 |  600   | 0x258  | 150    | `twinbee`
0x80088700 |  36    | 0x24   | 9      | `SD_Call_SD`
0x80088724 |  316   | 0x13c  | 79     | `SD_Task`
0x80088860 |  300   | 0x12c  | 75     | `SD_HandleVBLVAB`
0x8008898c |  200   | 0xc8   | 50     | `SD_TransVAB`
0x80088a54 |  76    | 0x4c   | 19     | `SD_ISVabAvailable`
0x80088aa0 |  80    | 0x50   | 20     | `SD_XATask`
0x80088af0 |  100   | 0x64   | 25     | `SD_CheckXASector`
0x80088b54 |  220   | 0xdc   | 55     | `SD_IsXAReady`
0x80088c30 |  156   | 0x9c   | 39     | `SD_HandleVBL`
0x80088ccc |  468   | 0x1d4  | 117    | `SD_BranchCTRL`
0x80088ea0 |  256   | 0x100  | 64     | `SD_VABTransfer`
0x80088fa0 |  232   | 0xe8   | 58     | `SD_BufferUpdate`
0x80089088 |  120   | 0x78   | 30     | `SD_HandleSys`
0x80089100 |  48    | 0x30   | 12     | `SD_HandleVBLXA`
0x80089130 |  176   | 0xb0   | 44     | `SD_HandleXAFadeOut`
0x800891e0 |  92    | 0x5c   | 23     | `SD_FinishFadeOutXA`
0x8008923c |  424   | 0x1a8  | 106    | `SD_XACall`
0x800893e4 |  188   | 0xbc   | 47     | `SD_XAParamUpdate`
0x800894a0 |  104   | 0x68   | 26     | `SD_PlayXA`
0x80089508 |  352   | 0x160  | 88     | `SD_StopXA`
0x80089668 |  188   | 0xbc   | 47     | `SD_FadeXA`
0x80089724 |  248   | 0xf8   | 62     | `SD_HandleVBLSEQ`
0x8008981c |  60    | 0x3c   | 15     | `SD_FinishFadeOutSEQ`
0x80089858 |  232   | 0xe8   | 58     | `SD_SEQCall`
0x80089940 |  76    | 0x4c   | 19     | `SD_PlaySeq`
0x8008998c |  380   | 0x17c  | 95     | `SD_SeqGo`
0x80089b08 |  348   | 0x15c  | 87     | `SD_StopSeq`
0x80089c64 |  168   | 0xa8   | 42     | `SD_FadeSeq`
0x80089d0c |  8     | 0x8    | 2      | `SD_HandleVBLSE`
0x80089d14 |  132   | 0x84   | 33     | `SD_SECall`
0x80089d98 |  132   | 0x84   | 33     | `SD_OtherSECall`
0x80089e1c |  132   | 0x84   | 33     | `SD_SECallInSEQ`
0x80089ea0 |  132   | 0x84   | 33     | `SD_OtherSECallInSEQ`
0x80089f24 |  60    | 0x3c   | 15     | `SD_PlaySE`
0x80089f60 |  32    | 0x20   | 8      | `SD_StopSE`
0x80089f80 |  8     | 0x8    | 2      | `SD_FadeSE`
0x80089f88 |  84    | 0x54   | 21     | `SD_AddEvt`
0x80089fdc |  12    | 0xc    | 3      | `SD_FlashEvent`
0x80089fe8 |  148   | 0x94   | 37     | `SD_GetNextEvent`
0x8008a07c |  92    | 0x5c   | 23     | `SD_KillXA`
0x8008a0d8 |  32    | 0x20   | 8      | `SD_KillSPU`
0x8008a0f8 |  196   | 0xc4   | 49     | `SD_Init`
0x8008a1bc |  164   | 0xa4   | 41     | `SD_SetVabAdrs`
0x8008a260 |  184   | 0xb8   | 46     | `SD_GetVabAdrs`
0x8008a318 |  88    | 0x58   | 22     | `SD_InitCD`
0x8008a370 |  312   | 0x138  | 78     | `SD_InitStruct`
0x8008a4a8 |  132   | 0x84   | 33     | `SD_SetSeqAdrs`
0x8008a52c |  180   | 0xb4   | 45     | `SD_ChnChange`
0x8008a5e0 |  156   | 0x9c   | 39     | `SD_Reset`
0x8008a67c |  40    | 0x28   | 10     | `SD_GetVAB`
0x8008a6a4 |  164   | 0xa4   | 41     | `SD_DisposeVAB`
0x8008a748 |  56    | 0x38   | 14     | `SD_InitCDLevelInfo`
0x8008a780 |  736   | 0x2e0  | 184    | `SD_GetCDLevel`
0x8008aa60 |  260   | 0x104  | 65     | `SD_DetectCDPeak`
0x8008ab64 |  264   | 0x108  | 66     | `SD_CalcCDAve`
0x8008ac6c |  68    | 0x44   | 17     | `getCDlevel`
0x8008acb0 |  108   | 0x6c   | 27     | `addr_init_weekly_sd`
0x8008ad1c |  108   | 0x6c   | 27     | `addr_init_holiday_sd`
0x8008ad88 |  112   | 0x70   | 28     | `addr_init_club_sd`
0x8008adf8 |  152   | 0x98   | 38     | `addr_init_else_sd`
0x8008ae90 |  68    | 0x44   | 17     | `addr_init_bustup`
0x8008aed4 |  52    | 0x34   | 13     | `cdread_callback`
0x8008af08 |  52    | 0x34   | 13     | `normal_date_bg_suddenin`
0x8008af3c |  44    | 0x2c   | 11     | `normal_date_bg_suddenout`
0x8008af68 |  52    | 0x34   | 13     | `normal_date_bg_in`
0x8008af9c |  2748  | 0xabc  | 687    | `normal_date_bg_in_sub`
0x8008ba58 |  764   | 0x2fc  | 191    | `set_tarao_bg`
0x8008bd54 |  264   | 0x108  | 66     | `set_tarao_sprt`
0x8008be5c |  240   | 0xf0   | 60     | `set_tarao_rect`
0x8008bf4c |  52    | 0x34   | 13     | `normal_date_bg_out`
0x8008bf80 |  2732  | 0xaac  | 683    | `normal_date_bg_out_sub`
0x8008ca2c |  104   | 0x68   | 26     | `normal_date_girl_in`
0x8008ca94 |  112   | 0x70   | 28     | `normal_date_girl_in_init`
0x8008cb04 |  200   | 0xc8   | 50     | `normal_date_girl_in_main`
0x8008cbcc |  112   | 0x70   | 28     | `normal_date_girl_suddenin`
0x8008cc3c |  104   | 0x68   | 26     | `normal_date_girl_out`
0x8008cca4 |  44    | 0x2c   | 11     | `normal_date_girl_out_init`
0x8008ccd0 |  296   | 0x128  | 74     | `normal_date_girl_out_main`
0x8008cdf8 |  192   | 0xc0   | 48     | `normal_date_girl_suddenout`
0x8008ceb8 |  104   | 0x68   | 26     | `normal_date_bg_fadein`
0x8008cf20 |  176   | 0xb0   | 44     | `normal_date_bggirl_fadein`
0x8008cfd0 |  104   | 0x68   | 26     | `normal_date_bg_fadeout`
0x8008d038 |  272   | 0x110  | 68     | `normal_date_bggirl_fadeout`
0x8008d148 |  96    | 0x60   | 24     | `normal_date_move_place`
0x8008d1a8 |  80    | 0x50   | 20     | `normal_date_move_place_init`
0x8008d1f8 |  268   | 0x10c  | 67     | `normal_date_move_place_main`
0x8008d304 |  52    | 0x34   | 13     | `place_init`
0x8008d338 |  52    | 0x34   | 13     | `place_init2`
0x8008d36c |  40    | 0x28   | 10     | `change_dec_bg`
0x8008d394 |  140   | 0x8c   | 35     | `dec_init`
0x8008d420 |  116   | 0x74   | 29     | `bg_read_sub2`
0x8008d494 |  268   | 0x10c  | 67     | `check_k_scroll`
0x8008d5a0 |  68    | 0x44   | 17     | `wait_sub_sub`
0x8008d5e4 |  8140  | 0x1fcc | 2035   | `set_window_message`
0x8008f5b0 |  96    | 0x60   | 24     | `seek_stop_xa`
0x8008f610 |  5588  | 0x15d4 | 1397   | `set_kanji_win_string`
0x80090be4 |  1464  | 0x5b8  | 366    | `speak_sub`
0x8009119c |  348   | 0x15c  | 87     | `make_three_select`
0x800912f8 |  188   | 0xbc   | 47     | `junban_init`
0x800913b4 |  96    | 0x60   | 24     | `normal_date_three_select`
0x80091414 |  168   | 0xa8   | 42     | `normal_date_three_select_init`
0x800914bc |  252   | 0xfc   | 63     | `normal_date_three_select_main`
0x800915b8 |  96    | 0x60   | 24     | `normal_date_two_select`
0x80091618 |  148   | 0x94   | 37     | `normal_date_two_select_init`
0x800916ac |  208   | 0xd0   | 52     | `normal_date_two_select_main`
0x8009177c |  72    | 0x48   | 18     | `normal_date_face_change_continue`
0x800917c4 |  64    | 0x40   | 16     | `hidden_face_change_continue`
0x80091804 |  48    | 0x30   | 12     | `normal_date_face_change0`
0x80091834 |  48    | 0x30   | 12     | `normal_date_face_change1`
0x80091864 |  48    | 0x30   | 12     | `normal_date_face_change2`
0x80091894 |  48    | 0x30   | 12     | `normal_date_face_change3`
0x800918c4 |  48    | 0x30   | 12     | `normal_date_face_change4`
0x800918f4 |  40    | 0x28   | 10     | `hidden_face_change0`
0x8009191c |  40    | 0x28   | 10     | `hidden_face_change1`
0x80091944 |  40    | 0x28   | 10     | `hidden_face_change2`
0x8009196c |  40    | 0x28   | 10     | `hidden_face_change3`
0x80091994 |  40    | 0x28   | 10     | `hidden_face_change4`
0x800919bc |  44    | 0x2c   | 11     | `face_change`
0x800919e8 |  352   | 0x160  | 88     | `bust_up_init2`
0x80091b48 |  308   | 0x134  | 77     | `bust_up_init3`
0x80091c7c |  520   | 0x208  | 130    | `bust_up_show2`
0x80091e84 |  180   | 0xb4   | 45     | `dec_bg_show2`
0x80091f38 |  40    | 0x28   | 10     | `hizuke_hide`
0x80091f60 |  40    | 0x28   | 10     | `hizuke_appear`
0x80091f88 |  1580  | 0x62c  | 395    | `read_bustup`
0x800925b4 |  980   | 0x3d4  | 245    | `read_bustup_uniform`
0x80092988 |  308   | 0x134  | 77     | `read_bustup_swimsuit`
0x80092abc |  32    | 0x20   | 8      | `bustup_return`
0x80092adc |  72    | 0x48   | 18     | `return_step`
0x80092b24 |  120   | 0x78   | 30     | `k_disp_inc2`
0x80092b9c |  44    | 0x2c   | 11     | `yosi_trans`
0x80092bc8 |  40    | 0x28   | 10     | `change_yoshio`
0x80092bf0 |  44    | 0x2c   | 11     | `change_girl`
0x80092c1c |  144   | 0x90   | 36     | `pg_name_init`
0x80092cac |  96    | 0x60   | 24     | `select_girl`
0x80092d0c |  96    | 0x60   | 24     | `select_girl2`
0x80092d6c |  656   | 0x290  | 164    | `select_girl_init`
0x80092ffc |  252   | 0xfc   | 63     | `select_girl_main`
0x800930f8 |  48    | 0x30   | 12     | `sprite_brightness`
0x80093128 |  116   | 0x74   | 29     | `day_plus`
0x8009319c |  272   | 0x110  | 68     | `check_para_limit`
0x800932ac |  232   | 0xe8   | 58     | `set_yajirusi`
0x80093394 |  36    | 0x24   | 9      | `bustup_mouse_on`
0x800933b8 |  580   | 0x244  | 145    | `load_ful`
0x800935fc |  344   | 0x158  | 86     | `load_opd`
0x80093754 |  260   | 0x104  | 65     | `event_char_onoff`
0x80093858 |  120   | 0x78   | 30     | `ev_fadein`
0x800938d0 |  148   | 0x94   | 37     | `ev_fadeout`
0x80093964 |  48    | 0x30   | 12     | `event_face0`
0x80093994 |  52    | 0x34   | 13     | `event_face1`
0x800939c8 |  52    | 0x34   | 13     | `event_face2`
0x800939fc |  52    | 0x34   | 13     | `event_face3`
0x80093a30 |  40    | 0x28   | 10     | `event_face_kuchi0`
0x80093a58 |  40    | 0x28   | 10     | `event_face_kuchi1`
0x80093a80 |  48    | 0x30   | 12     | `event_kuchi_ani_no`
0x80093ab0 |  48    | 0x30   | 12     | `event_kuchi_ani_yes`
0x80093ae0 |  48    | 0x30   | 12     | `ev_me_on`
0x80093b10 |  52    | 0x34   | 13     | `ev_me_on_continue`
0x80093b44 |  484   | 0x1e4  | 121    | `_sprite_set_box_shade_tarao`
0x80093d28 |  124   | 0x7c   | 31     | `clear_work_tarao`
0x80093da4 |  40    | 0x28   | 10     | `don_init2`
0x80093dcc |  72    | 0x48   | 18     | `don_wait`
0x80093e14 |  144   | 0x90   | 36     | `normal_date_speak_1line`
0x80093ea4 |  120   | 0x78   | 30     | `normal_date_speak_012`
0x80093f1c |  124   | 0x7c   | 31     | `normal_date_speak`
0x80093f98 |  96    | 0x60   | 24     | `vram_bustup_clear`
0x80093ff8 |  312   | 0x138  | 78     | `date_alubum_para_set`
0x80094130 |  352   | 0x160  | 88     | `bust_up_face`
0x80094290 |  248   | 0xf8   | 62     | `Graph_Init`
0x80094388 |  28    | 0x1c   | 7      | `Vblnk_Timer_Init`
0x800943a4 |  32    | 0x20   | 8      | `Vblnk_Timer`
0x800943c4 |  760   | 0x2f8  | 190    | `Scroll`
0x800946bc |  204   | 0xcc   | 51     | `Rot_2D`
0x80094788 |  32    | 0x20   | 8      | `Fade_Out_Init`
0x800947a8 |  96    | 0x60   | 24     | `Fade_Out_Main`
0x80094808 |  32    | 0x20   | 8      | `Fade_In_Init`
0x80094828 |  100   | 0x64   | 25     | `Fade_In_Main`
0x8009488c |  80    | 0x50   | 20     | `Yubi`
0x800948dc |  88    | 0x58   | 22     | `Default_Disp`
0x80094934 |  216   | 0xd8   | 54     | `Shiori_Case_Of_Mine`
0x80094a0c |  60    | 0x3c   | 15     | `Ev_Class_W_Switch`
0x80094a48 |  36    | 0x24   | 9      | `Get_Serifu`
0x80094a6c |  280   | 0x118  | 70     | `bust_up_read_myu`
0x80094b84 |  76    | 0x4c   | 19     | `pcm_read_myu`
0x80094bd0 |  52    | 0x34   | 13     | `DecDCTReset`
0x80094c04 |  12    | 0xc    | 3      | `DecDCTBufSize`
0x80094c10 |  64    | 0x40   | 16     | `DecDCTvlc`
0x80094c50 |  128   | 0x80   | 32     | `DecDCTin`
0x80094cd0 |  32    | 0x20   | 8      | `DecDCTout`
0x80094cf0 |  32    | 0x20   | 8      | `DecDCTinSync`
0x80094d10 |  1152  | 0x480  | 288    | `DecDCToutSync`
0x80095190 |  592   | 0x250  | 148    | `MDEC_vlc`
0x800953e0 |  960   | 0x3c0  | 240    | `MDEC_vlc2`
0x800957a0 |  496   | 0x1f0  | 124    | `ivlc_dct_dc_size`
0x80095990 |  124   | 0x7c   | 31     | `CdInit`
0x80095a0c |  228   | 0xe4   | 57     | `CdInitFileSystem`
0x80095af0 |  32    | 0x20   | 8      | `CdReset`
0x80095b10 |  32    | 0x20   | 8      | `CdSync`
0x80095b30 |  32    | 0x20   | 8      | `CdReady`
0x80095b50 |  32    | 0x20   | 8      | `CdReadSync`
0x80095b70 |  20    | 0x14   | 5      | `CdSetDebug`
0x80095b84 |  52    | 0x34   | 13     | `CdComstr`
0x80095bb8 |  52    | 0x34   | 13     | `CdIntstr`
0x80095bec |  20    | 0x14   | 5      | `CdSyncCallback`
0x80095c00 |  20    | 0x14   | 5      | `CdReadyCallback`
0x80095c14 |  308   | 0x134  | 77     | `CdReadCallback`
0x80095d48 |  36    | 0x24   | 9      | `CdControl`
0x80095d6c |  40    | 0x28   | 10     | `CdControlF`
0x80095d94 |  76    | 0x4c   | 19     | `CdControlB`
0x80095de0 |  32    | 0x20   | 8      | `CdGetSector`
0x80095e00 |  232   | 0xe8   | 58     | `CdRead`
0x80095ee8 |  32    | 0x20   | 8      | `CdMix`
0x80095f08 |  104   | 0x68   | 26     | `CdRead2`
0x80095f70 |  316   | 0x13c  | 79     | `CdIntToPos`
0x800960ac |  180   | 0xb4   | 45     | `CdPosToInt`
0x80096160 |  84    | 0x54   | 21     | `StSetRing`
0x800961b4 |  76    | 0x4c   | 19     | `StClearRing`
0x80096200 |  56    | 0x38   | 14     | `StUnSetRing`
0x80096238 |  100   | 0x64   | 25     | `data_ready_callback`
0x8009629c |  100   | 0x64   | 25     | `StSetStream`
0x80096300 |  112   | 0x70   | 28     | `StSetEmulate`
0x80096370 |  260   | 0x104  | 65     | `StFreeRing`
0x80096474 |  176   | 0xb0   | 44     | `StGetNext`
0x80096524 |  28    | 0x1c   | 7      | `StSetMask`
0x80096540 |  2936  | 0xb78  | 734    | `StCdInterrupt`
0x800970b8 |  40    | 0x28   | 10     | `StSetChannel`
0x800970e0 |  4064  | 0xfe0  | 1016   | `CdSearchFile`
0x800980c0 |  176   | 0xb0   | 44     | `CD_sync`
0x80098170 |  140   | 0x8c   | 35     | `CD_ready`
0x800981fc |  624   | 0x270  | 156    | `CD_cw`
0x8009846c |  172   | 0xac   | 43     | `CD_vol`
0x80098518 |  256   | 0x100  | 64     | `CD_init`
0x80098618 |  280   | 0x118  | 70     | `CD_readm`
0x80098730 |  504   | 0x1f8  | 126    | `CD_readsync`
0x80098928 |  296   | 0x128  | 74     | `CD_read`
0x80098a50 |  24    | 0x18   | 6      | `CD_set_test_parmnum`
0x80098a68 |  328   | 0x148  | 82     | `_96_vec`
0x80098bb0 |  372   | 0x174  | 93     | `SsSetMVol`
0x80098d24 |  32    | 0x20   | 8      | `SsInit`
0x80098d44 |  32    | 0x20   | 8      | `SsInitHot`
0x80098d64 |  416   | 0x1a0  | 104    | `SsSetTableSize`
0x80098f04 |  880   | 0x370  | 220    | `SsSetTickMode`
0x80099274 |  32    | 0x20   | 8      | `SsStart`
0x80099294 |  32    | 0x20   | 8      | `SsStart2`
0x800992b4 |  104   | 0x68   | 26     | `SsEnd`
0x8009931c |  36    | 0x24   | 9      | `SsQuit`
0x80099340 |  208   | 0xd0   | 52     | `SsSetSerialAttr`
0x80099410 |  464   | 0x1d0  | 116    | `SsSetSerialVol`
0x800995e0 |  48    | 0x30   | 12     | `SsVabTransCompleted`
0x80099610 |  48    | 0x30   | 12     | `SsVabOpenHead`
0x80099640 |  48    | 0x30   | 12     | `SsVabOpenHeadSticky`
0x80099670 |  1088  | 0x440  | 272    | `SsVabFakeHead`
0x80099ab0 |  208   | 0xd0   | 52     | `SsVabTransBody`
0x80099b80 |  56    | 0x38   | 14     | `SsSeqSetVol`
0x80099bb8 |  60    | 0x3c   | 15     | `SsSepSetVol`
0x80099bf4 |  124   | 0x7c   | 31     | `Snd_SetVol`
0x80099c70 |  32    | 0x20   | 8      | `SsUtReverbOn`
0x80099c90 |  32    | 0x20   | 8      | `SsUtReverbOff`
0x80099cb0 |  92    | 0x5c   | 23     | `SsUtSetReverbType`
0x80099d0c |  16    | 0x10   | 4      | `SsUtGetReverbType`
0x80099d1c |  196   | 0xc4   | 49     | `SsUtSetReverbDepth`
0x80099de0 |  64    | 0x40   | 16     | `SsUtSetReverbFeedback`
0x80099e20 |  64    | 0x40   | 16     | `SsUtSetReverbDelay`
0x80099e60 |  172   | 0xac   | 43     | `SsSeqOpen`
0x80099f0c |  292   | 0x124  | 73     | `SsSepOpen`
0x8009a030 |  224   | 0xe0   | 56     | `SsUtGetVabHdr`
0x8009a110 |  56    | 0x38   | 14     | `SsSeqPlay`
0x8009a148 |  60    | 0x3c   | 15     | `SsSepPlay`
0x8009a184 |  188   | 0xbc   | 47     | `SsPlayBack`
0x8009a240 |  256   | 0x100  | 64     | `Snd_SetPlayMode`
0x8009a340 |  148   | 0x94   | 37     | `SsSeqStop`
0x8009a3d4 |  188   | 0xbc   | 47     | `SsSepStop`
0x8009a490 |  272   | 0x110  | 68     | `Snd_stop`
0x8009a5a0 |  356   | 0x164  | 89     | `SsSeqClose`
0x8009a704 |  364   | 0x16c  | 91     | `SsSepClose`
0x8009a870 |  144   | 0x90   | 36     | `SsSeqPause`
0x8009a900 |  192   | 0xc0   | 48     | `SsSepPause`
0x8009a9c0 |  120   | 0x78   | 30     | `SsSeqReplay`
0x8009aa38 |  168   | 0xa8   | 42     | `SsSepReplay`
0x8009aae0 |  64    | 0x40   | 16     | `SsVoKeyOff`
0x8009ab20 |  4796  | 0x12bc | 1199   | `SsVoKeyOn`
0x8009bddc |  52    | 0x34   | 13     | `SsUtVibrateOn`
0x8009be10 |  36    | 0x24   | 9      | `SsUtVibrateOff`
0x8009be34 |  752   | 0x2f0  | 188    | `SpuVmInit`
0x8009c124 |  144   | 0x90   | 36     | `SpuVmNoiseOnWithAdsr`
0x8009c1b4 |  144   | 0x90   | 36     | `SpuVmNoiseOff`
0x8009c244 |  44    | 0x2c   | 11     | `SpuVmNoiseOn`
0x8009c270 |  704   | 0x2c0  | 176    | `SpuVmPitchBend`
0x8009c530 |  744   | 0x2e8  | 186    | `SpuVmFlush`
0x8009c818 |  1008  | 0x3f0  | 252    | `SpuVmKeyOn`
0x8009cc08 |  320   | 0x140  | 80     | `SpuVmKeyOff`
0x8009cd48 |  244   | 0xf4   | 61     | `SpuVmSeKeyOn`
0x8009ce3c |  52    | 0x34   | 13     | `SpuVmSeKeyOff`
0x8009ce70 |  8     | 0x8    | 2      | `KeyOnCheck`
0x8009ce78 |  400   | 0x190  | 100    | `SpuVmSetSeqVol`
0x8009d008 |  100   | 0x64   | 25     | `SpuVmGetSeqVol`
0x8009d06c |  56    | 0x38   | 14     | `SpuVmGetSeqLVol`
0x8009d0a4 |  56    | 0x38   | 14     | `SpuVmGetSeqRVol`
0x8009d0dc |  72    | 0x48   | 18     | `SpuVmGetSeqPan`
0x8009d124 |  144   | 0x90   | 36     | `SpuVmSeqKeyOff`
0x8009d1b4 |  116   | 0x74   | 29     | `SpuVmSetProgVol`
0x8009d228 |  84    | 0x54   | 21     | `SpuVmGetProgVol`
0x8009d27c |  116   | 0x74   | 29     | `SpuVmSetProgPan`
0x8009d2f0 |  84    | 0x54   | 21     | `SpuVmGetProgPan`
0x8009d344 |  1004  | 0x3ec  | 251    | `SsUtKeyOn`
0x8009d730 |  272   | 0x110  | 68     | `SsUtKeyOff`
0x8009d840 |  936   | 0x3a8  | 234    | `SsUtKeyOnV`
0x8009dbe8 |  112   | 0x70   | 28     | `SsUtKeyOffV`
0x8009dc58 |  60    | 0x3c   | 15     | `SsUtPitchBend`
0x8009dc94 |  312   | 0x138  | 78     | `SsUtChangePitch`
0x8009ddcc |  200   | 0xc8   | 50     | `SsUtChangeADSR`
0x8009de94 |  88    | 0x58   | 22     | `SsUtGetDetVVol`
0x8009deec |  100   | 0x64   | 25     | `SsUtSetDetVVol`
0x8009df50 |  184   | 0xb8   | 46     | `SsUtGetVVol`
0x8009e008 |  136   | 0x88   | 34     | `SsUtSetVVol`
0x8009e090 |  28    | 0x1c   | 7      | `SsUtAutoVol`
0x8009e0ac |  28    | 0x1c   | 7      | `SsUtAutoPan`
0x8009e0c8 |  328   | 0x148  | 82     | `SsUtAllKeyOff`
0x8009e210 |  64    | 0x40   | 16     | `SsSetReservedVoice`
0x8009e250 |  16    | 0x10   | 4      | `SsSetAutoKeyOffMode`
0x8009e260 |  16    | 0x10   | 4      | `SsSetMono`
0x8009e270 |  16    | 0x10   | 4      | `SsSetStereo`
0x8009e280 |  124   | 0x7c   | 31     | `SsVabClose`
0x8009e2fc |  100   | 0x64   | 25     | `SsVabOpen`
0x8009e360 |  576   | 0x240  | 144    | `SsSeqCalledTbyT`
0x8009e5a0 |  800   | 0x320  | 200    | `InitSoundSeq`
0x8009e8c0 |  896   | 0x380  | 224    | `InitSoundSep`
0x8009ec40 |  208   | 0xd0   | 52     | `SpuVmVSetUp`
0x8009ed10 |  48    | 0x30   | 12     | `Snd_play`
0x8009ed40 |  1120  | 0x460  | 280    | `Snd_crescendo`
0x8009f1a0 |  1120  | 0x460  | 280    | `Snd_decrescendo`
0x8009f600 |  464   | 0x1d0  | 116    | `Snd_tempo`
0x8009f7d0 |  140   | 0x8c   | 35     | `Snd_pause`
0x8009f85c |  100   | 0x64   | 25     | `Snd_nextpause`
0x8009f8c0 |  96    | 0x60   | 24     | `Snd_replay`
0x8009f920 |  260   | 0x104  | 65     | `SeqPlay`
0x8009fa24 |  664   | 0x298  | 166    | `GetSeqData`
0x8009fcbc |  260   | 0x104  | 65     | `NoteOn`
0x8009fdc0 |  108   | 0x6c   | 27     | `SetProgramChange`
0x8009fe2c |  736   | 0x2e0  | 184    | `SetControlChange`
0x800a010c |  284   | 0x11c  | 71     | `ContModulation`
0x800a0228 |  284   | 0x11c  | 71     | `ContPortaTime`
0x800a0344 |  420   | 0x1a4  | 105    | `ContPortamento`
0x800a04e8 |  180   | 0xb4   | 45     | `ContResetAll`
0x800a059c |  292   | 0x124  | 73     | `ContNrpn1`
0x800a06c0 |  296   | 0x128  | 74     | `ContNrpn2`
0x800a07e8 |  108   | 0x6c   | 27     | `ContRpn1`
0x800a0854 |  108   | 0x6c   | 27     | `ContRpn2`
0x800a08c0 |  1480  | 0x5c8  | 370    | `ContDataEntry`
0x800a0e88 |  856   | 0x358  | 214    | `Snd_setVabAttr`
0x800a11e0 |  160   | 0xa0   | 40     | `SetPitchBend`
0x800a1280 |  832   | 0x340  | 208    | `GetMetaEvent`
0x800a15c0 |  176   | 0xb0   | 44     | `ReadDeltaValue`
0x800a1670 |  16    | 0x10   | 4      | `SpuVmDamperOff`
0x800a1680 |  16    | 0x10   | 4      | `SpuVmDamperOn`
0x800a1690 |  272   | 0x110  | 68     | `SsUtGetProgAtr`
0x800a17a0 |  576   | 0x240  | 144    | `SsUtGetVagAtr`
0x800a19e0 |  464   | 0x1d0  | 116    | `SsUtSetVagAtr`
0x800a1bb0 |  92    | 0x5c   | 23     | `SsUtResolveADSR`
0x800a1c0c |  148   | 0x94   | 37     | `SsUtBuildADSR`
0x800a1ca0 |  304   | 0x130  | 76     | `Snd_nextseq`
0x800a1dd0 |  336   | 0x150  | 84     | `SpuClearReverbWorkArea`
0x800a1f20 |  176   | 0xb0   | 44     | `SpuIsTransferCompleted`
0x800a1fd0 |  40    | 0x28   | 10     | `_spu_setInTransfer`
0x800a1ff8 |  24    | 0x18   | 6      | `_spu_getInTransfer`
0x800a2010 |  80    | 0x50   | 20     | `SpuSetTransferStartAddr`
0x800a2060 |  188   | 0xbc   | 47     | `SpuRead`
0x800a211c |  584   | 0x248  | 146    | `_spu_init`
0x800a2364 |  40    | 0x28   | 10     | `_spu_close`
0x800a238c |  116   | 0x74   | 29     | `_spu_open`
0x800a2400 |  584   | 0x248  | 146    | `_spu_write`
0x800a2648 |  180   | 0xb4   | 45     | `_spu_read`
0x800a26fc |  296   | 0x128  | 74     | `_spu_w`
0x800a2824 |  260   | 0x104  | 65     | `_spu_r`
0x800a2928 |  176   | 0xb0   | 44     | `_spu_r_`
0x800a29d8 |  4936  | 0x1348 | 1234   | `_spu_ioctl`
0x800a3d20 |  28    | 0x1c   | 7      | `SysSpu_setRegister`
0x800a3d3c |  256   | 0x100  | 64     | `SysSpu_getRegister`
0x800a3e3c |  32    | 0x20   | 8      | `SpuInit`
0x800a3e5c |  32    | 0x20   | 8      | `SpuInitHot`
0x800a3e7c |  120   | 0x78   | 30     | `SpuStart`
0x800a3ef4 |  856   | 0x358  | 214    | `SpuQuit`
0x800a424c |  112   | 0x70   | 28     | `SpuInitMalloc`
0x800a42bc |  1564  | 0x61c  | 391    | `SpuMalloc`
0x800a48d8 |  676   | 0x2a4  | 169    | `SpuMallocWithStartAddr`
0x800a4b7c |  108   | 0x6c   | 27     | `_SpuIsInAllocateArea`
0x800a4be8 |  40    | 0x28   | 10     | `_SpuIsInAllocateArea_`
0x800a4c10 |  120   | 0x78   | 30     | `SpuFree`
0x800a4c88 |  184   | 0xb8   | 46     | `_print`
0x800a4d40 |  96    | 0x60   | 24     | `SpuSetTransferMode`
0x800a4da0 |  96    | 0x60   | 24     | `SpuWrite`
0x800a4e00 |  224   | 0xe0   | 56     | `SpuSetReverb`
0x800a4ee0 |  1248  | 0x4e0  | 312    | `SpuSetReverbModeParam`
0x800a53c0 |  408   | 0x198  | 102    | `GsInitGraph`
0x800a5558 |  724   | 0x2d4  | 181    | `GsInitGraph2`
0x800a582c |  244   | 0xf4   | 61     | `GsSortClear`
0x800a5920 |  16    | 0x10   | 4      | `GsGetActiveBuff`
0x800a5930 |  160   | 0xa0   | 40     | `GsSetDrawBuffOffset`
0x800a59d0 |  176   | 0xb0   | 44     | `GsDefDispBuff`
0x800a5a80 |  112   | 0x70   | 28     | `GsInit3D`
0x800a5af0 |  64    | 0x40   | 16     | `GsInitVcount`
0x800a5b30 |  16    | 0x10   | 4      | `GsSetWorkBase`
0x800a5b40 |  96    | 0x60   | 24     | `GsClearOt`
0x800a5ba0 |  48    | 0x30   | 12     | `GsGetVcount`
0x800a5bd0 |  1472  | 0x5c0  | 368    | `GsSortSprite`
0x800a6190 |  480   | 0x1e0  | 120    | `GsSortFastSprite`
0x800a6370 |  2288  | 0x8f0  | 572    | `GsSortBg`
0x800a6c60 |  1472  | 0x5c0  | 368    | `GsSetRefView2`
0x800a7220 |  704   | 0x2c0  | 176    | `GsGetLws`
0x800a74e0 |  124   | 0x7c   | 31     | `GsInitCoordinate2`
0x800a755c |  44    | 0x2c   | 11     | `GsInitCoord2param`
0x800a7588 |  44    | 0x2c   | 11     | `GsSetLsMatrix`
0x800a75b4 |  152   | 0x98   | 38     | `GsSetLightMatrix`
0x800a764c |  48    | 0x30   | 12     | `GsSetLightMatrix2`
0x800a767c |  144   | 0x90   | 36     | `GsMulCoord0`
0x800a770c |  128   | 0x80   | 32     | `GsMulCoord2`
0x800a778c |  128   | 0x80   | 32     | `GsMulCoord3`
0x800a780c |  112   | 0x70   | 28     | `print_matrix`
0x800a787c |  52    | 0x34   | 13     | `print_vector`
0x800a78b0 |  688   | 0x2b0  | 172    | `GsGetLs`
0x800a7b60 |  320   | 0x140  | 80     | `GsLinkObject4`
0x800a7ca0 |  5728  | 0x1660 | 1432   | `GsSortObject4`
0x800a9300 |  16    | 0x10   | 4      | `GsGetWorkBase`
0x800a9310 |  48    | 0x30   | 12     | `GsClearVcount`
0x800a9340 |  192   | 0xc0   | 48     | `GsSwapDispBuff`
0x800a9400 |  48    | 0x30   | 12     | `GsDrawOt`
0x800a9430 |  32    | 0x20   | 8      | `GsSetProjection`
0x800a9450 |  16    | 0x10   | 4      | `GsSetNearClip`
0x800a9460 |  16    | 0x10   | 4      | `GsSetFarClip`
0x800a9470 |  1760  | 0x6e0  | 440    | `GsSetFlatLight`
0x800a9b50 |  48    | 0x30   | 12     | `GsSetAmbient`
0x800a9b80 |  144   | 0x90   | 36     | `GsSetLightMode`
0x800a9c10 |  144   | 0x90   | 36     | `GsMapModelingData`
0x800a9ca0 |  64    | 0x40   | 16     | `gte_init`
0x800a9ce0 |  176   | 0xb0   | 44     | `GsSetDrawBuffClip`
0x800a9d90 |  24    | 0x18   | 6      | `GsLinkObject2`
0x800a9da8 |  732   | 0x2dc  | 183    | `GsSortObject2`
0x800aa084 |  208   | 0xd0   | 52     | `GsLinkObject`
0x800aa154 |  784   | 0x310  | 196    | `GsSortObject`
0x800aa464 |  444   | 0x1bc  | 111    | `Gslight_normal`
0x800aa620 |  456   | 0x1c8  | 114    | `Gslight_normal_fog`
0x800aa7e8 |  472   | 0x1d8  | 118    | `Gslight_mate`
0x800aa9c0 |  472   | 0x1d8  | 118    | `Gslight_mate_fog`
0x800aab98 |  8     | 0x8    | 2      | `gte_flat_mat3`
0x800aaba0 |  8     | 0x8    | 2      | `gte_texture_flat_mat3`
0x800aaba8 |  8     | 0x8    | 2      | `gte_gouraud_mat3`
0x800aabb0 |  8     | 0x8    | 2      | `gte_texture_gouraud_mat3`
0x800aabb8 |  8     | 0x8    | 2      | `gte_flat_mat_fog3`
0x800aabc0 |  8     | 0x8    | 2      | `gte_texture_flat_mat_fog3`
0x800aabc8 |  8     | 0x8    | 2      | `gte_gouraud_mat_fog3`
0x800aabd0 |  16    | 0x10   | 4      | `gte_texture_gouraud_mat_fog3`
0x800aabe0 |  160   | 0xa0   | 40     | `_make_packet`
0x800aac80 |  208   | 0xd0   | 52     | `gte_rotate_z_matrix`
0x800aad50 |  368   | 0x170  | 92     | `gte_scale_matrix`
0x800aaec0 |  64    | 0x40   | 16     | `_mk_spr_packet`
0x800aaf00 |  840   | 0x348  | 210    | `_mk_xpndsp`
0x800ab248 |  712   | 0x2c8  | 178    | `_mk_normsp`
0x800ab510 |  208   | 0xd0   | 52     | `Gssub_make_matrix`
0x800ab5e0 |  576   | 0x240  | 144    | `GsGetLw`
0x800ab820 |  72    | 0x48   | 18     | `GsInitCoordinate`
0x800ab868 |  1056  | 0x420  | 264    | `GsSetRefView`
0x800abc88 |  1628  | 0x65c  | 407    | `GsGetObjLw`
0x800ac2e4 |  152   | 0x98   | 38     | `GsGetObjLight`
0x800ac37c |  372   | 0x174  | 93     | `GsGetObjMatrix`
0x800ac4f0 |  336   | 0x150  | 84     | `gte_apply_matrixl`
0x800ac640 |  384   | 0x180  | 96     | `gte_apply_matrixll`
0x800ac7c0 |  208   | 0xd0   | 52     | `gte_rotate_y_matrix`
0x800ac890 |  248   | 0xf8   | 62     | `gte_rotate_x_matrix`
0x800ac988 |  448   | 0x1c0  | 112    | `ResetGraph`
0x800acb48 |  200   | 0xc8   | 50     | `SetGraphReverse`
0x800acc10 |  96    | 0x60   | 24     | `SetGraphDebug`
0x800acc70 |  16    | 0x10   | 4      | `GetGraphType`
0x800acc80 |  16    | 0x10   | 4      | `GetGraphDebug`
0x800acc90 |  20    | 0x14   | 5      | `DrawSyncCallback`
0x800acca4 |  68    | 0x44   | 17     | `SetDispMask`
0x800acce8 |  48    | 0x30   | 12     | `DrawSync`
0x800acd18 |  84    | 0x54   | 21     | `ClearImage`
0x800acd6c |  60    | 0x3c   | 15     | `LoadImage`
0x800acda8 |  60    | 0x3c   | 15     | `StoreImage`
0x800acde4 |  112   | 0x70   | 28     | `MoveImage`
0x800ace54 |  84    | 0x54   | 21     | `ClearOTag`
0x800acea8 |  56    | 0x38   | 14     | `ClearOTagR`
0x800acee0 |  132   | 0x84   | 33     | `DrawPrim`
0x800acf64 |  88    | 0x58   | 22     | `DrawOTag`
0x800acfbc |  196   | 0xc4   | 49     | `PutDrawEnv`
0x800ad080 |  96    | 0x60   | 24     | `GetDrawEnv`
0x800ad0e0 |  908   | 0x38c  | 227    | `PutDispEnv`
0x800ad46c |  96    | 0x60   | 24     | `GetDispEnv`
0x800ad4cc |  56    | 0x38   | 14     | `SetTexWindow`
0x800ad504 |  112   | 0x70   | 28     | `SetDrawArea`
0x800ad574 |  64    | 0x40   | 16     | `SetDrawOffset`
0x800ad5b4 |  44    | 0x2c   | 11     | `SetPriority`
0x800ad5e0 |  84    | 0x54   | 21     | `SetDrawMode`
0x800ad634 |  6336  | 0x18c0 | 1584   | `SetDrawEnv`
0x800aeef4 |  148   | 0x94   | 37     | `GetTPage`
0x800aef88 |  24    | 0x18   | 6      | `GetClut`
0x800aefa0 |  144   | 0x90   | 36     | `DumpTPage`
0x800af030 |  64    | 0x40   | 16     | `DumpClut`
0x800af070 |  28    | 0x1c   | 7      | `NextPrim`
0x800af08c |  28    | 0x1c   | 7      | `IsEndPrim`
0x800af0a8 |  60    | 0x3c   | 15     | `AddPrim`
0x800af0e4 |  60    | 0x3c   | 15     | `AddPrims`
0x800af120 |  36    | 0x24   | 9      | `CatPrim`
0x800af144 |  24    | 0x18   | 6      | `TermPrim`
0x800af15c |  44    | 0x2c   | 11     | `SetSemiTrans`
0x800af188 |  44    | 0x2c   | 11     | `SetShadeTex`
0x800af1b4 |  20    | 0x14   | 5      | `SetPolyF3`
0x800af1c8 |  20    | 0x14   | 5      | `SetPolyFT3`
0x800af1dc |  20    | 0x14   | 5      | `SetPolyG3`
0x800af1f0 |  20    | 0x14   | 5      | `SetPolyGT3`
0x800af204 |  20    | 0x14   | 5      | `SetPolyF4`
0x800af218 |  20    | 0x14   | 5      | `SetPolyFT4`
0x800af22c |  20    | 0x14   | 5      | `SetPolyG4`
0x800af240 |  20    | 0x14   | 5      | `SetPolyGT4`
0x800af254 |  20    | 0x14   | 5      | `SetSprt8`
0x800af268 |  20    | 0x14   | 5      | `SetSprt16`
0x800af27c |  20    | 0x14   | 5      | `SetSprt`
0x800af290 |  20    | 0x14   | 5      | `SetTile1`
0x800af2a4 |  20    | 0x14   | 5      | `SetTile8`
0x800af2b8 |  20    | 0x14   | 5      | `SetTile16`
0x800af2cc |  20    | 0x14   | 5      | `SetTile`
0x800af2e0 |  20    | 0x14   | 5      | `SetBlockFill`
0x800af2f4 |  20    | 0x14   | 5      | `SetLineF2`
0x800af308 |  20    | 0x14   | 5      | `SetLineG2`
0x800af31c |  32    | 0x20   | 8      | `SetLineF3`
0x800af33c |  32    | 0x20   | 8      | `SetLineG3`
0x800af35c |  32    | 0x20   | 8      | `SetLineF4`
0x800af37c |  32    | 0x20   | 8      | `SetLineG4`
0x800af39c |  52    | 0x34   | 13     | `MargePrim`
0x800af3d0 |  304   | 0x130  | 76     | `DumpDrawEnv`
0x800af500 |  176   | 0xb0   | 44     | `DumpDispEnv`
0x800af5b0 |  232   | 0xe8   | 58     | `LoadTPage`
0x800af698 |  100   | 0x64   | 25     | `LoadClut`
0x800af6fc |  140   | 0x8c   | 35     | `SetDefDrawEnv`
0x800af788 |  260   | 0x104  | 65     | `SetDefDispEnv`
0x800af88c |  168   | 0xa8   | 42     | `DrawOTagIO`
0x800af934 |  328   | 0x148  | 82     | `DumpOTag`
0x800afa7c |  148   | 0x94   | 37     | `CheckPrim`
0x800afb10 |  104   | 0x68   | 26     | `InitGeom`
0x800afb78 |  80    | 0x50   | 20     | `LoadAverage12`
0x800afbc8 |  80    | 0x50   | 20     | `LoadAverage0`
0x800afc18 |  136   | 0x88   | 34     | `LoadAverageShort12`
0x800afca0 |  136   | 0x88   | 34     | `LoadAverageShort0`
0x800afd28 |  92    | 0x5c   | 23     | `LoadAverageByte`
0x800afd84 |  116   | 0x74   | 29     | `LoadAverageCol`
0x800afdf8 |  200   | 0xc8   | 50     | `VectorNormal`
0x800afec0 |  200   | 0xc8   | 50     | `VectorNormalS`
0x800aff88 |  132   | 0x84   | 33     | `SquareRoot0`
0x800b000c |  148   | 0x94   | 37     | `SquareRoot12`
0x800b00a0 |  140   | 0x8c   | 35     | `InvSquareRoot`
0x800b012c |  128   | 0x80   | 32     | `gteMIMefunc`
0x800b01ac |  120   | 0x78   | 30     | `InterpolShort`
0x800b0224 |  76    | 0x4c   | 19     | `InterpolByte`
0x800b0270 |  80    | 0x50   | 20     | `rsin`
0x800b02c0 |  172   | 0xac   | 43     | `sin_1`
0x800b036c |  208   | 0xd0   | 52     | `rcos`
0x800b043c |  92    | 0x5c   | 23     | `SetFogFar`
0x800b0498 |  100   | 0x64   | 25     | `SetFogNear`
0x800b04fc |  976   | 0x3d0  | 244    | `EigenMatrix`
0x800b08cc |  212   | 0xd4   | 53     | `IsIdMatrix`
0x800b09a0 |  80    | 0x50   | 20     | `TransposeMatrix`
0x800b09f0 |  652   | 0x28c  | 163    | `RotMatrix`
0x800b0c7c |  652   | 0x28c  | 163    | `RotMatrixYXZ`
0x800b0f08 |  652   | 0x28c  | 163    | `RotMatrixZYX`
0x800b1194 |  408   | 0x198  | 102    | `RotMatrixX`
0x800b132c |  408   | 0x198  | 102    | `RotMatrixY`
0x800b14c4 |  524   | 0x20c  | 131    | `RotMatrixZ`
0x800b16d0 |  352   | 0x160  | 88     | `CompMatrix`
0x800b1830 |  268   | 0x10c  | 67     | `MulMatrix0`
0x800b193c |  228   | 0xe4   | 57     | `MulRotMatrix0`
0x800b1a20 |  268   | 0x10c  | 67     | `MulMatrix`
0x800b1b2c |  268   | 0x10c  | 67     | `MulMatrix2`
0x800b1c38 |  232   | 0xe8   | 58     | `MulRotMatrix`
0x800b1d20 |  272   | 0x110  | 68     | `SetMulMatrix`
0x800b1e30 |  80    | 0x50   | 20     | `ApplyMatrix`
0x800b1e80 |  92    | 0x5c   | 23     | `ApplyMatrixSV`
0x800b1edc |  352   | 0x160  | 88     | `ApplyMatrixLV`
0x800b203c |  48    | 0x30   | 12     | `ApplyRotMatrix`
0x800b206c |  36    | 0x24   | 9      | `TransMatrix`
0x800b2090 |  292   | 0x124  | 73     | `ScaleMatrix`
0x800b21b4 |  292   | 0x124  | 73     | `ScaleMatrixL`
0x800b22d8 |  48    | 0x30   | 12     | `SetRotMatrix`
0x800b2308 |  48    | 0x30   | 12     | `SetLightMatrix`
0x800b2338 |  48    | 0x30   | 12     | `SetColorMatrix`
0x800b2368 |  32    | 0x20   | 8      | `SetTransMatrix`
0x800b2388 |  160   | 0xa0   | 40     | `PushMatrix`
0x800b2428 |  160   | 0xa0   | 40     | `PopMatrix`
0x800b24c8 |  72    | 0x48   | 18     | `ReadRotMatrix`
0x800b2510 |  72    | 0x48   | 18     | `ReadLightMatrix`
0x800b2558 |  72    | 0x48   | 18     | `ReadColorMatrix`
0x800b25a0 |  16    | 0x10   | 4      | `SetVertex0`
0x800b25b0 |  16    | 0x10   | 4      | `SetVertex1`
0x800b25c0 |  16    | 0x10   | 4      | `SetVertex2`
0x800b25d0 |  32    | 0x20   | 8      | `SetVertexTri`
0x800b25f0 |  12    | 0xc    | 3      | `SetRGBcd`
0x800b25fc |  20    | 0x14   | 5      | `SetRGBfifo`
0x800b2610 |  20    | 0x14   | 5      | `SetIR123`
0x800b2624 |  12    | 0xc    | 3      | `SetIR0`
0x800b2630 |  32    | 0x20   | 8      | `SetBackColor`
0x800b2650 |  32    | 0x20   | 8      | `SetFarColor`
0x800b2670 |  20    | 0x14   | 5      | `SetSZfifo3`
0x800b2684 |  24    | 0x18   | 6      | `SetSZfifo4`
0x800b269c |  20    | 0x14   | 5      | `SetSXSYfifo`
0x800b26b0 |  20    | 0x14   | 5      | `SetRii`
0x800b26c4 |  20    | 0x14   | 5      | `SetMAC123`
0x800b26d8 |  12    | 0xc    | 3      | `SetData32`
0x800b26e4 |  24    | 0x18   | 6      | `SetGeomOffset`
0x800b26fc |  12    | 0xc    | 3      | `SetGeomScreen`
0x800b2708 |  12    | 0xc    | 3      | `SetDQA`
0x800b2714 |  12    | 0xc    | 3      | `SetDQB`
0x800b2720 |  12    | 0xc    | 3      | `ReadOTZ`
0x800b272c |  12    | 0xc    | 3      | `ReadIR0`
0x800b2738 |  20    | 0x14   | 5      | `ReadIR123`
0x800b274c |  12    | 0xc    | 3      | `ReadSZ2`
0x800b2758 |  20    | 0x14   | 5      | `ReadSZfifo3`
0x800b276c |  24    | 0x18   | 6      | `ReadSZfifo4`
0x800b2784 |  20    | 0x14   | 5      | `ReadSXSYfifo`
0x800b2798 |  20    | 0x14   | 5      | `ReadRGBfifo`
0x800b27ac |  12    | 0xc    | 3      | `ReadMac0`
0x800b27b8 |  20    | 0x14   | 5      | `ReadMAC123`
0x800b27cc |  48    | 0x30   | 12     | `ReadORGB`
0x800b27fc |  12    | 0xc    | 3      | `ReadLZC`
0x800b2808 |  12    | 0xc    | 3      | `ReadFLAG`
0x800b2814 |  32    | 0x20   | 8      | `ReadGeomOffset`
0x800b2834 |  12    | 0xc    | 3      | `ReadGeomScreen`
0x800b2840 |  84    | 0x54   | 21     | `RotTransPersN`
0x800b2894 |  124   | 0x7c   | 31     | `RotTransPers3N`
0x800b2910 |  120   | 0x78   | 30     | `RotTransPers4`
0x800b2988 |  88    | 0x58   | 22     | `RotAverage3`
0x800b29e0 |  124   | 0x7c   | 31     | `RotAverage4`
0x800b2a5c |  44    | 0x2c   | 11     | `RotNclip`
0x800b2a88 |  132   | 0x84   | 33     | `RotNclip3`
0x800b2b0c |  176   | 0xb0   | 44     | `RotNclip4`
0x800b2bbc |  136   | 0x88   | 34     | `RotAverageNclip3`
0x800b2c44 |  160   | 0xa0   | 40     | `RotAverageNclip3_1`
0x800b2ce4 |  176   | 0xb0   | 44     | `RotAverageNclip4`
0x800b2d94 |  76    | 0x4c   | 19     | `RotColorDpq`
0x800b2de0 |  152   | 0x98   | 38     | `RotColorDpq3`
0x800b2e78 |  200   | 0xc8   | 50     | `RotAverageNclipColorDpq3`
0x800b2f40 |  200   | 0xc8   | 50     | `RotAverageNclipColorCol3`
0x800b3008 |  104   | 0x68   | 26     | `RotColorMatDpq`
0x800b3070 |  64    | 0x40   | 16     | `ColorMatDpq`
0x800b30b0 |  64    | 0x40   | 16     | `ColorMatCol`
0x800b30f0 |  316   | 0x13c  | 79     | `GsTMDfastNF3`
0x800b322c |  320   | 0x140  | 80     | `GsTMDfastF3NL`
0x800b336c |  328   | 0x148  | 82     | `GsTMDfastF3L`
0x800b34b4 |  332   | 0x14c  | 83     | `GsTMDfastF3LFG`
0x800b3600 |  360   | 0x168  | 90     | `GsTMDfastNF4`
0x800b3768 |  364   | 0x16c  | 91     | `GsTMDfastF4NL`
0x800b38d4 |  376   | 0x178  | 94     | `GsTMDfastF4L`
0x800b3a4c |  388   | 0x184  | 97     | `GsTMDfastF4LFG`
0x800b3bd0 |  328   | 0x148  | 82     | `GsTMDfastNG3`
0x800b3d18 |  320   | 0x140  | 80     | `GsTMDfastG3NL`
0x800b3e58 |  400   | 0x190  | 100    | `GsTMDfastG3L`
0x800b3fe8 |  408   | 0x198  | 102    | `GsTMDfastG3LFG`
0x800b4180 |  364   | 0x16c  | 91     | `GsTMDfastTNF3`
0x800b42ec |  356   | 0x164  | 89     | `GsTMDfastTF3NL`
0x800b4450 |  368   | 0x170  | 92     | `GsTMDfastTF3L`
0x800b45c0 |  368   | 0x170  | 92     | `GsTMDfastTF3LFG`
0x800b4730 |  376   | 0x178  | 94     | `GsTMDfastTNG3`
0x800b48a8 |  348   | 0x15c  | 87     | `GsTMDfastTG3NL`
0x800b4a04 |  436   | 0x1b4  | 109    | `GsTMDfastTG3L`
0x800b4bb8 |  440   | 0x1b8  | 110    | `GsTMDfastTG3LFG`
0x800b4d70 |  384   | 0x180  | 96     | `GsTMDfastNG4`
0x800b4ef0 |  372   | 0x174  | 93     | `GsTMDfastG4NL`
0x800b5064 |  480   | 0x1e0  | 120    | `GsTMDfastG4L`
0x800b5244 |  492   | 0x1ec  | 123    | `GsTMDfastG4LFG`
0x800b5430 |  416   | 0x1a0  | 104    | `GsTMDfastTNF4`
0x800b55d0 |  412   | 0x19c  | 103    | `GsTMDfastTF4NL`
0x800b576c |  428   | 0x1ac  | 107    | `GsTMDfastTF4L`
0x800b5918 |  440   | 0x1b8  | 110    | `GsTMDfastTF4LFG`
0x800b5ad0 |  444   | 0x1bc  | 111    | `GsTMDfastTNG4`
0x800b5c8c |  408   | 0x198  | 102    | `GsTMDfastTG4NL`
0x800b5e24 |  524   | 0x20c  | 131    | `GsTMDfastTG4L`
0x800b6030 |  528   | 0x210  | 132    | `GsTMDfastTG4LFG`
0x800b6240 |  556   | 0x22c  | 139    | `GsTMDdivF3L`
0x800b646c |  556   | 0x22c  | 139    | `GsTMDdivF3LFG`
0x800b6698 |  488   | 0x1e8  | 122    | `GsTMDdivF3NL`
0x800b6880 |  480   | 0x1e0  | 120    | `GsTMDdivNF3`
0x800b6a60 |  336   | 0x150  | 84     | `DivideF3`
0x800b6bb0 |  608   | 0x260  | 152    | `GsTMDdivF4L`
0x800b6e10 |  612   | 0x264  | 153    | `GsTMDdivF4LFG`
0x800b7074 |  560   | 0x230  | 140    | `GsTMDdivF4NL`
0x800b72a4 |  560   | 0x230  | 140    | `GsTMDdivNF4`
0x800b74d4 |  396   | 0x18c  | 99     | `DivideF4`
0x800b7660 |  568   | 0x238  | 142    | `GsTMDdivG3L`
0x800b7898 |  568   | 0x238  | 142    | `GsTMDdivG3LFG`
0x800b7ad0 |  504   | 0x1f8  | 126    | `GsTMDdivG3NL`
0x800b7cc8 |  504   | 0x1f8  | 126    | `GsTMDdivNG3`
0x800b7ec0 |  384   | 0x180  | 96     | `DivideG3`
0x800b8040 |  616   | 0x268  | 154    | `GsTMDdivTF3L`
0x800b82a8 |  616   | 0x268  | 154    | `GsTMDdivTF3LFG`
0x800b8510 |  548   | 0x224  | 137    | `GsTMDdivTF3NL`
0x800b8734 |  540   | 0x21c  | 135    | `GsTMDdivTNF3`
0x800b8950 |  416   | 0x1a0  | 104    | `DivideFT3`
0x800b8af0 |  628   | 0x274  | 157    | `GsTMDdivTG3L`
0x800b8d64 |  628   | 0x274  | 157    | `GsTMDdivTG3LFG`
0x800b8fd8 |  556   | 0x22c  | 139    | `GsTMDdivTG3NL`
0x800b9204 |  568   | 0x238  | 142    | `GsTMDdivTNG3`
0x800b943c |  468   | 0x1d4  | 117    | `DivideGT3`
0x800b9610 |  676   | 0x2a4  | 169    | `GsTMDdivG4L`
0x800b98b4 |  688   | 0x2b0  | 172    | `GsTMDdivG4LFG`
0x800b9b64 |  596   | 0x254  | 149    | `GsTMDdivG4NL`
0x800b9db8 |  596   | 0x254  | 149    | `GsTMDdivNG4`
0x800ba00c |  468   | 0x1d4  | 117    | `DivideG4`
0x800ba1e0 |  664   | 0x298  | 166    | `GsTMDdivTF4L`
0x800ba478 |  668   | 0x29c  | 167    | `GsTMDdivTF4LFG`
0x800ba714 |  636   | 0x27c  | 159    | `GsTMDdivTF4NL`
0x800ba990 |  632   | 0x278  | 158    | `GsTMDdivTNF4`
0x800bac08 |  504   | 0x1f8  | 126    | `DivideFT4`
0x800bae00 |  740   | 0x2e4  | 185    | `GsTMDdivTG4L`
0x800bb0e4 |  748   | 0x2ec  | 187    | `GsTMDdivTG4LFG`
0x800bb3d0 |  644   | 0x284  | 161    | `GsTMDdivTG4NL`
0x800bb654 |  672   | 0x2a0  | 168    | `GsTMDdivTNG4`
0x800bb8f4 |  572   | 0x23c  | 143    | `DivideGT4`
0x800bbb30 |  284   | 0x11c  | 71     | `gte_scope_f3`
0x800bbc4c |  260   | 0x104  | 65     | `gte_scope_tf3`
0x800bbd50 |  288   | 0x120  | 72     | `gte_scope_g3`
0x800bbe70 |  288   | 0x120  | 72     | `gte_scope_tg3`
0x800bbf90 |  252   | 0xfc   | 63     | `gte_flat3`
0x800bc08c |  288   | 0x120  | 72     | `gte_texture_flat3`
0x800bc1ac |  332   | 0x14c  | 83     | `gte_gouraud3`
0x800bc2f8 |  356   | 0x164  | 89     | `gte_texture_gouraud3`
0x800bc45c |  244   | 0xf4   | 61     | `gte_flat_fog3`
0x800bc550 |  288   | 0x120  | 72     | `gte_texture_flat_fog3`
0x800bc670 |  320   | 0x140  | 80     | `gte_gouraud_fog3`
0x800bc7b0 |  356   | 0x164  | 89     | `gte_texture_gouraud_fog3`
0x800bc914 |  372   | 0x174  | 93     | `gte_scope_tf4_B`
0x800bca88 |  344   | 0x158  | 86     | `gte_scope_tf4`
0x800bcbe0 |  44    | 0x2c   | 11     | `RotTransPers`
0x800bcc0c |  84    | 0x54   | 21     | `RotTransPers3`
0x800bcc60 |  40    | 0x28   | 10     | `RotTrans`
0x800bcc88 |  40    | 0x28   | 10     | `RotTrans0`
0x800bccb0 |  36    | 0x24   | 9      | `LocalLight`
0x800bccd4 |  40    | 0x28   | 10     | `LightColor`
0x800bccfc |  40    | 0x28   | 10     | `DpqColorLight`
0x800bcd24 |  28    | 0x1c   | 7      | `DpqColor`
0x800bcd40 |  60    | 0x3c   | 15     | `DpqColor3`
0x800bcd7c |  36    | 0x24   | 9      | `Intpl`
0x800bcda0 |  40    | 0x28   | 10     | `Square12`
0x800bcdc8 |  40    | 0x28   | 10     | `Square0`
0x800bcdf0 |  28    | 0x1c   | 7      | `NormalColor`
0x800bce0c |  60    | 0x3c   | 15     | `NormalColor3`
0x800bce48 |  36    | 0x24   | 9      | `NormalColorDpq`
0x800bce6c |  72    | 0x48   | 18     | `NormalColorDpq3`
0x800bceb4 |  32    | 0x20   | 8      | `NormalColorCol`
0x800bced4 |  68    | 0x44   | 17     | `NormalColorCol3`
0x800bcf18 |  40    | 0x28   | 10     | `ColorDpq`
0x800bcf40 |  36    | 0x24   | 9      | `ColorCol`
0x800bcf64 |  36    | 0x24   | 9      | `NormalClip`
0x800bcf88 |  16    | 0x10   | 4      | `NormalClipS`
0x800bcf98 |  32    | 0x20   | 8      | `AverageZ3`
0x800bcfb8 |  16    | 0x10   | 4      | `AverageSZ3`
0x800bcfc8 |  36    | 0x24   | 9      | `AverageZ4`
0x800bcfec |  16    | 0x10   | 4      | `AverageSZ4`
0x800bcffc |  88    | 0x58   | 22     | `OuterProduct12`
0x800bd054 |  88    | 0x58   | 22     | `OuterProduct0`
0x800bd0ac |  36    | 0x24   | 9      | `Lzc`
0x800bd0d0 |  8     | 0x8    | 2      | `RCpolyF3`
0x800bd0d8 |  872   | 0x368  | 218    | `RCpolyF3A`
0x800bd440 |  8     | 0x8    | 2      | `RCpolyF4`
0x800bd448 |  1144  | 0x478  | 286    | `RCpolyF4A`
0x800bd8c0 |  8     | 0x8    | 2      | `RCpolyG3`
0x800bd8c8 |  1032  | 0x408  | 258    | `RCpolyG3A`
0x800bdcd0 |  8     | 0x8    | 2      | `RCpolyFT3`
0x800bdcd8 |  1016  | 0x3f8  | 254    | `RCpolyFT3A`
0x800be0d0 |  8     | 0x8    | 2      | `RCpolyGT3`
0x800be0d8 |  1176  | 0x498  | 294    | `RCpolyGT3A`
0x800be570 |  8     | 0x8    | 2      | `RCpolyG4`
0x800be578 |  1352  | 0x548  | 338    | `RCpolyG4A`
0x800beac0 |  8     | 0x8    | 2      | `RCpolyFT4`
0x800beac8 |  1312  | 0x520  | 328    | `RCpolyFT4A`
0x800befe8 |  8     | 0x8    | 2      | `RCpolyGT4`
0x800beff0 |  1568  | 0x620  | 392    | `RCpolyGT4A`
0x800bf610 |  48    | 0x30   | 12     | `ResetCallback`
0x800bf640 |  48    | 0x30   | 12     | `InterruptCallback`
0x800bf670 |  48    | 0x30   | 12     | `DMACallback`
0x800bf6a0 |  48    | 0x30   | 12     | `VSyncCallback`
0x800bf6d0 |  48    | 0x30   | 12     | `StopCallback`
0x800bf700 |  896   | 0x380  | 224    | `CheckCallback`
0x800bfa80 |  400   | 0x190  | 100    | `VSync`
0x800bfc10 |  36    | 0x24   | 9      | `DecDCTinCallback`
0x800bfc34 |  36    | 0x24   | 9      | `DecDCToutCallback`
0x800bfc58 |  36    | 0x24   | 9      | `CdDataCallback`
0x800bfc7c |  36    | 0x24   | 9      | `SpuDataCallback`
0x800bfca0 |  36    | 0x24   | 9      | `PioDataCallback`
0x800bfcc4 |  36    | 0x24   | 9      | `CdCallback`
0x800bfce8 |  36    | 0x24   | 9      | `SpuCallback`
0x800bfd0c |  36    | 0x24   | 9      | `PioCallback`
0x800bfd30 |  84    | 0x54   | 21     | `PadInit`
0x800bfd84 |  44    | 0x2c   | 11     | `PadRead`
0x800bfdb0 |  32    | 0x20   | 8      | `PadStop`
0x800bfdd0 |  116   | 0x74   | 29     | `VBLNKInit`
0x800bfe44 |  220   | 0xdc   | 55     | `VBLNKStop`
0x800bff20 |  96    | 0x60   | 24     | `DMAInit`
0x800bff80 |  560   | 0x230  | 140    | `DMAStop`
0x800c01b0 |  16    | 0x10   | 4      | `InitCARD`
0x800c01c0 |  16    | 0x10   | 4      | `StartCARD`
0x800c01d0 |  16    | 0x10   | 4      | `_bu_init`
0x800c01e0 |  16    | 0x10   | 4      | `_card_auto`
0x800c01f0 |  16    | 0x10   | 4      | `_card_info`
0x800c0200 |  16    | 0x10   | 4      | `_card_load`
0x800c0210 |  48    | 0x30   | 12     | `_card_clear`
0x800c0240 |  16    | 0x10   | 4      | `_card_status`
0x800c0250 |  16    | 0x10   | 4      | `_new_card`
0x800c0260 |  16    | 0x10   | 4      | `_card_write`
0x800c0270 |  16    | 0x10   | 4      | `printf`
0x800c0280 |  16    | 0x10   | 4      | `bzero`
0x800c0290 |  16    | 0x10   | 4      | `strcpy`
0x800c02a0 |  16    | 0x10   | 4      | `memcpy`
0x800c02b0 |  16    | 0x10   | 4      | `abs`
0x800c02c0 |  16    | 0x10   | 4      | `rand`
0x800c02d0 |  16    | 0x10   | 4      | `strlen`
0x800c02e0 |  16    | 0x10   | 4      | `strncpy`
0x800c02f0 |  16    | 0x10   | 4      | `strcat`
0x800c0300 |  16    | 0x10   | 4      | `strncat`
0x800c0310 |  16    | 0x10   | 4      | `srand`
0x800c0320 |  3456  | 0xd80  | 864    | `sprintf`
0x800c10a0 |  16    | 0x10   | 4      | `strcmp`
0x800c10b0 |  16    | 0x10   | 4      | `exit`
0x800c10c0 |  16    | 0x10   | 4      | `strncmp`
0x800c10d0 |  16    | 0x10   | 4      | `bcopy`
0x800c10e0 |  16    | 0x10   | 4      | `setjmp`
0x800c10f0 |  16    | 0x10   | 4      | `memchr`
0x800c1100 |  16    | 0x10   | 4      | `memmove`
0x800c1110 |  16    | 0x10   | 4      | `SetSp`
0x800c1120 |  16    | 0x10   | 4      | `InitHeap`
0x800c1130 |  16    | 0x10   | 4      | `GetGp`
0x800c1140 |  16    | 0x10   | 4      | `InitPAD`
0x800c1150 |  16    | 0x10   | 4      | `StartPAD`
0x800c1160 |  16    | 0x10   | 4      | `ChangeClearPAD`
0x800c1170 |  16    | 0x10   | 4      | `EnterCriticalSection`
0x800c1180 |  16    | 0x10   | 4      | `FlushCache`
0x800c1190 |  16    | 0x10   | 4      | `ExitCriticalSection`
0x800c11a0 |  16    | 0x10   | 4      | `OpenEvent`
0x800c11b0 |  16    | 0x10   | 4      | `EnableEvent`
0x800c11c0 |  156   | 0x9c   | 39     | `SetRCnt`
0x800c125c |  56    | 0x38   | 14     | `GetRCnt`
0x800c1294 |  52    | 0x34   | 13     | `StartRCnt`
0x800c12c8 |  52    | 0x34   | 13     | `StopRCnt`
0x800c12fc |  52    | 0x34   | 13     | `ResetRCnt`
0x800c1330 |  16    | 0x10   | 4      | `GetSp`
0x800c1340 |  16    | 0x10   | 4      | `TestEvent`
0x800c1350 |  16    | 0x10   | 4      | `CloseEvent`
0x800c1360 |  16    | 0x10   | 4      | `format`
0x800c1370 |  16    | 0x10   | 4      | `close`
0x800c1380 |  16    | 0x10   | 4      | `open`
0x800c1390 |  16    | 0x10   | 4      | `delete`
0x800c13a0 |  16    | 0x10   | 4      | `read`
0x800c13b0 |  16    | 0x10   | 4      | `write`
0x800c13c0 |  16    | 0x10   | 4      | `_96_init`
0x800c13d0 |  16    | 0x10   | 4      | `LoadExec`
0x800c13e0 |  16    | 0x10   | 4      | `_96_remove`
0x800c13f0 |  16    | 0x10   | 4      | `DeliverEvent`
0x800c1400 |  16    | 0x10   | 4      | `DisableEvent`
0x800c1410 |  16    | 0x10   | 4      | `GPU_cw`
0x800c1420 |  16    | 0x10   | 4      | `ReturnFromException`
0x800c1430 |  16    | 0x10   | 4      | `HookEntryInt`
0x800c1440 |  16    | 0x10   | 4      | `PAD_init`
0x800c1450 |  16    | 0x10   | 4      | `PAD_dr`
0x800c1460 |  16    | 0x10   | 4      | `StopPAD`
0x800c1470 |  21488 | 0x53f0 | 5372   | `ChangeClearRCnt`
0x800c6860 |  4     | 0x4    | 1      | `suuzi0`
0x800c6864 |  4     | 0x4    | 1      | `suuzi1`
0x800c6868 |  4     | 0x4    | 1      | `suuzi2`
0x800c686c |  4     | 0x4    | 1      | `suuzi3`
0x800c6870 |  4     | 0x4    | 1      | `suuzi4`
0x800c6874 |  4     | 0x4    | 1      | `suuzi5`
0x800c6878 |  4     | 0x4    | 1      | `suuzi6`
0x800c687c |  4     | 0x4    | 1      | `suuzi7`
0x800c6880 |  4     | 0x4    | 1      | `suuzi8`
0x800c6884 |  4     | 0x4    | 1      | `suuzi9`
0x800c6888 |  8     | 0x8    | 2      | `suuzi10`
0x800c6890 |  8     | 0x8    | 2      | `suuzi11`
0x800c6898 |  8     | 0x8    | 2      | `suuzi12`
0x800c68a0 |  8     | 0x8    | 2      | `suuzi13`
0x800c68a8 |  8     | 0x8    | 2      | `suuzi14`
0x800c68b0 |  8     | 0x8    | 2      | `suuzi15`
0x800c68b8 |  8     | 0x8    | 2      | `suuzi16`
0x800c68c0 |  68    | 0x44   | 17     | `suuzi_0org`
0x800c6904 |  4     | 0x4    | 1      | `suuzi`
0x800c6908 |  8     | 0x8    | 2      | `com_name_tai`
0x800c6910 |  8     | 0x8    | 2      | `com_name_bun`
0x800c6918 |  8     | 0x8    | 2      | `com_name_ri`
0x800c6920 |  8     | 0x8    | 2      | `com_name_gei`
0x800c6928 |  8     | 0x8    | 2      | `com_name_un`
0x800c6930 |  8     | 0x8    | 2      | `com_name_zat`
0x800c6938 |  8     | 0x8    | 2      | `com_name_you`
0x800c6940 |  8     | 0x8    | 2      | `com_name_kon`
0x800c6948 |  12    | 0xc    | 3      | `com_name_str`
0x800c6954 |  36    | 0x24   | 9      | `com_name`
0x800c6978 |  12    | 0xc    | 3      | `date_name_0`
0x800c6984 |  20    | 0x14   | 5      | `date_name_1`
0x800c6998 |  16    | 0x10   | 4      | `date_name_2`
0x800c69a8 |  8     | 0x8    | 2      | `date_name_3`
0x800c69b0 |  8     | 0x8    | 2      | `date_name_4`
0x800c69b8 |  8     | 0x8    | 2      | `date_name_5`
0x800c69c0 |  16    | 0x10   | 4      | `date_name_6`
0x800c69d0 |  8     | 0x8    | 2      | `date_name_7`
0x800c69d8 |  8     | 0x8    | 2      | `date_name_8`
0x800c69e0 |  16    | 0x10   | 4      | `date_name_9`
0x800c69f0 |  16    | 0x10   | 4      | `date_name_10`
0x800c6a00 |  12    | 0xc    | 3      | `date_name_11`
0x800c6a0c |  8     | 0x8    | 2      | `date_name_12`
0x800c6a14 |  12    | 0xc    | 3      | `date_name_13`
0x800c6a20 |  8     | 0x8    | 2      | `date_name_14`
0x800c6a28 |  16    | 0x10   | 4      | `date_name_15`
0x800c6a38 |  8     | 0x8    | 2      | `date_name_16`
0x800c6a40 |  4     | 0x4    | 1      | `date_name_17`
0x800c6a44 |  8     | 0x8    | 2      | `date_name_18`
0x800c6a4c |  12    | 0xc    | 3      | `date_name_19`
0x800c6a58 |  12    | 0xc    | 3      | `date_name_20`
0x800c6a64 |  84    | 0x54   | 21     | `date_name`
0x800c6ab8 |  12    | 0xc    | 3      | `tc_name_0`
0x800c6ac4 |  12    | 0xc    | 3      | `tc_name_1`
0x800c6ad0 |  12    | 0xc    | 3      | `tc_name_2`
0x800c6adc |  12    | 0xc    | 3      | `tc_name_3`
0x800c6ae8 |  12    | 0xc    | 3      | `tc_name_4`
0x800c6af4 |  12    | 0xc    | 3      | `tc_name_5`
0x800c6b00 |  8     | 0x8    | 2      | `tc_name_6`
0x800c6b08 |  8     | 0x8    | 2      | `tc_name_7`
0x800c6b10 |  12    | 0xc    | 3      | `tc_name_8`
0x800c6b1c |  12    | 0xc    | 3      | `tc_name_9`
0x800c6b28 |  12    | 0xc    | 3      | `tc_name_10`
0x800c6b34 |  12    | 0xc    | 3      | `tc_name_11`
0x800c6b40 |  12    | 0xc    | 3      | `tc_name_12`
0x800c6b4c |  12    | 0xc    | 3      | `tc_name_13`
0x800c6b58 |  12    | 0xc    | 3      | `tc_name_14`
0x800c6b64 |  12    | 0xc    | 3      | `tc_name_15`
0x800c6b70 |  64    | 0x40   | 16     | `tc_name`
0x800c6bb0 |  8     | 0x8    | 2      | `tc_sname_0`
0x800c6bb8 |  8     | 0x8    | 2      | `tc_sname_1`
0x800c6bc0 |  8     | 0x8    | 2      | `tc_sname_2`
0x800c6bc8 |  8     | 0x8    | 2      | `tc_sname_3`
0x800c6bd0 |  8     | 0x8    | 2      | `tc_sname_4`
0x800c6bd8 |  8     | 0x8    | 2      | `tc_sname_5`
0x800c6be0 |  8     | 0x8    | 2      | `tc_sname_6`
0x800c6be8 |  4     | 0x4    | 1      | `tc_sname_7`
0x800c6bec |  8     | 0x8    | 2      | `tc_sname_8`
0x800c6bf4 |  8     | 0x8    | 2      | `tc_sname_9`
0x800c6bfc |  8     | 0x8    | 2      | `tc_sname_10`
0x800c6c04 |  8     | 0x8    | 2      | `tc_sname_11`
0x800c6c0c |  8     | 0x8    | 2      | `tc_sname_12`
0x800c6c14 |  8     | 0x8    | 2      | `tc_sname_13`
0x800c6c1c |  8     | 0x8    | 2      | `tc_sname_14`
0x800c6c24 |  8     | 0x8    | 2      | `tc_sname_15`
0x800c6c2c |  64    | 0x40   | 16     | `tc_sname`
0x800c6c6c |  4     | 0x4    | 1      | `kun`
0x800c6c70 |  8     | 0x8    | 2      | `san`
0x800c6c78 |  4     | 0x4    | 1      | `non`
0x800c6c7c |  4     | 0x4    | 1      | `space`
0x800c6c80 |  64    | 0x40   | 16     | `xass`
0x800c6cc0 |  64    | 0x40   | 16     | `girl_vh`
0x800c6d00 |  64    | 0x40   | 16     | `girl_vb`
0x800c6d40 |  64    | 0x40   | 16     | `girl_seq`
0x800c6d80 |  4     | 0x4    | 1      | `cal_dat`
0x800c6d84 |  4     | 0x4    | 1      | `f_main07`
0x800c6d88 |  40    | 0x28   | 10     | `stadium_data`
0x800c6db0 |  92    | 0x5c   | 23     | `telephone_kigou`
0x800c6e0c |  104   | 0x68   | 26     | `aisatu_sector`
0x800c6e74 |  104   | 0x68   | 26     | `aisatu_sector2`
0x800c6edc |  8     | 0x8    | 2      | `bukatu_name0`
0x800c6ee4 |  8     | 0x8    | 2      | `bukatu_name1`
0x800c6eec |  8     | 0x8    | 2      | `bukatu_name2`
0x800c6ef4 |  8     | 0x8    | 2      | `bukatu_name3`
0x800c6efc |  8     | 0x8    | 2      | `bukatu_name4`
0x800c6f04 |  8     | 0x8    | 2      | `bukatu_name5`
0x800c6f0c |  8     | 0x8    | 2      | `bukatu_name6`
0x800c6f14 |  12    | 0xc    | 3      | `bukatu_name7`
0x800c6f20 |  8     | 0x8    | 2      | `bukatu_name8`
0x800c6f28 |  8     | 0x8    | 2      | `bukatu_name9`
0x800c6f30 |  8     | 0x8    | 2      | `bukatu_name10`
0x800c6f38 |  8     | 0x8    | 2      | `bukatu_name11`
0x800c6f40 |  48    | 0x30   | 12     | `bukatu_name_table`
0x800c6f70 |  32    | 0x20   | 8      | `card_file_name`
0x800c6f90 |  4     | 0x4    | 1      | `pad_mode`
0x800c6f94 |  80    | 0x50   | 20     | `konami_command`
0x800c6fe4 |  4     | 0x4    | 1      | `konami_command_tag`
0x800c6fe8 |  4     | 0x4    | 1      | `konami_command_flag`
0x800c6fec |  4     | 0x4    | 1      | `konami_command_timer`
0x800c6ff0 |  32    | 0x20   | 8      | `gs_vcnt`
0x800c7010 |  4     | 0x4    | 1      | `trans_flag`
0x800c7014 |  4     | 0x4    | 1      | `msflag`
0x800c7018 |  4     | 0x4    | 1      | `same_se`
0x800c701c |  4     | 0x4    | 1      | `same_seq`
0x800c7020 |  4     | 0x4    | 1      | `last_m_se`
0x800c7024 |  4     | 0x4    | 1      | `last_m_seq`
0x800c7028 |  4     | 0x4    | 1      | `last_s_se`
0x800c702c |  4     | 0x4    | 1      | `last_s_seq`
0x800c7030 |  4     | 0x4    | 1      | `seq_on_off`
0x800c7034 |  4     | 0x4    | 1      | `seq_info`
0x800c7038 |  4     | 0x4    | 1      | `cur_seq_num`
0x800c703c |  4     | 0x4    | 1      | `trans_wait_counter`
0x800c7040 |  16    | 0x10   | 4      | `sd_err_flag`
0x800c7050 |  4     | 0x4    | 1      | `cd_check_level`
0x800c7054 |  4     | 0x4    | 1      | `cdsectors`
0x800c7058 |  4     | 0x4    | 1      | `last_sector`
0x800c705c |  20    | 0x14   | 5      | `XAsector`
0x800c7070 |  4     | 0x4    | 1      | `night_x1`
0x800c7074 |  4     | 0x4    | 1      | `night_x2`
0x800c7078 |  4     | 0x4    | 1      | `night_x3`
0x800c707c |  4     | 0x4    | 1      | `night_y1`
0x800c7080 |  4     | 0x4    | 1      | `night_y2`
0x800c7084 |  12    | 0xc    | 3      | `night_y3`
0x800c7090 |  48    | 0x30   | 12     | `print_flag`
0x800c70c0 |  4     | 0x4    | 1      | `ko_move_ok`
0x800c70c4 |  12    | 0xc    | 3      | `s_count`
0x800c70d0 |  384   | 0x180  | 96     | `k_work`
0x800c7250 |  12    | 0xc    | 3      | `ksys`
0x800c725c |  64    | 0x40   | 16     | `sjis_col`
0x800c729c |  64    | 0x40   | 16     | `sjis_col_s`
0x800c72dc |  196   | 0xc4   | 49     | `sjis_data`
0x800c73a0 |  16    | 0x10   | 4      | `x_taku_y`
0x800c73b0 |  16    | 0x10   | 4      | `tokimeki_hosei_table`
0x800c73c0 |  16    | 0x10   | 4      | `tokimeki_check_table`
0x800c73d0 |  16    | 0x10   | 4      | `tokimeki_check_pattern`
0x800c73e0 |  104   | 0x68   | 26     | `girl_l`
0x800c7448 |  8     | 0x8    | 2      | `para_sl`
0x800c7450 |  16    | 0x10   | 4      | `yuukou_hosei_table`
0x800c7460 |  400   | 0x190  | 100    | `grp_tbl`
0x800c75f0 |  8     | 0x8    | 2      | `fuji_para_tbl`
0x800c75f8 |  12    | 0xc    | 3      | `SYOUSIN_BAIRITU`
0x800c7604 |  12    | 0xc    | 3      | `PARA_GA`
0x800c7610 |  12    | 0xc    | 3      | `PARA_GB`
0x800c761c |  16    | 0x10   | 4      | `END_PLUS_POINT`
0x800c762c |  20    | 0x14   | 5      | `STRESS_TABLE`
0x800c7640 |  416   | 0x1a0  | 104    | `icon_col`
0x800c77e0 |  384   | 0x180  | 96     | `icon_image0`
0x800c7960 |  384   | 0x180  | 96     | `icon_image1`
0x800c7ae0 |  384   | 0x180  | 96     | `icon_image2`
0x800c7c60 |  384   | 0x180  | 96     | `icon_image3`
0x800c7de0 |  384   | 0x180  | 96     | `icon_image4`
0x800c7f60 |  384   | 0x180  | 96     | `icon_image5`
0x800c80e0 |  384   | 0x180  | 96     | `icon_image6`
0x800c8260 |  384   | 0x180  | 96     | `icon_image7`
0x800c83e0 |  384   | 0x180  | 96     | `icon_image8`
0x800c8560 |  384   | 0x180  | 96     | `icon_image9`
0x800c86e0 |  384   | 0x180  | 96     | `icon_imagea`
0x800c8860 |  384   | 0x180  | 96     | `icon_imageb`
0x800c89e0 |  384   | 0x180  | 96     | `icon_imagec`
0x800c8b60 |  64    | 0x40   | 16     | `icon_image`
0x800c8ba0 |  4     | 0x4    | 1      | `frame_cnt`
0x800c8ba4 |  4     | 0x4    | 1      | `max_frame`
0x800c8ba8 |  4     | 0x4    | 1      | `movie_ofx`
0x800c8bac |  4     | 0x4    | 1      | `movie_ofy`
0x800c8bb0 |  4     | 0x4    | 1      | `rgb_mode`
0x800c8bb4 |  28    | 0x1c   | 7      | `next_line`
0x800c8bd0 |  24    | 0x18   | 6      | `dec_bg_sector`
0x800c8be8 |  4     | 0x4    | 1      | `now_dec_bg_show`
0x800c8bec |  4     | 0x4    | 1      | `last_gamen_mode`
0x800c8bf0 |  4     | 0x4    | 1      | `full_move_timer`
0x800c8bf4 |  12    | 0xc    | 3      | `tbg_bri`
0x800c8c00 |  16    | 0x10   | 4      | `season_main_e_bg_sector`
0x800c8c10 |  16    | 0x10   | 4      | `season_main_n_bg_sector`
0x800c8c20 |  64    | 0x40   | 16     | `radio_sector`
0x800c8c60 |  80    | 0x50   | 20     | `radio_sector_m`
0x800c8cb0 |  4     | 0x4    | 1      | `now_select_menu`
0x800c8cb4 |  4     | 0x4    | 1      | `message_kind`
0x800c8cb8 |  4     | 0x4    | 1      | `src_album`
0x800c8cbc |  4     | 0x4    | 1      | `dst_album`
0x800c8cc0 |  4     | 0x4    | 1      | `cardsys0`
0x800c8cc4 |  4     | 0x4    | 1      | `fan_size`
0x800c8cc8 |  4     | 0x4    | 1      | `fan_x_pos`
0x800c8ccc |  4     | 0x4    | 1      | `fan_y_pos`
0x800c8cd0 |  4     | 0x4    | 1      | `fan_x_speed`
0x800c8cd4 |  4     | 0x4    | 1      | `fan_y_speed`
0x800c8cd8 |  4     | 0x4    | 1      | `debug_step`
0x800c8cdc |  24    | 0x18   | 6      | `yes_string0`
0x800c8cf4 |  4     | 0x4    | 1      | `yes_string`
0x800c8cf8 |  24    | 0x18   | 6      | `no_string0`
0x800c8d10 |  4     | 0x4    | 1      | `no_string`
0x800c8d14 |  4     | 0x4    | 1      | `migi_string`
0x800c8d18 |  24    | 0x18   | 6      | `hidari_string`
0x800c8d30 |  120   | 0x78   | 30     | `no_memcard`
0x800c8da8 |  120   | 0x78   | 30     | `save_error`
0x800c8e20 |  120   | 0x78   | 30     | `cant_read_memcard`
0x800c8e98 |  120   | 0x78   | 30     | `cant_read_cd0`
0x800c8f10 |  112   | 0x70   | 28     | `cant_read_cd1`
0x800c8f80 |  208   | 0xd0   | 52     | `morning_sector`
0x800c9050 |  4     | 0x4    | 1      | `vol_max`
0x800c9054 |  4     | 0x4    | 1      | `now_icon`
0x800c9058 |  4     | 0x4    | 1      | `now_icon_timer`
0x800c905c |  64    | 0x40   | 16     | `icon_xy_b`
0x800c909c |  64    | 0x40   | 16     | `icon_xy_a`
0x800c90dc |  4     | 0x4    | 1      | `basyo_len`
0x800c90e0 |  160   | 0xa0   | 40     | `cal_color`
0x800c9180 |  4     | 0x4    | 1      | `season_timer`
0x800c9184 |  4     | 0x4    | 1      | `bg_scroll_x`
0x800c9188 |  4     | 0x4    | 1      | `bg_scroll_y`
0x800c918c |  4     | 0x4    | 1      | `back_bg_pri`
0x800c9190 |  16    | 0x10   | 4      | `season_seq`
0x800c91a0 |  16    | 0x10   | 4      | `season_vh`
0x800c91b0 |  16    | 0x10   | 4      | `season_vb`
0x800c91c0 |  16    | 0x10   | 4      | `mascot_kind`
0x800c91d0 |  28    | 0x1c   | 7      | `iv2ic`
0x800c91ec |  224   | 0xe0   | 56     | `concert_names`
0x800c92cc |  16    | 0x10   | 4      | `concert_kind_f`
0x800c92dc |  224   | 0xe0   | 56     | `cinema_name`
0x800c93bc |  16    | 0x10   | 4      | `cinema_kind`
0x800c93cc |  152   | 0x98   | 38     | `message_newspot`
0x800c9464 |  1404  | 0x57c  | 351    | `message_main`
0x800c99e0 |  108   | 0x6c   | 27     | `p_mes0`
0x800c9a4c |  72    | 0x48   | 18     | `p_mes1`
0x800c9a94 |  24    | 0x18   | 6      | `p_mes2`
0x800c9aac |  96    | 0x60   | 24     | `p_mes3`
0x800c9b0c |  28    | 0x1c   | 7      | `p_mes4`
0x800c9b28 |  60    | 0x3c   | 15     | `p_mes5`
0x800c9b64 |  20    | 0x14   | 5      | `p_mes6`
0x800c9b78 |  24    | 0x18   | 6      | `p_mes7`
0x800c9b90 |  112   | 0x70   | 28     | `p_mes8`
0x800c9c00 |  52    | 0x34   | 13     | `p_mes9`
0x800c9c34 |  108   | 0x6c   | 27     | `p_mes10`
0x800c9ca0 |  36    | 0x24   | 9      | `p_mes11`
0x800c9cc4 |  12    | 0xc    | 3      | `p_mes12`
0x800c9cd0 |  64    | 0x40   | 16     | `player_message`
0x800c9d10 |  20    | 0x14   | 5      | `date_light_x`
0x800c9d24 |  20    | 0x14   | 5      | `date_light_iso`
0x800c9d38 |  4     | 0x4    | 1      | `pat_pat`
0x800c9d3c |  36    | 0x24   | 9      | `sum_month`
0x800c9d60 |  4     | 0x4    | 1      | `first_girl`
0x800c9d64 |  28    | 0x1c   | 7      | `border`
0x800c9d80 |  32    | 0x20   | 8      | `sd_bg_sector`
0x800c9da0 |  44    | 0x2c   | 11     | `club_bg_sector`
0x800c9dcc |  100   | 0x64   | 25     | `main_sd_sector`
0x800c9e30 |  128   | 0x80   | 32     | `club_sd_sector`
0x800c9eb0 |  24    | 0x18   | 6      | `club_sd_data_s`
0x800c9ec8 |  24    | 0x18   | 6      | `club_sd_data_w`
0x800c9ee0 |  16    | 0x10   | 4      | `sd_data_s`
0x800c9ef0 |  16    | 0x10   | 4      | `sd_data_w`
0x800c9f00 |  72    | 0x48   | 18     | `toki_para_d`
0x800c9f48 |  104   | 0x68   | 26     | `toki_para_club_d`
0x800c9fb0 |  4     | 0x4    | 1      | `tel_check_tag`
0x800c9fb4 |  32    | 0x20   | 8      | `sd_h_bg_sector`
0x800c9fd4 |  20    | 0x14   | 5      | `demachiawase`
0x800c9fe8 |  8     | 0x8    | 2      | `sd_h_data_s`
0x800c9ff0 |  8     | 0x8    | 2      | `sd_h_data_w`
0x800c9ff8 |  56    | 0x38   | 14     | `main_h_sd_sector`
0x800ca030 |  4     | 0x4    | 1      | `lf_mode`
0x800ca034 |  4     | 0x4    | 1      | `lf_step`
0x800ca038 |  4     | 0x4    | 1      | `lf_sector_size`
0x800ca03c |  4     | 0x4    | 1      | `lf_addr`
0x800ca040 |  16    | 0x10   | 4      | `lf_cd_sector`
0x800ca050 |  62076 | 0xf27c | 15519  | `sjissce`
0x800d92cc |  8     | 0x8    | 2      | `o_asobi_rom_table`
0x800d92d4 |  60    | 0x3c   | 15     | `o_asobi_pattern_table`
0x800d9310 |  4     | 0x4    | 1      | `o_asobi_animation_table`
0x800d9314 |  4     | 0x4    | 1      | `o_asobi_max_animation`
0x800d9318 |  8     | 0x8    | 2      | `o_asobi_opd_info`
0x800d9320 |  13760 | 0x35c0 | 3440   | `c_main_col`
0x800dc8e0 |  20    | 0x14   | 5      | `BUNKEI`
0x800dc8f4 |  20    | 0x14   | 5      | `RIKEI`
0x800dc908 |  20    | 0x14   | 5      | `GEIJYUTU`
0x800dc91c |  20    | 0x14   | 5      | `UNDOU`
0x800dc930 |  32    | 0x20   | 8      | `BUKATU`
0x800dc950 |  20    | 0x14   | 5      | `ASOBI`
0x800dc964 |  20    | 0x14   | 5      | `YOUSI`
0x800dc978 |  32    | 0x20   | 8      | `NERU`
0x800dc998 |  12    | 0xc    | 3      | `DENWA`
0x800dc9a4 |  20    | 0x14   | 5      | `DATE`
0x800dc9b8 |  20    | 0x14   | 5      | `JYOUHOU`
0x800dc9cc |  20    | 0x14   | 5      | `SYSTEM`
0x800dc9e0 |  20    | 0x14   | 5      | `CALENDAR`
0x800dc9f4 |  28    | 0x1c   | 7      | `MEMORY`
0x800dca10 |  20    | 0x14   | 5      | `SAVETYUU`
0x800dca24 |  12    | 0xc    | 3      | `YOKUJITU`
0x800dca30 |  44    | 0x2c   | 11     | `o_main_rom_table`
0x800dca5c |  696   | 0x2b8  | 174    | `o_main_pattern_table`
0x800dcd14 |  64    | 0x40   | 16     | `o_main_animation_table`
0x800dcd54 |  4     | 0x4    | 1      | `o_main_max_animation`
0x800dcd58 |  8     | 0x8    | 2      | `o_main_opd_info`
0x800dcd60 |  768   | 0x300  | 192    | `byouki_csr`
0x800dd060 |  512   | 0x200  | 128    | `byouki_col`
0x800dd260 |  152   | 0x98   | 38     | `sd_adr`
0x800dd2f8 |  80    | 0x50   | 20     | `sd_h_adr`
0x800dd348 |  192   | 0xc0   | 48     | `sdc_adr`
0x800dd408 |  24    | 0x18   | 6      | `sde_adr`
0x800dd420 |  4     | 0x4    | 1      | `a_rom_table`
0x800dd424 |  4     | 0x4    | 1      | `a_pattern_table`
0x800dd428 |  4     | 0x4    | 1      | `a_animation_table`
0x800dd42c |  4     | 0x4    | 1      | `a_max_animation`
0x800dd430 |  4     | 0x4    | 1      | `a_col`
0x800dd434 |  4     | 0x4    | 1      | `now_s`
0x800dd438 |  4     | 0x4    | 1      | `now_s_in`
0x800dd43c |  4     | 0x4    | 1      | `ss_s`
0x800dd440 |  4     | 0x4    | 1      | `ss_s_kind`
0x800dd444 |  4     | 0x4    | 1      | `sss_so`
0x800dd448 |  4     | 0x4    | 1      | `now_serifu`
0x800dd44c |  4     | 0x4    | 1      | `now_serifu_in`
0x800dd450 |  4     | 0x4    | 1      | `now_serifuev`
0x800dd454 |  4     | 0x4    | 1      | `now_serifuev_in`
0x800dd458 |  4     | 0x4    | 1      | `now_serifue`
0x800dd45c |  4     | 0x4    | 1      | `now_serifue_in`
0x800dd460 |  4     | 0x4    | 1      | `ss_serifu`
0x800dd464 |  4     | 0x4    | 1      | `ss_serifu_kind`
0x800dd468 |  4     | 0x4    | 1      | `sss_sound`
0x800dd46c |  8     | 0x8    | 2      | `p_name`
0x800dd474 |  8     | 0x8    | 2      | `pp_name`
0x800dd47c |  12    | 0xc    | 3      | `p_name2`
0x800dd488 |  8     | 0x8    | 2      | `g_name`
0x800dd490 |  12    | 0xc    | 3      | `g_name2`
0x800dd49c |  64    | 0x40   | 16     | `ba_string`
0x800dd4dc |  64    | 0x40   | 16     | `ba_string2`
0x800dd51c |  8     | 0x8    | 2      | `kao`
0x800dd524 |  8     | 0x8    | 2      | `kao2`
0x800dd52c |  8     | 0x8    | 2      | `imp`
0x800dd534 |  8     | 0x8    | 2      | `ans`
0x800dd53c |  12    | 0xc    | 3      | `shu_name`
0x800dd548 |  8     | 0x8    | 2      | `oname`
0x800dd550 |  12    | 0xc    | 3      | `wname`
0x800dd55c |  36    | 0x24   | 9      | `aname`
0x800dd580 |  36    | 0x24   | 9      | `mname`
0x800dd5a4 |  4     | 0x4    | 1      | `junban`
0x800dd5a8 |  4     | 0x4    | 1      | `sound_seek_wait`
0x800dd5ac |  4     | 0x4    | 1      | `sound_seek_time`
0x800dd5b0 |  12    | 0xc    | 3      | `girl_appear`
0x800dd5bc |  4     | 0x4    | 1      | `scroll_exist`
0x800dd5c0 |  4     | 0x4    | 1      | `last_x_y`
0x800dd5c4 |  4     | 0x4    | 1      | `xcut`
0x800dd5c8 |  4     | 0x4    | 1      | `yajirusi_timer`
0x800dd5cc |  4     | 0x4    | 1      | `shugaku_place`
0x800dd5d0 |  4     | 0x4    | 1      | `ss_serifu_shugaku`
0x800dd5d4 |  4     | 0x4    | 1      | `ss_serifu_shugaku_kind`
0x800dd5d8 |  4     | 0x4    | 1      | `sss_sound_shugaku`
0x800dd5dc |  4     | 0x4    | 1      | `now_serifu_shugaku`
0x800dd5e0 |  4     | 0x4    | 1      | `now_serifu_shugaku_in`
0x800dd5e4 |  4     | 0x4    | 1      | `with_yoshi`
0x800dd5e8 |  4     | 0x4    | 1      | `move_in`
0x800dd5ec |  4     | 0x4    | 1      | `date_place`
0x800dd5f0 |  4     | 0x4    | 1      | `basho_num`
0x800dd5f4 |  24    | 0x18   | 6      | `menu_x`
0x800dd60c |  24    | 0x18   | 6      | `menu_y`
0x800dd624 |  24    | 0x18   | 6      | `menu_w`
0x800dd63c |  52    | 0x34   | 13     | `menu_h`
0x800dd670 |  132   | 0x84   | 33     | `mdec_iq`
0x800dd6f4 |  204   | 0xcc   | 51     | `mdec_coef`
0x800dd7c0 |  2048  | 0x800  | 512    | `DCL_DVLC`
0x800ddfc0 |  2048  | 0x800  | 512    | `DCC_DVLC`
0x800de7c0 |  65536 | 0x10000| 16384  | `CF_DVLC`
0x800ee7c0 |  4352  | 0x1100 | 1088   | `CF2_DVLC`
0x800ef8c0 |  4     | 0x4    | 1      | `CD_debug`
0x800ef8c4 |  4     | 0x4    | 1      | `CD_isopen`
0x800ef8c8 |  116   | 0x74   | 29     | `CD_comstr`
0x800ef93c |  1236  | 0x4d4  | 309    | `CD_intstr`
0x800efe10 |  1056  | 0x420  | 264    | `_spu_zerobuf`
0x800f0230 |  40    | 0x28   | 10     | `_spu_rev_startaddr`
0x800f0258 |  880   | 0x370  | 220    | `_spu_rev_workareasize`
0x800f05c8 |  1000  | 0x3e8  | 250    | `GPU_printf`
0x800f09b0 |  2048  | 0x800  | 512    | `rsin_tbl`
0x800f11b0 |  17424 | 0x4410 | 4356   | `rcossin_tbl`
0x800f55c0 |  17696 | 0x4520 | 4424   | `Vcount`
0x800f9ae0 |  6768  | 0x1a70 | 1692   | `sys`
0x800fb550 |  2144  | 0x860  | 536    | `sys0`
0x800fbdb0 |  64    | 0x40   | 16     | `padbuf0`
0x800fbdf0 |  64    | 0x40   | 16     | `padbuf1`
0x800fbe30 |  48    | 0x30   | 12     | `WorldOT`
0x800fbe60 |  2048  | 0x800  | 512    | `OTTags`
0x800fc660 |  40960 | 0xa000 | 10240  | `GpuPacketArea`
0x80106660 |2264    | 0x22000| 34816  | `out_packet2`
0x80128660 |  4     | 0x4    | 1      | `activeBuff`
0x80128664 |  4     | 0x4    | 1      | `cursor_flag`
0x80128668 |  4     | 0x4    | 1      | `VB`
0x8012866c |  4     | 0x4    | 1      | `CE0`
0x80128670 |  4     | 0x4    | 1      | `CE1`
0x80128674 |  4     | 0x4    | 1      | `CE2`
0x80128678 |  4     | 0x4    | 1      | `CE3`
0x8012867c |  4     | 0x4    | 1      | `CEH0`
0x80128680 |  4     | 0x4    | 1      | `CEH1`
0x80128684 |  4     | 0x4    | 1      | `CEH2`
0x80128688 |  8     | 0x8    | 2      | `CEH3`
0x80128690 |  10880 | 0x2a80 | 2720   | `class_w`
0x8012b110 |  80    | 0x50   | 20     | `srn_w`
0x8012b160 |  48    | 0x30   | 12     | `mod_w`
0x8012b190 |  2304  | 0x900  | 576    | `Sprites`
0x8012ba90 |  80    | 0x50   | 20     | `Bg`
0x8012bae0 |  32    | 0x20   | 8      | `Map`
0x8012bb00 |  1024  | 0x400  | 256    | `Cell`
0x8012bf00 |  256   | 0x100  | 64     | `C_index`
0x8012c000 |  560   | 0x230  | 140    | `object`
0x8012c230 |  32    | 0x20   | 8      | `view`
0x8012c250 |  48    | 0x30   | 12     | `pslt`
0x8012c280 |  16    | 0x10   | 4      | `fogp`
0x8012c290 |  2800  | 0xaf0  | 700    | `coord`
0x8012cd80 |  48    | 0x30   | 12     | `daen_obj`
0x8012cdb0 |  256   | 0x100  | 64     | `work_tarao`
0x8012ceb0 |  256   | 0x100  | 64     | `work_miura`
0x8012cfb0 |  256   | 0x100  | 64     | `work_takak`
0x8012d0b0 |  256   | 0x100  | 64     | `work_yamag`
0x8012d1b0 |  64    | 0x40   | 16     | `work_fuku`
0x8012d1f0 |  16    | 0x10   | 4      | `load_func`
0x8012d200 |  8192  | 0x2000 | 2048   | `card`
0x8012f200 |  4     | 0x4    | 1      | `set_gp`
0x8012f204 |  4     | 0x4    | 1      | `old_sp`
0x8012f208 |  4     | 0x4    | 1      | `now_packet_end`
0x8012f20c |  4     | 0x4    | 1      | `now_packet_end2`
0x8012f210 |  8     | 0x8    | 2      | `cd_read_end`
0x8012f218 |  8     | 0x8    | 2      | `rcdresult`
0x8012f220 |  8     | 0x8    | 2      | `scdresult`
0x8012f228 |  8     | 0x8    | 2      | `ccdresult`
0x8012f230 |  4     | 0x4    | 1      | `now_active_area`
0x8012f234 |  4     | 0x4    | 1      | `don_timer`
0x8012f238 |  8     | 0x8    | 2      | `POSITION`
0x8012f240 |  1536  | 0x600  | 384    | `string_buff`
0x8012f840 |  4     | 0x4    | 1      | `now_xa1`
0x8012f844 |  4     | 0x4    | 1      | `now_xa2`
0x8012f848 |  4     | 0x4    | 1      | `now_xa_num`
0x8012f84c |  4     | 0x4    | 1      | `now_xa_on`
0x8012f850 |  4     | 0x4    | 1      | `mdec_bs`
0x8012f854 |  4     | 0x4    | 1      | `mdec_rl`
0x8012f858 |  4     | 0x4    | 1      | `mdec_image`
0x8012f85c |  4     | 0x4    | 1      | `fd`
0x8012f860 |  16    | 0x10   | 4      | `vtw`
0x8012f870 |  8     | 0x8    | 2      | `m`
0x8012f878 |  8     | 0x8    | 2      | `StCdIntrFlag`
0x8012f880 |  16    | 0x10   | 4      | `dec_bg_brightness`
0x8012f890 |  32    | 0x20   | 8      | `GsIDMATRIX`
0x8012f8b0 |  16    | 0x10   | 4      | `vol_mean`
0x8012f8c0 |  64    | 0x40   | 16     | `icon_xy`
0x8012f900 |  16    | 0x10   | 4      | `icon_can_use`
0x8012f910 |  4     | 0x4    | 1      | `basyo_timer`
0x8012f914 |  4     | 0x4    | 1      | `mascot`
0x8012f918 |  1     | 0x1    | 0.25   | `mascot_hi`
0x8012f919 |  3     | 0x3    | 0.75   | `mascot_cw`
0x8012f91c |  4     | 0x4    | 1      | `sd_col`
0x8012f920 |  4     | 0x4    | 1      | `sd_pattern_table`
0x8012f924 |  4     | 0x4    | 1      | `sd_animation_table`
0x8012f928 |  4     | 0x4    | 1      | `sd_rom_table`
0x8012f92c |  7     | 0x7    | 1.75   | `tel_check`
0x8012f933 |  13    | 0xd    | 3.25   | `twinbee_mode`
0x8012f940 |  80    | 0x50   | 20     | `gSDEvt`
0x8012f990 |  80    | 0x50   | 20     | `gSDInfo`
0x8012f9e0 |  16    | 0x10   | 4      | `gSDHeadAdrs`
0x8012f9f0 |  16    | 0x10   | 4      | `gSDBodyAdrs`
0x8012fa00 |  16    | 0x10   | 4      | `gSDBodyLAdrs`
0x8012fa10 |  16    | 0x10   | 4      | `gSDBodySize`
0x8012fa20 |  128   | 0x80   | 32     | `gSDSeqAdrs`
0x8012faa0 |  64    | 0x40   | 16     | `gSDSeqReverb`
0x8012fae0 |  16    | 0x10   | 4      | `gSDCDLevelInfo`
0x8012faf0 |  1024  | 0x400  | 256    | `gSDCDLevel`
0x8012fef0 |  344   | 0x158  | 86     | `gSDSeqTable`
0x80130048 |  8     | 0x8    | 2      | `dc_y`
0x80130050 |  8     | 0x8    | 2      | `dc_cr`
0x80130058 |  8     | 0x8    | 2      | `dc_cb`
0x80130060 |  8     | 0x8    | 2      | `dc_type`
0x80130068 |  8     | 0x8    | 2      | `dec_used`
0x80130070 |  8     | 0x8    | 2      | `dec_pt`
0x80130078 |  8     | 0x8    | 2      | `bs_curt`
0x80130080 |  8     | 0x8    | 2      | `CD_cbsync`
0x80130088 |  8     | 0x8    | 2      | `CD_cbready`
0x80130090 |  8     | 0x8    | 2      | `CD_cbread`
0x80130098 |  8     | 0x8    | 2      | `RingAddr`
0x801300a0 |  8     | 0x8    | 2      | `FinalSector`
0x801300a8 |  8     | 0x8    | 2      | `RingBase`
0x801300b0 |  2048  | 0x800  | 512    | `MarkCallback`
0x801308b0 |  8     | 0x8    | 2      | `VBLANK_MINUS`
0x801308b8 |  8     | 0x8    | 2      | `_snd_openflag`
0x801308c0 |  8     | 0x8    | 2      | `_snd_ev_flag`
0x801308c8 |  8     | 0x8    | 2      | `_snd_seq_s_max`
0x801308d0 |  16    | 0x10   | 4      | `_snd_seq_t_max`
0x801308e0 |  128   | 0x80   | 32     | `_ss_score`
0x80130960 |  8     | 0x8    | 2      | `_snd_seq_no_tick`
0x80130968 |  8     | 0x8    | 2      | `_snd_seq_tick_mode`
0x80130970 |  16    | 0x10   | 4      | `_svm_vab_used`
0x80130980 |  16    | 0x10   | 4      | `_svm_vab_count`
0x80130990 |  64    | 0x40   | 16     | `_svm_vab_vh`
0x801309d0 |  8     | 0x8    | 2      | `_svm_vh`
0x801309d8 |  8     | 0x8    | 2      | `kMaxPrograms`
0x801309e0 |  64    | 0x40   | 16     | `_svm_vab_pg`
0x80130a20 |  16    | 0x10   | 4      | `_svm_pg`
0x80130a30 |  64    | 0x40   | 16     | `_svm_vab_tn`
0x80130a70 |  16    | 0x10   | 4      | `_svm_tn`
0x80130a80 |  64    | 0x40   | 16     | `_svm_brr_start_addr`
0x80130ac0 |  64    | 0x40   | 16     | `_svm_vab_start`
0x80130b00 |  64    | 0x40   | 16     | `_svm_vab_total`
0x80130b40 |  24    | 0x18   | 6      | `_svm_rattr`
0x80130b58 |  8     | 0x8    | 2      | `spuVmMaxVoice`
0x80130b60 |  32    | 0x20   | 8      | `_svm_cur`
0x80130b80 |  8     | 0x8    | 2      | `_svm_stereo_mono`
0x80130b88 |  8     | 0x8    | 2      | `_svm_orev1`
0x80130b90 |  8     | 0x8    | 2      | `_svm_orev2`
0x80130b98 |  8     | 0x8    | 2      | `_svm_okon1`
0x80130ba0 |  8     | 0x8    | 2      | `_svm_okon2`
0x80130ba8 |  8     | 0x8    | 2      | `_svm_okof1`
0x80130bb0 |  8     | 0x8    | 2      | `_svm_okof2`
0x80130bb8 |  8     | 0x8    | 2      | `_svm_damper`
0x80130bc0 |  8     | 0x8    | 2      | `_svm_vcf`
0x80130bc8 |  8     | 0x8    | 2      | `_svm_auto_kof_mode`
0x80130bd0 |  8     | 0x8    | 2      | `_svm_vg`
0x80130bd8 |  8     | 0x8    | 2      | `_spu_fd`
0x80130be0 |  8     | 0x8    | 2      | `_spu_trans_mode`
0x80130be8 |  8     | 0x8    | 2      | `_spu_inTransfer`
0x80130bf0 |  8     | 0x8    | 2      | `_spu_EVdma`
0x80130bf8 |  8     | 0x8    | 2      | `_spu_transferCallback`
0x80130c00 |  24    | 0x18   | 6      | `_spu_rev_attr`
0x80130c18 |  8     | 0x8    | 2      | `_spu_rev_flag`
0x80130c20 |  8     | 0x8    | 2      | `_spu_rev_reserve_wa`
0x80130c28 |  8     | 0x8    | 2      | `_spu_rev_offsetaddr`
0x80130c30 |  8     | 0x8    | 2      | `_spu_keystat`
0x80130c38 |  8     | 0x8    | 2      | `_spu_keyon_bit`
0x80130c40 |  16    | 0x10   | 4      | `_spu_keyoff_bit`
0x80130c50 |  48    | 0x30   | 12     | `_spu_voice_centerNote`
0x80130c80 |  8     | 0x8    | 2      | `_spu_keyevent_time`
0x80130c88 |  8     | 0x8    | 2      | `PSDIDX`
0x80130c90 |  96    | 0x60   | 24     | `GsDRAWENV`
0x80130cf0 |  24    | 0x18   | 6      | `GsDISPENV`
0x80130d08 |  8     | 0x8    | 2      | `PSDGPU`
0x80130d10 |  8     | 0x8    | 2      | `HWD0`
0x80130d18 |  8     | 0x8    | 2      | `VWD0`
0x80130d20 |  32    | 0x20   | 8      | `GsIDMATRIX2`
0x80130d40 |  32    | 0x20   | 8      | `GsLIGHTWSMATRIX`
0x80130d60 |  32    | 0x20   | 8      | `_LC`
0x80130d80 |  8     | 0x8    | 2      | `PSDBASEX`
0x80130d88 |  8     | 0x8    | 2      | `PSDBASEY`
0x80130d90 |  8     | 0x8    | 2      | `CLIP2`
0x80130d98 |  8     | 0x8    | 2      | `PSDOFSX`
0x80130da0 |  16    | 0x10   | 4      | `PSDOFSY`
0x80130db0 |  1280  | 0x500  | 320    | `GsDSTACK`
0x801312b0 |  32    | 0x20   | 8      | `GsWSMATRIX`
0x801312d0 |  8     | 0x8    | 2      | `GsLIGHT_MODE`
0x801312d8 |  8     | 0x8    | 2      | `GsCLIP3far`
0x801312e0 |  8     | 0x8    | 2      | `GsCLIP3near`
0x801312e8 |  8     | 0x8    | 2      | `GsOUT_PACKET_P`
0x801312f0 |  128   | 0x80   | 32     | `DSTACK`
0x80131370 |  8     | 0x8    | 2      | `GsMATE_C`
0x80131378 |  8     | 0x8    | 2      | `GsLMODE`
0x80131380 |  8     | 0x8    | 2      | `GsNDIV`
0x80131388 |  8     | 0x8    | 2      | `GsLIGNR`
0x80131390 |  8     | 0x8    | 2      | `GsLIOFF`
0x80131398 |  8     | 0x8    | 2      | `GsDISPON`
0x801313a0 |  8     | 0x8    | 2      | `GsZOVER`
0x801313a8 |  8     | 0x8    | 2      | `GsBACKC`
0x801313b0 |  8     | 0x8    | 2      | `GsTRATE`
0x801313b8 |  8     | 0x8    | 2      | `GsTON`
0x801313c0 |  16    | 0x10   | 4      | `GsLIGHT_FUNC`
0x801313d0 |  32    | 0x20   | 8      | `GsLSMATRIX`
0x801313f0 |  3088  | 0xc10  | 772    | `PadIdentifier`
0x80132000 |  112   | 0x70   | 28     | `olh_main (global proc .text)`
0x80132070 |  444   | 0x1bc  | 111    | `olh_init (global proc .text)`
0x8013222c |  240   | 0xf0   | 60     | `olh (global proc .text)`
0x8013231c |  32    | 0x20   | 8      | `olh_exit (global proc .text)`
0x8013233c |  244   | 0xf4   | 61     | `move_menu_title (global proc .text)`
0x80132430 |  16    | 0x10   | 4      | `menu0 (global .data)`
0x80132440 |  16    | 0x10   | 4      | `menu1 (global .data)`
0x80132450 |  16    | 0x10   | 4      | `menu2 (global .data)`
0x80132460 |  16    | 0x10   | 4      | `menu3 (global .data)`
0x80132470 |  16    | 0x10   | 4      | `menu4 (global .data)`
0x80132480 |  16    | 0x10   | 4      | `menu5 (global .data)`
0x80132490 |  16    | 0x10   | 4      | `menu6 (global .data)`
0x801324a0 |  16    | 0x10   | 4      | `menu7 (global .data)`
0x801324b0 |  ??    | ??     | ??     | `olh_menu (global .data)`

### Notes

According to [this PDF](http://h41361.www4.hp.com/docs/base_doc/DOCUMENTATION/V50A_ACRO_SUP/OBJSPEC.PDF)
on the COFF format, "impure" refers to a relocatable object or executable. "st 1
sc 2" refers to a global allocated in .data; "st 1 sc 5" refers to an absolute
global, and "st 6 sc 1" a global procedure defined in .text. Nearly all of these
are listed as the first type.
