---
layout: post
title: "User-defined labels"
categories: data
---

Exported symbol table for _Tokimeki Memorial_ based on partially analyzed
disassembly. Most named by myself based on what they appear to do, with many of
those names extracted from the [debug symbols dump](debug-symbols-dump.html)
from stray object file `cdrom/exedir/o.bin` left in by the developers.
`name_ext` refers to the file `cdrom/exedir/name_ext.exn` loaded as an overlay.
This list is for the original SLPS-00064/SLPS/00065 release. A complete dump of
the source code in ASCII won't be provided as it somehow turns out to be over
150 MB.

Name | Location | Type | Namespace | Source | Refcount | Offcut
-----|----------|------|-----------|--------|----------|-------
`copy_default_name` | name_ext::80132000 | Function | Global | User Defined | 15 | 0
`check_memory_card` | name_ext::8013c69c | Function | Global | User Defined | 1 | 0
`memcard_unable_createfile` | name_ext::80140e6c | Function | Global | User Defined | 1 | 0
`memorycard_message` | name_ext::80140f64 | Function | Global | User Defined | 1 | 0
`memcard_createfile` | name_ext::80141020 | Function | Global | User Defined | 1 | 0
`memcard_format__8014200c` | name_ext::8014200c | Function | Global | User Defined | 1 | 0
`opening_movie_main` | name_ext::80142a60 | Function | Global | User Defined | 1 | 0
`opening_narration_0` | name_ext::80142e40 | Function | Global | User Defined | 1 | 0
`opening_narration_1` | name_ext::8014343c | Function | Global | User Defined | 1 | 0
`opening_narration_exit` | name_ext::80144920 | Function | Global | User Defined | 1 | 0
`opening_narration` | name_ext::80144978 | Function | Global | User Defined | 1 | 0
`opening_movie` | name_ext::80144a14 | Function | Global | User Defined | 0 | 0
`s_anata_ga` | name_ext::8014c864 | Data Label | Global | User Defined | 1 | 0
`s_suki_desu` | name_ext::8014c874 | Data Label | Global | User Defined | 1 | 0
`s_girl_a` | name_ext::8014c900 | Data Label | Global | User Defined | 1 | 0
`s_girl_b` | name_ext::8014c908 | Data Label | Global | User Defined | 1 | 0
`s_prologue` | name_ext::8014c910 | Data Label | Global | User Defined | 1 | 0
`s_CHAIR` | name_ext::8014c91c | Data Label | Global | User Defined | 1 | 0
`s_month` | name_ext::8014c924 | Data Label | Global | User Defined | 1 | 0
`s_day` | name_ext::8014c928 | Data Label | Global | User Defined | 1 | 0
`s_kata` | name_ext::8014c930 | Data Label | Global | User Defined | 1 | 0
`default_names` | name_ext::8014ce68 | Data Label | Global | User Defined | 11 | 0
`default_nicknames` | name_ext::8014cf5c | Data Label | Global | User Defined | 4 | 0
`namescreen_q_text` | name_ext::8014d010 | Data Label | Global | User Defined | 8 | 0
`s_bloodtype_O` | name_ext::8014d16c | Data Label | Global | User Defined | 1 | 0
`s_bloodtype_A` | name_ext::8014d170 | Data Label | Global | User Defined | 1 | 0
`s_bloodtype_B` | name_ext::8014d174 | Data Label | Global | User Defined | 1 | 0
`s_bloodtype_AB` | name_ext::8014d178 | Data Label | Global | User Defined | 1 | 0
`arr_bloodtypes` | name_ext::8014d180 | Data Label | Global | User Defined | 1 | 0
`arr_intro_text` | name_ext::8014d938 | Data Label | Global | User Defined | 1 | 0
`warm_reset_init` | 80041000 | Function | Global | User Defined | 1 | 0
`draw_and_disp_env_init` | 800410ac | Function | Global | User Defined | 1 | 0
`print_dr_env` | 800412b4 | Function | Global | User Defined | 2 | 0
`print_di_env` | 800412c8 | Function | Global | User Defined | 2 | 0
`vram_clear` | 80041328 | Function | Global | User Defined | 17 | 0
`system_init` | 800414a0 | Function | Global | User Defined | 4 | 0
`prim_init` | 80041744 | Function | Global | User Defined | 23 | 0
`sprite_init` | 80041774 | Function | Global | User Defined | 3 | 0
`bg_init` | 8004180c | Function | Global | User Defined | 1 | 0
`game_system_init` | 80041a00 | Function | Global | User Defined | 1 | 0
`_game_work_init_set` | 80041a38 | Function | Global | User Defined | 14 | 0
`debug_data_init` | 80041a70 | Function | Global | User Defined | 1 | 0
`game_data_init` | 80041bbc | Function | Global | User Defined | 1 | 0
`play_data_init` | 80041dec | Function | Global | User Defined | 1 | 0
`girl_data_init` | 80042108 | Function | Global | User Defined | 6 | 0
`etc_data_init` | 80042218 | Function | Global | User Defined | 11 | 0
`addr_init_main_rom` | 80042290 | Function | Global | User Defined | 0 | 0
`add_init_main_dat` | 80042298 | Function | Global | User Defined | 0 | 0
`main` | 800422a0 | Function | Global | User Defined | 1 | 0
`_main` | 80042304 | Function | Global | User Defined | 1 | 0
`vblank_callback` | 800425a4 | Function | Global | User Defined | 1 | 0
`myrand` | 800425d0 | Function | Global | User Defined | 0 | 0
`cold_reset_init` | 800425e8 | Function | Global | User Defined | 1 | 0
`cashe_f` | 8004264c | Function | Global | User Defined | 2 | 0
`vblank_ev_set` | 8004267c | Function | Global | User Defined | 2 | 0
`game_main` | 800426f0 | Function | Global | User Defined | 1 | 0
`step_up` | 80042948 | Function | Global | User Defined | 0 | 0
`sub_step_up` | 800429b8 | Function | Global | User Defined | 55 | 0
`sub_sub_step_up` | 800429fc | Function | Global | User Defined | 233 | 0
`goto_step` | 80042a28 | Function | Global | User Defined | 103 | 0
`goto_sub_step` | 80042ab8 | Function | Global | User Defined | 137 | 0
`goto_sub_sub_step` | 80042af0 | Function | Global | User Defined | 131 | 0
`check_load_func` | 80042b10 | Function | Global | User Defined | 2 | 0
`step_display_func` | 80042ba4 | Function | Global | User Defined | 1 | 0
`PadDataRead` | 80042c80 | Function | Global | User Defined | 3 | 0
`controller_check` | 80042d48 | Function | Global | User Defined | 1 | 0
`_pad_data_read_mouse` | 80042f20 | Function | Global | User Defined | 1 | 0
`MyPadRead` | 80043280 | Function | Global | User Defined | 1 | 0
`_pad_data_read_pad` | 80043330 | Function | Global | User Defined | 1 | 0
`konami_command_check` | 80043688 | Function | Global | User Defined | 1 | 0
`pause_func` | 80043744 | Function | Global | User Defined | 1 | 0
`vblank_function` | 80043750 | Function | Global | User Defined | 1 | 0
`draw2d3d` | 80043ae8 | Function | Global | User Defined | 8 | 0
`back_clear_switch` | 80043afc | Function | Global | User Defined | 27 | 0
`load_palette` | 80043b20 | Function | Global | User Defined | 38 | 0
`PlayVoiceLine` | 80044980 | Function | Global | User Defined | 188 | 0
`unused_konamicheck` | 800454b8 | Function | Global | User Defined | 0 | 0
`SetVoiceLine` | 80046560 | Function | Global | User Defined | 37 | 0
`checksum_800466b4` | 800466b4 | Function | Global | User Defined | 7 | 0
`title_80046840` | 80046840 | Function | Global | User Defined | 13 | 0
`gfx_80049038` | 80049038 | Function | Global | User Defined | 7 | 0
`gfx_80049104` | 80049104 | Function | Global | User Defined | 37 | 0
`BG_8004a510` | 8004a510 | Function | Global | User Defined | 15 | 0
`bg_set` | 8004a784 | Function | Global | User Defined | 0 | 0
`gfx_8004e9bc` | 8004e9bc | Function | Global | User Defined | 109 | 0
`Dialog` | 8004ebb0 | Function | Global | User Defined | 536 | 0
`???_8004edd0` | 8004edd0 | Function | Global | User Defined | 0 | 0
`mag_cheat?_8004eed4` | 8004eed4 | Function | Global | User Defined | 55 | 0
`mag_cheat?_8004eefc` | 8004eefc | Function | Global | User Defined | 47 | 0
`mag_cheat_8005121c` | 8005121c | Function | Global | User Defined | 27 | 0
`strings_80051430` | 80051430 | Function | Global | User Defined | 11 | 0
`set_c_girl` | 8005184c | Function | Global | User Defined | 0 | 0
`get_g_name` | 80051858 | Function | Global | User Defined | 5 | 0
`get_p_name` | 80051928 | Function | Global | User Defined | 3 | 0
`get_g_zyotai_s` | 80051e88 | Function | Global | User Defined | 23 | 0
`get_g_zyotai_h` | 80051f68 | Function | Global | User Defined | 9 | 0
`menu_girl_taku_set` | 80051ffc | Function | Global | User Defined | 0 | 0
`xa_wait` | 800521dc | Function | Global | User Defined | 9 | 0
`xa_wait2` | 80052420 | Function | Global | User Defined | 0 | 0
`xa_set_m` | 80052480 | Function | Global | User Defined | 2 | 0
`xa_wait_m` | 8005257c | Function | Global | User Defined | 2 | 0
`get_h_tokimeki` | 80052a68 | Function | Global | User Defined | 9 | 0
`get_h_yuukou` | 800530a8 | Function | Global | User Defined | 10 | 0
`get_h_tokimeki_table` | 80053124 | Function | Global | User Defined | 1 | 0
`get_h_yuukou_table` | 80053174 | Function | Global | User Defined | 3 | 0
`birth_day_check` | 800531c4 | Function | Global | User Defined | 1 | 0
`birth_day_check_days` | 800531f4 | Function | Global | User Defined | 7 | 0
`ending_para_check_fuji` | 80053280 | Function | Global | User Defined | 1 | 0
`ending_para_check_else` | 80053364 | Function | Global | User Defined | 1 | 0
`get_grp` | 800537f0 | Function | Global | User Defined | 6 | 0
`club_undo_check` | 80053904 | Function | Global | User Defined | 3 | 0
`get_club_girl` | 8005393c | Function | Global | User Defined | 4 | 0
`dec_env_set` | 80053a30 | Function | Global | User Defined | 4 | 0
`decdct` | 80053a8c | Function | Global | User Defined | 6 | 0
`card_ev_set` | 80053be0 | Function | Global | User Defined | 1 | 0
`Sw_Start` | 80053c28 | Function | Global | User Defined | 1 | 0
`Hw_Start` | 80053d0c | Function | Global | User Defined | 1 | 0
`Sw_Test` | 80053df0 | Function | Global | User Defined | 1 | 0
`Sw_Clear` | 80053eb8 | Function | Global | User Defined | 6 | 0
`Hw_Test` | 80053f10 | Function | Global | User Defined | 1 | 0
`Hw_Clear` | 80053fdc | Function | Global | User Defined | 2 | 0
`Hw_Stop` | 80054034 | Function | Global | User Defined | 0 | 0
`make_file` | 80054a84 | Function | Global | User Defined | 9 | 0
`delete_file` | 80054af4 | Function | Global | User Defined | 4 | 0
`loadfile` | 80054b7c | Function | Global | User Defined | 2 | 0
`savefile` | 80054c74 | Function | Global | User Defined | 2 | 0
`find_card` | 80054ee4 | Function | Global | User Defined | 5 | 0
`system_check` | 80054f98 | Function | Global | User Defined | 0 | 0
`card_check` | 80054fd4 | Function | Global | User Defined | 0 | 0
`card_w_clear` | 8005503c | Function | Global | User Defined | 5 | 0
`SaveWriter_80055064` | 80055064 | Function | Global | User Defined | 0 | 0
`sys0w2card` | 800553b0 | Function | Global | User Defined | 2 | 0
`card2sys0w?` | 800556bc | Function | Global | User Defined | 3 | 0
`sysw2card?` | 80055950 | Function | Global | User Defined | 2 | 0
`save_80055dd0` | 80055dd0 | Function | Global | User Defined | 13 | 0
`get_file_name` | 800563dc | Function | Global | User Defined | 6 | 0
`vram_test?` | 800565f0 | Function | Global | User Defined | 35 | 0
`exit_function` | 80056670 | Function | Global | User Defined | 1 | 0
`set_movie_offset` | 80056760 | Function | Global | User Defined | 3 | 0
`strInit` | 80056784 | Function | Global | User Defined | 1 | 0
`strSetDefDecEnv` | 8005680c | Function | Global | User Defined | 1 | 0
`strCallback` | 800568fc | Function | Global | User Defined | 1 | 0
`strNextVlc` | 80056b7c | Function | Global | User Defined | 2 | 0
`strNext` | 80056c28 | Function | Global | User Defined | 2 | 0
`strSync` | 80056e18 | Function | Global | User Defined | 1 | 0
`strKickCD` | 80056eac | Function | Global | User Defined | 1 | 0
`movie_main` | 80056f18 | Function | Global | User Defined | 2 | 0
`song_base_set` | 80057420 | Function | Global | User Defined | 3 | 0
`song_set` | 800574c4 | Function | Global | User Defined | 1 | 0
`set_dec_bri` | 800576f8 | Function | Global | User Defined | 26 | 0
`get_last_gamen_mode` | 80057704 | Function | Global | User Defined | 8 | 0
`dec_bg_reset` | 80057714 | Function | Global | User Defined | 27 | 0
`dec_bg_show_switch` | 80057760 | Function | Global | User Defined | 6 | 0
`dec_bg_show_set` | 80057780 | Function | Global | User Defined | 33 | 0
`dec_bg_cd_read` | 80057794 | Function | Global | User Defined | 44 | 0
`dec_bg_init` | 80057884 | Function | Global | User Defined | 25 | 0
`vram_full_move` | 800579a8 | Function | Global | User Defined | 4 | 0
`goto_step_bg_out` | 80057a78 | Function | Global | User Defined | 2 | 0
`dec_bg_show` | 80057c5c | Function | Global | User Defined | 46 | 0
`set_tbg_bri` | 80058098 | Function | Global | User Defined | 4 | 0
`bg_show_girl_out` | 800580a4 | Function | Global | User Defined | 2 | 0
`bg_change` | 80058714 | Function | Global | User Defined | 6 | 0
`initView` | 800590a0 | Function | Global | User Defined | 0 | 0
`initLight` | 80059120 | Function | Global | User Defined | 0 | 0
`initCoordinate` | 80059230 | Function | Global | User Defined | 0 | 0
`initModelingData_init` | 8005928c | Function | Global | User Defined | 0 | 0
`initModelingData` | 8005931c | Function | Global | User Defined | 0 | 0
`class_clear_3d?` | 80059a08 | Function | Global | User Defined | 0 | 0
`MouseState` | 80059a90 | Function | Global | User Defined | 0 | 0
`InitMouse` | 80059b20 | Function | Global | User Defined | 1 | 0
`RangeMouse` | 80059b30 | Function | Global | User Defined | 1 | 0
`SenseMouse` | 80059b88 | Function | Global | User Defined | 1 | 0
`SetMouse` | 80059b9c | Function | Global | User Defined | 1 | 0
`MouseRead` | 80059be0 | Function | Global | User Defined | 0 | 0
`game_mode_init0_wait?` | 8005a638 | Function | Global | User Defined | 1 | 0
`FUN_8005c1a0?` | 8005c1a0 | Function | Global | User Defined | 0 | 0
`set_mouse_handedness` | 8005edb4 | Function | Global | User Defined | 1 | 0
`uwasa_set` | 80060b90 | Function | Global | User Defined | 1 | 0
`uwasa?` | 80060cbc | Function | Global | User Defined | 1 | 0
`uwasa_init` | 80060d5c | Function | Global | User Defined | 1 | 0
`uwasa_main0` | 80060db0 | Function | Global | User Defined | 1 | 0
`uwasa_exit0` | 80060e00 | Function | Global | User Defined | 1 | 0
`uwasa0` | 80060e20 | Function | Global | User Defined | 1 | 0
`uwasa_main` | 80060e74 | Function | Global | User Defined | 1 | 0
`get_nenga_girl` | 800610d8 | Function | Global | User Defined | 1 | 0
`pre_syogatu_init0` | 8006127c | Function | Global | User Defined | 1 | 0
`pre_syogatu_init1` | 80061348 | Function | Global | User Defined | 1 | 0
`pre_syogatu_init2` | 800613d0 | Function | Global | User Defined | 1 | 0
`pre_syogatu_init3` | 80061420 | Function | Global | User Defined | 1 | 0
`pre_syogatu_init` | 80061480 | Function | Global | User Defined | 1 | 0
`pre_syogatu0` | 80061518 | Function | Global | User Defined | 1 | 0
`pre_syogatu1` | 800616c8 | Function | Global | User Defined | 1 | 0
`pre_syogatu` | 80061864 | Function | Global | User Defined | 1 | 0
`pre_syogatu_main` | 800618b8 | Function | Global | User Defined | 1 | 0
`title_init_View` | 80061940 | Function | Global | User Defined | 1 | 0
`title_init_Light` | 800619c0 | Function | Global | User Defined | 1 | 0
`title_init_Coordinate` | 80061ae0 | Function | Global | User Defined | 1 | 0
`title_init_ModelingData` | 80061b3c | Function | Global | User Defined | 1 | 0
`title_data_read` | 80061c64 | Function | Global | User Defined | 1 | 0
`title_white_out` | 80062110 | Function | Global | User Defined | 1 | 0
`title_white_in` | 800621d8 | Function | Global | User Defined | 1 | 0
`title_white_in` | 80062330 | Function | Global | User Defined | 1 | 0
`title_move` | 800623a0 | Function | Global | User Defined | 1 | 0
`title_show_init` | 80062424 | Function | Global | User Defined | 1 | 0
`cursor_select` | 800625f8 | Function | Global | User Defined | 2 | 0
`title_show` | 80062738 | Function | Global | User Defined | 1 | 0
`cursor_elem` | 800627d4 | Function | Global | User Defined | 1 | 0
`title_elem` | 80062808 | Function | Global | User Defined | 1 | 0
`title_set` | 80062848 | Function | Global | User Defined | 1 | 0
`title_goto_else_stop` | 800628c4 | Function | Global | User Defined | 1 | 0
`title_fade_out` | 80062930 | Function | Global | User Defined | 1 | 0
`title_out` | 800629a8 | Function | Global | User Defined | 1 | 0
`title` | 80062a0c | Function | Global | User Defined | 1 | 0
`title_object_rotate` | 80062aec | Function | Global | User Defined | 1 | 0
`konami_intro` | 80062dcc | Function | Global | User Defined | 1 | 0
`bust_up_read?` | 80062e70 | Function | Global | User Defined | 88 | 0
`???_80062eac` | 80062eac | Function | Global | User Defined | 0 | 0
`bust_up_init` | 80062f5c | Function | Global | User Defined | 3 | 0
`bust_up_face_c?` | 800636c0 | Function | Global | User Defined | 1 | 0
`bust_up_show` | 80063808 | Function | Global | User Defined | 1 | 0
`bustup_speech` | 80063a30 | Function | Global | User Defined | 1 | 0
`bustup_wink` | 80063a64 | Function | Global | User Defined | 1 | 0
`parameter_change` | 80063a88 | Function | Global | User Defined | 8 | 0
`parameter_disp_switch` | 80063ad0 | Function | Global | User Defined | 9 | 0
`parameter_show_init` | 80063b78 | Function | Global | User Defined | 16 | 0
`parameter_show` | 8006486c | Function | Global | User Defined | 20 | 0
`hizuke_disp_switch` | 80064acc | Function | Global | User Defined | 10 | 0
`hizuke_init` | 80064b74 | Function | Global | User Defined | 11 | 0
`hizuke_show` | 80064f8c | Function | Global | User Defined | 25 | 0
`message_disp_switch` | 80064fe8 | Function | Global | User Defined | 2 | 0
`message_window_init` | 80065024 | Function | Global | User Defined | 10 | 0
`message_window_show` | 800650e8 | Function | Global | User Defined | 22 | 0
`icon_disp_switch` | 80065144 | Function | Global | User Defined | 17 | 0
`icon_can_use_set` | 800651e8 | Function | Global | User Defined | 36 | 0
`get_icon_can_use` | 80065214 | Function | Global | User Defined | 9 | 0
`icon_init` | 8006523c | Function | Global | User Defined | 20 | 0
`icon_menu_set` | 80065670 | Function | Global | User Defined | 14 | 0
`icon_mem_card_switch` | 80065aa0 | Function | Global | User Defined | 1 | 0
`icon_atari_check` | 80065acc | Function | Global | User Defined | 1 | 0
`icon_show` | 80065c74 | Function | Global | User Defined | 14 | 0
`basyo_disp_switch` | 80066064 | Function | Global | User Defined | 18 | 0
`basyo_init2` | 80066234 | Function | Global | User Defined | 14 | 0
`basyo_init` | 8006625c | Function | Global | User Defined | 20 | 0
`basyo_show` | 80066464 | Function | Global | User Defined | 17 | 0
`get_season` | 80066b5c | Function | Global | User Defined | 12 | 0
`get_nf` | 80066bb4 | Function | Global | User Defined | 5 | 0
`get_vacation` | 80066c70 | Function | Global | User Defined | 0 | 0
`back_scroll_move` | 80066d38 | Function | Global | User Defined | 16 | 0
`back_scroll_init` | 800674e8 | Function | Global | User Defined | 1 | 0
`normal_music_read_init0` | 80067568 | Function | Global | User Defined | 1 | 0
`normal_music_read_again` | 800675e0 | Function | Global | User Defined | 5 | 0
`normal_music_read_init1` | 80067740 | Function | Global | User Defined | 0 | 0
`mascot_disp_switch` | 8006777c | Function | Global | User Defined | 6 | 0
`mascot_init?` | 800677dc | Function | Global | User Defined | 7 | 0
`mascot_init` | 80067b94 | Function | Global | User Defined | 0 | 0
`event_bust_up_show` | 80067d58 | Function | Global | User Defined | 1 | 0
`event_bustup_wink` | 80067f04 | Function | Global | User Defined | 1 | 0
`event_bustup_kuchi_ani` | 80067f2c | Function | Global | User Defined | 2 | 0
`cal_class_init` | 80067f60 | Function | Global | User Defined | 1 | 0
`schedule_mark_on` | 80068030 | Function | Global | User Defined | 1 | 0
`get_calx_pos` | 8006895c | Function | Global | User Defined | 15 | 0
`get_caly_pos` | 800689b4 | Function | Global | User Defined | 15 | 0
`cal_font_load` | 800689fc | Function | Global | User Defined | 2 | 0
`biorhythm_curve` | 80068ca8 | Function | Global | User Defined | 1 | 0
`cal_show` | 80068f6c | Function | Global | User Defined | 1 | 0
`cal_base_show` | 800691d4 | Function | Global | User Defined | 7 | 0
`appraisal_base_show` | 80069224 | Function | Global | User Defined | 0 | 0
`magazine_base_show` | 80069274 | Function | Global | User Defined | 1 | 0
`cal_sprite_disp_switch` | 800692c4 | Function | Global | User Defined | 0 | 0
`cal_sprite_init` | 80069384 | Function | Global | User Defined | 1 | 0
`save_data_load_class_init` | 800696c0 | Function | Global | User Defined | 2 | 0
`memory_card_data_set` | 80069788 | Function | Global | User Defined | 7 | 0
`joho_check` | 8006a0f0 | Function | Global | User Defined | 1 | 0
`magazine_class_init` | 8006a378 | Function | Global | User Defined | 1 | 0
`reserved_date` | 8006af70 | Function | Global | User Defined | 5 | 0
`check_date_info` | 8006b0c0 | Function | Global | User Defined | 2 | 0
`sort_date_info` | 8006b174 | Function | Global | User Defined | 3 | 0
`set_date_info` | 8006b668 | Function | Global | User Defined | 0 | 0
`cursor_move` | 8006bae0 | Function | Global | User Defined | 25 | 0
`cursor_init` | 8006bcc8 | Function | Global | User Defined | 13 | 0
`cursor_disp_switch` | 8006be0c | Function | Global | User Defined | 16 | 0
`biorhythm_sf_set` | 8006be48 | Function | Global | User Defined | 7 | 0
`biorhythm_sf` | 8006c3a8 | Function | Global | User Defined | 0 | 0
`biorhythm_sf2` | 8006c3d4 | Function | Global | User Defined | 25 | 0
`get_pass_days` | 8006c7a0 | Function | Global | User Defined | 1 | 0
`konami_mark_set` | 8006c808 | Function | Global | User Defined | 5 | 0
`yazirushi_disp_switch` | 8006c8f0 | Function | Global | User Defined | 8 | 0
`put_yes_string` | 8006cb40 | Function | Global | User Defined | 15 | 0
`put_no_string` | 8006cb84 | Function | Global | User Defined | 13 | 0
`schedule_init` | 8006cbd0 | Function | Global | User Defined | 1 | 0
`_schedule_init` | 8006cc0c | Function | Global | User Defined | 1 | 0
`last_date_spot_timer_dec` | 8006ccc8 | Function | Global | User Defined | 1 | 0
`restore_bgm` | 8006cd84 | Function | Global | User Defined | 4 | 0
`schedule_icon_disp?` | 8006cdb4 | Function | Global | User Defined | 1 | 0
`normal_icon_set?` | 8006cf20 | Function | Global | User Defined | 3 | 0
`schedule_buf_clear` | 8006cfd4 | Function | Global | User Defined | 1 | 0
`season_mess_clear` | 8006d01c | Function | Global | User Defined | 8 | 0
`season_flag_set` | 8006d0a8 | Function | Global | User Defined | 2 | 0
`season_last_date_spot_clear` | 8006d0d4 | Function | Global | User Defined | 1 | 0
`basyo_flag_set` | 8006d1d4 | Function | Global | User Defined | 2 | 0
`bukatu_reset` | 8006d544 | Function | Global | User Defined | 2 | 0
`tate_last_date_check` | 8006d784 | Function | Global | User Defined | 0 | 0
`schedule_weekday?` | 8006d890 | Function | Global | User Defined | 1 | 0
`sched?_80070b94` | 80070b94 | Function | Global | User Defined | 1 | 0
`sched?_80070f50` | 80070f50 | Function | Global | User Defined | 1 | 0
`sched?_80070f8c` | 80070f8c | Function | Global | User Defined | 1 | 0
`himo_robo_check?` | 80071340 | Function | Global | User Defined | 1 | 0
`schedule_analyze` | 800713ec | Function | Global | User Defined | 1 | 0
`change_joho_look_f` | 80072384 | Function | Global | User Defined | 4 | 0
`cal_inc` | 800723f8 | Function | Global | User Defined | 3 | 0
`etc_flag_clear` | 8007265c | Function | Global | User Defined | 3 | 0
`kyuuka` | 80072670 | Function | Global | User Defined | 1 | 0
`_goto_vacation` | 800727b0 | Function | Global | User Defined | 1 | 0
`change_month` | 80072964 | Function | Global | User Defined | 1 | 0
`_change_month` | 80072a04 | Function | Global | User Defined | 1 | 0
`change_month_font_load` | 80072a58 | Function | Global | User Defined | 1 | 0
`change_month_bgm_read` | 80072be0 | Function | Global | User Defined | 1 | 0
`return_schedule` | 80072c1c | Function | Global | User Defined | 7 | 0
`kega_check` | 80072c80 | Function | Global | User Defined | 1 | 0
`_kega_check` | 80072d28 | Function | Global | User Defined | 1 | 0
`kega_check?` | 80072d60 | Function | Global | User Defined | 1 | 0
`kega_check1` | 80072e30 | Function | Global | User Defined | 1 | 0
`kega_hassei` | 80073244 | Function | Global | User Defined | 1 | 0
`noirize_hassei` | 800733a0 | Function | Global | User Defined | 1 | 0
`sick_hassei` | 80073480 | Function | Global | User Defined | 1 | 0
`kega_kaifuku` | 8007356c | Function | Global | User Defined | 1 | 0
`noiroze_kaifuku` | 80073660 | Function | Global | User Defined | 1 | 0
`sick_kaifuku` | 80073754 | Function | Global | User Defined | 1 | 0
`kega_exit` | 80073848 | Function | Global | User Defined | 1 | 0
`week_day` | 800738b4 | Function | Global | User Defined | 1 | 0
`week_day_exit` | 80073994 | Function | Global | User Defined | 1 | 0
`week_day_init` | 800739d4 | Function | Global | User Defined | 1 | 0
`week_day_main` | 80073a54 | Function | Global | User Defined | 1 | 0
`get_weekly_bg_sector` | 80073a94 | Function | Global | User Defined | 1 | 0
`get_weekly_bg_sector?` | 80073af4 | Function | Global | User Defined | 2 | 0
`week_day_init0` | 80073b8c | Function | Global | User Defined | 1 | 0
`set_sd` | 80073d64 | Function | Global | User Defined | 1 | 0
`week_day_init1` | 8007426c | Function | Global | User Defined | 1 | 0
`week_day_init2` | 80074430 | Function | Global | User Defined | 1 | 0
`week_day_main0` | 8007470c | Function | Global | User Defined | 1 | 0
`week_day_exit0` | 8007484c | Function | Global | User Defined | 1 | 0
`parameter_up_down` | 80074890 | Function | Global | User Defined | 2 | 0
`vacation_day_init` | 80074d5c | Function | Global | User Defined | 1 | 0
`vacation_day?` | 80074ddc | Function | Global | User Defined | 1 | 0
`vacation_day_init0` | 80074e94 | Function | Global | User Defined | 1 | 0
`vacation_day_init1` | 80074fd8 | Function | Global | User Defined | 1 | 0
`vacation_day_init2` | 80075110 | Function | Global | User Defined | 1 | 0
`holiday` | 800753e0 | Function | Global | User Defined | 1 | 0
`holiday_init` | 80075528 | Function | Global | User Defined | 1 | 0
`fujisaki_2nin_birth_check` | 80075580 | Function | Global | User Defined | 1 | 0
`holiday_init_0` | 80075674 | Function | Global | User Defined | 1 | 0
`holiday_init_1` | 80075b18 | Function | Global | User Defined | 1 | 0
`sunday_icon_phase` | 80075bac | Function | Global | User Defined | 1 | 0
`holiday_main` | 80075c9c | Function | Global | User Defined | 1 | 0
`holiday_main0` | 80075cd8 | Function | Global | User Defined | 1 | 0
`phone_check` | 80075d38 | Function | Global | User Defined | 1 | 0
`get_holiday_bg_sector` | 80076054 | Function | Global | User Defined | 3 | 0
`icon_check_h` | 800760b4 | Function | Global | User Defined | 1 | 0
`get_date_basyo_num` | 8007653c | Function | Global | User Defined | 2 | 0
`pre_date_init` | 800766c0 | Function | Global | User Defined | 1 | 0
`date_x_taku_set` | 80076830 | Function | Global | User Defined | 1 | 0
`get_date_basyo_num` | 80076bd4 | Function | Global | User Defined | 1 | 0
`pre_date_select` | 80076d08 | Function | Global | User Defined | 1 | 0
`pre_date_exit` | 80076e2c | Function | Global | User Defined | 1 | 0
`pre_date` | 80076f4c | Function | Global | User Defined | 1 | 0
`holiday_normal` | 80076fd4 | Function | Global | User Defined | 1 | 0
`holiday_normal_init0` | 80077428 | Function | Global | User Defined | 1 | 0
`holiday_normal_init1?` | 80077720 | Function | Global | User Defined | 1 | 0
`holiday_normal_main` | 8007798c | Function | Global | User Defined | 1 | 0
`holiday_magazine` | 80077c6c | Function | Global | User Defined | 1 | 0
`magazine_init` | 80077cdc | Function | Global | User Defined | 1 | 0
`magazine_debug?` | 80077d34 | Function | Global | User Defined | 1 | 0
`magazine_main` | 80077ebc | Function | Global | User Defined | 1 | 0
`magazine_exit` | 80077fb8 | Function | Global | User Defined | 1 | 0
`holiday_tel` | 80077fe8 | Function | Global | User Defined | 1 | 0
`holiday_tell_init` | 8007806c | Function | Global | User Defined | 1 | 0
`holiday_tel_call` | 800780e4 | Function | Global | User Defined | 1 | 0
`holiday_tel_exit` | 800781d4 | Function | Global | User Defined | 1 | 0
`telephone_class_init` | 8007837c | Function | Global | User Defined | 2 | 0
`holiday_club_init` | 80078690 | Function | Global | User Defined | 1 | 0
`holiday_club_select` | 800786f8 | Function | Global | User Defined | 1 | 0
`holiday_club_exit` | 80078848 | Function | Global | User Defined | 1 | 0
`holiday_taibu_club_exit` | 800788ec | Function | Global | User Defined | 1 | 0
`holiday_club` | 8007892c | Function | Global | User Defined | 1 | 0
`holiday_club_join_exit` | 800789b0 | Function | Global | User Defined | 1 | 0
`holiday_club_join` | 800789e0 | Function | Global | User Defined | 1 | 0
`load_exe_bin` | 80078a9c | Function | Global | User Defined | 1 | 0
`etc_disp?` | 80078b24 | Function | Global | User Defined | 1 | 0
`load_func_main` | 80078cd8 | Function | Global | User Defined | 1 | 0
`load_func_ok` | 8007906c | Function | Global | User Defined | 1 | 0
`load_fucn_check_sum` | 800790a0 | Function | Global | User Defined | 1 | 0
`load_func_go` | 800790fc | Function | Global | User Defined | 1 | 0
`twinbee?` | 8007988c | Function | Global | User Defined | 1 | 0
`SD_Call_SD` | 80079ba0 | Function | Global | User Defined | 1 | 0
`SD_Task?` | 80079bc4 | Function | Global | User Defined | 1 | 0
`SD?_8007b67c` | 8007b67c | Function | Global | User Defined | 1 | 0
`SD_ChnChange?` | 8007bd8c | Function | Global | User Defined | 2 | 0
`SD_Reset` | 8007be78 | Function | Global | User Defined | 3 | 0
`SD_GetVAB` | 8007bf24 | Function | Global | User Defined | 8 | 0
`SD_DisposeVAB` | 8007bf94 | Function | Global | User Defined | 8 | 0
`SD_InitCDLevelInfo` | 8007c088 | Function | Global | User Defined | 1 | 0
`SD_GetCDLevel` | 8007c0c0 | Function | Global | User Defined | 1 | 0
`SD_DetectCDPeak` | 8007c3a0 | Function | Global | User Defined | 1 | 0
`SD_CalcCDAve` | 8007c4a4 | Function | Global | User Defined | 1 | 0
`getCDlevel` | 8007c5ac | Function | Global | User Defined | 11 | 0
`addr_init_weekly_sd` | 8007c5f0 | Function | Global | User Defined | 1 | 0
`addr_init_holiday_sd` | 8007c65c | Function | Global | User Defined | 2 | 0
`addr_init_club_sd` | 8007c6c8 | Function | Global | User Defined | 3 | 0
`addr_init_else_sd` | 8007c738 | Function | Global | User Defined | 3 | 0
`addr_init_bustup` | 8007c7d0 | Function | Global | User Defined | 0 | 0
`cdread_callback` | 8007c814 | Function | Global | User Defined | 0 | 0
`normal_date_bg_suddenin` | 8007c8d4 | Function | Global | User Defined | 0 | 0
`normal_date_bg_suddenout` | 8007c908 | Function | Global | User Defined | 0 | 0
`normal_date_bg_in` | 8007c934 | Function | Global | User Defined | 0 | 0
`normal_date_bg_in_sub` | 8007c968 | Function | Global | User Defined | 1 | 0
`set_tarao_bg` | 8007d414 | Function | Global | User Defined | 4 | 0
`set_tarao_sprt` | 8007d7c4 | Function | Global | User Defined | 4 | 0
`set_tarao_rect` | 8007d8cc | Function | Global | User Defined | 0 | 0
`normal_date_bg_out` | 8007d9bc | Function | Global | User Defined | 0 | 0
`normal_date_bg_out_sub` | 8007d9f0 | Function | Global | User Defined | 1 | 0
`normal_date_girl_in` | 8007e4d4 | Function | Global | User Defined | 0 | 0
`normal_date_girl_in_init` | 8007e53c | Function | Global | User Defined | 1 | 0
`normal_date_girl_in_main` | 8007e5ac | Function | Global | User Defined | 1 | 0
`normal_date_girl_suddenin` | 8007e674 | Function | Global | User Defined | 0 | 0
`normal_date_girl_out` | 8007e6e4 | Function | Global | User Defined | 0 | 0
`normal_date_girl_out_init` | 8007e74c | Function | Global | User Defined | 1 | 0
`normal_date_girl_out_main` | 8007e778 | Function | Global | User Defined | 1 | 0
`normal_date_girl_suddenout` | 8007e8a0 | Function | Global | User Defined | 0 | 0
`normal_date_bg_fadein` | 8007e960 | Function | Global | User Defined | 2 | 0
`normal_date_bggirl_fadein` | 8007e9c8 | Function | Global | User Defined | 0 | 0
`normal_date_bg_fadeout` | 8007ea78 | Function | Global | User Defined | 2 | 0
`normal_date_bggirl_fadeout` | 8007eae0 | Function | Global | User Defined | 0 | 0
`normal_date_move_place` | 8007ebf0 | Function | Global | User Defined | 0 | 0
`normal_date_move_place_init` | 8007ec50 | Function | Global | User Defined | 1 | 0
`normal_date_move_place_main` | 8007eca0 | Function | Global | User Defined | 1 | 0
`place_init` | 8007edac | Function | Global | User Defined | 0 | 0
`place_init2` | 8007ede0 | Function | Global | User Defined | 0 | 0
`change_dec_bg` | 8007ee14 | Function | Global | User Defined | 0 | 0
`dec_init` | 8007ee3c | Function | Global | User Defined | 0 | 0
`bg_read_sub2` | 8007eec8 | Function | Global | User Defined | 0 | 0
`check_k_scroll` | 8007ef3c | Function | Global | User Defined | 1 | 0
`wait_sub_sub` | 8007f048 | Function | Global | User Defined | 0 | 0
`set_window_message` | 8007f08c | Function | Global | User Defined | 1 | 0
`seek_stop_xa` | 80081330 | Function | Global | User Defined | 9 | 0
`set_kanji_win_string` | 80081398 | Function | Global | User Defined | 33 | 0
`speak_sub` | 8008296c | Function | Global | User Defined | 3 | 0
`make_three_select` | 80082f60 | Function | Global | User Defined | 1 | 0
`junban_init` | 800830bc | Function | Global | User Defined | 1 | 0
`normal_date_three_select` | 80083178 | Function | Global | User Defined | 0 | 0
`normal_date_three_select_init` | 800831d8 | Function | Global | User Defined | 1 | 0
`normal_date_three_select_main` | 80083280 | Function | Global | User Defined | 1 | 0
`normal_date_two_select` | 8008337c | Function | Global | User Defined | 0 | 0
`normal_date_two_select_init` | 800833dc | Function | Global | User Defined | 1 | 0
`normal_date_two_select_main` | 80083470 | Function | Global | User Defined | 1 | 0
`normal_date_face_change_continue` | 80083540 | Function | Global | User Defined | 0 | 0
`hidden_face_change0` | 80083580 | Function | Global | User Defined | 0 | 0
`hidden_face_change1` | 800835a8 | Function | Global | User Defined | 0 | 0
`hidden_face_change2` | 800835d0 | Function | Global | User Defined | 0 | 0
`hidden_face_change3` | 800835f8 | Function | Global | User Defined | 0 | 0
`hidden_face_change4` | 80083620 | Function | Global | User Defined | 0 | 0
`face_change` | 80083648 | Function | Global | User Defined | 6 | 0
`bustup_8008367c` | 8008367c | Function | Global | User Defined | 0 | 0
`bustup_80083830` | 80083830 | Function | Global | User Defined | 0 | 0
`bustup_800838a8` | 800838a8 | Function | Global | User Defined | 0 | 0
`bust_up_show2` | 80083a10 | Function | Global | User Defined | 0 | 0
`dec_bg_show2` | 80083c18 | Function | Global | User Defined | 1 | 0
`hizuke_hide` | 80083cdc | Function | Global | User Defined | 0 | 0
`hizuke_appear` | 80083d04 | Function | Global | User Defined | 0 | 0
`read_bustup` | 80083d2c | Function | Global | User Defined | 1 | 0
`read_bustup_uniform` | 80084358 | Function | Global | User Defined | 0 | 0
`read_bustup_swimsuit` | 8008472c | Function | Global | User Defined | 0 | 0
`bustup_return` | 80084860 | Function | Global | User Defined | 0 | 0
`return_step` | 80084880 | Function | Global | User Defined | 0 | 0
`k_disp_inc2` | 800848c8 | Function | Global | User Defined | 1 | 0
`yoshi_trans` | 80084940 | Function | Global | User Defined | 0 | 0
`change_yoshio` | 8008496c | Function | Global | User Defined | 0 | 0
`change_girl` | 80084994 | Function | Global | User Defined | 0 | 0
`pg_name_init` | 800849c0 | Function | Global | User Defined | 0 | 0
`select_girl` | 80084a54 | Function | Global | User Defined | 0 | 0
`select_girl2` | 80084ab4 | Function | Global | User Defined | 0 | 0
`select_girl_init` | 80084b14 | Function | Global | User Defined | 2 | 0
`select_girl_main` | 80084da4 | Function | Global | User Defined | 2 | 0
`sprite_brightness` | 80084ea0 | Function | Global | User Defined | 2 | 0
`day_plus` | 80084ed0 | Function | Global | User Defined | 0 | 0
`check_para_limit` | 80084f44 | Function | Global | User Defined | 0 | 0
`bustup_mouse_on` | 80085074 | Function | Global | User Defined | 0 | 0
`load_ful` | 80085098 | Function | Global | User Defined | 0 | 0
`load_opd` | 800852dc | Function | Global | User Defined | 0 | 0
`event_char_onoff` | 8008543c | Function | Global | User Defined | 2 | 0
`ev_fadein` | 80085570 | Function | Global | User Defined | 0 | 0
`ev_fadeout` | 8008560c | Function | Global | User Defined | 0 | 0
`event_face0` | 800856b0 | Function | Global | User Defined | 0 | 0
`event_face1` | 800856e0 | Function | Global | User Defined | 0 | 0
`event_face2` | 80085714 | Function | Global | User Defined | 0 | 0
`event_face3` | 80085748 | Function | Global | User Defined | 0 | 0
`event_face_kuchi0` | 8008577c | Function | Global | User Defined | 0 | 0
`event_face_kuchi1` | 800857a4 | Function | Global | User Defined | 0 | 0
`event_kuchi_ani_no` | 800857cc | Function | Global | User Defined | 0 | 0
`event_kuchi_ani_yes` | 800857fc | Function | Global | User Defined | 0 | 0
`ev_me_on` | 8008582c | Function | Global | User Defined | 0 | 0
`ev_me_on_continue` | 8008585c | Function | Global | User Defined | 0 | 0
`_sprite_set_box_shade_tarao` | 80085890 | Function | Global | User Defined | 0 | 0
`clear_work_tarao` | 80085a74 | Function | Global | User Defined | 0 | 0
`don_init2` | 80085b00 | Function | Global | User Defined | 0 | 0
`don_wait` | 80085b28 | Function | Global | User Defined | 0 | 0
`normal_date_speak_1line` | 80085b70 | Function | Global | User Defined | 0 | 0
`normal_date_speak_012` | 80085c00 | Function | Global | User Defined | 0 | 0
`normal_date_speak` | 80085c78 | Function | Global | User Defined | 0 | 0
`vram_bustup_clear` | 80085cf4 | Function | Global | User Defined | 0 | 0
`date_alubum_para_set` | 80085d54 | Function | Global | User Defined | 0 | 0
`bust_up_face` | 80085eec | Function | Global | User Defined | 1 | 0
`Graph_Init` | 80086050 | Function | Global | User Defined | 0 | 0
`VBlnk_Timer_init` | 800860f0 | Function | Global | User Defined | 4 | 0
`Vblnk_Timer` | 8008610c | Function | Global | User Defined | 2 | 0
`Scroll` | 8008612c | Function | Global | User Defined | 0 | 0
`Rot_2D` | 80086424 | Function | Global | User Defined | 0 | 0
`Fade_Out_Init` | 800864f0 | Function | Global | User Defined | 0 | 0
`Fade_Out_Main` | 80086510 | Function | Global | User Defined | 0 | 0
`Fade_In_Init` | 80086570 | Function | Global | User Defined | 0 | 0
`Fade_In_Main` | 80086590 | Function | Global | User Defined | 0 | 0
`Yubi` | 800865f4 | Function | Global | User Defined | 0 | 0
`Default_Disp` | 80086644 | Function | Global | User Defined | 0 | 0
`Shiori_Case_Of_Mine` | 8008669c | Function | Global | User Defined | 0 | 0
`Ev_Class_W_Switch` | 800867c8 | Function | Global | User Defined | 0 | 0
`Get_Serifu` | 80086804 | Function | Global | User Defined | 2 | 0
`bust_up_read_myu` | 80086828 | Function | Global | User Defined | 0 | 0
`ivlc_dct_dc_size` | 800875c0 | Function | Global | User Defined | 2 | 0
`CDInit` | 800877b0 | Function | Global | User Defined | 1 | 0
`CD_80087828` | 80087828 | Function | Global | User Defined | 1 | 0
`CD_80087850` | 80087850 | Function | Global | User Defined | 1 | 0
`CD_80087878` | 80087878 | Function | Global | User Defined | 1 | 0
`CD_80087914` | 80087914 | Function | Global | User Defined | 0 | 0
`CD_8008797c` | 8008797c | Function | Global | User Defined | 1 | 0
`CD_80087990` | 80087990 | Function | Global | User Defined | 5 | 0
`CD_800879a4` | 800879a4 | Function | Global | User Defined | 1 | 0
`CdSearchFile` | 80088f90 | Function | Global | User Defined | 2 | 0
`strcmp12` | 80089264 | Function | Global | User Defined | 1 | 0
`CD_newmedia_80089284` | 80089284 | Function | Global | User Defined | 1 | 0
`CD_cachefile` | 800895f0 | Function | Global | User Defined | 1 | 0
`cdrom_800899c8` | 800899c8 | Function | Global | User Defined | 1 | 0
`CD_8008a5c4` | 8008a5c4 | Function | Global | User Defined | 7 | 0
`seq_8008fbd0` | 8008fbd0 | Function | Global | User Defined | 1 | 0
`read_seq` | 80091160 | Function | Global | User Defined | 1 | 0
`SetGraphDebug` | 8009fcb4 | Function | Global | User Defined | 0 | 0
`FGO_01_OBJ_64` | 800a4774 | Function | Global | User Defined | 1 | 0
`FGO_01_OBJ_CC` | 800a47dc | Function | Global | User Defined | 1 | 0
`FGO_01_OBJ_160` | 800a4870 | Function | Global | User Defined | 1 | 0
`ReadGeomOffset` | 800a5154 | Function | Global | User Defined | 0 | 0
`RotNclip4` | 800a545c | Function | Global | User Defined | 0 | 0
`RotAverageNclip3_1` | 800a5594 | Function | Global | User Defined | 0 | 0
`ColorMatDpq` | 800a59c0 | Function | Global | User Defined | 0 | 0
`ColorMatCol` | 800a5a00 | Function | Global | User Defined | 0 | 0
`SetMulMatrix` | 800a5e78 | Function | Global | User Defined | 0 | 0
`ReadColorMatrix` | 800a640c | Function | Global | User Defined | 0 | 0
`AverageZ3` | 800b0f90 | Function | Global | User Defined | 0 | 0
`RCpolyF3` | 800b12e0 | Function | Global | User Defined | 0 | 0
`RCpolyF4` | 800b1900 | Function | Global | User Defined | 0 | 0
`RCpolyG3` | 800b1d80 | Function | Global | User Defined | 0 | 0
`RCpolyFT3` | 800b2190 | Function | Global | User Defined | 0 | 0
`RCpolyGT3` | 800b2590 | Function | Global | User Defined | 0 | 0
`RCpolyG4` | 800b2a30 | Function | Global | User Defined | 0 | 0
`RCpolyFT4` | 800b2f80 | Function | Global | User Defined | 0 | 0
`RCpolyGT4` | 800b34a0 | Function | Global | User Defined | 0 | 0
`PadInit` | 800b4164 | Function | Global | User Defined | 2 | 0
`PadRead` | 800b4258 | Function | Global | User Defined | 0 | 0
`PadStop` | 800b4280 | Function | Global | User Defined | 1 | 0
`_card_clear` | 800b47d0 | Function | Global | User Defined | 1 | 0
`sprintf` | 800b48d0 | Function | Global | User Defined | 17 | 0
`SetSp` | 800b56d0 | Function | Global | User Defined | 1 | 0
`GetGp` | 800b56f0 | Function | Global | User Defined | 1 | 0
`EnterCriticalSelection` | 800b5730 | Function | Global | User Defined | 14 | 0
`ExitCriticalSelection` | 800b5750 | Function | Global | User Defined | 13 | 0
`SetRCnt` | 800b5780 | Function | Global | User Defined | 3 | 0
`GetRCnt` | 800b581c | Function | Global | User Defined | 1 | 0
`StartRCnt` | 800b5854 | Function | Global | User Defined | 3 | 0
`StopRCnt` | 800b5888 | Function | Global | User Defined | 4 | 0
`ResetRCnt` | 800b58bc | Function | Global | User Defined | 2 | 0
`GetSp` | 800b58f0 | Function | Global | User Defined | 1 | 0
`s_tokimeki` | 800b5a60 | Data Label | Global | User Defined | 1 | 0
`s_albu` | 800b5a6c | Data Label | Global | User Defined | 1 | 0
`s_m_creating` | 800b5a74 | Data Label | Global | User Defined | 1 | 0
`bra1` | 800b6330 | Data Label | Global | User Defined | 1 | 0
`bra2` | 800b6334 | Data Label | Global | User Defined | 1 | 0
`bra3` | 800b6338 | Data Label | Global | User Defined | 1 | 0
`shiori` | 800b633c | Data Label | Global | User Defined | 1 | 0
`chan` | 800b6344 | Data Label | Global | User Defined | 1 | 0
`san` | 800b634c | Data Label | Global | User Defined | 1 | 0
`tokimeki_memorial` | 800b63cc | Data Label | Global | User Defined | 1 | 0
`system` | 800b63e0 | Data Label | Global | User Defined | 1 | 0
`tokimeki_memorial_2` | 800b63f0 | Data Label | Global | User Defined | 1 | 0
`system_2` | 800b6404 | Data Label | Global | User Defined | 1 | 0
`suuzi0` | 800b6410 | Data Label | Global | User Defined | 1 | 0
`suuzi1` | 800b6414 | Data Label | Global | User Defined | 1 | 0
`suuzi2` | 800b6418 | Data Label | Global | User Defined | 1 | 0
`suuzi3` | 800b641c | Data Label | Global | User Defined | 1 | 0
`suuzi4` | 800b6420 | Data Label | Global | User Defined | 1 | 0
`suuzi5` | 800b6424 | Data Label | Global | User Defined | 1 | 0
`suuzi6` | 800b6428 | Data Label | Global | User Defined | 1 | 0
`suuzi7` | 800b642c | Data Label | Global | User Defined | 1 | 0
`suuzi8` | 800b6430 | Data Label | Global | User Defined | 1 | 0
`suuzi9` | 800b6434 | Data Label | Global | User Defined | 1 | 0
`suuzi10` | 800b6438 | Data Label | Global | User Defined | 1 | 0
`suuzi11` | 800b643c | Data Label | Global | User Defined | 1 | 0
`suuzi12` | 800b6440 | Data Label | Global | User Defined | 1 | 0
`suuzi13` | 800b6444 | Data Label | Global | User Defined | 1 | 0
`suuzi14` | 800b6448 | Data Label | Global | User Defined | 1 | 0
`suuzi15` | 800b644c | Data Label | Global | User Defined | 1 | 0
`s_weekday_command_screen` | 800b65d0 | Data Label | Global | User Defined | 1 | 0
`s_test_tomorrow` | 800b65e4 | Data Label | Global | User Defined | 1 | 0
`s_tomorrow_baseball_nationals` | 800b65f8 | Data Label | Global | User Defined | 1 | 0
`s_summer_camp` | 800b6620 | Data Label | Global | User Defined | 1 | 0
`s_bunkasai_for_club` | 800b6634 | Data Label | Global | User Defined | 1 | 0
`s_bunkasai_but_sick` | 800b6654 | Data Label | Global | User Defined | 1 | 0
`s_tomorrow_field_trip` | 800b668c | Data Label | Global | User Defined | 1 | 0
`s_1week_extra_lessons` | 800b66a4 | Data Label | Global | User Defined | 1 | 0
`s_sick_cant_move` | 800b66cc | Data Label | Global | User Defined | 1 | 0
`s_tomorrow_what_do` | 800b66e4 | Data Label | Global | User Defined | 1 | 0
`s_tomorrow_test` | 800b6700 | Data Label | Global | User Defined | 1 | 0
`s_tomorrow_field_trip_2` | 800b6714 | Data Label | Global | User Defined | 1 | 0
`s_calendar` | 800b672c | Data Label | Global | User Defined | 1 | 0
`s_this_next_month_plans` | 800b6738 | Data Label | Global | User Defined | 1 | 0
`s_date_break` | 800b6750 | Data Label | Global | User Defined | 1 | 0
`s_memory_card_unrecog` | 800b6768 | Data Label | Global | User Defined | 1 | 0
`s_memory_card_full` | 800b6788 | Data Label | Global | User Defined | 1 | 0
`s_memory_card_unrecog` | 800b67ac | Data Label | Global | User Defined | 1 | 0
`s_save` | 800b67bc | Data Label | Global | User Defined | 1 | 0
`s_load` | 800b67c4 | Data Label | Global | User Defined | 1 | 0
`s_choose_save_or_load` | 800b67cc | Data Label | Global | User Defined | 1 | 0
`s_choose_save_or_load2` | 800b67f0 | Data Label | Global | User Defined | 1 | 0
`s_unformatted_memory_card` | 800b6814 | Data Label | Global | User Defined | 1 | 0
`s_format?` | 800b6834 | Data Label | Global | User Defined | 1 | 0
`s_another_memory_card` | 800b684c | Data Label | Global | User Defined | 1 | 0
`s_insert_card` | 800b6864 | Data Label | Global | User Defined | 1 | 0
`s_set` | 800b6874 | Data Label | Global | User Defined | 1 | 0
`s_press_circle` | 800b6890 | Data Label | Global | User Defined | 1 | 0
`s_data_save` | 800b68ac | Data Label | Global | User Defined | 1 | 0
`s_select_save_file` | 800b68bc | Data Label | Global | User Defined | 1 | 0
`s_overwrite?` | 800b68e0 | Data Label | Global | User Defined | 1 | 0
`s_saving...` | 800b68fc | Data Label | Global | User Defined | 1 | 0
`s_until_blinking_ends` | 800b6910 | Data Label | Global | User Defined | 1 | 0
`s_dont_turn_off_power` | 800b692c | Data Label | Global | User Defined | 1 | 0
`s_data_load` | 800b6944 | Data Label | Global | User Defined | 1 | 0
`s_select_load_file` | 800b6954 | Data Label | Global | User Defined | 1 | 0
`s_loading...` | 800b6978 | Data Label | Global | User Defined | 1 | 0
`s_pls_wait` | 800b698c | Data Label | Global | User Defined | 1 | 0
`s_continue_play_this_file` | 800b69a4 | Data Label | Global | User Defined | 1 | 0
`s_system_settings_page` | 800b69c8 | Data Label | Global | User Defined | 1 | 0
`s_text_speed` | 800b69f8 | Data Label | Global | User Defined | 1 | 0
`s_cursor_speed` | 800b6a34 | Data Label | Global | User Defined | 1 | 0
`s_voice_mode` | 800b6a44 | Data Label | Global | User Defined | 1 | 0
`s_Recently_rumours` | 800b72a8 | Data Label | Global | User Defined | 1 | 0
`s_Lets_go_Ijuuins_Party` | 800b72e0 | Data Label | Global | User Defined | 1 | 0
`s_ping_pong` | 800b7328 | Data Label | Global | User Defined | 1 | 0
`s_huh_who` | 800b7338 | Data Label | Global | User Defined | 1 | 0
`s_delivery` | 800b7348 | Data Label | Global | User Defined | 1 | 0
`s_newyears_cards` | 800b7350 | Data Label | Global | User Defined | 1 | 0
`s_yatta` | 800b7360 | Data Label | Global | User Defined | 1 | 0
`s_to` | 800b736c | Data Label | Global | User Defined | 1 | 0
`s_newyears_card_lucky` | 800b7374 | Data Label | Global | User Defined | 1 | 0
`s_number_album` | 800b7750 | Data Label | Global | User Defined | 1 | 0
`s_system` | 800b775c | Data Label | Global | User Defined | 1 | 0
`s_unused` | 800b7768 | Data Label | Global | User Defined | 1 | 0
`s_ijou` | 800b7770 | Data Label | Global | User Defined | 1 | 0
`s_YEAR` | 800b777c | Data Label | Global | User Defined | 1 | 0
`s_MONTH` | 800b7780 | Data Label | Global | User Defined | 1 | 0
`s_DAY` | 800b7784 | Data Label | Global | User Defined | 1 | 0
`s_namae` | 800b7788 | Data Label | Global | User Defined | 1 | 0
`s_nickname` | 800b7790 | Data Label | Global | User Defined | 1 | 0
`s_club_catalog` | 800b7814 | Data Label | Global | User Defined | 1 | 0
`s_withdraw` | 800b7820 | Data Label | Global | User Defined | 1 | 0
`s_select_club_to_join` | 800b782c | Data Label | Global | User Defined | 1 | 0
`s_DUMMY` | 800b7900 | Data Label | Global | User Defined | 1 | 0
`s_neurosis` | 800b79a8 | Data Label | Global | User Defined | 1 | 0
`s_illness` | 800b79d4 | Data Label | Global | User Defined | 1 | 0
`s_1week_extra_lessons` | 800b7d64 | Data Label | Global | User Defined | 1 | 0
`s_today_what_do` | 800b7e38 | Data Label | Global | User Defined | 1 | 0
`s_fujisaki` | 800b8940 | Data Label | Global | User Defined | 1 | 0
`s_fujisaki2` | 800b8948 | Data Label | Global | User Defined | 1 | 0
`s_fujisaki3` | 800b895c | Data Label | Global | User Defined | 1 | 0
`s_yoshio` | 800b8978 | Data Label | Global | User Defined | 1 | 0
`s_stop` | 800b8a2c | Data Label | Global | User Defined | 1 | 0
`sCdlReadS_27` | 800b8e80 | Data Label | Global | User Defined | 1 | 0
`sCdlSeekP_22` | 800b8e8c | Data Label | Global | User Defined | 1 | 0
`sCdlSeekL_21` | 800b8e98 | Data Label | Global | User Defined | 1 | 0
`sCdlGetTD_20` | 800b8ea4 | Data Label | Global | User Defined | 1 | 0
`sCdlGetlocP_17` | 800b8eb0 | Data Label | Global | User Defined | 1 | 0
`sCdlGetlocL_16` | 800b8ebc | Data Label | Global | User Defined | 1 | 0
`sCdl_NONE` | 800b8ec8 | Data Label | Global | User Defined | 13 | 0
`sCdlSetmode_14` | 800b8ecc | Data Label | Global | User Defined | 1 | 0
`sCdlSetFilter_13` | 800b8ed8 | Data Label | Global | User Defined | 1 | 0
`sCdlDemute_12` | 800b8ee8 | Data Label | Global | User Defined | 1 | 0
`sCdlMute_11` | 800b8ef4 | Data Label | Global | User Defined | 1 | 0
`sCdlInit?Pause?_10` | 800b8efc | Data Label | Global | User Defined | 1 | 0
`sCdlPause_09` | 800b8f08 | Data Label | Global | User Defined | 1 | 0
`sCdlStop_08` | 800b8f14 | Data Label | Global | User Defined | 1 | 0
`sCdlStandby_07` | 800b8f1c | Data Label | Global | User Defined | 1 | 0
`sCdlReadN_06` | 800b8f28 | Data Label | Global | User Defined | 1 | 0
`sCdlBackward_05` | 800b8f34 | Data Label | Global | User Defined | 1 | 0
`sCdlForward_04` | 800b8f40 | Data Label | Global | User Defined | 1 | 0
`sCdlPlay_03` | 800b8f4c | Data Label | Global | User Defined | 1 | 0
`sCdlSetloc_02` | 800b8f54 | Data Label | Global | User Defined | 1 | 0
`sCdlNop_01` | 800b8f60 | Data Label | Global | User Defined | 1 | 0
`sCdlSync_00` | 800b8f68 | Data Label | Global | User Defined | 1 | 0
`suuzi0` | 800b9714 | Data Label | Global | User Defined | 1 | 0
`suuzi1` | 800b9718 | Data Label | Global | User Defined | 5 | 0
`suuzi2` | 800b971c | Data Label | Global | User Defined | 2 | 0
`suuzi3` | 800b9720 | Data Label | Global | User Defined | 2 | 0
`suuzi4` | 800b9724 | Data Label | Global | User Defined | 2 | 0
`suuzi5` | 800b9728 | Data Label | Global | User Defined | 2 | 0
`suuzi6` | 800b972c | Data Label | Global | User Defined | 8 | 0
`suuzi7` | 800b9730 | Data Label | Global | User Defined | 2 | 0
`suuzi8` | 800b9734 | Data Label | Global | User Defined | 2 | 0
`suuzi9` | 800b9738 | Data Label | Global | User Defined | 6 | 0
`suuzi10` | 800b973c | Data Label | Global | User Defined | 2 | 0
`suuzi11` | 800b9744 | Data Label | Global | User Defined | 2 | 0
`suuzi12` | 800b974c | Data Label | Global | User Defined | 2 | 0
`suuzi13` | 800b9754 | Data Label | Global | User Defined | 1 | 0
`suuzi14` | 800b975c | Data Label | Global | User Defined | 1 | 0
`suuzi15` | 800b9764 | Data Label | Global | User Defined | 1 | 0
`suuzi16` | 800b976c | Data Label | Global | User Defined | 1 | 0
`suuzi_0org` | 800b9774 | Data Label | Global | User Defined | 31 | 0
`suuzi` | 800b9778 | Data Label | Global | User Defined | 6 | 0
`com_name_tai` | 800b97bc | Data Label | Global | User Defined | 1 | 0
`com_name_bun` | 800b97c4 | Data Label | Global | User Defined | 1 | 0
`com_name_ri` | 800b97cc | Data Label | Global | User Defined | 1 | 0
`com_name_gei` | 800b97d4 | Data Label | Global | User Defined | 1 | 1
`com_name_un` | 800b97dc | Data Label | Global | User Defined | 1 | 0
`com_name_zat` | 800b97e4 | Data Label | Global | User Defined | 1 | 0
`com_name_you` | 800b97ec | Data Label | Global | User Defined | 1 | 0
`com_name_kon` | 800b97f4 | Data Label | Global | User Defined | 1 | 0
`com_name_str` | 800b97fc | Data Label | Global | User Defined | 1 | 0
`com_name` | 800b9808 | Data Label | Global | User Defined | 0 | 0
`date_name_0` | 800b982c | Data Label | Global | User Defined | 1 | 0
`date_name_1` | 800b9838 | Data Label | Global | User Defined | 1 | 0
`date_name_2` | 800b984c | Data Label | Global | User Defined | 1 | 0
`date_name_3` | 800b985c | Data Label | Global | User Defined | 1 | 0
`date_name_4` | 800b9864 | Data Label | Global | User Defined | 1 | 0
`date_name_5` | 800b986c | Data Label | Global | User Defined | 1 | 0
`date_name_6` | 800b9874 | Data Label | Global | User Defined | 1 | 0
`date_name_7` | 800b9884 | Data Label | Global | User Defined | 1 | 0
`date_name_8` | 800b988c | Data Label | Global | User Defined | 1 | 0
`date_name_9` | 800b9894 | Data Label | Global | User Defined | 1 | 0
`date_name_10` | 800b98a4 | Data Label | Global | User Defined | 1 | 0
`date_name_11` | 800b98b4 | Data Label | Global | User Defined | 1 | 0
`date_name_12` | 800b98c0 | Data Label | Global | User Defined | 1 | 0
`date_name_13` | 800b98c8 | Data Label | Global | User Defined | 1 | 0
`date_name_14` | 800b98d4 | Data Label | Global | User Defined | 1 | 0
`date_name_15` | 800b98dc | Data Label | Global | User Defined | 1 | 0
`date_name_16` | 800b98ec | Data Label | Global | User Defined | 1 | 0
`date_name_17` | 800b98f4 | Data Label | Global | User Defined | 1 | 0
`date_name_18` | 800b98f8 | Data Label | Global | User Defined | 1 | 0
`date_name_19` | 800b9900 | Data Label | Global | User Defined | 1 | 0
`date_name_20` | 800b990c | Data Label | Global | User Defined | 1 | 0
`date_name` | 800b9918 | Data Label | Global | User Defined | 6 | 0
`tc_name_0` | 800b996c | Data Label | Global | User Defined | 1 | 0
`tc_name_1` | 800b9978 | Data Label | Global | User Defined | 1 | 0
`tc_name_2` | 800b9984 | Data Label | Global | User Defined | 1 | 0
`tc_name_3` | 800b9990 | Data Label | Global | User Defined | 1 | 0
`tc_name_4` | 800b999c | Data Label | Global | User Defined | 1 | 0
`tc_name_5` | 800b99a8 | Data Label | Global | User Defined | 1 | 0
`tc_name_6` | 800b99b4 | Data Label | Global | User Defined | 1 | 0
`tc_name_7` | 800b99bc | Data Label | Global | User Defined | 1 | 0
`tc_name_8` | 800b99c4 | Data Label | Global | User Defined | 1 | 0
`tc_name_9` | 800b99d0 | Data Label | Global | User Defined | 1 | 0
`tc_name_10` | 800b99dc | Data Label | Global | User Defined | 1 | 0
`tc_name_11` | 800b99e8 | Data Label | Global | User Defined | 1 | 0
`tc_name_12` | 800b99f4 | Data Label | Global | User Defined | 2 | 0
`tc_name_13` | 800b9a00 | Data Label | Global | User Defined | 2 | 0
`tc_name_14` | 800b9a0c | Data Label | Global | User Defined | 1 | 0
`tc_name_15` | 800b9a18 | Data Label | Global | User Defined | 1 | 1
`tc_name` | 800b9a24 | Data Label | Global | User Defined | 0 | 0
`tc_sname_0` | 800b9a64 | Data Label | Global | User Defined | 3 | 0
`tc_sname_1` | 800b9a6c | Data Label | Global | User Defined | 1 | 0
`tc_sname_2` | 800b9a74 | Data Label | Global | User Defined | 1 | 0
`tc_sname_3` | 800b9a7c | Data Label | Global | User Defined | 1 | 0
`tc_sname_4` | 800b9a84 | Data Label | Global | User Defined | 1 | 0
`tc_sname_5` | 800b9a8c | Data Label | Global | User Defined | 1 | 0
`tc_sname_6` | 800b9a94 | Data Label | Global | User Defined | 1 | 0
`tc_sname_7` | 800b9a9c | Data Label | Global | User Defined | 1 | 0
`tc_sname_8` | 800b9aa0 | Data Label | Global | User Defined | 1 | 0
`tc_sname_9` | 800b9aa8 | Data Label | Global | User Defined | 1 | 0
`tc_sname_10` | 800b9ab0 | Data Label | Global | User Defined | 1 | 0
`tc_sname_11` | 800b9ab8 | Data Label | Global | User Defined | 1 | 0
`tc_sname_12` | 800b9ac0 | Data Label | Global | User Defined | 3 | 0
`tc_sname_13` | 800b9ac8 | Data Label | Global | User Defined | 1 | 0
`tc_sname_14` | 800b9ad0 | Data Label | Global | User Defined | 1 | 0
`tc_sname_15` | 800b9ad8 | Data Label | Global | User Defined | 2 | 0
`tc_sname` | 800b9ae0 | Data Label | Global | User Defined | 5 | 0
`kun` | 800b9b20 | Data Label | Global | User Defined | 16 | 0
`san` | 800b9b24 | Data Label | Global | User Defined | 7 | 0
`non` | 800b9b2c | Data Label | Global | User Defined | 0 | 0
`space` | 800b9b30 | Data Label | Global | User Defined | 18 | 1
`xass` | 800b9b34 | Data Label | Global | User Defined | 1 | 0
`girl_vh` | 800b9b74 | Data Label | Global | User Defined | 0 | 0
`girl_vb` | 800b9bb4 | Data Label | Global | User Defined | 0 | 0
`girl_seq` | 800b9bf4 | Data Label | Global | User Defined | 0 | 0
`cal_dat` | 800b9c34 | Data Label | Global | User Defined | 13 | 0
`f_main_07` | 800b9c38 | Data Label | Global | User Defined | 1 | 0
`stadium_data` | 800b9c3c | Data Label | Global | User Defined | 1 | 0
`_stadium_data_1` | 800b9c3d | Data Label | Global | User Defined | 1 | 0
`_stadium_data_2` | 800b9c3e | Data Label | Global | User Defined | 1 | 0
`telephone_kigou` | 800b9c64 | Data Label | Global | User Defined | 2 | 0
`_telephone_kigou_1` | 800b9c65 | Data Label | Global | User Defined | 1 | 0
`_telephone_kigou_2` | 800b9c6b | Data Label | Global | User Defined | 1 | 0
`_telephone_kigou_3` | 800b9ca6 | Data Label | Global | User Defined | 1 | 0
`aisatu_sector` | 800b9cc0 | Data Label | Global | User Defined | 1 | 0
`aisatu_sector_plus_1` | 800b9cc4 | Data Label | Global | User Defined | 1 | 0
`aisatu_sector2` | 800b9d28 | Data Label | Global | User Defined | 0 | 0
`bukatu_name0` | 800b9d90 | Data Label | Global | User Defined | 2 | 0
`bukatu_name1` | 800b9d98 | Data Label | Global | User Defined | 1 | 0
`bukatu_name2` | 800b9da0 | Data Label | Global | User Defined | 1 | 0
`bukatu_name3` | 800b9da8 | Data Label | Global | User Defined | 1 | 0
`bukatu_name4` | 800b9db0 | Data Label | Global | User Defined | 1 | 0
`bukatu_name5` | 800b9db8 | Data Label | Global | User Defined | 1 | 0
`bukatu_name6` | 800b9dc0 | Data Label | Global | User Defined | 1 | 0
`bukatu_name7` | 800b9dc8 | Data Label | Global | User Defined | 1 | 0
`bukatu_name8` | 800b9dd4 | Data Label | Global | User Defined | 1 | 0
`bukatu_name9` | 800b9ddc | Data Label | Global | User Defined | 1 | 0
`bukatu_name10` | 800b9de4 | Data Label | Global | User Defined | 1 | 0
`bukatu_name11` | 800b9dec | Data Label | Global | User Defined | 1 | 0
`bukatu_name_table` | 800b9df4 | Data Label | Global | User Defined | 7 | 0
`card_file_name` | 800b9e24 | Data Label | Global | User Defined | 1 | 0
`s_yes_button` | 800ba15c | Data Label | Global | User Defined | 12 | 0
`s_no_button` | 800ba174 | Data Label | Global | User Defined | 12 | 0
`pad_mode??` | 800ba190 | Data Label | Global | User Defined | 4 | 0
`pad_mode?` | 800ba194 | Data Label | Global | User Defined | 7 | 0
`konami_command` | 800ba198 | Data Label | Global | User Defined | 1 | 0
`konami_command_tag` | 800ba1e8 | Data Label | Global | User Defined | 5 | 0
`konami_command_flag` | 800ba1ec | Data Label | Global | User Defined | 6 | 0
`konami_command_timer` | 800ba1f0 | Data Label | Global | User Defined | 6 | 0
`voice?_800ba260` | 800ba260 | Data Label | Global | User Defined | 2 | 0
`voice?_800ba264` | 800ba264 | Data Label | Global | User Defined | 1 | 0
`voice_800ba268` | 800ba268 | Data Label | Global | User Defined | 1 | 0
`XAsector?` | 800ba26c | Data Label | Global | User Defined | 1 | 0
`yuukou_housei_table?` | 800ba600 | Data Label | Global | User Defined | 1 | 0
`yuukou_ba6a0` | 800ba6a0 | Data Label | Global | User Defined | 1 | 0
`grp_table` | 800ba6c3 | Data Label | Global | User Defined | 1 | 0
`_grp_table` | 800ba83f | Data Label | Global | User Defined | 1 | 0
`fuji_para_tbl?` | 800ba840 | Data Label | Global | User Defined | 1 | 0
`_fuji_para_tbl` | 800ba841 | Data Label | Global | User Defined | 1 | 0
`icon_col?` | 800ba890 | Data Label | Global | User Defined | 2 | 0
`icon_image0` | 800baa30 | Data Label | Global | User Defined | 2 | 0
`icon_image1` | 800babb0 | Data Label | Global | User Defined | 1 | 0
`icon_image2` | 800bad30 | Data Label | Global | User Defined | 1 | 0
`icon_image3` | 800baeb0 | Data Label | Global | User Defined | 1 | 0
`icon_image4` | 800bb030 | Data Label | Global | User Defined | 1 | 0
`icon_image5` | 800bb1b0 | Data Label | Global | User Defined | 1 | 0
`icon_image6` | 800bb330 | Data Label | Global | User Defined | 1 | 0
`icon_image7` | 800bb4b0 | Data Label | Global | User Defined | 1 | 0
`icon_image8` | 800bb630 | Data Label | Global | User Defined | 1 | 0
`icon_image9` | 800bb7b0 | Data Label | Global | User Defined | 1 | 0
`icon_imagea` | 800bb930 | Data Label | Global | User Defined | 1 | 0
`icon_imageb` | 800bbab0 | Data Label | Global | User Defined | 1 | 0
`icon_imagec` | 800bbc30 | Data Label | Global | User Defined | 1 | 0
`icon_image` | 800bbdb0 | Data Label | Global | User Defined | 2 | 0
`frame_cnt` | 800bbdf0 | Data Label | Global | User Defined | 3 | 0
`max_frame` | 800bbdf4 | Data Label | Global | User Defined | 2 | 0
`movie_ofx` | 800bbdf8 | Data Label | Global | User Defined | 4 | 0
`movie_ofy` | 800bbdfc | Data Label | Global | User Defined | 3 | 0
`rgb_mode?` | 800bbe00 | Data Label | Global | User Defined | 14 | 0
`next_line` | 800bbe04 | Data Label | Global | User Defined | 1 | 0
`dec_bg_sector?` | 800bbe20 | Data Label | Global | User Defined | 2 | 0
`now_dec_bg_show?` | 800bbe38 | Data Label | Global | User Defined | 10 | 0
`last_gamen_mode` | 800bbe3c | Data Label | Global | User Defined | 5 | 0
`full_move_timer` | 800bbe40 | Data Label | Global | User Defined | 3 | 0
`tbg_bri` | 800bbe44 | Data Label | Global | User Defined | 40 | 0
`season_main_e_bg_sector` | 800bbe50 | Data Label | Global | User Defined | 5 | 0
`season_main_n_bg_sector` | 800bbe60 | Data Label | Global | User Defined | 4 | 0
`radio_sector?` | 800bbe70 | Data Label | Global | User Defined | 1 | 0
`radio_sector_m?` | 800bbeb0 | Data Label | Global | User Defined | 1 | 0
`table_800bbf68` | 800bbf68 | Data Label | Global | User Defined | 2 | 0
`basyo_len` | 800bc024 | Data Label | Global | User Defined | 12 | 0
`cal_color` | 800bc028 | Data Label | Global | User Defined | 10 | 0
`season_timer` | 800bc0c8 | Data Label | Global | User Defined | 7 | 0
`bg_scroll_x` | 800bc0cc | Data Label | Global | User Defined | 13 | 0
`bg_scroll_y` | 800bc0d0 | Data Label | Global | User Defined | 13 | 0
`back_bg_pri?` | 800bc0d4 | Data Label | Global | User Defined | 5 | 0
`season_seq` | 800bc0d8 | Data Label | Global | User Defined | 2 | 0
`season_vh?` | 800bc0e8 | Data Label | Global | User Defined | 2 | 0
`season_vb?` | 800bc0f8 | Data Label | Global | User Defined | 2 | 0
`mascot_kind?` | 800bc108 | Data Label | Global | User Defined | 12 | 0
`iv2ic` | 800bc110 | Data Label | Global | User Defined | 6 | 0
`concert_names` | 800bc12c | Data Label | Global | User Defined | 0 | 0
`concert_kind_f` | 800bc20c | Data Label | Global | User Defined | 1 | 0
`cinema_name` | 800bc21c | Data Label | Global | User Defined | 0 | 0
`s_Banpo` | 800bc2b5 | Data Label | Global | User Defined | 1 | 0
`cinema_kind` | 800bc2fc | Data Label | Global | User Defined | 1 | 0
`message_newspot` | 800bc30c | Data Label | Global | User Defined | 1 | 0
`message_main` | 800bc3a4 | Data Label | Global | User Defined | 0 | 0
`p_mes0` | 800bc920 | Data Label | Global | User Defined | 1 | 0
`p_mes1` | 800bc98c | Data Label | Global | User Defined | 1 | 0
`p_mes2` | 800bc9a4 | Data Label | Global | User Defined | 1 | 0
`p_mes3` | 800bc9bc | Data Label | Global | User Defined | 1 | 0
`p_mes4` | 800bca20 | Data Label | Global | User Defined | 1 | 0
`p_mes5` | 800bca74 | Data Label | Global | User Defined | 1 | 0
`p_mes6` | 800bcacc | Data Label | Global | User Defined | 1 | 0
`p_mes7` | 800bcae0 | Data Label | Global | User Defined | 1 | 0
`p_mes8` | 800bcaf8 | Data Label | Global | User Defined | 1 | 0
`p_mes9` | 800bcb0c | Data Label | Global | User Defined | 2 | 0
`p_mes10` | 800bcb58 | Data Label | Global | User Defined | 2 | 0
`p_mes11` | 800bcb74 | Data Label | Global | User Defined | 2 | 0
`p_mes12` | 800bcb98 | Data Label | Global | User Defined | 2 | 0
`player_message` | 800bcba4 | Data Label | Global | User Defined | 1 | 0
`s_Circle` | 800bcc24 | Data Label | Global | User Defined | 1 | 0
`s_Cross` | 800bcc28 | Data Label | Global | User Defined | 1 | 0
`migi_string` | 800bcc2c | Data Label | Global | User Defined | 2 | 0
`hidari_string` | 800bcc30 | Data Label | Global | User Defined | 2 | 0
`s_de_machiawase` | 800bcebc | Data Label | Global | User Defined | 5 | 0
`arr_mag_messages` | 800bd1f8 | Data Label | Global | User Defined | 1 | 0
`checksum?_800bd234` | 800bd234 | Data Label | Global | User Defined | 8 | 0
`checksum??_800bd240` | 800bd240 | Data Label | Global | User Defined | 6 | 0
`BUNKEI` | 800cfae0 | Data Label | Global | User Defined | 1 | 0
`RIKEI` | 800cfaf4 | Data Label | Global | User Defined | 1 | 0
`GEIJYUTU` | 800cfb08 | Data Label | Global | User Defined | 1 | 0
`UNDOU` | 800cfb1c | Data Label | Global | User Defined | 1 | 0
`BUKATU` | 800cfb30 | Data Label | Global | User Defined | 1 | 0
`ASOBI` | 800cfb50 | Data Label | Global | User Defined | 1 | 0
`YOUSI` | 800cfb64 | Data Label | Global | User Defined | 1 | 0
`NERU` | 800cfb78 | Data Label | Global | User Defined | 1 | 0
`DENWA` | 800cfb98 | Data Label | Global | User Defined | 1 | 0
`DATE` | 800cfba4 | Data Label | Global | User Defined | 1 | 0
`JYOUHOU` | 800cfbb8 | Data Label | Global | User Defined | 1 | 0
`SYSTEM` | 800cfbcc | Data Label | Global | User Defined | 1 | 0
`CALENDAR` | 800cfbe0 | Data Label | Global | User Defined | 1 | 0
`MEMORY` | 800cfbf4 | Data Label | Global | User Defined | 1 | 0
`SAVETYUU` | 800cfc10 | Data Label | Global | User Defined | 1 | 0
`YOKUJITU` | 800cfc24 | Data Label | Global | User Defined | 1 | 0
`o_main_rom_table` | 800cfc30 | Data Label | Global | User Defined | 24 | 0
`o_main_pattern_table` | 800cfc5c | Data Label | Global | User Defined | 17 | 0
`o_main_animation_table` | 800cff14 | Data Label | Global | User Defined | 17 | 0
`CF2_DVLC?` | 800e19d6 | Data Label | Global | User Defined | 1 | 0
`arrCD_magic_numbers` | 800e2b0c | Data Label | Global | User Defined | 9 | 0
`cd_sync` | 800e2dc8 | Data Label | Global | User Defined | 20 | 0
`cd_rdy` | 800e2dcc | Data Label | Global | User Defined | 15 | 0
`cd_code_name` | 800eb720 | Data Label | Global | User Defined | 10 | 0
`sound_timeout_counter` | 800ebd10 | Data Label | Global | User Defined | 13 | 0
`flag_graphics_debug` | 800ebd62 | Data Label | Global | User Defined | 11 | 0
`padbuttons` | 800ee750 | Data Label | Global | User Defined | 3 | 0
`pad_800ee795` | 800ee795 | Data Label | Global | User Defined | 29 | 0
`debug_800ee79d` | 800ee79d | Data Label | Global | User Defined | 17 | 0
`current_year` | 800ee79e | Data Label | Global | User Defined | 62 | 0
`current_month` | 800ee79f | Data Label | Global | User Defined | 122 | 0
`current_day` | 800ee7a0 | Data Label | Global | User Defined | 66 | 0
`debug_800ee7a1` | 800ee7a1 | Data Label | Global | User Defined | 17 | 0
`debug_800ee7a2` | 800ee7a2 | Data Label | Global | User Defined | 23 | 0
`debug_800ee7a4` | 800ee7a4 | Data Label | Global | User Defined | 12 | 0
`debug_800ee7a6` | 800ee7a6 | Data Label | Global | User Defined | 1 | 0
`debug_800ee7ac` | 800ee7ac | Data Label | Global | User Defined | 2 | 1
`debug_800ee7b4` | 800ee7b4 | Data Label | Global | User Defined | 3 | 0
`debug_800ee7b8` | 800ee7b8 | Data Label | Global | User Defined | 2 | 1
`debug_800ee7c1` | 800ee7c1 | Data Label | Global | User Defined | 1 | 0
`debug_800ee7c2` | 800ee7c2 | Data Label | Global | User Defined | 1 | 0
`debug_800ee7c4` | 800ee7c4 | Data Label | Global | User Defined | 4 | 0
`debug_800ee7c8` | 800ee7c8 | Data Label | Global | User Defined | 1 | 0
`debug_800ee7e4` | 800ee7e4 | Data Label | Global | User Defined | 7 | 0
`debug_800ee7e7` | 800ee7e7 | Data Label | Global | User Defined | 3 | 0
`debug_800ee7e8` | 800ee7e8 | Data Label | Global | User Defined | 5 | 3
`debug_800ee7f0` | 800ee7f0 | Data Label | Global | User Defined | 2 | 1
`debug_800ee7f8` | 800ee7f8 | Data Label | Global | User Defined | 1 | 1
`debug_800ee800` | 800ee800 | Data Label | Global | User Defined | 1 | 0
`debug_800ee804` | 800ee804 | Data Label | Global | User Defined | 3 | 0
`player_name_800ee824` | 800ee824 | Data Label | Global | User Defined | 8 | 1
`surname_800ee834` | 800ee834 | Data Label | Global | User Defined | 46 | 1
`forename_800ee83c` | 800ee83c | Data Label | Global | User Defined | 16 | 0
`nickname_800ee844` | 800ee844 | Data Label | Global | User Defined | 8 | 0
`birthday_player` | 800ee858 | Data Label | Global | User Defined | 18 | 0
`yuukou_ee920` | 800ee920 | Data Label | Global | User Defined | 3 | 1
`club_800ee92a` | 800ee92a | Data Label | Global | User Defined | 28 | 0
`birthday_shiori` | 800ee92c | Data Label | Global | User Defined | 22 | 1
`debug_800eedcc` | 800eedcc | Data Label | Global | User Defined | 19 | 2
`etcflag_800eee7d` | 800eee7d | Data Label | Global | User Defined | 10 | 0
`etcflag_800eee7e` | 800eee7e | Data Label | Global | User Defined | 4 | 0
`c_girl` | 800ef6bf | Data Label | Global | User Defined | 52 | 0
`debug_800ef6c4` | 800ef6c4 | Data Label | Global | User Defined | 36 | 1
`last_joypad_check_result` | 800ef6d4 | Data Label | Global | User Defined | 18 | 0
`mouse_handedness` | 800ef6d5 | Data Label | Global | User Defined | 12 | 0
`pad1buttons` | 800ef6d6 | Data Label | Global | User Defined | 1 | 0
`pad_800ef6da` | 800ef6da | Data Label | Global | User Defined | 3 | 0
`pad_800ef6dc` | 800ef6dc | Data Label | Global | User Defined | 3 | 0
`pad2buttons` | 800ef6e0 | Data Label | Global | User Defined | 45 | 1
`pad_800ef6e4` | 800ef6e4 | Data Label | Global | User Defined | 7 | 0
`pad_800ef6e8` | 800ef6e8 | Data Label | Global | User Defined | 150 | 0
`not_mouse` | 800ef7f2 | Data Label | Global | User Defined | 21 | 0
`seed_800ef854` | 800ef854 | Data Label | Global | User Defined | 9 | 0
`seed_800ef858` | 800ef858 | Data Label | Global | User Defined | 66 | 0
`step?counter?` | 800ef864 | Data Label | Global | User Defined | 157 | 0
`loadtarget_800ef868` | 800ef868 | Data Label | Global | User Defined | 20 | 0
`sub_step_800ef869` | 800ef869 | Data Label | Global | User Defined | 34 | 0
`sub_sub_step` | 800ef86a | Data Label | Global | User Defined | 107 | 0
`scene` | 800ef86d | Data Label | Global | User Defined | 790 | 0
`step` | 800ef86e | Data Label | Global | User Defined | 6 | 0
`rng_800f01f0` | 800f01f0 | Data Label | Global | User Defined | 13 | 1
`JoyPad1` | 800f10d0 | Data Label | Global | User Defined | 5 | 0
`JoyPad1_type` | 800f10d1 | Data Label | Global | User Defined | 1 | 0
`JoyPad1_dpad` | 800f10d2 | Data Label | Global | User Defined | 1 | 0
`JoyPad1_buttons` | 800f10d3 | Data Label | Global | User Defined | 3 | 0
`JoyPad1_leftstick_X` | 800f10d4 | Data Label | Global | User Defined | 1 | 0
`JoyPad1_leftstick_Y` | 800f10d5 | Data Label | Global | User Defined | 1 | 0
`JoyPad2` | 800f1110 | Data Label | Global | User Defined | 5 | 0
`JoyPad2_type` | 800f1111 | Data Label | Global | User Defined | 1 | 0
`JoyPad2_dpad` | 800f1112 | Data Label | Global | User Defined | 2 | 0
`JoyPad2_buttons` | 800f1113 | Data Label | Global | User Defined | 2 | 0
`cursor_flag` | 801271b3 | Data Label | Global | User Defined | 34 | 0
`pad_801271d6` | 801271d6 | Data Label | Global | User Defined | 79 | 0
`pad_801271da` | 801271da | Data Label | Global | User Defined | 85 | 0
`face?wink?_80128b76` | 80128b76 | Data Label | Global | User Defined | 28 | 0
`extension_location` | 8012b5f0 | Data Label | Global | User Defined | 53 | 0
`savefile_buffer` | 8012b600 | Data Label | Global | User Defined | 11 | 0
`save_icon_anim_flag` | 8012b602 | Data Label | Global | User Defined | 2 | 0
`save_icon_block_count` | 8012b603 | Data Label | Global | User Defined | 2 | 0
`save_title` | 8012b604 | Data Label | Global | User Defined | 6 | 0
`save_reserved_44` | 8012b644 | Data Label | Global | User Defined | 2 | 0
`save_icon_palette` | 8012b660 | Data Label | Global | User Defined | 2 | 0
`save_icon_frame` | 8012b680 | Data Label | Global | User Defined | 2 | 0
`save_8012b800` | 8012b800 | Data Label | Global | User Defined | 5 | 0
`fileptr` | 8012dc60 | Data Label | Global | User Defined | 26 | 0
`xa?_8012dd30` | 8012dd30 | Data Label | Global | User Defined | 10 | 0
`ext_start` | 80132000 | Data Label | Global | User Defined | 12 | 0
`ext_80132040` | 80132040 | Data Label | Global | User Defined | 1 | 0
`ext_8013209c` | 8013209c | Data Label | Global | User Defined | 1 | 0
`ext_80132140` | 80132140 | Data Label | Global | User Defined | 1 | 0
`ext_80132214` | 80132214 | Data Label | Global | User Defined | 1 | 0
`ext_80132244` | 80132244 | Data Label | Global | User Defined | 1 | 0
`ext_80132274` | 80132274 | Data Label | Global | User Defined | 1 | 0
`ext_801322d4` | 801322d4 | Data Label | Global | User Defined | 1 | 0
`ext_80132334` | 80132334 | Data Label | Global | User Defined | 1 | 0
`ext_80133008` | 80133008 | Data Label | Global | User Defined | 1 | 0
`ext_80133120` | 80133120 | Data Label | Global | User Defined | 1 | 0
`ext_80133630` | 80133630 | Data Label | Global | User Defined | 1 | 0
`ext_80133a2c` | 80133a2c | Data Label | Global | User Defined | 1 | 0
`ext_80134040` | 80134040 | Data Label | Global | User Defined | 1 | 0
`ext_80134ec0` | 80134ec0 | Data Label | Global | User Defined | 1 | 0
`ext_80137124` | 80137124 | Data Label | Global | User Defined | 1 | 0
`ext_80137428` | 80137428 | Data Label | Global | User Defined | 1 | 0
`ext_80137890` | 80137890 | Data Label | Global | User Defined | 1 | 0
`ext_80137f64` | 80137f64 | Data Label | Global | User Defined | 1 | 0
`ext_801387e4` | 801387e4 | Data Label | Global | User Defined | 1 | 0
`ext_801389c0` | 801389c0 | Data Label | Global | User Defined | 1 | 0
`ext_80139150` | 80139150 | Data Label | Global | User Defined | 1 | 0
`ext_80139700` | 80139700 | Data Label | Global | User Defined | 1 | 0
`ext_8013b584` | 8013b584 | Data Label | Global | User Defined | 1 | 0
`ext_8013b5b0` | 8013b5b0 | Data Label | Global | User Defined | 1 | 0
`ext_8013c7a0` | 8013c7a0 | Data Label | Global | User Defined | 1 | 0
`ext_8013d258` | 8013d258 | Data Label | Global | User Defined | 1 | 0
`ext_80140770` | 80140770 | Data Label | Global | User Defined | 1 | 0
`ext_80141450` | 80141450 | Data Label | Global | User Defined | 1 | 0
`ext_80142300` | 80142300 | Data Label | Global | User Defined | 1 | 0
`ext_80142600` | 80142600 | Data Label | Global | User Defined | 1 | 0
`ext_80142700` | 80142700 | Data Label | Global | User Defined | 1 | 0
`ext_80142960` | 80142960 | Data Label | Global | User Defined | 1 | 0
`ext_8014484c` | 8014484c | Data Label | Global | User Defined | 1 | 0
`ext_80144a14` | 80144a14 | Data Label | Global | User Defined | 1 | 0
`ext_80144f94` | 80144f94 | Data Label | Global | User Defined | 1 | 0
`ext_80145a00` | 80145a00 | Data Label | Global | User Defined | 1 | 0
`ext_80146360` | 80146360 | Data Label | Global | User Defined | 1 | 0
`ext_801465e4` | 801465e4 | Data Label | Global | User Defined | 1 | 0
`ext_80149240` | 80149240 | Data Label | Global | User Defined | 1 | 0
`ext_8014ab50` | 8014ab50 | Data Label | Global | User Defined | 1 | 0
`ext_8014ae5c` | 8014ae5c | Data Label | Global | User Defined | 1 | 0
`ext_8014bff4` | 8014bff4 | Data Label | Global | User Defined | 1 | 0
`stack` | 801fff00 | Data Label | Global | User Defined | 0 | 0
`stackbase_801ffff0` | 801ffff0 | Data Label | Global | User Defined | 1 | 0
`filename` | Stack[-0x18]:20 | Local Var | delete_file | User Defined | 0 | 0
`filename` | Stack[-0x18]:24 | Local Var | make_file | User Defined | 0 | 0
`filename` | Stack[-0x1c]:28 | Local Var | SaveWriter_80055064 | User Defined | 0 | 0
`filename` | Stack[-0x1c]:28 | Local Var | find_card | User Defined | 0 | 0
`filename` | Stack[-0x1c]:28 | Local Var | savefile | User Defined | 0 | 0
`filename` | Stack[-0x20]:32 | Local Var | loadfile | User Defined | 0 | 0
`filen48` | Stack[-0x50]:48 | Local Var | CdSearchFile | User Defined | 6 | 0
`matc` | Stack[0x10]:4 | Parameter | ColorMatDpq | User Defined | 1 | 0
`sxy0` | Stack[0x10]:4 | Parameter | RotAverageNclip4 | User Defined | 1 | 0
`sxy0` | Stack[0x10]:4 | Parameter | RotNclip4 | User Defined | 1 | 0
`sxy1` | Stack[0x14]:4 | Parameter | RotNclip4 | User Defined | 1 | 0
`sxy1` | Stack[0x14]:4 | Parameter | RotAverageNclip4 | User Defined | 1 | 0
`sxy2` | Stack[0x18]:4 | Parameter | RotAverageNclip4 | User Defined | 1 | 0
`sxy2` | Stack[0x18]:4 | Parameter | RotNclip4 | User Defined | 1 | 0
`sxy3` | Stack[0x1c]:4 | Parameter | RotNclip4 | User Defined | 1 | 0
`sxy3` | Stack[0x1c]:4 | Parameter | RotAverageNclip4 | User Defined | 1 | 0
`p` | Stack[0x20]:4 | Parameter | RotAverageNclip4 | User Defined | 1 | 0
`p` | Stack[0x20]:4 | Parameter | RotNclip4 | User Defined | 1 | 0
`otz` | Stack[0x24]:4 | Parameter | RotAverageNclip4 | User Defined | 1 | 0
`otz` | Stack[0x24]:4 | Parameter | RotNclip4 | User Defined | 1 | 0
`flag` | Stack[0x28]:4 | Parameter | RotAverageNclip4 | User Defined | 2 | 0
`flag` | Stack[0x28]:4 | Parameter | RotNclip4 | User Defined | 2 | 0
`v0` | a0:4 | Parameter | ColorMatDpq | User Defined | 0 | 0
`m` | a0:4 | Parameter | ApplyMatrix | User Defined | 0 | 0
`name` | a0:4 | Parameter | get_p_name | User Defined | 0 | 0
`chan` | a0:4 | Parameter | _card_clear | User Defined | 0 | 0
`m` | a0:4 | Parameter | ReadColorMatrix | User Defined | 0 | 0
`v0` | a0:4 | Parameter | RotAverageNclip4 | User Defined | 0 | 0
`m` | a0:4 | Parameter | SetTransMatrix | User Defined | 0 | 0
`buffer` | a0:4 | Parameter | sprintf | User Defined | 0 | 0
`saveslot` | a0:4 | Parameter | savefile | User Defined | 0 | 0
`ofx` | a0:4 | Parameter | ReadGeomOffset | User Defined | 0 | 0
`m` | a0:4 | Parameter | SetLightMatrix | User Defined | 0 | 0
`filename` | a0:4 | Parameter | movie_main | User Defined | 0 | 0
`m0` | a0:4 | Parameter | SetMulMatrix | User Defined | 0 | 0
`id` | a0:4 | Parameter | PadRead | User Defined | 0 | 0
`level` | a0:4 | Parameter | SetGraphDebug | User Defined | 0 | 0
`r` | a0:4 | Parameter | RotMatrix | User Defined | 0 | 0
`sector` | a0:4 | Parameter | bust_up_read? | User Defined | 0 | 0
`r` | a0:4 | Parameter | GsSetAmbient | User Defined | 0 | 0
`m` | a0:4 | Parameter | SetColorMatrix | User Defined | 0 | 0
`v0` | a0:4 | Parameter | RotNclip4 | User Defined | 0 | 0
`fmt` | a0:4 | Parameter | printf | User Defined | 0 | 0
`chan` | a0:4 | Parameter | _card_info | User Defined | 0 | 0
`fp` | a0:4 | Parameter | CdSearchFile | User Defined | 0 | 0
`rfc` | a0:4 | Parameter | SetFarColor | User Defined | 0 | 0
`sz0` | a0:4 | Parameter | AverageZ3 | User Defined | 0 | 0
`v0` | a0:4 | Parameter | ColorMatCol | User Defined | 0 | 0
`name` | a0:4 | Parameter | get_g_name | User Defined | 0 | 0
`m` | a0:4 | Parameter | SetRotMatrix | User Defined | 0 | 0
`rbk` | a0:4 | Parameter | SetBackColor | User Defined | 0 | 0
`mode` | a0:4 | Parameter | PadInit | User Defined | 0 | 0
`v1` | a1:4 | Parameter | RotAverageNclip4 | User Defined | 0 | 0
`ofy` | a1:4 | Parameter | ReadGeomOffset | User Defined | 0 | 0
`sz1` | a1:4 | Parameter | AverageZ3 | User Defined | 0 | 0
`v1` | a1:4 | Parameter | ColorMatDpq | User Defined | 0 | 0
`g` | a1:4 | Parameter | GsSetAmbient | User Defined | 0 | 0
`gbk` | a1:4 | Parameter | SetBackColor | User Defined | 0 | 0
`gfc` | a1:4 | Parameter | SetFarColor | User Defined | 0 | 0
`fmt` | a1:4 | Parameter | sprintf | User Defined | 0 | 0
`filename` | a1:4 | Parameter | CdSearchFile | User Defined | 0 | 0
`maxf` | a1:4 | Parameter | movie_main | User Defined | 0 | 0
`v0` | a1:4 | Parameter | ApplyMatrix | User Defined | 0 | 0
`m1` | a1:4 | Parameter | SetMulMatrix | User Defined | 0 | 0
`m` | a1:4 | Parameter | RotMatrix | User Defined | 0 | 0
`v1` | a1:4 | Parameter | ColorMatCol | User Defined | 0 | 0
`v1` | a1:4 | Parameter | RotNclip4 | User Defined | 0 | 0
`v2` | a2:4 | Parameter | RotAverageNclip4 | User Defined | 0 | 0
`v2` | a2:4 | Parameter | ColorMatCol | User Defined | 0 | 0
`v2` | a2:4 | Parameter | RotNclip4 | User Defined | 0 | 0
`bbk` | a2:4 | Parameter | SetBackColor | User Defined | 0 | 0
`v1` | a2:4 | Parameter | ApplyMatrix | User Defined | 0 | 0
`sector` | a2:4 | Parameter | movie_main | User Defined | 0 | 0
`p` | a2:4 | Parameter | ColorMatDpq | User Defined | 0 | 0
`sz2` | a2:4 | Parameter | AverageZ3 | User Defined | 0 | 0
`bfc` | a2:4 | Parameter | SetFarColor | User Defined | 0 | 0
`b` | a2:4 | Parameter | GsSetAmbient | User Defined | 0 | 0
`matc` | a3:4 | Parameter | ColorMatCol | User Defined | 0 | 0
`func` | a3:4 | Parameter | OpenEvent | User Defined | 0 | 0
`v2` | a3:4 | Parameter | ColorMatDpq | User Defined | 0 | 0
`v3` | a3:4 | Parameter | RotNclip4 | User Defined | 0 | 0
`v3` | a3:4 | Parameter | RotAverageNclip4 | User Defined | 0 | 0
`write_hiragana` | name_ext::80132fd4 | Function | Global | User Defined | 1 | 0
`namescreen_1338dc` | name_ext::801338dc | Function | Global | User Defined | 10 | 0
`p_filen11` | s0:4 | Local Var | CdSearchFile | User Defined | 1 | 0
`n` | s0:4 | Local Var | savefile | User Defined | 1 | 0
`n` | s0:4 | Local Var | find_card | User Defined | 1 | 0
`n` | s0:4 | Local Var | loadfile | User Defined | 1 | 0
`left_stick_X` | t5:4 | Local Var | _pad_data_read_mouse | User Defined | 1 | 0
`left_stick_Y` | t7:4 | Local Var | _pad_data_read_mouse | User Defined | 1 | 0
`lt` | v0:1 | Local Var | check_load_func | User Defined | 1 | 0
`rng` | v0:4 | Local Var | FUN_8006ef68 | User Defined | 1 | 0
`rng` | v0:4 | Local Var | FUN_8006eae4 | User Defined | 1 | 0
`rng1` | v0:4 | Local Var | schedule_weekday? | User Defined | 1 | 0
`rng` | v0:4 | Local Var | title_init_ModelingData | User Defined | 1 | 0
`rng` | v0:4 | Local Var | FUN_8006f2bc | User Defined | 1 | 0
`rng2` | v0:4 | Local Var | bg_set | User Defined | 1 | 0
`rng` | v0:4 | Local Var | FUN_8006fbf0 | User Defined | 1 | 0
`rng` | v0:4 | Local Var | date_x_taku_set | User Defined | 1 | 0
`var1` | v0:4 | Local Var | holiday_init_0 | User Defined | 1 | 0
`rng` | v0:4 | Local Var | bg_set | User Defined | 1 | 0
`rng` | v0:4 | Local Var | phone_check | User Defined | 0 | 0
`raw_joypads` | v0:4 | Local Var | _pad_data_read_pad | User Defined | 1 | 0
`button` | v0:4 | Local Var | _pad_data_read_mouse | User Defined | 1 | 0
`result` | v0:4 | Local Var | controller_check | User Defined | 1 | 0
`rng1` | v0:4 | Local Var | kega_check1 | User Defined | 1 | 0
`bytes_written` | v0:4 | Local Var | SaveWriter_80055064 | User Defined | 1 | 0
`rng` | v0:4 | Local Var | kega_check1 | User Defined | 1 | 0
`rng` | v0:4 | Local Var | biorhythm_sf_set | User Defined | 1 | 0
`rng` | v0:4 | Local Var | FUN_80070754 | User Defined | 1 | 0
`rng2` | v0:4 | Local Var | FUN_8006fbf0 | User Defined | 1 | 0
`result` | v0:4 | Local Var | strcmp12 | User Defined | 1 | 0
`rng2` | v0:4 | Local Var | schedule_weekday? | User Defined | 1 | 0
`bytes_read` | v0:4 | Local Var | loadfile | User Defined | 1 | 0
`rng` | v0:4 | Local Var | FUN_80070910 | User Defined | 1 | 0
`rng1` | v0:4 | Local Var | FUN_8006fbf0 | User Defined | 1 | 0
`result` | v0:4 | Local Var | fujisaki_2nin_birth_check | User Defined | 1 | 0
`rng` | v0:4 | Local Var | schedule_analyze | User Defined | 1 | 0
`rng2` | v0:4 | Local Var | kega_check1 | User Defined | 1 | 0
`rng` | v0:4 | Local Var | schedule_weekday? | User Defined | 1 | 0
`rng` | v0:4 | Local Var | FUN_8006ec08 | User Defined | 1 | 0
`rng1` | v0:4 | Local Var | date_x_taku_set | User Defined | 1 | 0
