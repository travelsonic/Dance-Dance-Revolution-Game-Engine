Note: This document is far from complete. 

For the purpose of this document, "physical address" will refer to the address of the data / information in the game's executable, and the logical address will refer to where the information resides from the perspective of the Playstation2, a Playstation2 emulator, and many reverse engineering tools like IDA Pro, Ghidra, and PS2DIS.

The difference between physical and logical addresses is 0xFFF80.

<pre>
Physical Address(es):       Logical Address(es):        Description:  
0x001119B0 - 0x001119BC     0x00211930 - 0x0021193C     Function:
                                                        sysGetLanguage
0x001119C0 - 0x001119CC     0x00211940 - 0x0021194C     Function:
                                                        sysGetDateNotation
0x001119D0 - 0x00111A00     0x00211950 - 0x00211980     Function:
                                                        sysInitScf
0x00111A00 - 0x00111DD8     0x00211980 - 0x00211D58     Function:
                                                        draw_cur
0x00111DE0 - 0x00112108     0x00211D60 - 0x00212088     Function:
                                                        control_cur
0x00112110 - 0x00112220     0x00212090 - 0x002121A0     Function:
                                                        init_cur
0x00112220 - 0x00112264     0x002121A0 - 0x002121E4     Function:
                                                        set_cur_moving_pos
0x00112270 - 0x00112330     0x002121F0 - 0x002122B0     Function:
                                                        draw_title
0x00112330 - 0x00112460     0x002122B0 - 0x002123E0     Function:
                                                        Update_LesSelLevel
0x00112460 - 0x00112964     0x002123E0 - 0x002128E4     Function:
                                                        View_LesSelLevel
0x00112970 - 0x00112A6C     0x002128F0 - 0x002129EC     Function:
                                                        cursor_ud
0x00112A70 - 0x00112C80     0x002129F0 - 0x00212C00     Function:
                                                        Control_LesSelLevel
0x00112C80 - 0x00112CFC     0x00212C00 - 0x00212C7C     Function:
                                                        Init_LesSelLevel
0x00112D00 - 0x00112D50     0x00212C80 - 0x00212CD0     Function:
                                                        is_can_play_last_section
0x00112D50 - 0x00112D6C     0x00212CD0 - 0x00212CEC     Function:
                                                        SetLessonState
0x00112D70 - 0x00112D8C     0x00212CF0 - 0x00212D0C     Function:
                                                        GetLessonState
0x00112D90 - 0x00112FBC     0x00212D10 - 0x00212F3C     Function:
                                                        init_tex
0x00112FC0 - 0x00113098     0x00212F40 - 0x00213018     Function:
                                                        init_kanji
0x001130A0 - 0x00113190     0x00213020 - 0x00213110     Function:
                                                        close_func
0x00113190 - 0x00113318     0x00213110 - 0x00213298     Function:
                                                        open_func
0x00113320 - 0x00113434     0x002132A0 - 0x002133B4     Function:
                                                        init_func
0x00113440 - 0x00113454     0x002133C0 - 0x002133D4     Function:
                                                        Term_Les
0x00113460 - 0x001136A4     0x002133E0 - 0x00213624     Function:
                                                        Step_Les
0x001136B0 - 0x0011372C     0x00213630 - 0x002136AC     Function:
                                                        Init_Les
0x00113730 - 0x00113750     0x002136B0 - 0x002136D0     Function:
                                                        SetStep_Les
0x00113750 - 0x00113838     0x002136D0 - 0x002137B8     Function:
                                                        update_section_banner
0x00113840 - 0x00114264     0x002137C0 - 0x002141E4     Function:
                                                        view_section_banner
0x00114270 - 0x001149E4     0x002141F0 - 0x00214964     Function:
                                                        view_lesson_banner
0x001149F0 - 0x00114F50     0x00214970 - 0x00214ED0     Function:
                                                        DispStatusBar_LesSelSection
0x00114F50 - 0x00114FAC     0x00214ED0 - 0x00214F2C     Function:
                                                        InitStatusBar_LesSelSection
0x00114FB0 - 0x001150F4     0x00214F30 - 0x00215074     Function:
                                                        Update_LesSelSection
0x00115100 - 0x00115274     0x00215080 - 0x002151F4     Function:
                                                        View_LesSelSection
0x00115280 - 0x001156F0     0x00215200 - 0x00215670     Function:
                                                        Control_LesSelSection
0x001156F0 - 0x00115908     0x00215670 - 0x00215888     Function:
                                                        Init_LesSelSection
0x00115910 - 0x00115E60     0x00215890 - 0x00215DE0     Function:
                                                        lesson_data_setup
0x00115E60 - 0x001161BC     0x00215DE0 - 0x0021613C     Function:
                                                        make_ssq_at_lesson
0x001161C0 - 0x001162B4     0x00216140 - 0x00216234     Function:
                                                        disp_step
0x001162C0 - 0x001166CC     0x00216240 - 0x0021664C     Function:
                                                        play_main
