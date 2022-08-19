Note: This document is far from complete. 

For the purpose of this document, "physical address" will refer to the address of the data / information in the game's executable, and the logical address will refer to where the information resides from the perspective of the Playstation2, a Playstation2 emulator, and many reverse engineering tools like IDA Pro, Ghidra, and PS2DIS.

The difference between physical and logical addresses is 0xFFF80.

<pre>
Physical Address(es):       Logical Address(es):        Description:  
0x00127920 - 0x0012794C     0x002278A0 - 0x002278CC     Function:
                                                        sysInitScf
0x00127950 - 0x00127DF0     0x002278D0 - 0x00227D70     Function:
                                                        draw_cur
0x00127DF0 - 0x00128128     0x00227D70 - 0x002280A8     Function:
                                                        control_cur
0x00128130 - 0x00128240     0x002280B0 - 0x002281C0     Function:
                                                        init_cur
0x00128240 - 0x00128370     0x002281C0 - 0x002282F0     Function:
                                                        Update_LesSelLevel
0x00128370 - 0x0012892C     0x002282F0 - 0x002288AC     Function:
                                                        View_LesSelLevel
0x00128930 - 0x00128A30     0x002288B0 - 0x002289B0     Function:
                                                        cursor_ud
0x00128A30 - 0x00128C7C     0x002289B0 - 0x00228BFC     Function:
                                                        Control_LesSelLevel
0x00128C80 - 0x00128D4C     0x00228C00 - 0x00228CCC     Function:
                                                        Init_LesSelLevel
0x00128D50 - 0x00128DA0     0x00228CD0 - 0x00228D20     Function:
                                                        is_can_play_last_section
0x00128DA0 - 0x00128DBC     0x00228D20 - 0x00228D3C     Function:
                                                        SetLessonState
0x00128DC0 - 0x00128DDC     0x00228D40 - 0x00228D5C     Function:
                                                        GetLessonState
0x00128DE0 - 0x00129060     0x00228D60 - 0x00228FE0     Function:
                                                        init_tex
0x00129060 - 0x00129074     0x00228FE0 - 0x00228FF4     Function:
                                                        SetPreRead_Les
0x00129080 - 0x00129164     0x00229000 - 0x002290E4     Function:
                                                        init_kanji
0x00129170 - 0x0012926C     0x002290F0 - 0x002291EC     Function:
                                                        close_func
0x00129270 - 0x0012940C     0x002291F0 - 0x0022938C     Function:
                                                        open_func
0x00129410 - 0x00129564     0x00229390 - 0x002294E4     Function:
                                                        init_func
0x00129570 - 0x00129584     0x002294F0 - 0x00229504     Function:
                                                        Term_Les
0x00129590 - 0x001297E8     0x00229510 - 0x00229768     Function:
                                                        Step_Les
0x001297F0 - 0x0012986C     0x00229770 - 0x002297EC     Function:
                                                        Init_Les
0x00129870 - 0x00129894     0x002297F0 - 0x00229814     Function:
                                                        SetStep_Les
0x001298A0 - 0x00129988     0x00229820 - 0x00229908     Function:
                                                        update_section_banner
0x00129990 - 0x0012A5F4     0x00229910 - 0x0022A574     Function:
                                                        view_section_banner
0x0012A600 - 0x0012A9A0     0x0022A580 - 0x0022A920     Function:
                                                        view_lesson_banner
0x0012A9A0 - 0x0012AD98     0x0022A920 - 0x0022AD18     Function:
                                                        DispStatusBar_LesSelSection
0x0012ADA0 - 0x0012ADFC     0x0022AD20 - 0x0022AD7C     Function:
                                                        InitStatusBar_LesSelSection
0x0012AE00 - 0x0012AF40     0x0022AD80 - 0x0022AEC0     Function:
                                                        Update_LesSelSection
0x0012AF40 - 0x0012B0BC     0x0022AEC0 - 0x0022B03C     Function:
                                                        View_LesSelSection
0x0012B0C0 - 0x0012B548     0x0022B040 - 0x0022B4C8     Function:
                                                        Control_LesSelSection
0x0012B550 - 0x0012B768     0x0022B4D0 - 0x0022B6E8     Function:
                                                        Init_LesSelSection
0x0012B770 - 0x0012BCE0     0x0022B6F0 - 0x0022BC60     Function:
                                                        lesson_data_setup
0x0012BCE0 - 0x0012C044     0x0022BC60 - 0x0022BFC4     Function:
                                                        make_ssq_at_lesson
0x0012C050 - 0x0012C14C     0x0022BFD0 - 0x0022C0CC     Function:
                                                        disp_step
0x0012C150 - 0x0012C5A0     0x0022C0D0 - 0x0022C520     Function:
                                                        play_main
0x0012C5A0 - 0x0012C6B8     0x0022C520 - 0x0022C638     Function:
                                                        intro_play
0x0012C6C0 - 0x0012CCCC     0x0022C640 - 0x0022CC4C     Function:
                                                        play_init
0x0012CCD0 - 0x0012CD08     0x0022CC50 - 0x0022CC88     Function:
                                                        Update_LesPlay
0x0012CD10 - 0x0012CD18     0x0022CC90 - 0x0022CC98     Function:
                                                        View_LesPlay
0x0012CD20 - 0x0012CF6C     0x0022CCA0 - 0x0022CEEC     Function:
                                                        Control_LesPlay
0x0012CF70 - 0x0012D390     0x0022CEF0 - 0x0022D310     Function:
                                                        Init_LesPlay
0x0012D390 - 0x0012D3FC     0x0022D310 - 0x0022D37C     Function:
                                                        kn_lstep_lesson_play
0x0012D400 - 0x0012D5C4     0x0022D380 - 0x0022D544     Function:
                                                        kn_lstep_lesson_play_init
0x0012D5D0 - 0x0012D664     0x0022D550 - 0x0022D5E4     Function:
                                                        kn_lstep_main_init
0x0012D670 - 0x0012D8B0     0x0022D5F0 - 0x0022D830     Function:
                                                        kn_lfunc_finger_op
0x0012D8B0 - 0x0012D990     0x0022D830 - 0x0022D910     Function:
                                                        kn_lfunc_set_play_ct
0x0012D990 - 0x0012DA40     0x0022D910 - 0x0022D9C0     Function:
                                                        kn_lfunc_set_msg_status
0x0012DA40 - 0x0012DBCC     0x0022D9C0 - 0x0022DB4C     Function:
                                                        kn_lfunc_set_foot_status
0x0012DBD0 - 0x0012DC98     0x0022DB50 - 0x0022DC18     Function:
                                                        kn_lfunc_msg_op
0x0012DCA0 - 0x0012DEB0     0x0022DC20 - 0x0022DE30     Function:
                                                        kn_lfunc_set_foot_move
0x0012DEB0 - 0x0012E04C     0x0022DE30 - 0x0022DFCC     Function:
                                                        kn_lfunc_foot_op
0x0012E050 - 0x0012E298     0x0022DFD0 - 0x0022E218     Function:
                                                        kn_lfunc_chk_timing
0x0012E2A0 - 0x0012E340     0x0022E220 - 0x0022E2C0     Function:
                                                        kn_lfunc_chk_teach_mode
0x0012E340 - 0x0012E3E8     0x0022E2C0 - 0x0022E368     Function:
                                                        kn_lfunc_chk_clap
0x0012E3F0 - 0x0012E414     0x0022E370 - 0x0022E394     Function:
                                                        kn_lfunc_chk_now_music
0x0012E420 - 0x0012E64C     0x0022E3A0 - 0x0022E5CC     Function:
                                                        kn_lfunc_set_head_data
0x0012E650 - 0x0012E6F0     0x0022E5D0 - 0x0022E670     Function:
                                                        kn_ldisp_start_exit
0x0012E6F0 - 0x0012E7B0     0x0022E670 - 0x0022E730     Function:
                                                        kn_ldisp_back
0x0012E7B0 - 0x0012E9FC     0x0022E730 - 0x0022E97C     Function:
                                                        kn_ldisp_foot_stage
0x0012EA00 - 0x0012EC2C     0x0022E980 - 0x0022EBAC     Function:
                                                        kn_ldisp_foot_touch
0x0012EC30 - 0x0012F060     0x0022EBB0 - 0x0022EFE0     Function:
                                                        kn_set_ft4_gte
0x0012F060 - 0x0012F1F8     0x0022EFE0 - 0x0022F178     Function:
                                                        kn_ldisp_face_obj
0x0012F200 - 0x0012F5F0     0x0022F180 - 0x0022F570     Function:
                                                        kn_ldisp_foot_obj
0x0012F5F0 - 0x0012F7C4     0x0022F570 - 0x0022F744     Function:
                                                        kn_ldisp_now_teach
0x0012F7D0 - 0x0012F878     0x0022F750 - 0x0022F7F8     Function:
                                                        kn_ldisp_play_msg_win
0x0012F880 - 0x0012F894     0x0022F800 - 0x0022F814     Function:
                                                        kn_ldisp_kanji_font_init
0x0012F8A0 - 0x0012F8A8     0x0022F820 - 0x0022F828     Function:
                                                        kn_ldisp_reset_font_emi
0x0012F8B0 - 0x0012FA38     0x0022F830 - 0x0022F9B8     Function:
                                                        kn_ldisp_message
0x0012FA40 - 0x0012FBFC     0x0022F9C0 - 0x0022FB7C     Function:
                                                        kn_kanji_font_emi
0x0012FC00 - 0x0012FE44     0x0022FB80 - 0x0022FDC4     Function:
                                                        kn_ldisp_lesson_play
0x0012FE50 - 0x0013000C     0x0022FDD0 - 0x0022FF8C     Function:
                                                        RecOniLoadData
0x00130010 - 0x00130258     0x0022FF90 - 0x002301D8     Function:
                                                        Update_Reconi
0x00130260 - 0x00130390     0x002301E0 - 0x00230310     Function:
                                                        View_Reconi
0x00130390 - 0x00130468     0x00230310 - 0x002303E8     Function:
                                                        Control_Reconi
0x00130470 - 0x001305A8     0x002303F0 - 0x00230528     Function:
                                                        Init_Reconi
0x001305B0 - 0x001308C0     0x00230530 - 0x00230840     Function:
                                                        draw_ope
0x001308C0 - 0x00130AD0     0x00230840 - 0x00230A50     Function:
                                                        draw_dir_arrow
0x00130AD0 - 0x00130D4C     0x00230A50 - 0x00230CCC     Function:
                                                        draw_cursor
0x00130D50 - 0x001316A0     0x00230CD0 - 0x00231620     Function:
                                                        draw_table
0x001316A0 - 0x00131D10     0x00231620 - 0x00231C90     Function:
                                                        draw_detail_data
0x00131D10 - 0x00131EF0     0x00231C90 - 0x00231E70     Function:
                                                        puts_combo
0x00131EF0 - 0x00132178     0x00231E70 - 0x002320F8     Function:
                                                        puts_oni_time
0x00132180 - 0x00132378     0x00232100 - 0x002322F8     Function:
                                                        puts_oni_re2424
0x00132380 - 0x00132620     0x00232300 - 0x002325A0     Function:
                                                        puts_oni_score
0x00132620 - 0x00132C54     0x002325A0 - 0x00232BD4     Function:
                                                        control_loop
0x00132C60 - 0x00132DA8     0x00232BE0 - 0x00232D28     Function:
                                                        control_delete
0x00132DB0 - 0x00132ECC     0x00232D30 - 0x00232E4C     Function:
                                                        SetDelStep
0x00132ED0 - 0x00132F68     0x00232E50 - 0x00232EE8     Function:
                                                        check_move_cursor
0x00132F70 - 0x00133110     0x00232EF0 - 0x00233090     Function:
                                                        set_data_scroll
0x00133110 - 0x001331E8     0x00233090 - 0x00233168     Function:
                                                        update_data
0x001331F0 - 0x00133284     0x00233170 - 0x00233204     Function:
                                                        init_data
0x00133290 - 0x00133438     0x00233210 - 0x002333B8     Function:
                                                        init_oni_record
0x00133440 - 0x00133448     0x002333C0 - 0x002333C8     Function:
                                                        sysDemoSet
0x00133450 - 0x00133608     0x002333D0 - 0x00233588     Function:
                                                        onimode_load_tex_step
0x00133610 - 0x00133624     0x00233590 - 0x002335A4     Function:
                                                        onimode_load_tex_init
0x00133630 - 0x0013363C     0x002335B0 - 0x002335BC     Function:
                                                        onimode_get_onicourse_id
0x00133640 - 0x0013364C     0x002335C0 - 0x002335CC     Function:
                                                        onimode_get_onicourse_work
0x00133650 - 0x00133828     0x002335D0 - 0x002337A8     Function:
                                                        is_oni_course_passed
0x00133830 - 0x001338C0     0x002337B0 - 0x00233840     Function:
                                                        onimode_get_course_nm_color
0x001338C0 - 0x001338E8     0x00233840 - 0x00233868     Function:
                                                        onimode_get_course_list
0x001338F0 - 0x00133C48     0x00233870 - 0x00233BC8     Function:
                                                        onimode_set_order_mode
0x00133C50 - 0x00133EBC     0x00233BD0 - 0x00233E3C     Function:
                                                        onimode_get_order_mode
0x00133EC0 - 0x00133EF8     0x00233E40 - 0x00233E78     Function:
                                                        onimode_is_course_order
0x00133F00 - 0x00133F30     0x00233E80 - 0x00233EB0     Function:
                                                        onimode_is_course_cs_random
0x00133F30 - 0x001344A8     0x00233EB0 - 0x00234428     Function:
                                                        onimode_order_setup
0x001344B0 - 0x00135428     0x00234430 - 0x002353A8     Function:
                                                        onimode_random_setup
0x00135430 - 0x001355A8     0x002353B0 - 0x00235528     Function:
                                                        onimode_set_linknum
0x001355B0 - 0x001355F4     0x00235530 - 0x00235574     Function:
                                                        onimode_ta_load
0x00135600 - 0x00135700     0x00235580 - 0x00235680     Function:
                                                        onimode_set_order_stage
0x00135700 - 0x00135768     0x00235680 - 0x002356E8     Function:
                                                        onimode_get_real_stage_num
0x00135770 - 0x001357C0     0x002356F0 - 0x00235740     Function:
                                                        onimode_get_stage_allnum
0x001357C0 - 0x00135810     0x00235740 - 0x00235790     Function:
                                                        onimode_get_stage_num
0x00135810 - 0x00135B04     0x00235790 - 0x00235A84     Function:
                                                        onimode_set_playmode
0x00135B10 - 0x00135B80     0x00235A90 - 0x00235B00     Function:
                                                        onimode_get_add_life
0x00135B80 - 0x00135D08     0x00235B00 - 0x00235C88     Function:
                                                        onimode_set_seqkind
0x00135D10 - 0x00135DB8     0x00235C90 - 0x00235D38     Function:
                                                        onimode_get_seqkind
0x00135DC0 - 0x00136178     0x00235D40 - 0x002360F8     Function:
                                                        onimode_set_course_difficulty
0x00136180 - 0x001364A8     0x00236100 - 0x00236428     Function:
                                                        onimode_setup_nonstop_course
0x001364B0 - 0x0013657C     0x00236430 - 0x002364FC     Function:
                                                        onimode_get_disp_mip
0x00136580 - 0x0013665C     0x00236500 - 0x002365DC     Function:
                                                        onimode_get_mip
0x00136660 - 0x001366A8     0x002365E0 - 0x00236628     Function:
                                                        onimode_get_steps
0x001366B0 - 0x001369D8     0x00236630 - 0x00236958     Function:
                                                        onimode_set_steps
0x001369E0 - 0x00136A30     0x00236960 - 0x002369B0     Function:
                                                        onimode_get_start_life
0x00136A30 - 0x00136A80     0x002369B0 - 0x00236A00     Function:
                                                        onimode_get_order
0x00136A80 - 0x00136AD0     0x00236A00 - 0x00236A50     Function:
                                                        onimode_get_irid