0x001166D0 - 0x001167E4     0x00216650 - 0x00216764     Function:
                                                        intro_play
0x001167F0 - 0x00116DFC     0x00216770 - 0x00216D7C     Function:
                                                        play_init
0x00116E00 - 0x00116E3C     0x00216D80 - 0x00216DBC     Function:
                                                        Update_LesPlay
0x00116E40 - 0x00116E48     0x00216DC0 - 0x00216DC8     Function:
                                                        View_LesPlay
0x00116E50 - 0x0011707C     0x00216DD0 - 0x00216FFC     Function:
                                                        Control_LesPlay
0x00117080 - 0x00117430     0x00217000 - 0x002173B0     Function:
                                                        Init_LesPlay
0x00117430 - 0x0011749C     0x002173B0 - 0x0021741C     Function:
                                                        kn_lstep_lesson_play
0x001174A0 - 0x00117664     0x00217420 - 0x002175E4     Function:
                                                        kn_lstep_lesson_play_init
0x00117670 - 0x00117704     0x002175F0 - 0x00217684     Function:
                                                        kn_lstep_main_init
0x00117710 - 0x0011794C     0x00217690 - 0x002178CC     Function:
                                                        kn_lfunc_finger_op
0x00117950 - 0x00117A30     0x002178D0 - 0x002179B0     Function:
                                                        kn_lfunc_set_play_ct
0x00117A30 - 0x00117AC8     0x002179B0 - 0x00217A48     Function:
                                                        kn_lfunc_set_msg_status
0x00117AD0 - 0x00117C58     0x00217A50 - 0x00217BD8     Function:
                                                        kn_lfunc_set_foot_status
0x00117C60 - 0x00117D20     0x00217BE0 - 0x00217CA0     Function:
                                                        kn_lfunc_msg_op
0x00117D20 - 0x00117F44     0x00217CA0 - 0x00217EC4     Function:
                                                        kn_lfunc_set_foot_move
0x00117F50 - 0x001180F0     0x00217ED0 - 0x00218070     Function:
                                                        kn_lfunc_foot_op
0x001180F0 - 0x00118324     0x00218070 - 0x002182A4     Function:
                                                        kn_lfunc_chk_timing
0x00118330 - 0x001183C8     0x002182B0 - 0x00218348     Function:
                                                        kn_lfunc_chk_teach_mode
0x001183D0 - 0x00118474     0x00218350 - 0x002183F4     Function:
                                                        kn_lfunc_chk_clap
0x00118480 - 0x001184A4     0x00218400 - 0x00218424     Function:
                                                        kn_lfunc_chk_now_music
0x001184B0 - 0x001186DC     0x00218430 - 0x0021865C     Function:
                                                        kn_lfunc_set_head_data
0x001186E0 - 0x00118878     0x00218660 - 0x002187F8     Function:
                                                        kn_ldisp_start_exit
0x00118880 - 0x0011893C     0x00218800 - 0x002188BC     Function:
                                                        kn_ldisp_back
0x00118940 - 0x00118B28     0x002188C0 - 0x00218AA8     Function:
                                                        kn_ldisp_foot_stage
0x00118B30 - 0x00118CF4     0x00218AB0 - 0x00218C74     Function:
                                                        kn_ldisp_foot_touch
0x00118D00 - 0x00119124     0x00218C80 - 0x002190A4     Function:
                                                        kn_set_ft4_gte
0x00119130 - 0x00119290     0x002190B0 - 0x00219210     Function:
                                                        kn_ldisp_face_obj
0x00119290 - 0x001195B8     0x00219210 - 0x00219538     Function:
                                                        kn_ldisp_foot_obj
0x001195C0 - 0x00119734     0x00219540 - 0x002196B4     Function:
                                                        kn_ldisp_now_teach
0x00119740 - 0x00119AD4     0x002196C0 - 0x00219A54     Function:
                                                        kn_ldisp_play_msg_win
0x00119AE0 - 0x00119AF4     0x00219A60 - 0x00219A74     Function:
                                                        kn_ldisp_kanji_font_init
0x00119B00 - 0x00119B08     0x00219A80 - 0x00219A88     Function:
                                                        kn_ldisp_reset_font_emi
0x00119B10 - 0x00119C88     0x00219A90 - 0x00219C08     Function:
                                                        kn_ldisp_message
0x00119C90 - 0x00119DAC     0x00219C10 - 0x00219D2C     Function:
                                                        kn_kanji_font_emi
0x00119DB0 - 0x00119F6C     0x00219D30 - 0x00219EEC     Function:
                                                        kn_ldisp_lesson_play
0x00119F70 - 0x0011A1C8     0x00219EF0 - 0x0021A148     Function:
                                                        Update_Reconi
0x0011A1D0 - 0x0011A2EC     0x0021A150 - 0x0021A26C     Function:
                                                        View_Reconi
0x0011A2F0 - 0x0011A3B8     0x0021A270 - 0x0021A338     Function:
                                                        Control_Reconi