0x00136AD0 - 0x00136B40     0x00236A50 - 0x00236AC0     Function:
                                                        onimode_is_course_default
0x00136B40 - 0x00136BC0     0x00236AC0 - 0x00236B40     Function:
                                                        onimode_course_avairable
0x00136BC0 - 0x00136E5C     0x00236B40 - 0x00236DDC     Function:
                                                        onimode_course_load
0x00136E60 - 0x00136EA0     0x00236DE0 - 0x00236E20     Function:
                                                        onimode_is_course_data
0x00136EA0 - 0x00136F84     0x00236E20 - 0x00236F04     Function:
                                                        onimode_boot
0x00136F90 - 0x00136FF0     0x00236F10 - 0x00236F70     Function:
                                                        GetMusicData_by_link_num
0x00136FF0 - 0x00137088     0x00236F70 - 0x00237008     Function:
                                                        GetMusicData_by_base_name
0x00137090 - 0x001370C0     0x00237010 - 0x00237040     Function:
                                                        GetMusicData_by_index
0x001370C0 - 0x001372CC     0x00237040 - 0x0023724C     Function:
                                                        sp_ending_loading_print
0x001372D0 - 0x0013766C     0x00237250 - 0x002375EC     Function:
                                                        sp_ending_get_bk_movie_prim
0x00137670 - 0x00137E80     0x002375F0 - 0x00237E00     Function:
                                                        special_ending_disp_step
0x00137E80 - 0x00137F40     0x00237E00 - 0x00237EC0     Function:
                                                        special_ending_disp_init
0x00137F40 - 0x00137FAC     0x00237EC0 - 0x00237F2C     Function:
                                                        sysReadMusicBk
0x00137FB0 - 0x00137FE4     0x00237F30 - 0x00237F64     Function:
                                                        sysWaitMusicBk
0x00137FF0 - 0x00138030     0x00237F70 - 0x00237FB0     Function:
                                                        sysSetMusicBk
0x00138030 - 0x00138338     0x00237FB0 - 0x002382B8     Function:
                                                        RecendPrintDigit
0x00138340 - 0x00138700     0x002382C0 - 0x00238680     Function:
                                                        RecendTexDisp
0x00138700 - 0x00138F58     0x00238680 - 0x00238ED8     Function:
                                                        RecendAllDisp
0x00138F60 - 0x001390C8     0x00238EE0 - 0x00239048     Function:
                                                        RecendTexWaveRGB
0x001390D0 - 0x00139320     0x00239050 - 0x002392A0     Function:
                                                        RecendTexMoveXY
0x00139320 - 0x00139AFC     0x002392A0 - 0x00239A7C     Function:
                                                        RecendTexSetPage
0x00139B00 - 0x00139D68     0x00239A80 - 0x00239CE8     Function:
                                                        RecendDataDelete
0x00139D70 - 0x00139EDC     0x00239CF0 - 0x00239E5C     Function:
                                                        RecendTexDelOpen
0x00139EE0 - 0x0013A0A8     0x00239E60 - 0x0023A028     Function:
                                                        Update_Recend
0x0013A0B0 - 0x0013A0E8     0x0023A030 - 0x0023A068     Function:
                                                        View_Recend
0x0013A0F0 - 0x0013A878     0x0023A070 - 0x0023A7F8     Function:
                                                        Control_Recend
0x0013A880 - 0x0013B504     0x0023A800 - 0x0023B484     Function:
                                                        Init_Recend
0x0013B510 - 0x0013B718     0x0023B490 - 0x0023B698     Function:
                                                        EdsSelectPrintDigit
0x0013B720 - 0x0013CC74     0x0023B6A0 - 0x0023CBF4     Function:
                                                        EdsOrderCommon
0x0013CC80 - 0x0013CFF8     0x0023CC00 - 0x0023CF78     Function:
                                                        EdsOrderInit
0x0013D000 - 0x0013D010     0x0023CF80 - 0x0023CF90     Function:
                                                        EdsToOrderTexInit
0x0013D010 - 0x0013D108     0x0023CF90 - 0x0023D088     Function:
                                                        EdsPlayCommon
0x0013D110 - 0x0013DB54     0x0023D090 - 0x0023DAD4     Function:
                                                        EdsPlayInit
0x0013DB60 - 0x0013DBEC     0x0023DAE0 - 0x0023DB6C     Function:
                                                        EdsMenuBlackWait
0x0013DBF0 - 0x0013EB08     0x0023DB70 - 0x0023EA88     Function:
                                                        EdsMenuCommon
0x0013EB10 - 0x0013EEAC     0x0023EA90 - 0x0023EE2C     Function:
                                                        EdsMenuInit2
0x0013EEB0 - 0x0013F27C     0x0023EE30 - 0x0023F1FC     Function:
                                                        EdsMenuInit
0x0013F280 - 0x0013F3C0     0x0023F200 - 0x0023F340     Function:
                                                        EdsToMenuTexInit
0x0013F3C0 - 0x0013F4F0     0x0023F340 - 0x0023F470     Function:
                                                        EdsWarningCommon
0x0013F4F0 - 0x0013F54C     0x0023F470 - 0x0023F4CC     Function:
                                                        EdsWarningInit
0x0013F550 - 0x0013F5B0     0x0023F4D0 - 0x0023F530     Function:
                                                        EdsMainMenuTexture
0x0013F5B0 - 0x0013F5E4     0x0023F530 - 0x0023F564     Function:
                                                        EdsMainMenuInit
0x0013F5F0 - 0x0013F75C     0x0023F570 - 0x0023F6DC     Function:
                                                        EdsSelectMain
0x0013F760 - 0x0013F8D8     0x0023F6E0 - 0x0023F858     Function:
                                                        EdsInitBreakTex
0x0013F8E0 - 0x0013FB78     0x0023F860 - 0x0023FAF8     Function:
                                                        EdsInitTex
0x0013FB80 - 0x0013FB8C     0x0023FB00 - 0x0023FB0C     Function:
                                                        EdsSystemEnd
0x0013FB90 - 0x0013FBCC     0x0023FB10 - 0x0023FB4C     Function:
                                                        EdsSystemMain
0x0013FBD0 - 0x0013FC74     0x0023FB50 - 0x0023FBF4     Function:
                                                        EdsSystemInit
0x0013FC80 - 0x0013FC88     0x0023FC00 - 0x0023FC08     Function:
                                                        EdsSetPreRead
0x0013FC90 - 0x0013FE78     0x0023FC10 - 0x0023FDF8     Function:
                                                        Update_Optscr
0x0013FE80 - 0x00140518     0x0023FE00 - 0x00240498     Function:
                                                        View_Optscr
0x00140520 - 0x00140AD8     0x002404A0 - 0x00240A58     Function:
                                                        Control_Optscr
0x00140AE0 - 0x00140B98     0x00240A60 - 0x00240B18     Function:
                                                        Init_Optscr
0x00140BA0 - 0x00140C2C     0x00240B20 - 0x00240BAC     Function:
                                                        EdsWinSelectAllFrameDisp
0x00140C30 - 0x00140F08     0x00240BB0 - 0x00240E88     Function:
                                                        EdsWinSelectFrame
0x00140F10 - 0x00140FDC     0x00240E90 - 0x00240F5C     Function:
                                                        EdsWinSelectBox
0x00140FE0 - 0x0014110C     0x00240F60 - 0x0024108C     Function:
                                                        EdsOrderCheckList
0x00141110 - 0x001412E8     0x00241090 - 0x00241268     Function:
                                                        EdsCheck
0x001412F0 - 0x00141490     0x00241270 - 0x00241410     Function:
                                                        EdsWinAllDestroy
0x00141490 - 0x00141514     0x00241410 - 0x00241494     Function:
                                                        EdsWinSetTex
0x00141520 - 0x001415A0     0x002414A0 - 0x00241520     Function:
                                                        EdsWinSetMoveXY
0x001415A0 - 0x001415F8     0x00241520 - 0x00241578     Function:
                                                        EdsWinSetXY
0x00141600 - 0x00141664     0x00241580 - 0x002415E4     Function:
                                                        EdsWinSetType