0x0011A3C0 - 0x0011A4CC     0x0021A340 - 0x0021A44C     Function:
                                                        Init_Reconi
0x0011A4D0 - 0x0011A788     0x0021A450 - 0x0021A708     Function:
                                                        draw_ope
0x0011A790 - 0x0011A96C     0x0021A710 - 0x0021A8EC     Function:
                                                        draw_dir_arrow
0x0011A970 - 0x0011AB70     0x0021A8F0 - 0x0021AAF0     Function:
                                                        draw_cursor
0x0011AB70 - 0x0011B2A8     0x0021AAF0 - 0x0021B228     Function:
                                                        draw_table
0x0011B2B0 - 0x0011B728     0x0021B230 - 0x0021B6A8     Function:
                                                        draw_detail_data
0x0011B730 - 0x0011B8CC     0x0021B6B0 - 0x0021B84C     Function:
                                                        puts_combo
0x0011B8D0 - 0x0011BAB0     0x0021B850 - 0x0021BA30     Function:
                                                        puts_oni_time
0x0011BAB0 - 0x0011BC50     0x0021BA30 - 0x0021BBD0     Function:
                                                        puts_oni_re2424
0x0011BC50 - 0x0011C210     0x0021BBD0 - 0x0021C190     Function:
                                                        puts_oni_score
0x0011C210 - 0x0011C87C     0x0021C190 - 0x0021C7FC     Function:
                                                        control_loop
0x0011C880 - 0x0011C9C4     0x0021C800 - 0x0021C944     Function:
                                                        control_delete
0x0011C9D0 - 0x0011CAD4     0x0021C950 - 0x0021CA54     Function:
                                                        SetDelStep
0x0011CAE0 - 0x0011CB70     0x0021CA60 - 0x0021CAF0     Function:
                                                        check_move_cursor
0x0011CB70 - 0x0011CD14     0x0021CAF0 - 0x0021CC94     Function:
                                                        set_data_scroll
0x0011CD20 - 0x0011CE00     0x0021CCA0 - 0x0021CD80     Function:
                                                        update_data
0x0011CE00 - 0x0011CE94     0x0021CD80 - 0x0021CE14     Function:
                                                        init_data
0x0011CEA0 - 0x0011D030     0x0021CE20 - 0x0021CFB0     Function:
                                                        init_oni_record
0x0011D030 - 0x0011D038     0x0021CFB0 - 0x0021CFB8     Function:
                                                        sysDemoSet
0x0011D040 - 0x0011D098     0x0021CFC0 - 0x0021D018     Function:
                                                        onimode_ta_load
0x0011D0A0 - 0x0011D0F0     0x0021D020 - 0x0021D070     Function:
                                                        onimode_get_stage_allnum
0x0011D0F0 - 0x0011D140     0x0021D070 - 0x0021D0C0     Function:
                                                        onimode_get_stage_num
0x0011D140 - 0x0011D374     0x0021D0C0 - 0x0021D2F4     Function:
                                                        onimode_set_playmode
0x0011D380 - 0x0011D3F4     0x0021D300 - 0x0021D374     Function:
                                                        onimode_get_add_life
0x0011D400 - 0x0011D49C     0x0021D380 - 0x0021D41C     Function:
                                                        onimode_get_disp_mip
0x0011D4A0 - 0x0011D510     0x0021D420 - 0x0021D490     Function:
                                                        onimode_get_mip
0x0011D510 - 0x0011D580     0x0021D490 - 0x0021D500     Function:
                                                        onimode_get_steps
0x0011D580 - 0x0011D5D4     0x0021D500 - 0x0021D554     Function:
                                                        onimode_get_start_life
0x0011D5E0 - 0x0011D634     0x0021D560 - 0x0021D5B4     Function:
                                                        onimode_get_order
0x0011D640 - 0x0011D708     0x0021D5C0 - 0x0021D688     Function:
                                                        onimode_course_avairable
0x0011D710 - 0x0011D764     0x0021D690 - 0x0021D6E4     Function:
                                                        onimode_course_load
0x0011D770 - 0x0011D7B8     0x0021D6F0 - 0x0021D738     Function:
                                                        onimode_is_course_data
0x0011D7C0 - 0x0011D91C     0x0021D740 - 0x0021D89C     Function:
                                                        onimode_boot
0x0011D920 - 0x0011D92C     0x0021D8A0 - 0x0021D8AC     Function:
                                                        oni_work_init
0x0011D930 - 0x0011D9C4     0x0021D8B0 - 0x0021D944     Function:
                                                        code2mip
0x0011D9D0 - 0x0011DA38     0x0021D950 - 0x0021D9B8     Function:
                                                        GetMusicData_by_link_num
0x0011DA40 - 0x0011DAE0     0x0021D9C0 - 0x0021DA60     Function:
                                                        GetMusicData_by_base_name
0x0011DAE0 - 0x0011DB0C     0x0021DA60 - 0x0021DA8C     Function:
                                                        GetMusicData_by_index
</pre>