0x00141670 - 0x0014178C     0x002415F0 - 0x0024170C     Function:
                                                        EdsWinSetMode
0x00141790 - 0x00141870     0x00241710 - 0x002417F0     Function:
                                                        EdsWinSetDefaultPartsWH
0x00141870 - 0x00141948     0x002417F0 - 0x002418C8     Function:
                                                        EdsWinDefaultAllSet
0x00141950 - 0x00141BE8     0x002418D0 - 0x00241B68     Function:
                                                        EdsWinAlphaAnime
0x00141BF0 - 0x00141DB8     0x00241B70 - 0x00241D38     Function:
                                                        EdsWinWHMove
0x00141DC0 - 0x00141FD0     0x00241D40 - 0x00241F50     Function:
                                                        EdsWinXYMove
0x00141FD0 - 0x00142270     0x00241F50 - 0x002421F0     Function:
                                                        EdsWinXYWHMove
0x00142270 - 0x001427C8     0x002421F0 - 0x00242748     Function:
                                                        EdsWinDisp
0x001427D0 - 0x00142830     0x00242750 - 0x002427B0     Function:
                                                        EdsWinDestroy
0x00142830 - 0x00142A10     0x002427B0 - 0x00242990     Function:
                                                        EdsWinClose
0x00142A10 - 0x00142AD8     0x00242990 - 0x00242A58     Function:
                                                        EdsWinMain
0x00142AE0 - 0x00142D48     0x00242A60 - 0x00242CC8     Function:
                                                        EdsWinOpen
0x00142D50 - 0x00142D5C     0x00242CD0 - 0x00242CDC     Function:
                                                        EdsWinSet
0x00142D60 - 0x00142E44     0x00242CE0 - 0x00242DC4     Function:
                                                        EdsWinGetInit
0x00142E50 - 0x00142F10     0x00242DD0 - 0x00242E90     Function:
                                                        EdsWinFunc
0x00142F10 - 0x001430C0     0x00242E90 - 0x00243040     Function:
                                                        EdsAidPrintFont
0x001430C0 - 0x0014344C     0x00243040 - 0x002433CC     Function:
                                                        EdsScoreCreate
0x00143450 - 0x00143D7C     0x002433D0 - 0x00243CFC     Function:
                                                        EdsNextStageCreate
0x00143D80 - 0x00143E40     0x00243D00 - 0x00243DC0     Function:
                                                        EdsBeforeStageDataSet
0x00143E40 - 0x00143EE0     0x00243DC0 - 0x00243E60     Function:
                                                        EdsMOMax
0x00143EE0 - 0x00144290     0x00243E60 - 0x00244210     Function:
                                                        EdsPlayFlag
0x00144290 - 0x00144360     0x00244210 - 0x002442E0     Function:
                                                        EdsAdjudRegulationLevel
0x00144360 - 0x001445B0     0x002442E0 - 0x00244530     Function:
                                                        EdsGetRegulationStatus
0x001445B0 - 0x00144688     0x00244530 - 0x00244608     Function:
                                                        EdsGetMipTable
0x00144690 - 0x00144860     0x00244610 - 0x002447E0     Function:
                                                        EdsInitMipTable
0x00144860 - 0x00144CA8     0x002447E0 - 0x00244C28     Function:
                                                        EdsGetLevelType
0x00144CB0 - 0x00144F80     0x00244C30 - 0x00244F00     Function:
                                                        EdsInitOrderFlag
0x00144F80 - 0x001453D8     0x00244F00 - 0x00245358     Function:
                                                        EdsTrackSorting
0x001453E0 - 0x001454B0     0x00245360 - 0x00245430     Function:
                                                        EdsInitAllMusicMax
0x001454B0 - 0x00145508     0x00245430 - 0x00245488     Function:
                                                        EdsBreakStageEnd
0x00145510 - 0x001456F0     0x00245490 - 0x00245670     Function:
                                                        EdsBreakStageMain
0x001456F0 - 0x001457D0     0x00245670 - 0x00245750     Function:
                                                        EdsBreakStageInit
0x001457D0 - 0x00145A98     0x00245750 - 0x00245A18     Function:
                                                        EdsRecordPrintDigit
0x00145AA0 - 0x00145E98     0x00245A20 - 0x00245E18     Function:
                                                        EdsRenewalRecord
0x00145EA0 - 0x00145ED8     0x00245E20 - 0x00245E58     Function:
                                                        EdsRecordEnd
0x00145EE0 - 0x00146AB0     0x00245E60 - 0x00246A30     Function:
                                                        EdsRecordCommon
0x00146AB0 - 0x001470A8     0x00246A30 - 0x00247028     Function:
                                                        EdsRecordTexture
0x001470B0 - 0x0014710C     0x00247030 - 0x0024708C     Function:
                                                        EdsRecordInit
0x00147110 - 0x00147218     0x00247090 - 0x00247198     Function:
                                                        Update_Optlang
0x00147220 - 0x00147728     0x002471A0 - 0x002476A8     Function:
                                                        View_Optlang
0x00147730 - 0x00147A94     0x002476B0 - 0x00247A14     Function:
                                                        Control_Optlang
0x00147AA0 - 0x00147B64     0x00247A20 - 0x00247AE4     Function:
                                                        Init_Optlang
0x00147B70 - 0x00147B78     0x00247AF0 - 0x00247AF8     Function:
                                                        GetBoolExist_spanish
0x00147B80 - 0x00147B88     0x00247B00 - 0x00247B08     Function:
                                                        GetBoolExist_italian
0x00147B90 - 0x00147B98     0x00247B10 - 0x00247B18     Function:
                                                        GetBoolExist_german
0x00147BA0 - 0x00147BA8     0x00247B20 - 0x00247B28     Function:
                                                        GetBoolExist_french
0x00147BB0 - 0x00147BB8     0x00247B30 - 0x00247B38     Function:
                                                        GetBoolExist_english
0x00147BC0 - 0x00147D20     0x00247B40 - 0x00247CA0     Function:
                                                        EdsBox4SetRGBA
0x00147D20 - 0x00147DC8     0x00247CA0 - 0x00247D48     Function:
                                                        EdsBoxSetWH
0x00147DD0 - 0x00147E00     0x00247D50 - 0x00247D80     Function:
                                                        EdsBoxSetY
0x00147E00 - 0x00147E48     0x00247D80 - 0x00247DC8     Function:
                                                        EdsBoxSetXY
0x00147E50 - 0x00147F08     0x00247DD0 - 0x00247E88     Function:
                                                        EdsBoxSetRGBAnime
0x00147F10 - 0x00147F70     0x00247E90 - 0x00247EF0     Function:
                                                        EdsBoxSetType
0x00147F70 - 0x00148080     0x00247EF0 - 0x00248000     Function:
                                                        EdsBoxSetMode
0x00148080 - 0x00148820     0x00248000 - 0x002487A0     Function:
                                                        EdsBoxRGBAnime
0x00148820 - 0x00148930     0x002487A0 - 0x002488B0     Function:
                                                        EdsBoxOpenCloseMove
0x00148930 - 0x00148E38     0x002488B0 - 0x00248DB8     Function:
                                                        EdsBoxDisp
0x00148E40 - 0x00148E48     0x00248DC0 - 0x00248DC8     Function:
                                                        EdsBoxDestroy
0x00148E50 - 0x00148F08     0x00248DD0 - 0x00248E88     Function:
                                                        EdsBoxClose
0x00148F10 - 0x00148F30     0x00248E90 - 0x00248EB0     Function:
                                                        EdsBoxMain
0x00148F30 - 0x00149000     0x00248EB0 - 0x00248F80     Function:
                                                        EdsBoxOpen
0x00149000 - 0x00149008     0x00248F80 - 0x00248F88     Function:
                                                        EdsBoxSet
0x00149010 - 0x00149098     0x00248F90 - 0x00249018     Function:
                                                        EdsBoxGetInit
0x001490A0 - 0x001491AC     0x00249020 - 0x0024912C     Function:
                                                        EdsBoxFunc
0x001491B0 - 0x001491BC     0x00249130 - 0x0024913C     Function:
                                                        EdsBoxAllInit
0x00150750 - 0x001508DC     0x002506D0 - 0x0025085C     Function:
                                                        csStaffRollSdMain
0x001508E0 - 0x00150928     0x00250860 - 0x002508A8     Function:
                                                        csStaffRollDecode
0x00150930 - 0x00150944     0x002508B0 - 0x002508C4     Function:
                                                        csStaffRollGetBinAddr
0x00150950 - 0x00150A0C     0x002508D0 - 0x0025098C     Function:
                                                        csStaffRollBinaryRead
0x00150A10 - 0x00150A18     0x00250990 - 0x00250998     Function:
                                                        csStaffRollBinaryReadInit
0x00150A20 - 0x00150A44     0x002509A0 - 0x002509C4     Function:
                                                        csStaffRollFinish
0x00150A50 - 0x001510D0     0x002509D0 - 0x00251050     Function:
                                                        csStaffRollStep
0x001510D0 - 0x00151100     0x00251050 - 0x00251080     Function:
                                                        csStaffRollInit
0x00151100 - 0x00151128     0x00251080 - 0x002510A8     Function:
                                                        mesGetCancel
0x00151130 - 0x00151158     0x002510B0 - 0x002510D8     Function:
                                                        mesGetOk
0x00151160 - 0x001511A4     0x002510E0 - 0x00251124     Function:
                                                        mesGetLanguage01
0x001511B0 - 0x00151214     0x00251130 - 0x00251194     Function:
                                                        LesWinSetType
0x00151220 - 0x0015133C     0x002511A0 - 0x002512BC     Function:
                                                        LesWinSetMode
0x00151340 - 0x00151420     0x002512C0 - 0x002513A0     Function:
                                                        LesWinSetDefaultPartsWH
0x00151420 - 0x00151500     0x002513A0 - 0x00251480     Function:
                                                        LesWinDefaultAllSet
0x00151500 - 0x001517A0     0x00251480 - 0x00251720     Function:
                                                        LesWinXYWHMove
0x001517A0 - 0x00151E70     0x00251720 - 0x00251DF0     Function:
                                                        LesWinDisp
0x00151E70 - 0x00151ECC     0x00251DF0 - 0x00251E4C     Function:
                                                        LesWinDestroy
0x00151ED0 - 0x001520B0     0x00251E50 - 0x00252030     Function:
                                                        LesWinClose
0x001520B0 - 0x001520B8     0x00252030 - 0x00252038     Function:
                                                        LesWinMain
0x001520C0 - 0x001522D0     0x00252040 - 0x00252250     Function:
                                                        LesWinOpen
0x001522D0 - 0x001522DC     0x00252250 - 0x0025225C     Function:
                                                        LesWinSet
0x001522E0 - 0x0015233C     0x00252260 - 0x002522BC     Function:
                                                        LesWinGetInit
0x00152340 - 0x00152400     0x002522C0 - 0x00252380     Function:
                                                        LesWinFunc
0x00152400 - 0x001526D8     0x00252380 - 0x00252658     Function:
                                                        marker_anime_disp
0x001526E0 - 0x00152724     0x00252660 - 0x002526A4     Function:
                                                        marker_anime_set_ct
0x00152730 - 0x00152750     0x002526B0 - 0x002526D0     Function:
                                                        marker_anime_reset
0x00152750 - 0x0015276C     0x002526D0 - 0x002526EC     Function:
                                                        marker_anime_set
0x00152770 - 0x00152DEC     0x002526F0 - 0x00252D6C     Function:
                                                        back_anime_disp
0x00152DF0 - 0x00152DF8     0x00252D70 - 0x00252D78     Function:
                                                        back_anime_finish
0x00152E00 - 0x00152ED4     0x00252D80 - 0x00252E54     Function:
                                                        back_anime_step
0x00152EE0 - 0x00153038     0x00252E60 - 0x00252FB8     Function:
                                                        back_anime_init
0x00153040 - 0x00153050     0x00252FC0 - 0x00252FD0     Function:
                                                        back_anime_set_flash_id
0x00153050 - 0x00153060     0x00252FD0 - 0x00252FE0     Function:
                                                        back_anime_set_inst_mode
0x00153060 - 0x00153090     0x00252FE0 - 0x00253010     Function:
                                                        back_anime_set_normal_anime
0x00153090 - 0x00153114     0x00253010 - 0x00253094     Function:
                                                        back_anime_set_anime
0x00153120 - 0x00153190     0x002530A0 - 0x00253110     Function:
                                                        back_anime_init_can
0x00153190 - 0x0015325C     0x00253110 - 0x002531DC     Function:
                                                        down_load_anime
0x00153260 - 0x00153268     0x002531E0 - 0x002531E8     Function:
                                                        play_anime_finish
0x00153270 - 0x001535E4     0x002531F0 - 0x00253564     Function:
                                                        play_anime_step
0x001535F0 - 0x00153630     0x00253570 - 0x002535B0     Function:
                                                        play_anime_init
0x00153630 - 0x00153640     0x002535B0 - 0x002535C0     Function:
                                                        play_anime_set_inst_mode
0x00153640 - 0x0015364C     0x002535C0 - 0x002535CC     Function:
                                                        SetBeginnerFlg2p
0x00153650 - 0x0015365C     0x002535D0 - 0x002535DC     Function:
                                                        SetBeginnerFlg1p
0x00153660 - 0x001536C8     0x002535E0 - 0x00253648     Function:
                                                        sysReadAnimeWait2
0x001536D0 - 0x00153730     0x00253650 - 0x002536B0     Function:
                                                        sysReadAnimeInit2
0x00153730 - 0x00153898     0x002536B0 - 0x00253818     Function:
                                                        csStaffRollScrlDrawFunc_Copyright
0x001538A0 - 0x00153A40     0x00253820 - 0x002539C0     Function:
                                                        csStaffRollScrlDrawFunc_Toemi
0x00153A40 - 0x00153BE0     0x002539C0 - 0x00253B60     Function:
                                                        csStaffRollScrlDrawFunc_Xax
0x00153BE0 - 0x00153DD0     0x00253B60 - 0x00253D50     Function:
                                                        csStaffRollScrlDrawFunc_Konami
0x00153DD0 - 0x00153DEC     0x00253D50 - 0x00253D6C     Function:
                                                        csStaffRollScrlDrawFunc_Name
0x00153DF0 - 0x00153E34     0x00253D70 - 0x00253DB4     Function:
                                                        csStaffRollScrlDrawFunc_Title
0x00153E40 - 0x00153F7C     0x00253DC0 - 0x00253EFC     Function:
                                                        csStaffRollScrlAct
0x00153F80 - 0x001540BC     0x00253F00 - 0x0025403C     Function:
                                                        csStaffRollScrlMain
0x001540C0 - 0x001541A4     0x00254040 - 0x00254124     Function:
                                                        csStaffRollScrlReadFont
0x001541B0 - 0x0015424C     0x00254130 - 0x002541CC     Function:
                                                        csStaffRollScrlInit
0x00154250 - 0x0015425C     0x002541D0 - 0x002541DC     Function:
                                                        csStaffRollFadeCheck
0x00154260 - 0x001542EC     0x002541E0 - 0x0025426C     Function:
                                                        csStaffRollFadeDraw
0x001542F0 - 0x001544D0     0x00254270 - 0x00254450     Function:
                                                        csStaffRollFadeAct
0x001544D0 - 0x00154698     0x00254450 - 0x00254618     Function:
                                                        csStaffRollFadeStart
0x001546A0 - 0x001546B0     0x00254620 - 0x00254630     Function:
                                                        csStaffRollFadeInit
0x001546B0 - 0x001546B8     0x00254630 - 0x00254638     Function:
                                                        csStaffRollPicGetBase
0x001546C0 - 0x001546C8     0x00254640 - 0x00254648     Function:
                                                        csStaffRollPicGetBaseFO
0x001546D0 - 0x00154770     0x00254650 - 0x002546F0     Function:
                                                        csStaffRollPicActBaseFO
0x00154770 - 0x00154810     0x002546F0 - 0x00254790     Function:
                                                        csStaffRollPicActBaseFI
0x00154810 - 0x00154958     0x00254790 - 0x002548D8     Function:
                                                        csStaffRollPicDraw_Noise
0x00154960 - 0x00154C88     0x002548E0 - 0x00254C08     Function:
                                                        csStaffRollPicDraw_Picture
0x00154C90 - 0x0015542C     0x00254C10 - 0x002553AC     Function:
                                                        csStaffRollPicDraw
0x00155430 - 0x00155904     0x002553B0 - 0x00255884     Function:
                                                        csStaffRollPicComFunc_OverLapZO
0x00155910 - 0x00155C94     0x00255890 - 0x00255C14     Function:
                                                        csStaffRollPicComFunc_OverLap
0x00155CA0 - 0x001560D4     0x00255C20 - 0x00256054     Function:
                                                        csStaffRollPicComFunc_FadeOutFadeIn
0x001560E0 - 0x00156330     0x00256060 - 0x002562B0     Function:
                                                        csStaffRollPicComFunc_FadeOut
0x00156330 - 0x00156668     0x002562B0 - 0x002565E8     Function:
                                                        csStaffRollPicComFunc_FadeIn
0x00156670 - 0x00156838     0x002565F0 - 0x002567B8     Function:
                                                        csStaffRollPicComFunc_CepiaFO
0x00156840 - 0x00156908     0x002567C0 - 0x00256888     Function:
                                                        csStaffRollPicComFunc_CepiaSw
0x00156910 - 0x001569C0     0x00256890 - 0x00256940     Function:
                                                        csStaffRollPicComFunc_Wait
0x001569C0 - 0x001569C8     0x00256940 - 0x00256948     Function:
                                                        csStaffRollPicComFunc_Terminate
0x001569D0 - 0x001569E4     0x00256950 - 0x00256964     Function:
                                                        csStaffRollPicComFunc_Init
0x001569F0 - 0x00156A98     0x00256970 - 0x00256A18     Function:
                                                        csStaffRollPicMain
0x00156AA0 - 0x00156C44     0x00256A20 - 0x00256BC4     Function:
                                                        csStaffRollPicInit
0x00156C50 - 0x00156C68     0x00256BD0 - 0x00256BE8     Function:
                                                        csStaffRollPicStepInit
0x00156C70 - 0x00156CDC     0x00256BF0 - 0x00256C5C     Function:
                                                        a_make
0x00156CE0 - 0x00156D68     0x00256C60 - 0x00256CE8     Function:
                                                        rgb_make
0x00156D70 - 0x00156E2C     0x00256CF0 - 0x00256DAC     Function:
                                                        xyz_make
0x00156E30 - 0x00156E3C     0x00256DB0 - 0x00256DBC     Function:
                                                        ps2dancerSetUnison
0x00156E40 - 0x00156E4C     0x00256DC0 - 0x00256DCC     Function:
                                                        ps2dancerSetFloor
0x00156E50 - 0x00156E5C     0x00256DD0 - 0x00256DDC     Function:
                                                        ps2dancerSetToon
0x00156E60 - 0x00156E8C     0x00256DE0 - 0x00256E0C     Function:
                                                        ps2dancerSetPlayCounter
0x00156E90 - 0x00156EC4     0x00256E10 - 0x00256E44     Function:
                                                        ps2dancerSetAllPlayCounter
0x00156ED0 - 0x00157034     0x00256E50 - 0x00256FB4     Function:
                                                        ps2dancerAdjPos
0x00157040 - 0x001573DC     0x00256FC0 - 0x0025735C     Function:
                                                        draw_floor
0x001573E0 - 0x001574A4     0x00257360 - 0x00257424     Function:
                                                        get_floor_cull
0x001574B0 - 0x00157570     0x00257430 - 0x002574F0     Function:
                                                        clear_zbuf
0x00157570 - 0x00157A20     0x002574F0 - 0x002579A0     Function:
                                                        ps2dancerDispStep
0x00157A20 - 0x00157A48     0x002579A0 - 0x002579C8     Function:
                                                        get_chara_hide
0x00157A50 - 0x00157A74     0x002579D0 - 0x002579F4     Function:
                                                        get_chara_lst_id
0x00157A80 - 0x00157AA0     0x00257A00 - 0x00257A20     Function:
                                                        get_shadow_bri
0x00157AA0 - 0x00157AC8     0x00257A20 - 0x00257A48     Function:
                                                        get_edge_info
0x00157AD0 - 0x00157AF0     0x00257A50 - 0x00257A70     Function:
                                                        ps2dancerGetName
0x00157AF0 - 0x00157B14     0x00257A70 - 0x00257A94     Function:
                                                        get_dancer_default_mot
0x00157B20 - 0x00157B7C     0x00257AA0 - 0x00257AFC     Function:
                                                        rnd_get_dancer_mot
0x00157B80 - 0x00157BA0     0x00257B00 - 0x00257B20     Function:
                                                        get_primdt_tbl
0x00157BA0 - 0x00157BC0     0x00257B20 - 0x00257B40     Function:
                                                        get_dancer_scale
0x00157BC0 - 0x00157BD8     0x00257B40 - 0x00257B58     Function:
                                                        get_mdt_name
0x00157BE0 - 0x00157BF8     0x00257B60 - 0x00257B78     Function:
                                                        get_cdt_name
0x00157C00 - 0x00157C40     0x00257B80 - 0x00257BC0     Function:
                                                        CreateRotMatrixX
0x00157C40 - 0x00157C80     0x00257BC0 - 0x00257C00     Function:
                                                        CreateRotMatrixZ
0x00157C80 - 0x00157CC0     0x00257C00 - 0x00257C40     Function:
                                                        CreateRotMatrixY
0x00157CC0 - 0x00157DDC     0x00257C40 - 0x00257D5C     Function:
                                                        convert_matrix_ps2dx
0x00157DE0 - 0x00157F00     0x00257D60 - 0x00257E80     Function:
                                                        convert_matrix_dx2ps
0x00157F00 - 0x00157F78     0x00257E80 - 0x00257EF8     Function:
                                                        NMDPrsetPacketGT3
0x00157F80 - 0x00157FE0     0x00257F00 - 0x00257F60     Function:
                                                        NMDPrsetPacketG3
0x00157FE0 - 0x0015808C     0x00257F60 - 0x0025800C     Function:
                                                        NMDPresetObject
0x00158090 - 0x00158160     0x00258010 - 0x002580E0     Function:
                                                        NMDMapModelingData
0x00158160 - 0x0015839C     0x002580E0 - 0x0025831C     Function:
                                                        dancer_model_setup
0x001583A0 - 0x00158740     0x00258320 - 0x002586C0     Function:
                                                        NormCulcG3US
0x00158740 - 0x00158ACC     0x002586C0 - 0x00258A4C     Function:
                                                        NormCulcG3U
0x00158AD0 - 0x00158F28     0x00258A50 - 0x00258EA8     Function:
                                                        VertCulcU
0x00158F30 - 0x00159268     0x00258EB0 - 0x002591E8     Function:
                                                        drawGT3
0x00159270 - 0x00159584     0x002591F0 - 0x00259504     Function:
                                                        drawGT3L
0x00159590 - 0x0015976C     0x00259510 - 0x002596EC     Function:
                                                        drawG3core
0x00159770 - 0x00159954     0x002596F0 - 0x002598D4     Function:
                                                        drawG3L
0x00159960 - 0x00159CEC     0x002598E0 - 0x00259C6C     Function:
                                                        NMDSortObject5
0x00159CF0 - 0x00159F18     0x00259C70 - 0x00259E98     Function:
                                                        nmd_model_disp
0x00159F20 - 0x0015A19C     0x00259EA0 - 0x0025A11C     Function:
                                                        draw_dancer_model
0x0015A1A0 - 0x0015A2EC     0x0025A120 - 0x0025A26C     Function:
                                                        PsGsGetLs
0x0015A2F0 - 0x0015A4F8     0x0025A270 - 0x0025A478     Function:
                                                        pre_draw_dancer_model
0x0015A500 - 0x0015A6E0     0x0025A480 - 0x0025A660     Function:
                                                        set_dance_motion_pack_tab
0x0015A6E0 - 0x0015A798     0x0025A660 - 0x0025A718     Function:
                                                        get_dance_mpack
0x0015A7A0 - 0x0015AD2C     0x0025A720 - 0x0025ACAC     Function:
                                                        set_dance_motion
0x0015AD30 - 0x0015B09C     0x0025ACB0 - 0x0025B01C     Function:
                                                        init_dance_motion
0x0015B0A0 - 0x0015B2D0     0x0025B020 - 0x0025B250     Function:
                                                        dancer_motion_setup
0x0015B2D0 - 0x0015B6FC     0x0025B250 - 0x0025B67C     Function:
                                                        decodeMimeParam
0x0015B700 - 0x0015B914     0x0025B680 - 0x0025B894     Function:
                                                        mimeAnimation_local
0x0015B920 - 0x0015BBC8     0x0025B8A0 - 0x0025BB48     Function:
                                                        mimeAnimation
0x0015BBD0 - 0x0015BD10     0x0025BB50 - 0x0025BC90     Function:
                                                        decodeRotateFormat
0x0015BD10 - 0x0015BEFC     0x0025BC90 - 0x0025BE7C     Function:
                                                        decodeVectorFormat
0x0015BF00 - 0x0015C010     0x0025BE80 - 0x0025BF90     Function:
                                                        decodeBody
0x0015C010 - 0x0015C334     0x0025BF90 - 0x0025C2B4     Function:
                                                        decodeAnimation
0x0015C340 - 0x0015C4A4     0x0025C2C0 - 0x0025C424     Function:
                                                        dancer_motion_decode
0x0015C4B0 - 0x0015C52C     0x0025C430 - 0x0025C4AC     Function:
                                                        LoadAverageShort12
0x0015C530 - 0x0015C5E8     0x0025C4B0 - 0x0025C568     Function:
                                                        VectorNormalSS
0x0015C5F0 - 0x0015C684     0x0025C570 - 0x0025C604     Function:
                                                        OuterProduct12
0x0015C690 - 0x0015C6F0     0x0025C610 - 0x0025C670     Function:
                                                        TransposeMatrix
0x0015C6F0 - 0x0015C744     0x0025C670 - 0x0025C6C4     Function:
                                                        ps1rcos
0x0015C750 - 0x0015C7A4     0x0025C6D0 - 0x0025C724     Function:
                                                        ps1rsin
0x0015C7B0 - 0x0015CAF8     0x0025C730 - 0x0025CA78     Function:
                                                        PsRotMatrix
0x0015CB00 - 0x0015CB98     0x0025CA80 - 0x0025CB18     Function:
                                                        GsInitCoordinate2
0x0015CBA0 - 0x0015CBC8     0x0025CB20 - 0x0025CB48     Function:
                                                        dist3d
0x0015CBD0 - 0x0015CBEC     0x0025CB50 - 0x0025CB6C     Function:
                                                        frd
0x0015CBF0 - 0x0015CD78     0x0025CB70 - 0x0025CCF8     Function:
                                                        gs3dSetRenderUnitMatrix
0x0015CD80 - 0x0015CF0C     0x0025CD00 - 0x0025CE8C     Function:
                                                        gs3dSetRenderMatrix
0x0015CF10 - 0x0015CF84     0x0025CE90 - 0x0025CF04     Function:
                                                        gs3dSetFrustum
0x0015CF90 - 0x0015CFF8     0x0025CF10 - 0x0025CF78     Function:
                                                        gs3dSetLightMatrix
0x0015D000 - 0x0015D1D0     0x0025CF80 - 0x0025D150     Function:
                                                        gs3dEnd
0x0015D1D0 - 0x0015D220     0x0025D150 - 0x0025D1A0     Function:
                                                        gs3dTexture
0x0015D220 - 0x0015D26C     0x0025D1A0 - 0x0025D1EC     Function:
                                                        gs3dColor
0x0015D270 - 0x0015D2D0     0x0025D1F0 - 0x0025D250     Function:
                                                        gs3dVertex
0x0015D2D0 - 0x0015D3B0     0x0025D250 - 0x0025D330     Function:
                                                        gs3dBegin
0x0015D3B0 - 0x0015D3D4     0x0025D330 - 0x0025D354     Function:
                                                        gs3dSetLightAmbient
0x0015D3E0 - 0x0015D418     0x0025D360 - 0x0025D398     Function:
                                                        gs3dSetLightVector
0x0015D420 - 0x0015D458     0x0025D3A0 - 0x0025D3D8     Function:
                                                        gs3dSetLightColor
0x0015D460 - 0x0015D508     0x0025D3E0 - 0x0025D488     Function:
                                                        gsInit3d
0x0015D510 - 0x0015D618     0x0025D490 - 0x0025D598     Function:
                                                        gxRenderVCT
0x0015D620 - 0x0015D718     0x0025D5A0 - 0x0025D698     Function:
                                                        gxRenderVC
0x0015D720 - 0x0015D868     0x0025D6A0 - 0x0025D7E8     Function:
                                                        gxRenderVNCT
0x0015D870 - 0x0015D87C     0x0025D7F0 - 0x0025D7FC     Function:
                                                        ps2dancerSetDebugCamera
0x0015D880 - 0x0015DE3C     0x0025D800 - 0x0025DDBC     Function:
                                                        camera_tst
0x0015DE40 - 0x0015DE54     0x0025DDC0 - 0x0025DDD4     Function:
                                                        ps2dancerSetCameraPos
0x0015DE60 - 0x0015DE6C     0x0025DDE0 - 0x0025DDEC     Function:
                                                        GetDancerCameraW
0x0015DE70 - 0x0015E0E4     0x0025DDF0 - 0x0025E064     Function:
                                                        camera_ero
0x0015E0F0 - 0x0015E4B8     0x0025E070 - 0x0025E438     Function:
                                                        camera_roll
0x0015E4C0 - 0x0015E890     0x0025E440 - 0x0025E810     Function:
                                                        camera_s03
0x0015E890 - 0x0015E9F0     0x0025E810 - 0x0025E970     Function:
                                                        camera_s02
0x0015E9F0 - 0x0015EC34     0x0025E970 - 0x0025EBB4     Function:
                                                        camera_s01
0x0015EC40 - 0x0015EE0C     0x0025EBC0 - 0x0025ED8C     Function:
                                                        change_camera_type
0x0015EE10 - 0x0015F10C     0x0025ED90 - 0x0025F08C     Function:
                                                        ps2dancerCameraStep
0x0015F110 - 0x0015F1C0     0x0025F090 - 0x0025F140     Function:
                                                        ps2dancerCameraPreStep
0x0015F1C0 - 0x0015F2CC     0x0025F140 - 0x0025F24C     Function:
                                                        ps2dancerCameraInit
0x0015F2D0 - 0x0015F494     0x0025F250 - 0x0025F414     Function:
                                                        csStaffRollMovieDrawFilter
0x0015F4A0 - 0x0015F93C     0x0025F420 - 0x0025F8BC     Function:
                                                        csStaffRollMovieDraw
0x0015F940 - 0x0015FAFC     0x0025F8C0 - 0x0025FA7C     Function:
                                                        csStaffRollMovieRead
0x0015FB00 - 0x0015FCF8     0x0025FA80 - 0x0025FC78     Function:
                                                        csStaffRollMovieMain
0x0015FD00 - 0x0015FD28     0x0025FC80 - 0x0025FCA8     Function:
                                                        csStaffRollMovieInit
0x0015FD30 - 0x0015FFDC     0x0025FCB0 - 0x0025FF5C     Function:
                                                        csStaffRollStrDraw
0x0015FFE0 - 0x0016001C     0x0025FF60 - 0x0025FF9C     Function:
                                                        csStaffRollFontInit
0x00160020 - 0x00160500     0x0025FFA0 - 0x00260480     Function:
                                                        modeltest
0x00160500 - 0x001605A0     0x00260480 - 0x00260520     Function:
                                                        Update_OptDoll
0x001605A0 - 0x00160B38     0x00260520 - 0x00260AB8     Function:
                                                        View_OptDoll
0x00160B40 - 0x00160C70     0x00260AC0 - 0x00260BF0     Function:
                                                        control_lr
0x00160C70 - 0x00161278     0x00260BF0 - 0x002611F8     Function:
                                                        Control_OptDoll
0x00161280 - 0x001613EC     0x00261200 - 0x0026136C     Function:
                                                        Init_OptDoll
0x001613F0 - 0x001613F8     0x00261370 - 0x00261378     Function:
                                                        GetBoolExist_exit
0x00161400 - 0x00161430     0x00261380 - 0x002613B0     Function:
                                                        GetBoolExist_3p
0x00161430 - 0x00161444     0x002613B0 - 0x002613C4     Function:
                                                        GetBoolExist_2p
0x00161450 - 0x00161464     0x002613D0 - 0x002613E4     Function:
                                                        GetBoolExist_1p
0x00161470 - 0x001614A0     0x002613F0 - 0x00261420     Function:
                                                        GetBoolExist_guest
0x001614A0 - 0x001614A8     0x00261420 - 0x00261428     Function:
                                                        GetBoolExist_disp
0x001614B0 - 0x001614D8     0x00261430 - 0x00261458     Function:
                                                        Update_Openinglogo
0x001614E0 - 0x00161608     0x00261460 - 0x00261588     Function:
                                                        View_Openinglogo
0x00161610 - 0x00161774     0x00261590 - 0x002616F4     Function:
                                                        Control_Openinglogo
0x00161780 - 0x001617FC     0x00261700 - 0x0026177C     Function:
                                                        Init_Openinglogo
0x00161800 - 0x001618DC     0x00261780 - 0x0026185C     Function:
                                                        dietprogram_load_tex_step
0x001618E0 - 0x001618F4     0x00261860 - 0x00261874     Function:
                                                        dietprogram_load_tex_init
0x00161900 - 0x00161920     0x00261880 - 0x002618A0     Function:
                                                        dietprogram_init
0x00161920 - 0x00161A08     0x002618A0 - 0x00261988     Function:
                                                        ps2dancerExHide2MBentry
0x00161A10 - 0x00161C1C     0x00261990 - 0x00261B9C     Function:
                                                        ps2dancerExHideCheck
0x00161C20 - 0x00161D2C     0x00261BA0 - 0x00261CAC     Function:
                                                        ps2dancerUnHideRnd
0x00161D30 - 0x00161D78     0x00261CB0 - 0x00261CF8     Function:
                                                        ps2dancerSetDefaultCharaInfo
0x00161D80 - 0x00161DE8     0x00261D00 - 0x00261D68     Function:
                                                        ps2dancerInitHide
0x00161DF0 - 0x00161E60     0x00261D70 - 0x00261DE0     Function:
                                                        ps2dancerGetDollListForOPT
0x00161E60 - 0x00161FB8     0x00261DE0 - 0x00261F38     Function:
                                                        ps2dancerGetDollList
0x00161FC0 - 0x001620B4     0x00261F40 - 0x00262034     Function:
                                                        typical_entry
0x001620C0 - 0x001620E4     0x00262040 - 0x00262064     Function:
                                                        ps2dancerReChoiceChara
0x001620F0 - 0x0016211C     0x00262070 - 0x0026209C     Function:
                                                        ps2dancerTypicalInit
0x00162120 - 0x001622E4     0x002620A0 - 0x00262264     Function:
                                                        RecNonstopLoadData
0x001622F0 - 0x00162538     0x00262270 - 0x002624B8     Function:
                                                        Update_Recnon
0x00162540 - 0x00162670     0x002624C0 - 0x002625F0     Function:
                                                        View_Recnon
0x00162670 - 0x00162748     0x002625F0 - 0x002626C8     Function:
                                                        Control_Recnon
0x00162750 - 0x00162888     0x002626D0 - 0x00262808     Function:
                                                        Init_Recnon
0x00162890 - 0x00162BD0     0x00262810 - 0x00262B50     Function:
                                                        draw_ope
0x00162BD0 - 0x00162DE0     0x00262B50 - 0x00262D60     Function:
                                                        draw_dir_arrow
0x00162DE0 - 0x001630C8     0x00262D60 - 0x00263048     Function:
                                                        draw_cursor
0x001630D0 - 0x00163D60     0x00263050 - 0x00263CE0     Function:
                                                        draw_table
0x00163D60 - 0x001640E4     0x00263CE0 - 0x00264064     Function:
                                                        draw_detail_data
0x001640F0 - 0x001642C8     0x00264070 - 0x00264248     Function:
                                                        puts_combo
0x001642D0 - 0x001644A4     0x00264250 - 0x00264424     Function:
                                                        puts_non_re2424
0x001644B0 - 0x00164B24     0x00264430 - 0x00264AA4     Function:
                                                        control_loop
0x00164B30 - 0x00164C78     0x00264AB0 - 0x00264BF8     Function:
                                                        control_delete
0x00164C80 - 0x00164D9C     0x00264C00 - 0x00264D1C     Function:
                                                        SetDelStep
0x00164DA0 - 0x00164E38     0x00264D20 - 0x00264DB8     Function:
                                                        check_move_cursor
0x00164E40 - 0x00164FF8     0x00264DC0 - 0x00264F78     Function:
                                                        set_data_scroll
0x00165000 - 0x001650E0     0x00264F80 - 0x00265060     Function:
                                                        update_data
0x001650E0 - 0x0016517C     0x00265060 - 0x002650FC     Function:
                                                        init_data
0x00165180 - 0x00165458     0x00265100 - 0x002653D8     Function:
                                                        init_nonstop_record
0x00165460 - 0x0016547C     0x002653E0 - 0x002653FC     Function:
                                                        req_info_doll_chara
0x00165480 - 0x0016548C     0x00265400 - 0x0026540C     Function:
                                                        req_info_doll_in
0x00165490 - 0x0016549C     0x00265410 - 0x0026541C     Function:
                                                        is_info_doll_loading
0x001654A0 - 0x001656F0     0x00265420 - 0x00265670     Function:
                                                        View_InfoDollDisp
0x001656F0 - 0x0016573C     0x00265670 - 0x002656BC     Function:
                                                        Init_InfoDollDisp
0x00165740 - 0x001657C8     0x002656C0 - 0x00265748     Function:
                                                        ps2dancerPdataLoadStep
0x001657D0 - 0x001657EC     0x00265750 - 0x0026576C     Function:
                                                        ps2dancerPdataLoadInit
0x001657F0 - 0x00165848     0x00265770 - 0x002657C8     Function:
                                                        ps2dancerGetOpenChrNum
0x00165850 - 0x00165888     0x002657D0 - 0x00265808     Function:
                                                        ps2dancerExistChara
0x00165890 - 0x00165AA4     0x00265810 - 0x00265A24     Function:
                                                        shape_mot_id
0x00165AB0 - 0x00165B78     0x00265A30 - 0x00265AF8     Function:
                                                        ps2dancerSetup
0x00165B80 - 0x00165FAC     0x00265B00 - 0x00265F2C     Function:
                                                        ps2dancerLoadStep
0x00165FB0 - 0x00166048     0x00265F30 - 0x00265FC8     Function:
                                                        get_free_motbuf
0x00166050 - 0x00166254     0x00265FD0 - 0x002661D4     Function:
                                                        ps2dancerLoadInit
0x00166260 - 0x001662E8     0x002661E0 - 0x00266268     Function:
                                                        ps2dancerEntry2
0x001662F0 - 0x00166388     0x00266270 - 0x00266308     Function:
                                                        ps2dancerEntry
0x00166390 - 0x0016646C     0x00266310 - 0x002663EC     Function:
                                                        auto_chara_select
0x00166470 - 0x00166488     0x002663F0 - 0x00266408     Function:
                                                        ps2dancerResetEntry
0x00166490 - 0x001664A0     0x00266410 - 0x00266420     Function:
                                                        ps2dancerBreakDataArea
0x001664A0 - 0x00166568     0x00266420 - 0x002664E8     Function:
                                                        ps2dancerInit
</pre>
