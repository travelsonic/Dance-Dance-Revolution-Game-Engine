Note: This document is far from complete. 

For the purpose of this document, "physical address" will refer to the address of the data / information in the game's executable, and the logical address will refer to where the information resides from the perspective of the Playstation2, a Playstation2 emulator, and many reverse engineering tools like IDA Pro, Ghidra, and PS2DIS.

The difference between physical and logical addresses is 0xFFF80

<pre>
Physical Address(es):       Logical Address(es):        Description: 
0x000B3DB0 - 0x000B3DBC     0x001B3D30 - 0x001B3D3C     Function:
                                                        signed int sysGetDateNotation();
0x000B3DC0 - 0x000B3DF0     0x001B3D40 - 0x001B3D70     Function:
                                                        void sysInitScf(_tag_SYS_SCF_WORK* p);
0x000B3DF0 - 0x000B3DFC     0x001B3D70 - 0x001B3D7C     Function:
                                                        void sysDemoSetMainLoopBreakRequest(signed int val);
0x000B3E00 - 0x000B3E08     0x001B3D80 - 0x001B3D88     Function:
                                                        void sysDemoSet(_tag_SYS_DEMO_WORK* p);
0x000B3E10 - 0x000B42FC     0x001B3D90 - 0x001B427C     Function:
                                                        void setup_nonstop_option(signed int pid, signed int stage_num);
0x000B4300 - 0x000B4380     0x001B4280 - 0x001B4300     Function:
                                                        oni_mode* get_course_list_work(signed int id, signed int stage);
0x000B4380 - 0x000B454C     0x001B4300 - 0x001B44CC     Function:
                                                        signed int get_nonstop_best_record(signed int course, signed int type);
0x000B4550 - 0x000B471C     0x001B44D0 - 0x001B469C     Function:
                                                        signed int is_option_changed_this_course(signed int course, signed int index);
0x000B4720 - 0x000B47D0     0x001B46A0 - 0x001B4750     Function:
                                                        void set_course_real_stage_num(signed int id, signed int stage);
0x000B47D0 - 0x000B4838     0x001B4750 - 0x001B47B8     Function:
                                                        signed int get_course_real_stage_num(signed int id);  
0x000B4840 - 0x000B49F4     0x001B47C0 - 0x001B4974     Function:
                                                        signed int is_this_course_option_locked(signed int id);
0x000B4A00 - 0x000B4A78     0x001B4980 - 0x001B49F8     Function:
                                                        oni_mode* onimode_get_save_course(signed int id);
0x000B4A80 - 0x000B4B10     0x001B4A00 - 0x001B4A90     Function:
                                                        oni_course* onimode_get_save_order(signed int id);
0x000B4B10 - 0x000B4B38     0x001B4A90 - 0x001B4AB8     Function:
                                                        oni_course* onimode_get_course_list(signed int id);
0x000B4B40 - 0x000B4D9C     0x001B4AC0 - 0x001B4D1C     Function:
                                                        void onimode_get_order_mode(signed int id, signed int stage_num);
0x000B4DA0 - 0x000B4DD8     0x001B4D20 - 0x001B4D58     Function:
                                                        signed int onimode_is_course_order(signed int id);
0x000B4DE0 - 0x000B53C8     0x001B4D60 - 0x001B5348     Function:
                                                        void onimode_order_setup(); 
0x000B53D0 - 0x000B5628     0x001B5350 - 0x001B55A8     Function:
                                                        void onimode_random_setup_patch_for_easy();
0x000B5630 - 0x000B6528     0x001B55B0 - 0x001B64A8     Function:
                                                        void onimode_random_setup();
0x000B6530 - 0x000B6658     0x001B64B0 - 0x001B65D8     Function:
                                                        void onimode_set_linknum(signed int id, signed int stage, music_info* mip);
0x000B6660 - 0x000B66A4     0x001B65E0 - 0x001B6624     Function:
                                                        signed int onimode_ta_load(signed int id);
0x000B66B0 - 0x000B6718     0x001B6630 - 0x001B6698     Function:
                                                        signed int onimode_get_real_stage_num(signed int id);
0x000B6720 - 0x000B6770     0x001B66A0 - 0x001B66F0     Function:
                                                        signed int onimode_get_stage_allnum(signed int id);
0x000B6770 - 0x000B67C0     0x001B66F0 - 0x001B6740     Function:
                                                        signed int onimode_get_stage_num(signed int id);
0x000B67C0 - 0x000B6918     0x001B6740 - 0x001B6898     Function:
                                                        signed int onimode_set_playmode(signed int stage_num, signed int mode);
0x000B6920 - 0x000B6990     0x001B68A0 - 0x001B6910     Function:
                                                        signed int onimode_get_add_life(signed int stage_num);
0x000B6990 - 0x000B6AD8     0x001B6910 - 0x001B6A58     Function:
                                                        void onimode_set_seqkind(signed int id, signed int stage_num, signed int kind);
0x000B6AE0 - 0x000B6B88     0x001B6A60 - 0x001B6B08     Function:
                                                        signed int onimode_get_seqkind(signed int stage_num, signed int mode);
0x000B6B90 - 0x000B6F30     0x001B6B10 - 0x001B6EB0     Function:
                                                        void onimode_set_course_difficulty(signed int id, signed int mode);
0x000B6F30 - 0x000B6FFC     0x001B6EB0 - 0x001B6F7C     Function:
                                                        music_info* onimode_get_disp_mip(signed int id, signed int stage_num);
0x000B7000 - 0x000B70DC     0x001B6F80 - 0x001B705C     Function:
                                                        music_info* onimode_get_mip(signed int stage_num);
0x000B70E0 - 0x000B7128     0x001B7060 - 0x001B70A8     Function:
                                                        signed int onimode_get_steps(signed int style);
0x000B7130 - 0x000B74E8     0x001B70B0 - 0x001B7468     Function:
                                                        void onimode_set_steps();
0x000B74F0 - 0x000B7540     0x001B7470 - 0x001B74C0     Function:
                                                        signed int onimode_get_start_life();
0x000B7540 - 0x000B7590     0x001B74C0 - 0x001B7510     Function:
                                                        signed int onimode_get_irid(signed int id, signed int mode);
0x000B7590 - 0x000B7844     0x001B7510 - 0x001B77C4     Function:
                                                        signed int onimode_course_load(signed int id);
0x000B7850 - 0x000B7890     0x001B77D0 - 0x001B7810     Function:
                                                        signed int onimode_is_course_data(signed int id);
0x000B7890 - 0x000B7974     0x001B7810 - 0x001B78F4     Function:
                                                        void onimode_boot();
0x000B7980 - 0x000B79E0     0x001B7900 - 0x001B7960     Function:
                                                        _tag_cMusicData* GetMusicData_by_link_num(unsigned short link_num);
0x000B79E0 - 0x000B7A78     0x001B7960 - 0x001B79F8     Function:
                                                        _tag_cMusicData* GetMusicData_by_base_name(unsigned char* base_name);
0x000B7A80 - 0x000B7AB0     0x001B7A00 - 0x001B7A30     Function:
                                                        _tag_cMusicData* GetMusicData_by_index(signed int id);
0x000B7AB0 - 0x000B7AE4     0x001B7A30 - 0x001B7A64     Function:
                                                        signed int sysWaitMusicBk();
0x000B7AF0 - 0x000B7B30     0x001B7A70 - 0x001B7AB0     Function:
                                                        signed int sysSetMusicBk(unsigned int* load_addr, signed int id);
0x000C47A0 - 0x000C47E4     0x001C4720 - 0x001C4764     Function:
                                                        mesGetLanguage01
0x000C47F0 - 0x000C4DB0     0x001C4770 - 0x001C4D30     Function:
                                                        freeze_eff_disp
0x000C4DB0 - 0x000C4DBC     0x001C4D30 - 0x001C4D3C     Function:
                                                        freeze_eff_off
0x000C4DC0 - 0x000C4DD0     0x001C4D40 - 0x001C4D50     Function:
                                                        freeze_eff_on
0x000C4DD0 - 0x000C4DF0     0x001C4D50 - 0x001C4D70     Function:
                                                        freeze_eff_set
0x000C4DF0 - 0x000C50C8     0x001C4D70 - 0x001C5048     Function:
                                                        marker_anime_disp
0x000C50D0 - 0x000C5114     0x001C5050 - 0x001C5094     Function:
                                                        marker_anime_set_ct
0x000C5120 - 0x000C5140     0x001C50A0 - 0x001C50C0     Function:
                                                        marker_anime_reset
0x000C5140 - 0x000C515C     0x001C50C0 - 0x001C50DC     Function:
                                                        marker_anime_set
0x000C5160 - 0x000C5750     0x001C50E0 - 0x001C56D0     Function:
                                                        back_anime_disp
0x000C5750 - 0x000C5758     0x001C56D0 - 0x001C56D8     Function:
                                                        back_anime_finish
0x000C5760 - 0x000C5834     0x001C56E0 - 0x001C57B4     Function:
                                                        back_anime_step
0x000C5840 - 0x000C59A4     0x001C57C0 - 0x001C5924     Function:
                                                        back_anime_init
0x000C59B0 - 0x000C59C0     0x001C5930 - 0x001C5940     Function:
                                                        back_anime_set_inst_mode
0x000C59C0 - 0x000C59F0     0x001C5940 - 0x001C5970     Function:
                                                        back_anime_set_normal_anime
0x000C59F0 - 0x000C5A74     0x001C5970 - 0x001C59F4     Function:
                                                        back_anime_set_anime
0x000C5A80 - 0x000C5AF0     0x001C5A00 - 0x001C5A70     Function:
                                                        back_anime_init_can
0x000C5AF0 - 0x000C5BBC     0x001C5A70 - 0x001C5B3C     Function:
                                                        down_load_anime
0x000C5BC0 - 0x000C5FDC     0x001C5B40 - 0x001C5F5C     Function:
                                                        play_anime_step_inst
0x000C5FE0 - 0x000C5FE8     0x001C5F60 - 0x001C5F68     Function:
                                                        play_anime_finish
0x000C5FF0 - 0x000C6494     0x001C5F70 - 0x001C6414     Function:
                                                        play_anime_step
0x000C64A0 - 0x000C64F8     0x001C6420 - 0x001C6478     Function:
                                                        play_anime_init
0x000C6500 - 0x000C6510     0x001C6480 - 0x001C6490     Function:
                                                        play_anime_set_inst_mode
0x000C6510 - 0x000C651C     0x001C6490 - 0x001C649C     Function:
                                                        SetBeginnerFlg2p
0x000C6520 - 0x000C652C     0x001C64A0 - 0x001C64AC     Function:
                                                        SetBeginnerFlg1p
0x000C6530 - 0x000C6598     0x001C64B0 - 0x001C6518     Function:
                                                        sysReadAnimeWait2
0x000C65A0 - 0x000C6600     0x001C6520 - 0x001C6580     Function:
                                                        sysReadAnimeInit2
0x000C6600 - 0x000C666C     0x001C6580 - 0x001C65EC     Function:
                                                        a_make
0x000C6670 - 0x000C66F8     0x001C65F0 - 0x001C6678     Function:
                                                        rgb_make
0x000C6700 - 0x000C67BC     0x001C6680 - 0x001C673C     Function:
                                                        xyz_make
0x000C67C0 - 0x000C67D4     0x001C6740 - 0x001C6754     Function:
                                                        ps2dancerSetPidBright
0x000C67E0 - 0x000C67EC     0x001C6760 - 0x001C676C     Function:
                                                        ps2dancerSetFloor
0x000C67F0 - 0x000C67FC     0x001C6770 - 0x001C677C     Function:
                                                        ps2dancerSetToon
0x000C6800 - 0x000C682C     0x001C6780 - 0x001C67AC     Function:
                                                        ps2dancerSetPlayCounter
0x000C6830 - 0x000C6864     0x001C67B0 - 0x001C67E4     Function:
                                                        ps2dancerSetAllPlayCounter
0x000C6870 - 0x000C69F4     0x001C67F0 - 0x001C6974     Function:
                                                        ps2dancerAdjPos
0x000C6A00 - 0x000C6D8C     0x001C6980 - 0x001C6D0C     Function:
                                                        draw_floor
0x000C6D90 - 0x000C6E54     0x001C6D10 - 0x001C6DD4     Function:
                                                        get_floor_cull
0x000C6E60 - 0x000C6F20     0x001C6DE0 - 0x001C6EA0     Function:
                                                        clear_zbuf
0x000C6F20 - 0x000C72D0     0x001C6EA0 - 0x001C7250     Function:
                                                        ps2dancerDispStep
0x000C72D0 - 0x000C72F8     0x001C7250 - 0x001C7278     Function:
                                                        get_chara_hide
0x000C7300 - 0x000C7324     0x001C7280 - 0x001C72A4     Function:
                                                        get_chara_lst_id
0x000C7330 - 0x000C7350     0x001C72B0 - 0x001C72D0     Function:
                                                        get_shadow_bri
0x000C7350 - 0x000C7378     0x001C72D0 - 0x001C72F8     Function:
                                                        get_edge_info
0x000C7380 - 0x000C73A0     0x001C7300 - 0x001C7320     Function:
                                                        ps2dancerGetName
0x000C73A0 - 0x000C73C4     0x001C7320 - 0x001C7344     Function:
                                                        get_dancer_default_mot
0x000C73D0 - 0x000C742C     0x001C7350 - 0x001C73AC     Function:
                                                        rnd_get_dancer_mot
0x000C7430 - 0x000C7450     0x001C73B0 - 0x001C73D0     Function:
                                                        get_primdt_tbl
0x000C7450 - 0x000C7470     0x001C73D0 - 0x001C73F0     Function:
                                                        get_dancer_scale
0x000C7470 - 0x000C7488     0x001C73F0 - 0x001C7408     Function:
                                                        get_mdt_name
0x000C7490 - 0x000C74A8     0x001C7410 - 0x001C7428     Function:
                                                        get_cdt_name
0x000C74B0 - 0x000C74F0     0x001C7430 - 0x001C7470     Function:
                                                        CreateRotMatrixX
0x000C74F0 - 0x000C7530     0x001C7470 - 0x001C74B0     Function:
                                                        CreateRotMatrixZ
0x000C7530 - 0x000C7570     0x001C74B0 - 0x001C74F0     Function:
                                                        CreateRotMatrixY
0x000C7570 - 0x000C768C     0x001C74F0 - 0x001C760C     Function:
                                                        convert_matrix_ps2dx
0x000C7690 - 0x000C77B0     0x001C7610 - 0x001C7730     Function:
                                                        convert_matrix_dx2ps
0x000C77B0 - 0x000C7828     0x001C7730 - 0x001C77A8     Function:
                                                        NMDPrsetPacketGT3
0x000C7830 - 0x000C7890     0x001C77B0 - 0x001C7810     Function:
                                                        NMDPrsetPacketG3
0x000C7890 - 0x000C793C     0x001C7810 - 0x001C78BC     Function:
                                                        NMDPresetObject
0x000C7940 - 0x000C7A10     0x001C78C0 - 0x001C7990     Function:
                                                        NMDMapModelingData
0x000C7A10 - 0x000C7C24     0x001C7990 - 0x001C7BA4     Function:
                                                        dancer_model_setup
0x000C7C30 - 0x000C7FD0     0x001C7BB0 - 0x001C7F50     Function:
                                                        NormCulcG3US
0x000C7FD0 - 0x000C835C     0x001C7F50 - 0x001C82DC     Function:
                                                        NormCulcG3U
0x000C8360 - 0x000C87B8     0x001C82E0 - 0x001C8738     Function:
                                                        VertCulcU
0x000C87C0 - 0x000C8AF8     0x001C8740 - 0x001C8A78     Function:
                                                        drawGT3
0x000C8B00 - 0x000C8E14     0x001C8A80 - 0x001C8D94     Function:
                                                        drawGT3L
0x000C8E20 - 0x000C8FB0     0x001C8DA0 - 0x001C8F30     Function:
                                                        drawLcore
0x000C8FB0 - 0x000C918C     0x001C8F30 - 0x001C910C     Function:
                                                        drawG3core
0x000C9190 - 0x000C9374     0x001C9110 - 0x001C92F4     Function:
                                                        drawG3L
0x000C9380 - 0x000C9764     0x001C9300 - 0x001C96E4     Function:
                                                        NMDSortObject5
0x000C9770 - 0x000C9AB8     0x001C96F0 - 0x001C9A38     Function:
                                                        nmd_model_disp
0x000C9AC0 - 0x000C9D84     0x001C9A40 - 0x001C9D04     Function:
                                                        draw_dancer_model
0x000C9D90 - 0x000C9EDC     0x001C9D10 - 0x001C9E5C     Function:
                                                        PsGsGetLs
0x000C9EE0 - 0x000CA0D8     0x001C9E60 - 0x001CA058     Function:
                                                        pre_draw_dancer_model
0x000CA0E0 - 0x000CA2C0     0x001CA060 - 0x001CA240     Function:
                                                        set_dance_motion_pack_tab
0x000CA2C0 - 0x000CA378     0x001CA240 - 0x001CA2F8     Function:
                                                        get_dance_mpack
0x000CA380 - 0x000CA90C     0x001CA300 - 0x001CA88C     Function:
                                                        set_dance_motion
0x000CA910 - 0x000CAC7C     0x001CA890 - 0x001CABFC     Function:
                                                        init_dance_motion
0x000CAC80 - 0x000CAEB0     0x001CAC00 - 0x001CAE30     Function:
                                                        dancer_motion_setup
0x000CAEB0 - 0x000CB2DC     0x001CAE30 - 0x001CB25C     Function:
                                                        decodeMimeParam
0x000CB2E0 - 0x000CB4F4     0x001CB260 - 0x001CB474     Function:
                                                        mimeAnimation_local
0x000CB500 - 0x000CB7A8     0x001CB480 - 0x001CB728     Function:
                                                        mimeAnimation
0x000CB7B0 - 0x000CB8F0     0x001CB730 - 0x001CB870     Function:
                                                        decodeRotateFormat
0x000CB8F0 - 0x000CBADC     0x001CB870 - 0x001CBA5C     Function:
                                                        decodeVectorFormat
0x000CBAE0 - 0x000CBBF0     0x001CBA60 - 0x001CBB70     Function:
                                                        decodeBody
0x000CBBF0 - 0x000CBF14     0x001CBB70 - 0x001CBE94     Function:
                                                        decodeAnimation
0x000CBF20 - 0x000CC084     0x001CBEA0 - 0x001CC004     Function:
                                                        dancer_motion_decode
0x000CC090 - 0x000CC10C     0x001CC010 - 0x001CC08C     Function:
                                                        LoadAverageShort12
0x000CC110 - 0x000CC1C8     0x001CC090 - 0x001CC148     Function:
                                                        VectorNormalSS
0x000CC1D0 - 0x000CC264     0x001CC150 - 0x001CC1E4     Function:
                                                        OuterProduct12
0x000CC270 - 0x000CC2D0     0x001CC1F0 - 0x001CC250     Function:
                                                        TransposeMatrix
0x000CC2D0 - 0x000CC324     0x001CC250 - 0x001CC2A4     Function:
                                                        ps1rcos
0x000CC330 - 0x000CC384     0x001CC2B0 - 0x001CC304     Function:
                                                        ps1rsin
0x000CC390 - 0x000CC6D8     0x001CC310 - 0x001CC658     Function:
                                                        PsRotMatrix
0x000CC6E0 - 0x000CC778     0x001CC660 - 0x001CC6F8     Function:
                                                        GsInitCoordinate2
0x000CC780 - 0x000CC7A8     0x001CC700 - 0x001CC728     Function:
                                                        dist3d
0x000CC7B0 - 0x000CC7CC     0x001CC730 - 0x001CC74C     Function:
                                                        frd
0x000CC7D0 - 0x000CC958     0x001CC750 - 0x001CC8D8     Function:
                                                        gs3dSetRenderUnitMatrix
0x000CC960 - 0x000CCAEC     0x001CC8E0 - 0x001CCA6C     Function:
                                                        gs3dSetRenderMatrix
0x000CCAF0 - 0x000CCB64     0x001CCA70 - 0x001CCAE4     Function:
                                                        gs3dSetFrustum
0x000CCB70 - 0x000CCBD8     0x001CCAF0 - 0x001CCB58     Function:
                                                        gs3dSetLightMatrix
0x000CCBE0 - 0x000CCDB0     0x001CCB60 - 0x001CCD30     Function:
                                                        gs3dEnd
0x000CCDB0 - 0x000CCE00     0x001CCD30 - 0x001CCD80     Function:
                                                        gs3dTexture
0x000CCE00 - 0x000CCE4C     0x001CCD80 - 0x001CCDCC     Function:
                                                        gs3dColor
0x000CCE50 - 0x000CCEB0     0x001CCDD0 - 0x001CCE30     Function:
                                                        gs3dVertex
0x000CCEB0 - 0x000CCF90     0x001CCE30 - 0x001CCF10     Function:
                                                        gs3dBegin
0x000CCF90 - 0x000CCFB4     0x001CCF10 - 0x001CCF34     Function:
                                                        gs3dSetLightAmbient
0x000CCFC0 - 0x000CCFF8     0x001CCF40 - 0x001CCF78     Function:
                                                        gs3dSetLightVector
0x000CD000 - 0x000CD038     0x001CCF80 - 0x001CCFB8     Function:
                                                        gs3dSetLightColor
0x000CD040 - 0x000CD0E8     0x001CCFC0 - 0x001CD068     Function:
                                                        gsInit3d
0x000CD0F0 - 0x000CD1F8     0x001CD070 - 0x001CD178     Function:
                                                        gxRenderVCT
0x000CD200 - 0x000CD2F8     0x001CD180 - 0x001CD278     Function:
                                                        gxRenderVC
0x000CD300 - 0x000CD448     0x001CD280 - 0x001CD3C8     Function:
                                                        gxRenderVNCT
0x000CD450 - 0x000CD9F0     0x001CD3D0 - 0x001CD970     Function:
                                                        camera_tst
0x000CD9F0 - 0x000CDA04     0x001CD970 - 0x001CD984     Function:
                                                        ps2dancerSetCameraPos
0x000CDA10 - 0x000CDA1C     0x001CD990 - 0x001CD99C     Function:
                                                        GetDancerCameraW
0x000CDA20 - 0x000CDC8C     0x001CD9A0 - 0x001CDC0C     Function:
                                                        camera_ero
0x000CDC90 - 0x000CE058     0x001CDC10 - 0x001CDFD8     Function:
                                                        camera_roll
0x000CE060 - 0x000CE420     0x001CDFE0 - 0x001CE3A0     Function:
                                                        camera_s03
0x000CE420 - 0x000CE580     0x001CE3A0 - 0x001CE500     Function:
                                                        camera_s02
0x000CE580 - 0x000CE7AC     0x001CE500 - 0x001CE72C     Function:
                                                        camera_s01
0x000CE7B0 - 0x000CEAA4     0x001CE730 - 0x001CEA24     Function:
                                                        change_camera_type
0x000CEAB0 - 0x000CED8C     0x001CEA30 - 0x001CED0C     Function:
                                                        ps2dancerCameraStep
0x000CED90 - 0x000CEE40     0x001CED10 - 0x001CEDC0     Function:
                                                        ps2dancerCameraPreStep
0x000CEE40 - 0x000CEF7C     0x001CEDC0 - 0x001CEEFC     Function:
                                                        ps2dancerCameraInit
0x000CEF80 - 0x000CEF98     0x001CEF00 - 0x001CEF18     Function:
                                                        Update_Openinglogo
0x000CEFA0 - 0x000CF0C8     0x001CEF20 - 0x001CF048     Function:
                                                        View_Openinglogo
0x000CF0D0 - 0x000CF1C0     0x001CF050 - 0x001CF140     Function:
                                                        Control_Openinglogo
0x000CF1C0 - 0x000CF224     0x001CF140 - 0x001CF1A4     Function:
                                                        Init_Openinglogo
0x000CF230 - 0x000CF2A0     0x001CF1B0 - 0x001CF220     Function:
                                                        ps2dancerInitHide
0x000CF2A0 - 0x000CF3F8     0x001CF220 - 0x001CF378     Function:
                                                        ps2dancerGetDollList
0x000CF400 - 0x000CF488     0x001CF380 - 0x001CF408     Function:
                                                        ps2dancerPdataLoadStep
0x000CF490 - 0x000CF4AC     0x001CF410 - 0x001CF42C     Function:
                                                        ps2dancerPdataLoadInit
0x000CF4B0 - 0x000CF4F0     0x001CF430 - 0x001CF470     Function:
                                                        ps2dancerGetEntryNum
0x000CF4F0 - 0x000CF704     0x001CF470 - 0x001CF684     Function:
                                                        shape_mot_id
0x000CF710 - 0x000CF7D8     0x001CF690 - 0x001CF758     Function:
                                                        ps2dancerSetup
0x000CF7E0 - 0x000CF948     0x001CF760 - 0x001CF8C8     Function:
                                                        ps2dancerChangeStep
0x000CF950 - 0x000CF9B8     0x001CF8D0 - 0x001CF938     Function:
                                                        ps2dancerChange
0x000CF9C0 - 0x000CFE34     0x001CF940 - 0x001CFDB4     Function:
                                                        ps2dancerLoadStep
0x000CFE40 - 0x000CFED8     0x001CFDC0 - 0x001CFE58     Function:
                                                        get_free_motbuf
0x000CFEE0 - 0x000D012C     0x001CFE60 - 0x001D00AC     Function:
                                                        ps2dancerLoadInit
0x000D0130 - 0x000D01C0     0x001D00B0 - 0x001D0140     Function:
                                                        ps2dancerEntry2
0x000D01C0 - 0x000D0260     0x001D0140 - 0x001D01E0     Function:
                                                        ps2dancerEntry
0x000D0260 - 0x000D033C     0x001D01E0 - 0x001D02BC     Function:
                                                        auto_chara_select
0x000D0340 - 0x000D0358     0x001D02C0 - 0x001D02D8     Function:
                                                        ps2dancerResetEntry
0x000D0360 - 0x000D0370     0x001D02E0 - 0x001D02F0     Function:
                                                        ps2dancerBreakDataArea
0x000D0370 - 0x000D043C     0x001D02F0 - 0x001D03BC     Function:
                                                        ps2dancerInit
0x000D0440 - 0x000D08E4     0x001D03C0 - 0x001D0864     Function:
                                                        decodeVAG
0x000D08F0 - 0x000D090C     0x001D0870 - 0x001D088C     Function:
                                                        setR
0x000D0910 - 0x000D092C     0x001D0890 - 0x001D08AC     Function:
                                                        setL
0x000D0930 - 0x000D0A6C     0x001D08B0 - 0x001D09EC     Function:
                                                        SdMakewt
0x000D0A70 - 0x000D0F3C     0x001D09F0 - 0x001D0EBC     Function:
                                                        SdBitrv2conj
0x000D0F40 - 0x000D1368     0x001D0EC0 - 0x001D12E8     Function:
                                                        SdBitrv2
0x000D1370 - 0x000D17D8     0x001D12F0 - 0x001D1758     Function:
                                                        SdCftmdl
0x000D17E0 - 0x000D1AF8     0x001D1760 - 0x001D1A78     Function:
                                                        SdCft1st
0x000D1B00 - 0x000D1CB4     0x001D1A80 - 0x001D1C34     Function:
                                                        SdCftbsub
0x000D1CC0 - 0x000D20A4     0x001D1C40 - 0x001D2024     Function:
                                                        SdFFTCore
0x000D20B0 - 0x000D216C     0x001D2030 - 0x001D20EC     Function:
                                                        SdFFTInit
0x000D2170 - 0x000D217C     0x001D20F0 - 0x001D20FC     Function:
                                                        SdGetFFTStart
0x000D2180 - 0x000D218C     0x001D2100 - 0x001D210C     Function:
                                                        SdSetFFTEnd
0x000D2190 - 0x000D21A0     0x001D2110 - 0x001D2120     Function:
                                                        SdSetFFTStart
0x000D21A0 - 0x000D21AC     0x001D2120 - 0x001D212C     Function:
                                                        SdSetFFTSet
0x000D21B0 - 0x000D21BC     0x001D2130 - 0x001D213C     Function:
                                                        SdGetFFTSet
0x000D21C0 - 0x000D21D0     0x001D2140 - 0x001D2150     Function:
                                                        SdGetFFTWorkL
0x000D21D0 - 0x000D21E0     0x001D2150 - 0x001D2160     Function:
                                                        SdGetFFTWorkR
0x000D21E0 - 0x000D21F0     0x001D2160 - 0x001D2170     Function:
                                                        SdGetDecodeWorkL
0x000D21F0 - 0x000D2200     0x001D2170 - 0x001D2180     Function:
                                                        SdGetDecodeWorkR
0x000D2200 - 0x000D2264     0x001D2180 - 0x001D21E4     Function:
                                                        EyeSceEnd
0x000D2270 - 0x000D26F8     0x001D21F0 - 0x001D2678     Function:
                                                        EyeSystemFilter
0x000D2700 - 0x000D2EF4     0x001D2680 - 0x001D2E74     Function:
                                                        EyeSystemDispColorAnimeWindow
0x000D2F00 - 0x000D3280     0x001D2E80 - 0x001D3200     Function:
                                                        EyeSystemDispWindow
0x000D3280 - 0x000D3890     0x001D3200 - 0x001D3810     Function:
                                                        EyeSystemDrawPict
0x000D3890 - 0x000D39AC     0x001D3810 - 0x001D392C     Function:
                                                        EyeSystemDestroy
0x000D39B0 - 0x000D3B1C     0x001D3930 - 0x001D3A9C     Function:
                                                        EyeSystemStop
0x000D3B20 - 0x000D3B70     0x001D3AA0 - 0x001D3AF0     Function:
                                                        EyeSystemMain
0x000D3B70 - 0x000D3C98     0x001D3AF0 - 0x001D3C18     Function:
                                                        EyeSystemStart
0x000D3CA0 - 0x000D3CF0     0x001D3C20 - 0x001D3C70     Function:
                                                        EyeSystemSet
0x000D3CF0 - 0x000D4BAC     0x001D3C70 - 0x001D4B2C     Function:
                                                        EyeSystemInit
0x000D4BB0 - 0x000D4C3C     0x001D4B30 - 0x001D4BBC     Function:
                                                        EyeSystemFunc
0x000D4C40 - 0x000D4D50     0x001D4BC0 - 0x001D4CD0     Function:
                                                        EyeSystemReset
0x000D4D50 - 0x000D4DF4     0x001D4CD0 - 0x001D4D74     Function:
                                                        EyeSystemCreate
0x000D4E00 - 0x000D4E30     0x001D4D80 - 0x001D4DB0     Function:
                                                        EyeRefSetIPUCode
0x000D4E30 - 0x000D4E44     0x001D4DB0 - 0x001D4DC4     Function:
                                                        EyeRefGetPeerBitstreamAddr
0x000D4E50 - 0x000D4E6C     0x001D4DD0 - 0x001D4DEC     Function:
                                                        EyeRefGetMyBitstreamAddr
0x000D4E70 - 0x000D4E7C     0x001D4DF0 - 0x001D4DFC     Function:
                                                        EyeRefSetPeerBitstreamNum
0x000D4E80 - 0x000D4E8C     0x001D4E00 - 0x001D4E0C     Function:
                                                        EyeRefGetPeerBitstreamNum
0x000D4E90 - 0x000D4EC4     0x001D4E10 - 0x001D4E44     Function:
                                                        EyeRefChangeMyBitstream
0x000D4ED0 - 0x000D4EF4     0x001D4E50 - 0x001D4E74     Function:
                                                        EyeRefSetDefaultMemAddr
0x000D4F00 - 0x000D5054     0x001D4E80 - 0x001D4FD4     Function:
                                                        EyeRefGetCircleCheckTotal
0x000D5060 - 0x000D510C     0x001D4FE0 - 0x001D508C     Function:
                                                        EyeRefGetCircleCheckStrikePDF
0x000D5110 - 0x000D5204     0x001D5090 - 0x001D5184     Function:
                                                        EyeRefGetCheckTotal
0x000D5210 - 0x000D52BC     0x001D5190 - 0x001D523C     Function:
                                                        EyeRefGetCheckStrikePDF
0x000D52C0 - 0x000D53E0     0x001D5240 - 0x001D5360     Function:
                                                        EyeRefSetOneWindow
0x000D53E0 - 0x000D5408     0x001D5360 - 0x001D5388     Function:
                                                        EyeRefSetPositionZ
0x000D5410 - 0x000D551C     0x001D5390 - 0x001D549C     Function:
                                                        EyeRegGetSystemStatus
0x000E0730 - 0x000E0738     0x001E06B0 - 0x001E06B8     Function:
                                                        Main_Dmm_ol
0x000E0740 - 0x000E07C4     0x001E06C0 - 0x001E0744     Function:
                                                        Init_Dmm_ol
0x000E07D0 - 0x000E07D8     0x001E0750 - 0x001E0758     Function:
                                                        Term_Opt_ol
0x000E07E0 - 0x000E07E8     0x001E0760 - 0x001E0768     Function:
                                                        Step_Opt_ol
0x000E07F0 - 0x000E0874     0x001E0770 - 0x001E07F4     Function:
                                                        Init_Opt_ol
0x000E0880 - 0x000E08BC     0x001E0800 - 0x001E083C     Function:
                                                        SetPreRead_Opt
0x000E08C0 - 0x000E08FC     0x001E0840 - 0x001E087C     Function:
                                                        SetPreRead_Rec
0x000E0900 - 0x000E0908     0x001E0880 - 0x001E0888     Function:
                                                        Term_Rec_ol
0x000E0910 - 0x000E0918     0x001E0890 - 0x001E0898     Function:
                                                        Step_Rec_ol
0x000E0920 - 0x000E09A4     0x001E08A0 - 0x001E0924     Function:
                                                        Init_Rec_ol
0x000E09B0 - 0x000E09EC     0x001E0930 - 0x001E096C     Function:
                                                        SetPreRead_Workout
0x000E09F0 - 0x000E09F8     0x001E0970 - 0x001E0978     Function:
                                                        Term_Workout_ol
0x000E0A00 - 0x000E0A08     0x001E0980 - 0x001E0988     Function:
                                                        Step_Workout_ol
0x000E0A10 - 0x000E0A94     0x001E0990 - 0x001E0A14     Function:
                                                        Init_Workout_ol
0x000E0AA0 - 0x000E0AA8     0x001E0A20 - 0x001E0A28     Function:
                                                        Term_Les_ol
0x000E0AB0 - 0x000E0AB8     0x001E0A30 - 0x001E0A38     Function:
                                                        Step_Les_ol
0x000E0AC0 - 0x000E0B40     0x001E0A40 - 0x001E0AC0     Function:
                                                        Init_Les_ol
0x000E0B40 - 0x000E0B7C     0x001E0AC0 - 0x001E0AFC     Function:
                                                        SetPreRead_Les
0x000E0B80 - 0x000E0B88     0x001E0B00 - 0x001E0B08     Function:
                                                        Term_Info_ol
0x000E0B90 - 0x000E0B98     0x001E0B10 - 0x001E0B18     Function:
                                                        Step_Info_ol
0x000E0BA0 - 0x000E0C20     0x001E0B20 - 0x001E0BA0     Function:
                                                        Init_Info_ol
0x000E0C20 - 0x000E0C5C     0x001E0BA0 - 0x001E0BDC     Function:
                                                        SetPreRead_Info
0x000E0C60 - 0x000E0C8C     0x001E0BE0 - 0x001E0C0C     Function:
                                                        rom_load_th
0x000E0C90 - 0x000E0E28     0x001E0C10 - 0x001E0DA8     Function:
                                                        SetOverlayPos_main
0x000E0E30 - 0x000E0E38     0x001E0DB0 - 0x001E0DB8     Function:
                                                        SetOverlayPos_init
0x000E0E40 - 0x000E10E4     0x001E0DC0 - 0x001E1064     Function:
                                                        Main_Overlay
0x000E10F0 - 0x000E118C     0x001E1070 - 0x001E110C     Function:
                                                        Init_Overlay
0x000E1190 - 0x000E11C4     0x001E1110 - 0x001E1144     Function:
                                                        ReleaseInformation_AllSongsUnlocked
0x000E11D0 - 0x000E1210     0x001E1150 - 0x001E1190     Function:
                                                        get_dancer_id_by_infotext_num
0x000E1210 - 0x000E1238     0x001E1190 - 0x001E11B8     Function:
                                                        get_course_id_by_infotxt_num
0x000E1240 - 0x000E12C4     0x001E11C0 - 0x001E1244     Function:
                                                        get_table_no_by_infotxt_num
0x000E12D0 - 0x000E1328     0x001E1250 - 0x001E12A8     Function:
                                                        get_infotxt_num_by_mip
0x000E1330 - 0x000E139C     0x001E12B0 - 0x001E131C     Function:
                                                        get_minfo_by_infotxt_num
0x000E13A0 - 0x000E13A8     0x001E1320 - 0x001E1328     Function:
                                                        GetInfoOrderNum_for_course
0x000E13B0 - 0x000E13B8     0x001E1330 - 0x001E1338     Function:
                                                        GetInfoOrderNum_for_music
0x000E13C0 - 0x000E13C8     0x001E1340 - 0x001E1348     Function:
                                                        GetInfoOrderNum
0x000E13D0 - 0x000E1754     0x001E1350 - 0x001E16D4     Function:
                                                        CsFontPutsI
0x000E1760 - 0x000E17C0     0x001E16E0 - 0x001E1740     Function:
                                                        GetCsFontLenI
0x000E17C0 - 0x000E1CA0     0x001E1740 - 0x001E1C20     Function:
                                                        CSXX20Puts
0x000E1CA0 - 0x000E1CAC     0x001E1C20 - 0x001E1C2C     Function:
                                                        GetCSXX20Len
0x000E1CB0 - 0x000E1E38     0x001E1C30 - 0x001E1DB8     Function:
                                                        CsGetFontLength
0x000E1E40 - 0x000E1FE8     0x001E1DC0 - 0x001E1F68     Function:
                                                        CsFontPrintf
0x000E1FF0 - 0x000E22C0     0x001E1F70 - 0x001E2240     Function:
                                                        CSXX18Puts
0x000E22C0 - 0x000E2558     0x001E2240 - 0x001E24D8     Function:
                                                        MgFontPuts
0x000E2560 - 0x000E28C0     0x001E24E0 - 0x001E2840     Function:
                                                        CsFontPutsRGB
0x000E28C0 - 0x000E2EE0     0x001E2840 - 0x001E2E60     Function:
                                                        CsFontPuts
0x000E2EE0 - 0x000E2F20     0x001E2E60 - 0x001E2EA0     Function:
                                                        GetCsFontLen
0x000E2F20 - 0x000E2F60     0x001E2EA0 - 0x001E2EE0     Function:
                                                        GetCSXX18FontLen
0x000E2F60 - 0x000E2F84     0x001E2EE0 - 0x001E2F04     Function:
                                                        sdstr3_ret
0x000E2F90 - 0x000E32A0     0x001E2F10 - 0x001E3220     Function:
                                                        sdstr3_eeread_th
0x000E32A0 - 0x000E32B0     0x001E3220 - 0x001E3230     Function:
                                                        SdStrSetDiv
0x000E32B0 - 0x000E330C     0x001E3230 - 0x001E328C     Function:
                                                        SdStriVsync
0x000E3310 - 0x000E3390     0x001E3290 - 0x001E3310     Function:
                                                        SdStrCdSync
0x000E3390 - 0x000E33F0     0x001E3310 - 0x001E3370     Function:
                                                        SdStrCdRead
0x000E33F0 - 0x000E34FC     0x001E3370 - 0x001E347C     Function:
                                                        SdStrCdInit
0x000E4690 - 0x000E4C0C     0x001E4610 - 0x001E4B8C     Function:
                                                        DispFFTFlower1
0x000E4C10 - 0x000E5444     0x001E4B90 - 0x001E53C4     Function:
                                                        DispFFTMeter1
0x000E5450 - 0x000E5F24     0x001E53D0 - 0x001E5EA4     Function:
                                                        DispFFTWire2
0x000E5F30 - 0x000E6AB4     0x001E5EB0 - 0x001E6A34     Function:
                                                        DispFFTWire1
0x000E6AC0 - 0x000E7398     0x001E6A40 - 0x001E7318     Function:
                                                        DispFFTMeter2
0x000E73A0 - 0x000E7454     0x001E7320 - 0x001E73D4     Function:
                                                        FFTDisp
0x000E7460 - 0x000E7490     0x001E73E0 - 0x001E7410     Function:
                                                        SetFFTDispWork
0x000E7490 - 0x000E7534     0x001E7410 - 0x001E74B4     Function:
                                                        BkEffectTypeSet
0x000E7540 - 0x000E760C     0x001E74C0 - 0x001E758C     Function:
                                                        BkEffectColSet
0x000E7610 - 0x000E76E0     0x001E7590 - 0x001E7660     Function:
                                                        sepia
0x000E76E0 - 0x000E7784     0x001E7660 - 0x001E7704     Function:
                                                        negaposi
0x000E7790 - 0x000E7928     0x001E7710 - 0x001E78A8     Function:
                                                        ti_movie_SetDecTag
0x000E7930 - 0x000E7A0C     0x001E78B0 - 0x001E798C     Function:
                                                        ti_movie_work_set
0x000E7A10 - 0x000E7B94     0x001E7990 - 0x001E7B14     Function:
                                                        ti_movie_play
0x000E7BA0 - 0x000E7E34     0x001E7B20 - 0x001E7DB4     Function:
                                                        title_movie_disp
0x000E7E40 - 0x000E8034     0x001E7DC0 - 0x001E7FB4     Function:
                                                        title_movie_manage
0x000E8040 - 0x000E804C     0x001E7FC0 - 0x001E7FCC     Function:
                                                        title_movie_play_ok
0x000E8050 - 0x000E8060     0x001E7FD0 - 0x001E7FE0     Function:
                                                        title_movie_play_start
0x000E8060 - 0x000E80E8     0x001E7FE0 - 0x001E8068     Function:
                                                        title_movie_init
0x000E92D0 - 0x000E9514     0x001E9250 - 0x001E9494     Function:
                                                        main_libmc_reset
0x000E9520 - 0x000E9528     0x001E94A0 - 0x001E94A8     Function:
                                                        init_libmc_reset
0x000E9530 - 0x000E95B8     0x001E94B0 - 0x001E9538     Function:
                                                        libmc_set_th
0x000E95C0 - 0x000E969C     0x001E9540 - 0x001E961C     Function:
                                                        main_libmc_set
0x000E96A0 - 0x000E96A8     0x001E9620 - 0x001E9628     Function:
                                                        init_libmc_set
0x000E96B0 - 0x000E9774     0x001E9630 - 0x001E96F4     Function:
                                                        unload_bsdsocki_th
0x000E9780 - 0x000E97DC     0x001E9700 - 0x001E975C     Function:
                                                        load_bsdsocki_th
0x000E97E0 - 0x000E9818     0x001E9760 - 0x001E9798     Function:
                                                        NetD2ucMsgErr
0x000E9820 - 0x000E982C     0x001E97A0 - 0x001E97AC     Function:
                                                        NetD2ucMsgRecv
0x000E9830 - 0x000E98F4     0x001E97B0 - 0x001E9874     Function:
                                                        NsNetFunc
0x000E9900 - 0x000E9C1C     0x001E9880 - 0x001E9B9C     Function:
                                                        NsNetSend
0x000E9C20 - 0x000EA0F0     0x001E9BA0 - 0x001EA070     Function:
                                                        NsNetRecv
0x000EA0F0 - 0x000EA1C8     0x001EA070 - 0x001EA148     Function:
                                                        NsNetSocketClose
0x000EA1D0 - 0x000EA240     0x001EA150 - 0x001EA1C0     Function:
                                                        NsNetSocketSetPeer
0x000EA240 - 0x000EA37C     0x001EA1C0 - 0x001EA2FC     Function:
                                                        NsNetSocketCreate
0x000EA380 - 0x000EA744     0x001EA300 - 0x001EA6C4     Function:
                                                        NsNetLogout
0x000EA750 - 0x000EA774     0x001EA6D0 - 0x001EA6F4     Function:
                                                        net_ave_end
0x000EA780 - 0x000EB044     0x001EA700 - 0x001EAFC4     Function:
                                                        NsNetLogin
0x000EB050 - 0x000EB074     0x001EAFD0 - 0x001EAFF4     Function:
                                                        net_ave_start
0x000EB080 - 0x000EB08C     0x001EB000 - 0x001EB00C     Function:
                                                        NsNetInitialize
0x000EB090 - 0x000EB218     0x001EB010 - 0x001EB198     Function:
                                                        NetPadCon
0x000EB220 - 0x000EB2E0     0x001EB1A0 - 0x001EB260     Function:
                                                        NetToLogout
0x000EB2E0 - 0x000EB3C0     0x001EB260 - 0x001EB340     Function:
                                                        NetToGameInit
0x000EB3C0 - 0x000EB4E0     0x001EB340 - 0x001EB460     Function:
                                                        NetToSysInit
0x000EB4E0 - 0x000EB524     0x001EB460 - 0x001EB4A4     Function:
                                                        NetEnd
0x000EB530 - 0x000EB9AC     0x001EB4B0 - 0x001EB92C     Function:
                                                        NetMain
0x000EB9B0 - 0x000EBA40     0x001EB930 - 0x001EB9C0     Function:
                                                        NetInit
0x000EBA40 - 0x000EBA70     0x001EB9C0 - 0x001EB9F0     Function:
                                                        NsNetP2PRecv
0x000EBA70 - 0x000EBB48     0x001EB9F0 - 0x001EBAC8     Function:
                                                        NetP2PSendProgram
0x000EBB50 - 0x000EBBE4     0x001EBAD0 - 0x001EBB64     Function:
                                                        NetRecvProgramData
0x000EBBF0 - 0x000EBCA4     0x001EBB70 - 0x001EBC24     Function:
                                                        NetSendPicture
0x000EBCB0 - 0x000EBDC0     0x001EBC30 - 0x001EBD40     Function:
                                                        NetSendProgram
0x000EBDC0 - 0x000EBE28     0x001EBD40 - 0x001EBDA8     Function:
                                                        peerPrintf
0x000EBE30 - 0x000EBE78     0x001EBDB0 - 0x001EBDF8     Function:
                                                        NetGrfGetDancerIDToNumberPoint
0x000EBE80 - 0x000EC214     0x001EBE00 - 0x001EC194     Function:
                                                        NetPrgGetRCIdList
0x000EC220 - 0x000EC5B4     0x001EC1A0 - 0x001EC534     Function:
                                                        NetPrgGetSchedule
0x000EC5C0 - 0x000EC954     0x001EC540 - 0x001EC8D4     Function:
                                                        NetPrgGetRuleMask
0x000EC960 - 0x000ECDD4     0x001EC8E0 - 0x001ECD54     Function:
                                                        NetPrgSetMyAddr
0x000ECDE0 - 0x000ED390     0x001ECD60 - 0x001ED310     Function:
                                                        NetPrgGetRCRanking
0x000ED390 - 0x000ED8D4     0x001ED310 - 0x001ED854     Function:
                                                        NetPrgGetPointRanking
0x000ED8E0 - 0x000EDF64     0x001ED860 - 0x001EDEE4     Function:
                                                        NetPrgGetHtoHRanking
0x000EDF70 - 0x000EE514     0x001EDEF0 - 0x001EE494     Function:
                                                        NetPrgGetPlyerRCLog
0x000EE520 - 0x000EEA08     0x001EE4A0 - 0x001EE988     Function:
                                                        NetPrgGetPlyerHtoHLog
0x000EEA10 - 0x000EEDCC     0x001EE990 - 0x001EED4C     Function:
                                                        NetPrgGetRCRegist
0x000EEDD0 - 0x000EF174     0x001EED50 - 0x001EF0F4     Function:
                                                        NetPrgGetRCEntry
0x000EF180 - 0x000EF51C     0x001EF100 - 0x001EF49C     Function:
                                                        NetPrgGetRCTrycount
0x000EF520 - 0x000EFA70     0x001EF4A0 - 0x001EF9F0     Function:
                                                        NetPrgGetRCInfo
0x000EFA70 - 0x000EFFD4     0x001EF9F0 - 0x001EFF54     Function:
                                                        NetPrgConfiscate
0x000EFFE0 - 0x000F049C     0x001EFF60 - 0x001F041C     Function:
                                                        NetPrgGetEndgame
0x000F04A0 - 0x000F0964     0x001F0420 - 0x001F08E4     Function:
                                                        NetPrgGetStartStaus
0x000F0970 - 0x000F0E78     0x001F08F0 - 0x001F0DF8     Function:
                                                        NetPrgGetRoomList
0x000F0E80 - 0x000F1394     0x001F0E00 - 0x001F1314     Function:
                                                        NetPrgOutRoom
0x000F13A0 - 0x000F1804     0x001F1320 - 0x001F1784     Function:
                                                        NetPrgCreateRoom
0x000F1810 - 0x000F1D20     0x001F1790 - 0x001F1CA0     Function:
                                                        NetPrgSavePlayerOption
0x000F1D20 - 0x000F20B4     0x001F1CA0 - 0x001F2034     Function:
                                                        NetPrgGetPlayerOption
0x000F20C0 - 0x000F2454     0x001F2040 - 0x001F23D4     Function:
                                                        NetPrgGetPlayerInfo
0x000F2460 - 0x000F28B4     0x001F23E0 - 0x001F2834     Function:
                                                        NetPrgGetPlayerList
0x000F28C0 - 0x000F2C54     0x001F2840 - 0x001F2BD4     Function:
                                                        NetPrgEntryBlock
0x000F2C60 - 0x000F2FF4     0x001F2BE0 - 0x001F2F74     Function:
                                                        NetPrgGetBlockList
0x000F3000 - 0x000F33FC     0x001F2F80 - 0x001F337C     Function:
                                                        NetPrgSelectPlayerFile
0x000F3400 - 0x000F377C     0x001F3380 - 0x001F36FC     Function:
                                                        NetPrgDeletePlayerFile
0x000F3780 - 0x000F3B5C     0x001F3700 - 0x001F3ADC     Function:
                                                        NetPrgNewCreatePlayerFile
0x000F3B60 - 0x000F3F14     0x001F3AE0 - 0x001F3E94     Function:
                                                        NetPrgGetPlayerFileList
0x000F3F20 - 0x000F4624     0x001F3EA0 - 0x001F45A4     Function:
                                                        NetPrgConnectLobbyServer
0x000F4630 - 0x000F4DF4     0x001F45B0 - 0x001F4D74     Function:
                                                        NetPrgConnectAccountServer
0x000F4E00 - 0x000F5144     0x001F4D80 - 0x001F50C4     Function:
                                                        NetPrgSvrTime
0x000F5150 - 0x000F5628     0x001F50D0 - 0x001F55A8     Function:
                                                        NetPrgSvrList
0x000F5630 - 0x000F5944     0x001F55B0 - 0x001F58C4     Function:
                                                        NetPrgSvrInfo
0x000F5950 - 0x000F5BB8     0x001F58D0 - 0x001F5B38     Function:
                                                        NetPrgConnectGate
0x000F5BC0 - 0x000F5D3C     0x001F5B40 - 0x001F5CBC     Function:
                                                        NetPrgEtherStart
0x000F5D40 - 0x000F5E6C     0x001F5CC0 - 0x001F5DEC     Function:
                                                        NetPrgBsdsocketInit
0x000F5E70 - 0x000F5FA0     0x001F5DF0 - 0x001F5F20     Function:
                                                        NetPrgErrorFunc
0x000F5FA0 - 0x000F6064     0x001F5F20 - 0x001F5FE4     Function:
                                                        NetReadDataDecode
0x000F6070 - 0x000F62AC     0x001F5FF0 - 0x001F622C     Function:
                                                        NetReadDataInitFreeDataAddr
0x000F62B0 - 0x000F6300     0x001F6230 - 0x001F6280     Function:
                                                        NetReadDataGetStrLFNum
0x000F6300 - 0x000F6314     0x001F6280 - 0x001F6294     Function:
                                                        NetReadDataGetStr
0x000F6320 - 0x000F67F0     0x001F62A0 - 0x001F6770     Function:
                                                        NetReadData
0x000F67F0 - 0x000F6814     0x001F6770 - 0x001F6794     Function:
                                                        NetGameGetMusicNum
0x000F6820 - 0x000F6860     0x001F67A0 - 0x001F67E0     Function:
                                                        NetGameReverseMenu
0x000F6860 - 0x000F68B0     0x001F67E0 - 0x001F6830     Function:
                                                        NetGameEnd
0x000F68B0 - 0x000F7314     0x001F6830 - 0x001F7294     Function:
                                                        NetGameInit
0x000F7320 - 0x000F7388     0x001F72A0 - 0x001F7308     Function:
                                                        NetGameWinInterVSKey
0x000F7390 - 0x000F7AB8     0x001F7310 - 0x001F7A38     Function:
                                                        NetGameWinInterVSMain
0x000F7AC0 - 0x000F7FE8     0x001F7A40 - 0x001F7F68     Function:
                                                        NetGameWinInterVSInit
0x000F7FF0 - 0x000F8130     0x001F7F70 - 0x001F80B0     Function:
                                                        StepGetDate
0x000F8130 - 0x000F818C     0x001F80B0 - 0x001F810C     Function:
                                                        WorkoutStepInit
0x000F8190 - 0x000F82F8     0x001F8110 - 0x001F8278     Function:
                                                        StepNextDataLoad
0x000F8300 - 0x000F8628     0x001F8280 - 0x001F85A8     Function:
                                                        WorkoutTexInit
0x000F8630 - 0x000F863C     0x001F85B0 - 0x001F85BC     Function:
                                                        Workout_DispTitleFlameOut
0x000F8640 - 0x000F8B0C     0x001F85C0 - 0x001F8A8C     Function:
                                                        Workout_DispTitleDraw
0x000F8B10 - 0x000F8B38     0x001F8A90 - 0x001F8AB8     Function:
                                                        is_workout_simultaneous_step
0x000F8B40 - 0x000F8B48     0x001F8AC0 - 0x001F8AC8     Function:
                                                        is_workout_step
0x000F8B50 - 0x000F8B78     0x001F8AD0 - 0x001F8AF8     Function:
                                                        is_workout_program
0x000F8B80 - 0x000F8BC8     0x001F8B00 - 0x001F8B48     Function:
                                                        csWorkoutGetNormTime
0x000F8BD0 - 0x000F8C0C     0x001F8B50 - 0x001F8B8C     Function:
                                                        csWorkoutGetNormCalorie
0x000F8C10 - 0x000F8C2C     0x001F8B90 - 0x001F8BAC     Function:
                                                        csWorkoutGetWeight
0x000F8C30 - 0x000F8EF0     0x001F8BB0 - 0x001F8E70     Function:
                                                        csWorkoutDataDefault
0x000F8EF0 - 0x000F8EFC     0x001F8E70 - 0x001F8E7C     Function:
                                                        csWorkoutGetFlagCancel
0x000F8F00 - 0x000F8F0C     0x001F8E80 - 0x001F8E8C     Function:
                                                        csWorkoutSetFlagCancel
0x000F8F10 - 0x000F8F4C     0x001F8E90 - 0x001F8ECC     Function:
                                                        csWorkoutFinish
0x000F8F50 - 0x000F9048     0x001F8ED0 - 0x001F8FC8     Function:
                                                        csWorkoutStep
0x000F9050 - 0x000F918C     0x001F8FD0 - 0x001F910C     Function:
                                                        csWorkoutInit_GameWork
0x000F9190 - 0x000F927C     0x001F9110 - 0x001F91FC     Function:
                                                        csWorkoutInit
0x000F9280 - 0x000F92D0     0x001F9200 - 0x001F9250     Function:
                                                        Workout_FadeOut
0x000F92D0 - 0x000F9330     0x001F9250 - 0x001F92B0     Function:
                                                        Workout_FadeIn
0x000F9330 - 0x000F9618     0x001F92B0 - 0x001F9598     Function:
                                                        NetGameOptPortSetKey
0x000F9620 - 0x000F99E4     0x001F95A0 - 0x001F9964     Function:
                                                        NetGameOptPortSetMain
0x000F99F0 - 0x000F9A2C     0x001F9970 - 0x001F99AC     Function:
                                                        NetGameOptPortSetInit
0x000F9A30 - 0x000F9D18     0x001F99B0 - 0x001F9C98     Function:
                                                        NetGameOptKey
0x000F9D20 - 0x000F9F58     0x001F9CA0 - 0x001F9ED8     Function:
                                                        NetGameOptMain
0x000F9F60 - 0x000F9F98     0x001F9EE0 - 0x001F9F18     Function:
                                                        NetGameOptInit2
0x000F9FA0 - 0x000F9FE0     0x001F9F20 - 0x001F9F60     Function:
                                                        NetGameOptStepout
0x000F9FE0 - 0x000FA040     0x001F9F60 - 0x001F9FC0     Function:
                                                        NetGameOptStepin
0x000FA040 - 0x000FA304     0x001F9FC0 - 0x001FA284     Function:
                                                        NetGameOptExCursorOn
0x000FA310 - 0x000FA3F4     0x001FA290 - 0x001FA374     Function:
                                                        NetGameOptExCursorOff
0x000FA400 - 0x000FA494     0x001FA380 - 0x001FA414     Function:
                                                        NetGameOptExClose
0x000FA4A0 - 0x000FA534     0x001FA420 - 0x001FA4B4     Function:
                                                        NetGameOptExOpen
0x000FA540 - 0x000FA6F0     0x001FA4C0 - 0x001FA670     Function:
                                                        NetGameOptInit
0x000FA6F0 - 0x000FA868     0x001FA670 - 0x001FA7E8     Function:
                                                        NetGameLogoutKey
0x000FA870 - 0x000FA9FC     0x001FA7F0 - 0x001FA97C     Function:
                                                        NetGameLogoutMain
0x000FAA00 - 0x000FAA4C     0x001FA980 - 0x001FA9CC     Function:
                                                        NetGameLogoutStepout
0x000FAA50 - 0x000FAB40     0x001FA9D0 - 0x001FAAC0     Function:
                                                        NetGameLogoutStepin
0x000FAB40 - 0x000FAB48     0x001FAAC0 - 0x001FAAC8     Function:
                                                        NetGameLogoutExCursorOff
0x000FAB50 - 0x000FAB58     0x001FAAD0 - 0x001FAAD8     Function:
                                                        NetGameLogoutExClose
0x000FAB60 - 0x000FAB68     0x001FAAE0 - 0x001FAAE8     Function:
                                                        NetGameLogoutExOpen
0x000FAB70 - 0x000FAC40     0x001FAAF0 - 0x001FABC0     Function:
                                                        NetGameLogoutInit
0x000FAC40 - 0x000FAE9C     0x001FABC0 - 0x001FAE1C     Function:
                                                        NetGameMenuChangeTab
0x000FAEA0 - 0x000FB040     0x001FAE20 - 0x001FAFC0     Function:
                                                        NetGameMenuSelectKey
0x000FB040 - 0x000FB2F8     0x001FAFC0 - 0x001FB278     Function:
                                                        NetGameMenuSelect
0x000FB300 - 0x000FB3D4     0x001FB280 - 0x001FB354     Function:
                                                        NetGameMenuInit2
0x000FB3E0 - 0x000FB69C     0x001FB360 - 0x001FB61C     Function:
                                                        NetGameMenuInit
0x000FB6A0 - 0x000FB850     0x001FB620 - 0x001FB7D0     Function:
                                                        NetGameMatchSearchKey
0x000FB850 - 0x000FBA98     0x001FB7D0 - 0x001FBA18     Function:
                                                        NetGameMatchSearchMain
0x000FBAA0 - 0x000FC020     0x001FBA20 - 0x001FBFA0     Function:
                                                        NetGameMatchKey
0x000FC020 - 0x000FC348     0x001FBFA0 - 0x001FC2C8     Function:
                                                        NetGameMatchMain
0x000FC350 - 0x000FC390     0x001FC2D0 - 0x001FC310     Function:
                                                        NetGameMatchStepout
0x000FC390 - 0x000FC410     0x001FC310 - 0x001FC390     Function:
                                                        NetGameMatchStepin
0x000FC410 - 0x000FC734     0x001FC390 - 0x001FC6B4     Function:
                                                        NetGameMatchExCursorOn
0x000FC740 - 0x000FC978     0x001FC6C0 - 0x001FC8F8     Function:
                                                        NetGameMatchExCursorOff
0x000FC980 - 0x000FCA48     0x001FC900 - 0x001FC9C8     Function:
                                                        NetGameMatchExClose
0x000FCA50 - 0x000FCB10     0x001FC9D0 - 0x001FCA90     Function:
                                                        NetGameMatchExOpen
0x000FCB10 - 0x000FCD98     0x001FCA90 - 0x001FCD18     Function:
                                                        NetGameMatchInit
0x000FCDA0 - 0x000FCFA0     0x001FCD20 - 0x001FCF20     Function:
                                                        NetGameDataPersonalDataClose
0x000FCFA0 - 0x000FD128     0x001FCF20 - 0x001FD0A8     Function:
                                                        NetGameDataPersonalDataSet
0x000FD130 - 0x000FD338     0x001FD0B0 - 0x001FD2B8     Function:
                                                        NetGameDataPersonalKey
0x000FD340 - 0x000FD610     0x001FD2C0 - 0x001FD590     Function:
                                                        NetGameDataPersonalMain
0x000FD610 - 0x000FD9E0     0x001FD590 - 0x001FD960     Function:
                                                        NetGameDataPersonalInit
0x000FD9E0 - 0x000FDB18     0x001FD960 - 0x001FDA98     Function:
                                                        NetGameDataPointKey
0x000FDB20 - 0x000FDD10     0x001FDAA0 - 0x001FDC90     Function:
                                                        NetGameDataPointMain
0x000FDD10 - 0x000FE094     0x001FDC90 - 0x001FE014     Function:
                                                        NetGameDataPointInit
0x000FE0A0 - 0x000FE390     0x001FE020 - 0x001FE310     Function:
                                                        NetGameDataRCListKey
0x000FE390 - 0x000FE630     0x001FE310 - 0x001FE5B0     Function:
                                                        NetGameDataRCListMain
0x000FE630 - 0x000FEBE8     0x001FE5B0 - 0x001FEB68     Function:
                                                        NetGameDataRCListInit
0x000FEBF0 - 0x000FECFC     0x001FEB70 - 0x001FEC7C     Function:
                                                        NetGameDataRCSetNM
0x000FED00 - 0x000FF1D8     0x001FEC80 - 0x001FF158     Function:
                                                        NetGameDataRCKey
0x000FF1E0 - 0x000FF618     0x001FF160 - 0x001FF598     Function:
                                                        NetGameDataRCMain
0x000FF620 - 0x000FF70C     0x001FF5A0 - 0x001FF68C     Function:
                                                        NetGameDataRCInit2
0x000FF710 - 0x000FFC10     0x001FF690 - 0x001FFB90     Function:
                                                        NetGameDataRCInit
0x000FFC10 - 0x000FFD48     0x001FFB90 - 0x001FFCC8     Function:
                                                        NetGameDataHtoHKey
0x000FFD50 - 0x000FFF30     0x001FFCD0 - 0x001FFEB0     Function:
                                                        NetGameDataHtoHMain
0x000FFF30 - 0x001002FC     0x001FFEB0 - 0x0020027C     Function:
                                                        NetGameDataHtoHInit
0x00100300 - 0x00100530     0x00200280 - 0x002004B0     Function:
                                                        NetGameDataKey
0x00100530 - 0x00100720     0x002004B0 - 0x002006A0     Function:
                                                        NetGameDataMain
0x00100720 - 0x00100778     0x002006A0 - 0x002006F8     Function:
                                                        NetGameDataInit2
0x00100780 - 0x001007F8     0x00200700 - 0x00200778     Function:
                                                        NetGameDataStepout
0x00100800 - 0x001008C0     0x00200780 - 0x00200840     Function:
                                                        NetGameDataStepin
0x001008C0 - 0x00100A94     0x00200840 - 0x00200A14     Function:
                                                        NetGameDataExCursorOn
0x00100AA0 - 0x00100AF4     0x00200A20 - 0x00200A74     Function:
                                                        NetGameDataExCursorOff
0x00100B00 - 0x00100B10     0x00200A80 - 0x00200A90     Function:
                                                        NetGameDataExClose
0x00100B10 - 0x00100B20     0x00200A90 - 0x00200AA0     Function:
                                                        NetGameDataExOpen
0x00100B20 - 0x00100C0C     0x00200AA0 - 0x00200B8C     Function:
                                                        NetGameDataInit
0x00100C10 - 0x00100F38     0x00200B90 - 0x00200EB8     Function:
                                                        NetGamePracKey
0x00100F40 - 0x00101028     0x00200EC0 - 0x00200FA8     Function:
                                                        NetGamePracMain
0x00101030 - 0x00101070     0x00200FB0 - 0x00200FF0     Function:
                                                        NetGamePracStepout
0x00101070 - 0x001010B0     0x00200FF0 - 0x00201030     Function:
                                                        NetGamePracStepin
0x001010B0 - 0x00101270     0x00201030 - 0x002011F0     Function:
                                                        NetGamePracExCursorOn
0x00101270 - 0x00101350     0x002011F0 - 0x002012D0     Function:
                                                        NetGamePracExCursorOff
0x00101350 - 0x00101394     0x002012D0 - 0x00201314     Function:
                                                        NetGamePracExClose
0x001013A0 - 0x001013E4     0x00201320 - 0x00201364     Function:
                                                        NetGamePracExOpen
0x001013F0 - 0x00101628     0x00201370 - 0x002015A8     Function:
                                                        NetGamePracInit
0x00101630 - 0x00101698     0x002015B0 - 0x00201618     Function:
                                                        NetGameListDetailKey
0x001016A0 - 0x001017D8     0x00201620 - 0x00201758     Function:
                                                        NetGameListDetailMain
0x001017E0 - 0x00101984     0x00201760 - 0x00201904     Function:
                                                        NetGameListDetailInit
0x00101990 - 0x00101B90     0x00201910 - 0x00201B10     Function:
                                                        NetGameListKey
0x00101B90 - 0x001021B0     0x00201B10 - 0x00202130     Function:
                                                        NetGameListMain
0x001021B0 - 0x001021C0     0x00202130 - 0x00202140     Function:
                                                        NetGameListInit2
0x001021C0 - 0x001028B4     0x00202140 - 0x00202834     Function:
                                                        NetGameListInit
0x001028C0 - 0x001028CC     0x00202840 - 0x0020284C     Function:
                                                        bk_cur_mv_tbl
0x001028D0 - 0x001028DC     0x00202850 - 0x0020285C     Function:
                                                        bk_is_start
0x001028E0 - 0x001028EC     0x00202860 - 0x0020286C     Function:
                                                        bk_is_eyetoy
0x001028F0 - 0x001028FC     0x00202870 - 0x0020287C     Function:
                                                        bk_is_prarare
0x00102900 - 0x0010290C     0x00202880 - 0x0020288C     Function:
                                                        bk_is_err
0x00102910 - 0x00102AE4     0x00202890 - 0x00202A64     Function:
                                                        bk_mpeg_manager
0x00102AF0 - 0x00102C4C     0x00202A70 - 0x00202BCC     Function:
                                                        bkm_man_request_load
0x00102C50 - 0x00102DE4     0x00202BD0 - 0x00202D64     Function:
                                                        bkm_man_change_play_label
0x00102DF0 - 0x00103808     0x00202D70 - 0x00203788     Function:
                                                        bk_mpeg_disp
0x00103810 - 0x00103848     0x00203790 - 0x002037C8     Function:
                                                        bk_mpeg_term
0x00103850 - 0x001039BC     0x002037D0 - 0x0020393C     Function:
                                                        bk_mpeg_play
0x001039C0 - 0x001039E8     0x00203940 - 0x00203968     Function:
                                                        bk_mpeg_play_start
0x001039F0 - 0x00103BA8     0x00203970 - 0x00203B28     Function:
                                                        bk_mpeg_init
0x00103BB0 - 0x00103DDC     0x00203B30 - 0x00203D5C     Function:
                                                        bk_mpeg_SetDecTag
0x00103DE0 - 0x00103F28     0x00203D60 - 0x00203EA8     Function:
                                                        bk_mpeg_work_set
0x00103F30 - 0x001042EC     0x00203EB0 - 0x0020426C     Function:
                                                        bk_disp_title
0x001042F0 - 0x0010431C     0x00204270 - 0x0020429C     Function:
                                                        bk_play_disp_finish
0x00104320 - 0x00104634     0x002042A0 - 0x002045B4     Function:
                                                        bk_play_disp_step
0x00104640 - 0x001046EC     0x002045C0 - 0x0020466C     Function:
                                                        bk_play_disp_init
0x001046F0 - 0x0010472C     0x00204670 - 0x002046AC     Function:
                                                        bk_disp_read_wait
0x00104730 - 0x00104740     0x002046B0 - 0x002046C0     Function:
                                                        bk_disp_read_set
0x00104740 - 0x001050F8     0x002046C0 - 0x00205078     Function:
                                                        CwsObjDisp
0x00105100 - 0x001051EC     0x00205080 - 0x0020516C     Function:
                                                        CwsObjMoveOpt
0x001051F0 - 0x00105300     0x00205170 - 0x00205280     Function:
                                                        CwsObjMove
0x00105300 - 0x00105334     0x00205280 - 0x002052B4     Function:
                                                        CwsObjDelete
0x00105340 - 0x00105368     0x002052C0 - 0x002052E8     Function:
                                                        CwsObjChangeTex
0x00105370 - 0x001053A0     0x002052F0 - 0x00205320     Function:
                                                        CwsObjSetXYWH
0x001053A0 - 0x00105430     0x00205320 - 0x002053B0     Function:
                                                        CwsObjChangePlate
0x00105430 - 0x00105590     0x002053B0 - 0x00205510     Function:
                                                        CwsObjCreate
0x00105590 - 0x00105950     0x00205510 - 0x002058D0     Function:
                                                        CwsStrDigi
0x00105950 - 0x00106140     0x002058D0 - 0x002060C0     Function:
                                                        CwsStrDisp
0x00106140 - 0x001061B8     0x002060C0 - 0x00206138     Function:
                                                        CwsStrSetDispStatus
0x001061C0 - 0x00106224     0x00206140 - 0x002061A4     Function:
                                                        CwsStrAllDelete
0x00106230 - 0x00106298     0x002061B0 - 0x00206218     Function:
                                                        CwsStrDelete
0x001062A0 - 0x0010632C     0x00206220 - 0x002062AC     Function:
                                                        CwsStrSetTex
0x00106330 - 0x001063BC     0x002062B0 - 0x0020633C     Function:
                                                        CwsStrSetFlag
0x001063C0 - 0x0010644C     0x00206340 - 0x002063CC     Function:
                                                        CwsStrSetA
0x00106450 - 0x001064DC     0x002063D0 - 0x0020645C     Function:
                                                        CwsStrSetBri
0x001064E0 - 0x0010656C     0x00206460 - 0x002064EC     Function:
                                                        CwsStrSetCol
0x00106570 - 0x001065FC     0x002064F0 - 0x0020657C     Function:
                                                        CwsStrSetFontType
0x00106600 - 0x0010668C     0x00206580 - 0x0020660C     Function:
                                                        CwsStrSetPri
0x00106690 - 0x0010671C     0x00206610 - 0x0020669C     Function:
                                                        CwsStrSetY
0x00106720 - 0x001067AC     0x002066A0 - 0x0020672C     Function:
                                                        CwsStrSetX
0x001067B0 - 0x00106904     0x00206730 - 0x00206884     Function:
                                                        CwsStrSetStrightString
0x00106910 - 0x001069F8     0x00206890 - 0x00206978     Function:
                                                        CwsStrSetString
0x00106A00 - 0x00106AB0     0x00206980 - 0x00206A30     Function:
                                                        CwsStrClear
0x00106AB0 - 0x00106C98     0x00206A30 - 0x00206C18     Function:
                                                        CwsStrSetStrightAll
0x00106CA0 - 0x00106E00     0x00206C20 - 0x00206D80     Function:
                                                        CwsStrSetAll
0x00106E00 - 0x00106EC8     0x00206D80 - 0x00206E48     Function:
                                                        GetStrFreeWork
0x00106ED0 - 0x00106EDC     0x00206E50 - 0x00206E5C     Function:
                                                        CwsWinDestroy
0x00106EE0 - 0x001073E0     0x00206E60 - 0x00207360     Function:
                                                        CwsWinClose
0x001073E0 - 0x001078E0     0x00207360 - 0x00207860     Function:
                                                        CwsWinOpen
0x001078E0 - 0x00107CAC     0x00207860 - 0x00207C2C     Function:
                                                        cws_win_move_xywh
0x00107CB0 - 0x00107D50     0x00207C30 - 0x00207CD0     Function:
                                                        CwsWinDelete
0x00107D50 - 0x00107DA8     0x00207CD0 - 0x00207D28     Function:
                                                        CwsWinMoveH
0x00107DB0 - 0x00107E08     0x00207D30 - 0x00207D88     Function:
                                                        CwsWinMoveW
0x00107E10 - 0x00107E58     0x00207D90 - 0x00207DD8     Function:
                                                        CwsWinSetRGBA
0x00107E60 - 0x00107E88     0x00207DE0 - 0x00207E08     Function:
                                                        CwsWinSetBri
0x00107E90 - 0x00107EB8     0x00207E10 - 0x00207E38     Function:
                                                        CwsWinSetPri
0x00107EC0 - 0x00107EF0     0x00207E40 - 0x00207E70     Function:
                                                        CwsWinSetWH
0x00107EF0 - 0x00107F20     0x00207E70 - 0x00207EA0     Function:
                                                        CwsWinSetXY
0x00107F20 - 0x00107F50     0x00207EA0 - 0x00207ED0     Function:
                                                        CwsWinDefSetXYWH
0x00107F50 - 0x001080A8     0x00207ED0 - 0x00208028     Function:
                                                        CwsWinCreate
0x001080B0 - 0x001080F0     0x00208030 - 0x00208070     Function:
                                                        CwsWinReflash
0x001080F0 - 0x00108118     0x00208070 - 0x00208098     Function:
                                                        CwsWinSetCode
0x00108120 - 0x001081D0     0x002080A0 - 0x00208150     Function:
                                                        CwsWinGetStatus
0x001081D0 - 0x00108288     0x00208150 - 0x00208208     Function:
                                                        CwsWinsAllDestroy
0x00108290 - 0x0010839C     0x00208210 - 0x0020831C     Function:
                                                        CwsWinsAllGetStatus
0x001083A0 - 0x001083A8     0x00208320 - 0x00208328     Function:
                                                        GetWinsAddr
0x001083B0 - 0x0010871C     0x00208330 - 0x0020869C     Function:
                                                        CwsWins_Func
0x00108720 - 0x0010872C     0x002086A0 - 0x002086AC     Function:
                                                        CwsWinsDelete
0x00108730 - 0x0010892C     0x002086B0 - 0x002088AC     Function:
                                                        CwsWinsCreate
0x00108930 - 0x0010893C     0x002088B0 - 0x002088BC     Function:
                                                        WinsInit
0x00108940 - 0x00108978     0x002088C0 - 0x002088F8     Function:
                                                        CwsWin_MultiSetCautionMark
0x00108980 - 0x00108998     0x00208900 - 0x00208918     Function:
                                                        CwsWin_MultiSetWinClut
0x001089A0 - 0x00108CC0     0x00208920 - 0x00208C40     Function:
                                                        CwsWin_LineDisp
0x00108CC0 - 0x001094A8     0x00208C40 - 0x00209428     Function:
                                                        CwsWin_MultiDisp
0x001094B0 - 0x001094C4     0x00209430 - 0x00209444     Function:
                                                        CwsWin_MultiEnd
0x001094D0 - 0x001096D8     0x00209450 - 0x00209658     Function:
                                                        CwsWin_MultiMain
0x001096E0 - 0x0010979C     0x00209660 - 0x0020971C     Function:
                                                        CwsWin_MultiInit
0x001097A0 - 0x00109A64     0x00209720 - 0x002099E4     Function:
                                                        CwsWin_MultiClose
0x00109A70 - 0x00109E30     0x002099F0 - 0x00209DB0     Function:
                                                        CwsWin_MultiOpen
0x00109E30 - 0x00109E98     0x00209DB0 - 0x00209E18     Function:
                                                        CwsWin_Multi
0x00109EA0 - 0x00109FBC     0x00209E20 - 0x00209F3C     Function:
                                                        MultiWindowSetCautionMark
0x00109FC0 - 0x00109FD8     0x00209F40 - 0x00209F58     Function:
                                                        MultiWindowSetMode
0x00109FE0 - 0x00109FF8     0x00209F60 - 0x00209F78     Function:
                                                        MultiWindowClose
0x0010A000 - 0x0010A018     0x00209F80 - 0x00209F98     Function:
                                                        MultiWindowOpen
0x0010A020 - 0x0010A058     0x00209FA0 - 0x00209FD8     Function:
                                                        MultiWindowDelete
0x0010A060 - 0x0010A1E8     0x00209FE0 - 0x0020A168     Function:
                                                        MultiWindowCreate
0x0010A1F0 - 0x0010A21C     0x0020A170 - 0x0020A19C     Function:
                                                        MultiWindowDestroy
0x0010A220 - 0x0010A228     0x0020A1A0 - 0x0020A1A8     Function:
                                                        MultiWindowCommon
0x0010A230 - 0x0010A264     0x0020A1B0 - 0x0020A1E4     Function:
                                                        MultiWindowInit
0x0010A270 - 0x0010A27C     0x0020A1F0 - 0x0020A1FC     Function:
                                                        ncmesGetNo
0x0010A280 - 0x0010A28C     0x0020A200 - 0x0020A20C     Function:
                                                        ncmesGetYes
0x0010A290 - 0x0010A2C8     0x0020A210 - 0x0020A248     Function:
                                                        ncmesGetMessageTable
0x0010A2D0 - 0x0010A348     0x0020A250 - 0x0020A2C8     Function:
                                                        NetWin_AnySetTexture
0x0010A350 - 0x0010A364     0x0020A2D0 - 0x0020A2E4     Function:
                                                        NetWin_AnyEnd
0x0010A370 - 0x0010A3E0     0x0020A2F0 - 0x0020A360     Function:
                                                        NetWin_AnyMain
0x0010A3E0 - 0x0010A470     0x0020A360 - 0x0020A3F0     Function:
                                                        NetWin_AnyInit
0x0010A470 - 0x0010A4D8     0x0020A3F0 - 0x0020A458     Function:
                                                        NetWin_Any
0x0010A4E0 - 0x0010AAD8     0x0020A460 - 0x0020AA58     Function:
                                                        editmode_music_sel_step
0x0010AAE0 - 0x0010AB50     0x0020AA60 - 0x0020AAD0     Function:
                                                        editmode_music_sel_set
0x0010AB50 - 0x0010B240     0x0020AAD0 - 0x0020B1C0     Function:
                                                        nonstop_music_sel_step
0x0010B240 - 0x0010B294     0x0020B1C0 - 0x0020B214     Function:
                                                        nonstop_music_sel_set
0x0010B2A0 - 0x0010B430     0x0020B220 - 0x0020B3B0     Function:
                                                        fp_ms_get_dnum_info
0x0010B430 - 0x0010B550     0x0020B3B0 - 0x0020B4D0     Function:
                                                        fp_is_step_exist
0x0010B550 - 0x0010B65C     0x0020B4D0 - 0x0020B5DC     Function:
                                                        fp_ms_adj_cur_ud
0x0010B660 - 0x0010B748     0x0020B5E0 - 0x0020B6C8     Function:
                                                        fp_ms_close_abc_kind
0x0010B750 - 0x0010BA04     0x0020B6D0 - 0x0020B984     Function:
                                                        fp_ms_open_abc_kind
0x0010BA10 - 0x0010BB08     0x0020B990 - 0x0020BA88     Function:
                                                        fp_ms_get_abc_kind
0x0010BB10 - 0x0010BBB8     0x0020BA90 - 0x0020BB38     Function:
                                                        fp_ms_set_cur_lr
0x0010BBC0 - 0x0010C2F0     0x0020BB40 - 0x0020C270     Function:
                                                        fp_ms_create_sel_tab
0x0010C2F0 - 0x0010C3A4     0x0020C270 - 0x0020C324     Function:
                                                        fp_msel_get_sn
0x0010C3B0 - 0x0010C40C     0x0020C330 - 0x0020C38C     Function:
                                                        fp_msel_sd_call
0x0010C410 - 0x0010CA90     0x0020C390 - 0x0020CA10     Function:
                                                        fp_ms_roulette
0x0010CA90 - 0x0010CEF4     0x0020CA10 - 0x0020CE74     Function:
                                                        fp_ms_ed_mcard
0x0010CF00 - 0x0010CF80     0x0020CE80 - 0x0020CF00     Function:
                                                        fp_ms_PadRepeat
0x0010CF80 - 0x0010D76C     0x0020CF00 - 0x0020D6EC     Function:
                                                        fp_music_sel_finish_all
0x0010D770 - 0x0010D794     0x0020D6F0 - 0x0020D714     Function:
                                                        fp_music_sel_finish
0x0010D7A0 - 0x0010E988     0x0020D720 - 0x0020E908     Function:
                                                        fp_music_sel_step
0x0010E990 - 0x0010EDEC     0x0020E910 - 0x0020ED6C     Function:
                                                        fp_music_sel_init
0x0010EDF0 - 0x0010F104     0x0020ED70 - 0x0020F084     Function:
                                                        fp_music_sel_init_all
0x0010F110 - 0x0010F118     0x0020F090 - 0x0020F098     Function:
                                                        fp_es_warn_disp
0x0010F120 - 0x0010F128     0x0020F0A0 - 0x0020F0A8     Function:
                                                        fp_es_warn_disap
0x0010F130 - 0x0010F138     0x0020F0B0 - 0x0020F0B8     Function:
                                                        fp_es_warn_exec
0x0010F140 - 0x0010F148     0x0020F0C0 - 0x0020F0C8     Function:
                                                        fp_es_warn_apper
0x0010F150 - 0x0010F294     0x0020F0D0 - 0x0020F214     Function:
                                                        fp_es_item_disp
0x0010F2A0 - 0x0010F4F0     0x0020F220 - 0x0020F470     Function:
                                                        fp_es_item_func
0x0010F4F0 - 0x0010F640     0x0020F470 - 0x0020F5C0     Function:
                                                        fp_eyetoy_sel_finish_all
0x0010F640 - 0x0010F648     0x0020F5C0 - 0x0020F5C8     Function:
                                                        fp_eyetoy_sel_finish
0x0010F650 - 0x0010F89C     0x0020F5D0 - 0x0020F81C     Function:
                                                        fp_eyetoy_sel_step
0x0010F8A0 - 0x0010F8EC     0x0020F820 - 0x0020F86C     Function:
                                                        fp_eyetoy_sel_init
0x0010F8F0 - 0x0010F928     0x0020F870 - 0x0020F8A8     Function:
                                                        fp_eyetoy_sel_init_all
0x0010F930 - 0x0010FA00     0x0020F8B0 - 0x0020F980     Function:
                                                        fp_cs_entry_disp
0x0010FA00 - 0x0010FA64     0x0020F980 - 0x0020F9E4     Function:
                                                        fp_cs_entry_exec
0x0010FA70 - 0x00110334     0x0020F9F0 - 0x002102B4     Function:
                                                        fp_cs_display_disp
0x00110340 - 0x00110348     0x002102C0 - 0x002102C8     Function:
                                                        fp_cs_display_disap
0x00110350 - 0x001103A0     0x002102D0 - 0x00210320     Function:
                                                        fp_cs_display_exec
0x001103A0 - 0x001103C0     0x00210320 - 0x00210340     Function:
                                                        fp_cs_display_apper
0x001103C0 - 0x00111B28     0x00210340 - 0x00211AA8     Function:
                                                        fp_cs_item_disp
0x00111B30 - 0x00111DA0     0x00211AB0 - 0x00211D20     Function:
                                                        fp_cs_item_disap
0x00111DA0 - 0x00111E48     0x00211D20 - 0x00211DC8     Function:
                                                        fp_cs_item_exec
0x00111E50 - 0x00112068     0x00211DD0 - 0x00211FE8     Function:
                                                        fp_cs_item_apper
0x00112070 - 0x00112294     0x00211FF0 - 0x00212214     Function:
                                                        fp_cs_disap
0x001122A0 - 0x001124EC     0x00212220 - 0x0021246C     Function:
                                                        fp_cs_apper
0x001124F0 - 0x00112640     0x00212470 - 0x002125C0     Function:
                                                        fp_set_new_entry
0x00112640 - 0x0011266C     0x002125C0 - 0x002125EC     Function:
                                                        fp_get_doll_num
0x00112670 - 0x0011286C     0x002125F0 - 0x002127EC     Function:
                                                        fp_chara_sel_finish_all
0x00112870 - 0x00112878     0x002127F0 - 0x002127F8     Function:
                                                        fp_chara_sel_finish
0x00112880 - 0x001133BC     0x00212800 - 0x0021333C     Function:
                                                        fp_chara_sel_step
0x001133C0 - 0x0011364C     0x00213340 - 0x002135CC     Function:
                                                        fp_chara_sel_init
0x00113650 - 0x00113700     0x002135D0 - 0x00213680     Function:
                                                        fp_chara_sel_init_all
0x00113700 - 0x001137CC     0x00213680 - 0x0021374C     Function:
                                                        editmode_msel_pre
0x001137D0 - 0x001138C8     0x00213750 - 0x00213848     Function:
                                                        editmode_msel_init
0x001138D0 - 0x00113994     0x00213850 - 0x00213914     Function:
                                                        onlineplay_result_finish
0x001139A0 - 0x00113A60     0x00213920 - 0x002139E0     Function:
                                                        onlineplay_result_step
0x00113A60 - 0x00113D98     0x002139E0 - 0x00213D18     Function:
                                                        onlineplay_result_init
0x00113DA0 - 0x00113DCC     0x00213D20 - 0x00213D4C     Function:
                                                        onlineplay_chara_finish
0x00113DD0 - 0x00113E90     0x00213D50 - 0x00213E10     Function:
                                                        onlineplay_chara_step
0x00113E90 - 0x00114100     0x00213E10 - 0x00214080     Function:
                                                        onlineplay_chara_init
0x00114100 - 0x00114344     0x00214080 - 0x002142C4     Function:
                                                        dmm_freeplay_step
0x00114350 - 0x001143EC     0x002142D0 - 0x0021436C     Function:
                                                        dmm_freeplay_result_load
0x001143F0 - 0x0011483C     0x00214370 - 0x002147BC     Function:
                                                        dmm_freeplay_result_init
0x00114840 - 0x00114948     0x002147C0 - 0x002148C8     Function:
                                                        dmm_freeplay_chara_finish
0x00114950 - 0x00114A4C     0x002148D0 - 0x002149CC     Function:
                                                        dmm_freeplay_chara_load
0x00114A50 - 0x00114E64     0x002149D0 - 0x00214DE4     Function:
                                                        dmm_freeplay_chara_init
0x00114E70 - 0x00114E90     0x00214DF0 - 0x00214E10     Function:
                                                        fp_win_disp_obj
0x00114E90 - 0x00114F58     0x00214E10 - 0x00214ED8     Function:
                                                        fp_display_disp
0x00114F60 - 0x00114F90     0x00214EE0 - 0x00214F10     Function:
                                                        fp_display_disap
0x00114F90 - 0x001153C4     0x00214F10 - 0x00215344     Function:
                                                        fp_display_exec
0x001153D0 - 0x001155D8     0x00215350 - 0x00215558     Function:
                                                        fp_btn_disp
0x001155E0 - 0x001157EC     0x00215560 - 0x0021576C     Function:
                                                        fp_btn_change
0x001157F0 - 0x00115940     0x00215770 - 0x002158C0     Function:
                                                        fp_btn_move
0x00115940 - 0x00115A48     0x002158C0 - 0x002159C8     Function:
                                                        fp_make_enenu_str20
0x00115A50 - 0x00115A6C     0x002159D0 - 0x002159EC     Function:
                                                        fp_OutStrGet
0x00115A70 - 0x00115ADC     0x002159F0 - 0x00215A5C     Function:
                                                        fp_RotTransPersF
0x00115AE0 - 0x00115B0C     0x00215A60 - 0x00215A8C     Function:
                                                        fp_ApplyMatrixXYZ1
0x00115B10 - 0x00115DDC     0x00215A90 - 0x00215D5C     Function:
                                                        fp_pre_end
0x00115DE0 - 0x00115E68     0x00215D60 - 0x00215DE8     Function:
                                                        fp_bind_load_th
0x00115E70 - 0x00115E94     0x00215DF0 - 0x00215E14     Function:
                                                        fp_sel_tex_set
0x00115EA0 - 0x00115F78     0x00215E20 - 0x00215EF8     Function:
                                                        fp_trans_title_th
0x00115F80 - 0x001162CC     0x00215F00 - 0x0021624C     Function:
                                                        fp_prepare
0x001162D0 - 0x001163FC     0x00216250 - 0x0021637C     Function:
                                                        fp_prim_packet_set_sp_col
0x00116400 - 0x00116538     0x00216380 - 0x002164B8     Function:
                                                        fp_prim_packet_set_sp
0x00116540 - 0x001166E0     0x002164C0 - 0x00216660     Function:
                                                        fp_prim_packet_set_f4
0x001166E0 - 0x001168EC     0x00216660 - 0x0021686C     Function:
                                                        fp_prim_packet_set_gt4
0x001168F0 - 0x00116994     0x00216870 - 0x00216914     Function:
                                                        fp_cancel_quit_check
0x001169A0 - 0x00116B44     0x00216920 - 0x00216AC4     Function:
                                                        fp_PadPush
0x00116B50 - 0x00116CF4     0x00216AD0 - 0x00216C74     Function:
                                                        fp_PadTrg
0x00116D00 - 0x00116D84     0x00216C80 - 0x00216D04     Function:
                                                        freeplay_finish
0x00116D90 - 0x00117078     0x00216D10 - 0x00216FF8     Function:
                                                        freeplay_step
0x00117080 - 0x001176CC     0x00217000 - 0x0021764C     Function:
                                                        freeplay_init
0x001176D0 - 0x00117A2C     0x00217650 - 0x002179AC     Function:
                                                        fp_ss_display_disp
0x00117A30 - 0x00117A38     0x002179B0 - 0x002179B8     Function:
                                                        fp_ss_display_disap
0x00117A40 - 0x00117A48     0x002179C0 - 0x002179C8     Function:
                                                        fp_ss_display_apper
0x00117A50 - 0x001186F4     0x002179D0 - 0x00218674     Function:
                                                        fp_ss_item_disp
0x00118700 - 0x001189D4     0x00218680 - 0x00218954     Function:
                                                        fp_ss_item_disap
0x001189E0 - 0x00118B44     0x00218960 - 0x00218AC4     Function:
                                                        fp_ss_item_exec
0x00118B50 - 0x00118E34     0x00218AD0 - 0x00218DB4     Function:
                                                        fp_ss_item_apper
0x00118E40 - 0x001190F4     0x00218DC0 - 0x00219074     Function:
                                                        fp_ss_disap
0x00119100 - 0x00119300     0x00219080 - 0x00219280     Function:
                                                        fp_ss_apper
0x00119300 - 0x00119460     0x00219280 - 0x002193E0     Function:
                                                        fp_style_sel_finish_all
0x00119460 - 0x00119594     0x002193E0 - 0x00219514     Function:
                                                        fp_style_sel_finish
0x001195A0 - 0x001198F0     0x00219520 - 0x00219870     Function:
                                                        fp_style_sel_step
0x001198F0 - 0x001199C8     0x00219870 - 0x00219948     Function:
                                                        fp_style_sel_init
0x001199D0 - 0x00119A38     0x00219950 - 0x002199B8     Function:
                                                        fp_style_sel_init_all
0x00119A40 - 0x00119EC0     0x002199C0 - 0x00219E40     Function:
                                                        endless_rs_score_disp
0x00119EC0 - 0x0011A32C     0x00219E40 - 0x0021A2AC     Function:
                                                        nonstop_rs_score_disp
0x0011A330 - 0x0011A660     0x0021A2B0 - 0x0021A5E0     Function:
                                                        adv_rs_utime_disp
0x0011A660 - 0x0011A814     0x0021A5E0 - 0x0021A794     Function:
                                                        adv_rs_frame_disp
0x0011A820 - 0x0011AB40     0x0021A7A0 - 0x0021AAC0     Function:
                                                        adv_endless_number_disp
0x0011AB40 - 0x0011AC20     0x0021AAC0 - 0x0021ABA0     Function:
                                                        fp_rs_btn_disp
0x0011AC20 - 0x0011AD20     0x0021ABA0 - 0x0021ACA0     Function:
                                                        fp_rs_btn_move
0x0011AD20 - 0x0011BAF4     0x0021ACA0 - 0x0021BA74     Function:
                                                        fp_rs_score_disp
0x0011BB00 - 0x0011BB08     0x0021BA80 - 0x0021BA88     Function:
                                                        fp_rs_score_disap
0x0011BB10 - 0x0011C168     0x0021BA90 - 0x0021C0E8     Function:
                                                        fp_rs_score_func
0x0011C170 - 0x0011C4DC     0x0021C0F0 - 0x0021C45C     Function:
                                                        fp_rs_point_disp
0x0011C4E0 - 0x0011C5E0     0x0021C460 - 0x0021C560     Function:
                                                        fp_rs_point_move
0x0011C5E0 - 0x0011CC94     0x0021C560 - 0x0021CC14     Function:
                                                        fp_rs_value_disp
0x0011CCA0 - 0x0011CCA8     0x0021CC20 - 0x0021CC28     Function:
                                                        fp_rs_value_exec
0x0011CCB0 - 0x0011CDF8     0x0021CC30 - 0x0021CD78     Function:
                                                        fp_rs_value_disap
0x0011CE00 - 0x0011CF28     0x0021CD80 - 0x0021CEA8     Function:
                                                        fp_rs_value_apper
0x0011CF30 - 0x0011D9E8     0x0021CEB0 - 0x0021D968     Function:
                                                        fp_rs_base_disp
0x0011D9F0 - 0x0011E430     0x0021D970 - 0x0021E3B0     Function:
                                                        fp_rs_base_func
0x0011E430 - 0x0011E620     0x0021E3B0 - 0x0021E5A0     Function:
                                                        fp_rs_cs00_disp
0x0011E620 - 0x0011EB88     0x0021E5A0 - 0x0021EB08     Function:
                                                        fp_rs_meter_disp
0x0011EB90 - 0x0011EF78     0x0021EB10 - 0x0021EEF8     Function:
                                                        fp_rs_utime_disp
0x0011EF80 - 0x0011F598     0x0021EF00 - 0x0021F518     Function:
                                                        fp_rs_number_disp
0x0011F5A0 - 0x0011F8DC     0x0021F520 - 0x0021F85C     Function:
                                                        fp_rs_line_square_disp
0x0011F8E0 - 0x0011FAA0     0x0021F860 - 0x0021FA20     Function:
                                                        fp_rs_ujudge_disp
0x0011FAA0 - 0x0011FD60     0x0021FA20 - 0x0021FCE0     Function:
                                                        fp_rs_uname_disp
0x0011FD60 - 0x0011FED4     0x0021FCE0 - 0x0021FE54     Function:
                                                        fp_rs_disap
0x0011FEE0 - 0x001200AC     0x0021FE60 - 0x0022002C     Function:
                                                        fp_rs_apper
0x001200B0 - 0x001200B8     0x00220030 - 0x00220038     Function:
                                                        fp_result_finish_all
0x001200C0 - 0x001200C8     0x00220040 - 0x00220048     Function:
                                                        fp_result_finish
0x001200D0 - 0x0012037C     0x00220050 - 0x002202FC     Function:
                                                        fp_result_step
0x00120380 - 0x00120BA8     0x00220300 - 0x00220B28     Function:
                                                        fp_result_init
0x00120BB0 - 0x00120E6C     0x00220B30 - 0x00220DEC     Function:
                                                        fp_result_init_all
0x00120E70 - 0x00120F3C     0x00220DF0 - 0x00220EBC     Function:
                                                        fp_so_win_disap
0x00120F40 - 0x00121078     0x00220EC0 - 0x00220FF8     Function:
                                                        fp_so_win_exec
0x00121080 - 0x0012134C     0x00221000 - 0x002212CC     Function:
                                                        fp_so_win_apper
0x00121350 - 0x001219B8     0x002212D0 - 0x00221938     Function:
                                                        fp_so_item_one_disp
0x001219C0 - 0x00121BB8     0x00221940 - 0x00221B38     Function:
                                                        fp_so_line_disp
0x00121BC0 - 0x001228DC     0x00221B40 - 0x0022285C     Function:
                                                        fp_so_item_disp
0x001228E0 - 0x00122984     0x00222860 - 0x00222904     Function:
                                                        fp_so_item_disap
0x00122990 - 0x00122A10     0x00222910 - 0x00222990     Function:
                                                        fp_so_item_exec
0x00122A10 - 0x00122C2C     0x00222990 - 0x00222BAC     Function:
                                                        fp_so_item_apper
0x00122C30 - 0x00122D94     0x00222BB0 - 0x00222D14     Function:
                                                        fp_so_disap
0x00122DA0 - 0x00122EA8     0x00222D20 - 0x00222E28     Function:
                                                        fp_so_apper
0x00122EB0 - 0x00123110     0x00222E30 - 0x00223090     Function:
                                                        fp_sel_option_finish_all
0x00123110 - 0x001231E0     0x00223090 - 0x00223160     Function:
                                                        fp_sel_option_finish
0x001231E0 - 0x00123B68     0x00223160 - 0x00223AE8     Function:
                                                        fp_sel_option_step
0x00123B70 - 0x00123D74     0x00223AF0 - 0x00223CF4     Function:
                                                        fp_sel_option_init
0x00123D80 - 0x00124018     0x00223D00 - 0x00223F98     Function:
                                                        fp_sel_option_init_all
0x00124020 - 0x00124074     0x00223FA0 - 0x00223FF4     Function:
                                                        NetWin_MenuSetSelect
0x00124080 - 0x001241D0     0x00224000 - 0x00224150     Function:
                                                        NetWin_MenuSetFont
0x001241D0 - 0x001241E4     0x00224150 - 0x00224164     Function:
                                                        NetWin_MenuEnd
0x001241F0 - 0x001241F8     0x00224170 - 0x00224178     Function:
                                                        NetWin_MenuMain
0x00124200 - 0x0012427C     0x00224180 - 0x002241FC     Function:
                                                        NetWin_MenuInit
0x00124280 - 0x001242E8     0x00224200 - 0x00224268     Function:
                                                        NetWin_Menu
0x001242F0 - 0x001243B0     0x00224270 - 0x00224330     Function:
                                                        NetSysEnd
0x001243B0 - 0x001245FC     0x00224330 - 0x0022457C     Function:
                                                        NetSysInit
0x00124600 - 0x00124790     0x00224580 - 0x00224710     Function:
                                                        NetSysMenuSelectKey
0x00124790 - 0x00124B48     0x00224710 - 0x00224AC8     Function:
                                                        NetSysMenuMain
0x00124B50 - 0x00124DBC     0x00224AD0 - 0x00224D3C     Function:
                                                        NetSysMenuInit2
0x00124DC0 - 0x00125034     0x00224D40 - 0x00224FB4     Function:
                                                        NetSysMenuInit
0x00125040 - 0x00125128     0x00224FC0 - 0x002250A8     Function:
                                                        NetSysNewInitKeyborad
0x00125130 - 0x00125554     0x002250B0 - 0x002254D4     Function:
                                                        NetSysNewKey
0x00125560 - 0x00125BE0     0x002254E0 - 0x00225B60     Function:
                                                        NetSysNewMain
0x00125BE0 - 0x00125CD8     0x00225B60 - 0x00225C58     Function:
                                                        NetSysNewInit
0x00125CE0 - 0x00125F28     0x00225C60 - 0x00225EA8     Function:
                                                        NetSysTopKey
0x00125F30 - 0x00126400     0x00225EB0 - 0x00226380     Function:
                                                        NetSysTopMain
0x00126400 - 0x0012667C     0x00226380 - 0x002265FC     Function:
                                                        NetSysTopInit2
0x00126680 - 0x001268F4     0x00226600 - 0x00226874     Function:
                                                        NetSysTopInit
0x00126900 - 0x0012693C     0x00226880 - 0x002268BC     Function:
                                                        NetSysUserConnect
0x00126940 - 0x00126AC8     0x002268C0 - 0x00226A48     Function:
                                                        NetSysUserSelKey
0x00126AD0 - 0x00126C78     0x00226A50 - 0x00226BF8     Function:
                                                        NetSysUserKey
0x00126C80 - 0x00126FBC     0x00226C00 - 0x00226F3C     Function:
                                                        NetSysUserSelMain
0x00126FC0 - 0x001271B4     0x00226F40 - 0x00227134     Function:
                                                        NetSysUserSelInit
0x001271C0 - 0x00127418     0x00227140 - 0x00227398     Function:
                                                        NetSysUserMain
0x00127420 - 0x00127520     0x002273A0 - 0x002274A0     Function:
                                                        NetSysUserInit_Sel
0x00127520 - 0x00127800     0x002274A0 - 0x00227780     Function:
                                                        NetSysUserInit2
0x00127800 - 0x00127B1C     0x00227780 - 0x00227A9C     Function:
                                                        NetSysUserInit
0x00127B20 - 0x00127C48     0x00227AA0 - 0x00227BC8     Function:
                                                        NetSysRuleSelectKey
0x00127C50 - 0x00127DFC     0x00227BD0 - 0x00227D7C     Function:
                                                        NetSysRuleKey
0x00127E00 - 0x001281B4     0x00227D80 - 0x00228134     Function:
                                                        NetSysRuleMain
0x001281C0 - 0x00128310     0x00228140 - 0x00228290     Function:
                                                        NetSysRuleInit
0x00128310 - 0x00128568     0x00228290 - 0x002284E8     Function:
                                                        NetSysRuleStartInit
0x00128570 - 0x00128630     0x002284F0 - 0x002285B0     Function:
                                                        NetSysConnectMain
0x00128630 - 0x00128640     0x002285B0 - 0x002285C0     Function:
                                                        NetSysConnectInit
0x00128640 - 0x0012885C     0x002285C0 - 0x002287DC     Function:
                                                        NetSysInfoDispKey
0x00128860 - 0x001289E0     0x002287E0 - 0x00228960     Function:
                                                        NetSysInfoDispMain
0x001289E0 - 0x00128B40     0x00228960 - 0x00228AC0     Function:
                                                        NetSysInfoDispInit
0x00128B40 - 0x00128D28     0x00228AC0 - 0x00228CA8     Function:
                                                        NetSysInfoKey
0x00128D30 - 0x001290CC     0x00228CB0 - 0x0022904C     Function:
                                                        NetSysInfoMain
0x001290D0 - 0x0012945C     0x00229050 - 0x002293DC     Function:
                                                        NetSysInfoInit
0x00129460 - 0x00129478     0x002293E0 - 0x002293F8     Function:
                                                        dmm_data_get_change_music_speed
0x00129480 - 0x00129730     0x00229400 - 0x002296B0     Function:
                                                        dmm_data_convert_play_mode
0x00129730 - 0x00129744     0x002296B0 - 0x002296C4     Function:
                                                        dmm_get_extra_arrow_data
0x00129750 - 0x001297B0     0x002296D0 - 0x00229730     Function:
                                                        dmm_get_boss_No
0x001297B0 - 0x001297E4     0x00229730 - 0x00229764     Function:
                                                        dmm_data_get_subject_dat
0x001297F0 - 0x00129840     0x00229770 - 0x002297C0     Function:
                                                        dmm_clear_route
0x00129840 - 0x00129898     0x002297C0 - 0x00229818     Function:
                                                        dmm_set_route
0x001298A0 - 0x00129910     0x00229820 - 0x00229890     Function:
                                                        dmm_is_default_connect_appear_ok
0x00129910 - 0x00129BC8     0x00229890 - 0x00229B48     Function:
                                                        dmm_set_connect_sbj_state_playable
0x00129BD0 - 0x00129C58     0x00229B50 - 0x00229BD8     Function:
                                                        dmm_is_change_chart_ok
0x00129C60 - 0x00129D40     0x00229BE0 - 0x00229CC0     Function:
                                                        dmm_is_sbj_allclear_expect_for_lastboss
0x00129D40 - 0x00129DC0     0x00229CC0 - 0x00229D40     Function:
                                                        dmm_is_area_boss_allclear
0x00129DC0 - 0x00129E14     0x00229D40 - 0x00229D94     Function:
                                                        dmm_get_clear_sbj_num
0x00129E20 - 0x00129E74     0x00229DA0 - 0x00229DF4     Function:
                                                        dmm_search_appear_area
0x00129E80 - 0x00129EE0     0x00229E00 - 0x00229E60     Function:
                                                        dmm_get_subject_area_no
0x00129EE0 - 0x00129F00     0x00229E60 - 0x00229E80     Function:
                                                        dmm_get_subject_area
0x00129F00 - 0x00129F38     0x00229E80 - 0x00229EB8     Function:
                                                        dmm_get_all_sbj_num
0x00129F40 - 0x00129F5C     0x00229EC0 - 0x00229EDC     Function:
                                                        dmm_get_subject_w
0x00129F60 - 0x0012A140     0x00229EE0 - 0x0022A0C0     Function:
                                                        dmm_disp_th
0x0012A140 - 0x0012A34C     0x0022A0C0 - 0x0022A2CC     Function:
                                                        dmm_disp_bk
0x0012A350 - 0x0012A378     0x0022A2D0 - 0x0022A2F8     Function:
                                                        dmm_is_sys_fade_out
0x0012A380 - 0x0012A3CC     0x0022A300 - 0x0022A34C     Function:
                                                        dmm_is_sys_fade_off
0x0012A3D0 - 0x0012A5B4     0x0022A350 - 0x0022A534     Function:
                                                        dmm_sys_fade
0x0012A5C0 - 0x0012A620     0x0022A540 - 0x0022A5A0     Function:
                                                        dmm_sys_fade_set
0x0012A620 - 0x0012A648     0x0022A5A0 - 0x0022A5C8     Function:
                                                        dmm_sys_fade_out_init
0x0012A650 - 0x0012A678     0x0022A5D0 - 0x0022A5F8     Function:
                                                        dmm_sys_fade_in_init
0x0012A680 - 0x0012A6B8     0x0022A600 - 0x0022A638     Function:
                                                        dmm_sys_fade_init
0x0012A6C0 - 0x0012AC8C     0x0022A640 - 0x0022AC0C     Function:
                                                        dmm_disp_button
0x0012AC90 - 0x0012B050     0x0022AC10 - 0x0022AFD0     Function:
                                                        dmm_disp_area_sign
0x0012B050 - 0x0012B3C4     0x0022AFD0 - 0x0022B344     Function:
                                                        dmm_disp_title
0x0012B3D0 - 0x0012B538     0x0022B350 - 0x0022B4B8     Function:
                                                        dmm_calc_max_bar
0x0012B540 - 0x0012B614     0x0022B4C0 - 0x0022B594     Function:
                                                        dmm_init_work
0x0012B620 - 0x0012B810     0x0022B5A0 - 0x0022B790     Function:
                                                        dmm_init
0x0012B810 - 0x0012B870     0x0022B790 - 0x0022B7F0     Function:
                                                        dmm_get_back_step
0x0012B870 - 0x0012B8F0     0x0022B7F0 - 0x0022B870     Function:
                                                        dmm_get_next_step
0x0012B8F0 - 0x0012B95C     0x0022B870 - 0x0022B8DC     Function:
                                                        dmm_set_step
0x0012B960 - 0x0012B968     0x0022B8E0 - 0x0022B8E8     Function:
                                                        dmm_get_work
0x0012B970 - 0x0012B994     0x0022B8F0 - 0x0022B914     Function:
                                                        DanceMasterFinish
0x0012B9A0 - 0x0012BA88     0x0022B920 - 0x0022BA08     Function:
                                                        DanceMasterStep
0x0012BA90 - 0x0012BACC     0x0022BA10 - 0x0022BA4C     Function:
                                                        DanceMasterInit
0x0012BAD0 - 0x0012BB00     0x0022BA50 - 0x0022BA80     Function:
                                                        ComKeyBoardIsAvailableKey
0x0012BB00 - 0x0012BCC8     0x0022BA80 - 0x0022BC48     Function:
                                                        ComKeyBoardGetCode
0x0012BCD0 - 0x0012C528     0x0022BC50 - 0x0022C4A8     Function:
                                                        ComKeyBoardDisp
0x0012C530 - 0x0012C698     0x0022C4B0 - 0x0022C618     Function:
                                                        NetSysLogoutKey
0x0012C6A0 - 0x0012CBD4     0x0022C620 - 0x0022CB54     Function:
                                                        NetSysLogoutMain
0x0012CBE0 - 0x0012CD6C     0x0022CB60 - 0x0022CCEC     Function:
                                                        NetSysLogoutInit
0x0012CD70 - 0x0012CDA0     0x0022CCF0 - 0x0022CD20     Function:
                                                        NetWin_SuserSetEntryMode
0x0012CDA0 - 0x0012CDA8     0x0022CD20 - 0x0022CD28     Function:
                                                        NetWin_SuserSetUserFile
0x0012CDB0 - 0x0012CE30     0x0022CD30 - 0x0022CDB0     Function:
                                                        NetWin_SuserSetSelect
0x0012CE30 - 0x0012CE84     0x0022CDB0 - 0x0022CE04     Function:
                                                        NetWin_SuserSetNum
0x0012CE90 - 0x0012CEA4     0x0022CE10 - 0x0022CE24     Function:
                                                        NetWin_SuserEnd
0x0012CEB0 - 0x0012D2AC     0x0022CE30 - 0x0022D22C     Function:
                                                        NetWin_SuserMain
0x0012D2B0 - 0x0012D630     0x0022D230 - 0x0022D5B0     Function:
                                                        NetWin_SuserInit
0x0012D630 - 0x0012D698     0x0022D5B0 - 0x0022D618     Function:
                                                        NetWin_Suser
0x0012D6A0 - 0x0012D730     0x0022D620 - 0x0022D6B0     Function:
                                                        NetWin_TabSetOff
0x0012D730 - 0x0012D788     0x0022D6B0 - 0x0022D708     Function:
                                                        NetWin_TabSetOn
0x0012D790 - 0x0012D83C     0x0022D710 - 0x0022D7BC     Function:
                                                        NetWin_TabSetSelect
0x0012D840 - 0x0012D854     0x0022D7C0 - 0x0022D7D4     Function:
                                                        NetWin_TabEnd
0x0012D860 - 0x0012D9A0     0x0022D7E0 - 0x0022D920     Function:
                                                        NetWin_TabMain
0x0012D9A0 - 0x0012DA30     0x0022D920 - 0x0022D9B0     Function:
                                                        NetWin_TabInit
0x0012DA30 - 0x0012DA98     0x0022D9B0 - 0x0022DA18     Function:
                                                        NetWin_Tab
0x0012DAA0 - 0x0012DB20     0x0022DA20 - 0x0022DAA0     Function:
                                                        NetWin_WatchSetRestTime
0x0012DB20 - 0x0012DB50     0x0022DAA0 - 0x0022DAD0     Function:
                                                        NetWin_WatchSetWeek
0x0012DB50 - 0x0012DB64     0x0022DAD0 - 0x0022DAE4     Function:
                                                        NetWin_WatchEnd
0x0012DB70 - 0x0012DCB8     0x0022DAF0 - 0x0022DC38     Function:
                                                        NetWin_WatchMain
0x0012DCC0 - 0x0012DDE8     0x0022DC40 - 0x0022DD68     Function:
                                                        NetWin_WatchInit
0x0012DDF0 - 0x0012DE58     0x0022DD70 - 0x0022DDD8     Function:
                                                        NetWin_Watch
0x0012DE60 - 0x0012DE88     0x0022DDE0 - 0x0022DE08     Function:
                                                        NetWin_SearchType
0x0012DE90 - 0x0012E368     0x0022DE10 - 0x0022E2E8     Function:
                                                        NetWin_RotDisp
0x0012E370 - 0x0012E384     0x0022E2F0 - 0x0022E304     Function:
                                                        NetWin_SearchEnd
0x0012E390 - 0x0012E5E8     0x0022E310 - 0x0022E568     Function:
                                                        NetWin_SearchMain
0x0012E5F0 - 0x0012E750     0x0022E570 - 0x0022E6D0     Function:
                                                        NetWin_SearchInit
0x0012E750 - 0x0012E7B8     0x0022E6D0 - 0x0022E738     Function:
                                                        NetWin_Search
0x0012E7C0 - 0x0012EBB0     0x0022E740 - 0x0022EB30     Function:
                                                        NetWin_ItemSetSelect
0x0012EBB0 - 0x0012EDE0     0x0022EB30 - 0x0022ED60     Function:
                                                        NetWin_ItemSetType
0x0012EDE0 - 0x0012EDF4     0x0022ED60 - 0x0022ED74     Function:
                                                        NetWin_ItemEnd
0x0012EE00 - 0x0012EE08     0x0022ED80 - 0x0022ED88     Function:
                                                        NetWin_ItemMain
0x0012EE10 - 0x0012EED0     0x0022ED90 - 0x0022EE50     Function:
                                                        NetWin_ItemInit
0x0012EED0 - 0x0012EF38     0x0022EE50 - 0x0022EEB8     Function:
                                                        NetWin_Item
0x0012EF40 - 0x0012EF48     0x0022EEC0 - 0x0022EEC8     Function:
                                                        NetWin_UserSetUserFile
0x0012EF50 - 0x0012F298     0x0022EED0 - 0x0022F218     Function:
                                                        NetWin_UserBoardDisp
0x0012F2A0 - 0x0012F2B4     0x0022F220 - 0x0022F234     Function:
                                                        NetWin_UserEnd
0x0012F2C0 - 0x0012F4B0     0x0022F240 - 0x0022F430     Function:
                                                        NetWin_UserMain
0x0012F4B0 - 0x0012F7E4     0x0022F430 - 0x0022F764     Function:
                                                        NetWin_UserInit
0x0012F7F0 - 0x0012F858     0x0022F770 - 0x0022F7D8     Function:
                                                        NetWin_User
0x0012F860 - 0x0012F9D0     0x0022F7E0 - 0x0022F950     Function:
                                                        ndmesMakeDNASErrorMessage
0x0012F9D0 - 0x0012FA08     0x0022F950 - 0x0022F988     Function:
                                                        ndmesGetMessageTable
0x0012FA10 - 0x0012FC0C     0x0022F990 - 0x0022FB8C     Function:
                                                        fp_foot_panel_disp
0x0012FC10 - 0x0012FCE0     0x0022FB90 - 0x0022FC60     Function:
                                                        fp_foot_panel_disap
0x0012FCE0 - 0x0012FD10     0x0022FC60 - 0x0022FC90     Function:
                                                        fp_foot_panel_exec
0x0012FD10 - 0x0012FE10     0x0022FC90 - 0x0022FD90     Function:
                                                        fp_foot_panel_apper
0x0012FE10 - 0x0013003C     0x0022FD90 - 0x0022FFBC     Function:
                                                        fp_doll_disp
0x00130040 - 0x001300F0     0x0022FFC0 - 0x00230070     Function:
                                                        fp_doll_exec
0x001300F0 - 0x00130244     0x00230070 - 0x002301C4     Function:
                                                        fp_doll_set_pos
0x00130250 - 0x00130394     0x002301D0 - 0x00230314     Function:
                                                        fp_doll_fpanel_update
0x001303A0 - 0x0013046C     0x00230320 - 0x002303EC     Function:
                                                        fp_doll_cam_set
0x00130470 - 0x00130580     0x002303F0 - 0x00230500     Function:
                                                        fp_doll_load
0x00130580 - 0x001305C0     0x00230500 - 0x00230540     Function:
                                                        fp_doll_init
0x001305C0 - 0x001305E8     0x00230540 - 0x00230568     Function:
                                                        co_obj_all_del
0x001305F0 - 0x001305F8     0x00230570 - 0x00230578     Function:
                                                        co_obj_own_step
0x00130600 - 0x00130608     0x00230580 - 0x00230588     Function:
                                                        co_obj_step
0x00130610 - 0x00130618     0x00230590 - 0x00230598     Function:
                                                        co_obj_disp_on_off
0x00130620 - 0x0013064C     0x002305A0 - 0x002305CC     Function:
                                                        co_obj_step_set
0x00130650 - 0x00130678     0x002305D0 - 0x002305F8     Function:
                                                        co_obj_is_exist
0x00130680 - 0x00130688     0x00230600 - 0x00230608     Function:
                                                        co_obj_get_id
0x00130690 - 0x00130698     0x00230610 - 0x00230618     Function:
                                                        co_obj_work_p
0x001306A0 - 0x001306A8     0x00230620 - 0x00230628     Function:
                                                        co_obj_own_ini_flag
0x001306B0 - 0x001306B8     0x00230630 - 0x00230638     Function:
                                                        co_obj_ini_flag
0x001306C0 - 0x00130740     0x00230640 - 0x002306C0     Function:
                                                        co_obj_del
0x00130740 - 0x001308C4     0x002306C0 - 0x00230844     Function:
                                                        co_obj_set
0x001308D0 - 0x00130950     0x00230850 - 0x002308D0     Function:
                                                        co_obj_disp
0x00130950 - 0x00130A70     0x002308D0 - 0x002309F0     Function:
                                                        co_obj_exec
0x00130A70 - 0x00130AD0     0x002309F0 - 0x00230A50     Function:
                                                        co_obj_init
0x00130AD0 - 0x00130B04     0x00230A50 - 0x00230A84     Function:
                                                        co_disp_all_init
0x00130B10 - 0x00130D30     0x00230A90 - 0x00230CB0     Function:
                                                        co_sel00_disp
0x00130D30 - 0x00130E9C     0x00230CB0 - 0x00230E1C     Function:
                                                        co_sel00_move
0x00130EA0 - 0x00130F04     0x00230E20 - 0x00230E84     Function:
                                                        co_sel00_x
0x00130F10 - 0x00130F4C     0x00230E90 - 0x00230ECC     Function:
                                                        co_sel00_is_exist
0x00130F50 - 0x00130F7C     0x00230ED0 - 0x00230EFC     Function:
                                                        co_sel00_is_apper_end
0x00130F80 - 0x00130FF8     0x00230F00 - 0x00230F78     Function:
                                                        co_sel00_disap_set
0x00131000 - 0x00131080     0x00230F80 - 0x00231000     Function:
                                                        co_base00_set
0x00131080 - 0x001310F4     0x00231000 - 0x00231074     Function:
                                                        co_sel00_set
0x00131100 - 0x00131438     0x00231080 - 0x002313B8     Function:
                                                        co_caption_disp
0x00131440 - 0x001314D0     0x002313C0 - 0x00231450     Function:
                                                        co_caption_move
0x001314D0 - 0x0013150C     0x00231450 - 0x0023148C     Function:
                                                        co_caption_is_exist
0x00131510 - 0x0013153C     0x00231490 - 0x002314BC     Function:
                                                        co_caption_is_apper_end
0x00131540 - 0x001315A0     0x002314C0 - 0x00231520     Function:
                                                        co_caption_del
0x001315A0 - 0x00131608     0x00231520 - 0x00231588     Function:
                                                        co_caption_disap
0x00131610 - 0x0013161C     0x00231590 - 0x0023159C     Function:
                                                        co_caption_tex_id_set
0x00131620 - 0x001316A4     0x002315A0 - 0x00231624     Function:
                                                        co_caption_set
0x001316B0 - 0x001316F8     0x00231630 - 0x00231678     Function:
                                                        NetWin_RcnameSetOption
0x00131700 - 0x00131714     0x00231680 - 0x00231694     Function:
                                                        NetWin_RcnameSetMax
0x00131720 - 0x00131734     0x002316A0 - 0x002316B4     Function:
                                                        NetWin_RcnameSetNow
0x00131740 - 0x00131754     0x002316C0 - 0x002316D4     Function:
                                                        NetWin_RcnameSetName
0x00131760 - 0x001317D8     0x002316E0 - 0x00231758     Function:
                                                        NetWin_RcnameSetCursor
0x001317E0 - 0x00131840     0x00231760 - 0x002317C0     Function:
                                                        NetWin_RcnameSetType
0x00131840 - 0x00131854     0x002317C0 - 0x002317D4     Function:
                                                        NetWin_RcnameEnd
0x00131860 - 0x001318F0     0x002317E0 - 0x00231870     Function:
                                                        NetWin_RcnameMain
0x001318F0 - 0x00131A98     0x00231870 - 0x00231A18     Function:
                                                        NetWin_RcnameInit
0x00131AA0 - 0x00131B08     0x00231A20 - 0x00231A88     Function:
                                                        NetWin_Rcname
0x00131B10 - 0x00131B48     0x00231A90 - 0x00231AC8     Function:
                                                        npGetUseDancerNum
0x00131B50 - 0x00131B5C     0x00231AD0 - 0x00231ADC     Function:
                                                        npGetResultDataAddr
0x00131B60 - 0x00131B6C     0x00231AE0 - 0x00231AEC     Function:
                                                        npGetPlayDataAddr
0x00131B70 - 0x00131B7C     0x00231AF0 - 0x00231AFC     Function:
                                                        npGetAfterSyncState
0x00131B80 - 0x00131B8C     0x00231B00 - 0x00231B0C     Function:
                                                        npSetAfterSyncState
0x00131B90 - 0x00131B9C     0x00231B10 - 0x00231B1C     Function:
                                                        npGetBeforeSyncState
0x00131BA0 - 0x00131BAC     0x00231B20 - 0x00231B2C     Function:
                                                        npSetBeforeSyncState
0x00131BB0 - 0x00131BBC     0x00231B30 - 0x00231B3C     Function:
                                                        npGetAfterSyncFlag
0x00131BC0 - 0x00131BCC     0x00231B40 - 0x00231B4C     Function:
                                                        npSetAfterSyncFlag
0x00131BD0 - 0x00131BDC     0x00231B50 - 0x00231B5C     Function:
                                                        npGetBeforeSyncFlag
0x00131BE0 - 0x00131BEC     0x00231B60 - 0x00231B6C     Function:
                                                        npSetBeforeSyncFlag
0x00131BF0 - 0x00131BFC     0x00231B70 - 0x00231B7C     Function:
                                                        npGetForceClearFlag
0x00131C00 - 0x00131C0C     0x00231B80 - 0x00231B8C     Function:
                                                        npSetForceClearFlag
0x00131C10 - 0x00131C38     0x00231B90 - 0x00231BB8     Function:
                                                        TermNetRankPlay
0x00131C40 - 0x00131D5C     0x00231BC0 - 0x00231CDC     Function:
                                                        MainNetRankPlay
0x00131D60 - 0x00131F38     0x00231CE0 - 0x00231EB8     Function:
                                                        InitNetRankPlay
0x00131F40 - 0x00131F6C     0x00231EC0 - 0x00231EEC     Function:
                                                        TermNetPlay
0x00131F70 - 0x0013208C     0x00231EF0 - 0x0023200C     Function:
                                                        MainNetPlay
0x00132090 - 0x0013226C     0x00232010 - 0x002321EC     Function:
                                                        InitNetPlay
0x00132270 - 0x00132FC0     0x002321F0 - 0x00232F40     Function:
                                                        NetGameVsPlay
0x00132FC0 - 0x0013342C     0x00232F40 - 0x002333AC     Function:
                                                        NetGameVsSetup
0x00133430 - 0x00133944     0x002333B0 - 0x002338C4     Function:
                                                        NetGameVsMain
0x00133950 - 0x00133C58     0x002338D0 - 0x00233BD8     Function:
                                                        NetGameVsInit
0x00133C60 - 0x00133CC8     0x00233BE0 - 0x00233C48     Function:
                                                        NetGameVsInitForWin
0x00133CD0 - 0x00133D78     0x00233C50 - 0x00233CF8     Function:
                                                        fp_ms_edmc_msg_disp
0x00133D80 - 0x001340D8     0x00233D00 - 0x00234058     Function:
                                                        fp_ms_edmc_msg_func
0x001340E0 - 0x001341D0     0x00234060 - 0x00234150     Function:
                                                        fp_ms_entry_disp
0x001341D0 - 0x00134234     0x00234150 - 0x002341B4     Function:
                                                        fp_ms_entry_exec
0x00134240 - 0x00134360     0x002341C0 - 0x002342E0     Function:
                                                        fp_ms_base_disp
0x00134360 - 0x001343E0     0x002342E0 - 0x00234360     Function:
                                                        fp_ms_base_disap
0x001343E0 - 0x00134468     0x00234360 - 0x002343E8     Function:
                                                        fp_ms_base_apper
0x00134470 - 0x001347D8     0x002343F0 - 0x00234758     Function:
                                                        fp_ms_scbar_disp
0x001347E0 - 0x00134880     0x00234760 - 0x00234800     Function:
                                                        fp_ms_scbar_alpha
0x00134880 - 0x00134E48     0x00234800 - 0x00234DC8     Function:
                                                        fp_ms_sort_disp
0x00134E50 - 0x00134E58     0x00234DD0 - 0x00234DD8     Function:
                                                        fp_ms_sort_exec
0x00134E60 - 0x00134F68     0x00234DE0 - 0x00234EE8     Function:
                                                        fp_ms_sort_move
0x00134F70 - 0x00134FB4     0x00234EF0 - 0x00234F34     Function:
                                                        fp_ms_entry_opt_set
0x00134FC0 - 0x00135374     0x00234F40 - 0x002352F4     Function:
                                                        fp_ms_option_disp
0x00135380 - 0x0013556C     0x00235300 - 0x002354EC     Function:
                                                        fp_ms_option_disap
0x00135570 - 0x001357E8     0x002354F0 - 0x00235768     Function:
                                                        fp_ms_option_exec
0x001357F0 - 0x00135A3C     0x00235770 - 0x002359BC     Function:
                                                        fp_ms_option_apper
0x00135A40 - 0x001365D8     0x002359C0 - 0x00236558     Function:
                                                        fp_ms_radar_disp
0x001365E0 - 0x00136670     0x00236560 - 0x002365F0     Function:
                                                        fp_ms_radar_disap
0x00136670 - 0x00136884     0x002365F0 - 0x00236804     Function:
                                                        fp_ms_radar_exec
0x00136890 - 0x001369CC     0x00236810 - 0x0023694C     Function:
                                                        fp_ms_radar_apper
0x001369D0 - 0x001370D0     0x00236950 - 0x00237050     Function:
                                                        fp_ms_banner_one_disp
0x001370D0 - 0x001371E0     0x00237050 - 0x00237160     Function:
                                                        fp_ms_display_disp
0x001371E0 - 0x001371E8     0x00237160 - 0x00237168     Function:
                                                        fp_ms_display_disap
0x001371F0 - 0x001374DC     0x00237170 - 0x0023745C     Function:
                                                        fp_ms_display_exec
0x001374E0 - 0x0013753C     0x00237460 - 0x002374BC     Function:
                                                        fp_ms_display_apper
0x00137540 - 0x0013903C     0x002374C0 - 0x00238FBC     Function:
                                                        fp_ms_ud_item_disp
0x00139040 - 0x0013911C     0x00238FC0 - 0x0023909C     Function:
                                                        fp_ms_ud_item_disap
0x00139120 - 0x00139588     0x002390A0 - 0x00239508     Function:
                                                        fp_ms_ud_item_exec
0x00139590 - 0x001397A0     0x00239510 - 0x00239720     Function:
                                                        fp_ms_ud_item_apper
0x001397A0 - 0x0013A320     0x00239720 - 0x0023A2A0     Function:
                                                        fp_ms_nm_one_disp
0x0013A320 - 0x0013B52C     0x0023A2A0 - 0x0023B4AC     Function:
                                                        fp_ms_lr_item_disp
0x0013B530 - 0x0013B904     0x0023B4B0 - 0x0023B884     Function:
                                                        fp_ms_spe
0x0013B910 - 0x0013BBA0     0x0023B890 - 0x0023BB20     Function:
                                                        fp_ms_lr_item_disap
0x0013BBA0 - 0x0013BC3C     0x0023BB20 - 0x0023BBBC     Function:
                                                        fp_ms_lr_item_exec
0x0013BC40 - 0x0013BF50     0x0023BBC0 - 0x0023BED0     Function:
                                                        fp_ms_lr_item_apper2
0x0013BF50 - 0x0013C1D8     0x0023BED0 - 0x0023C158     Function:
                                                        fp_ms_lr_item_apper
0x0013C1E0 - 0x0013C5D4     0x0023C160 - 0x0023C554     Function:
                                                        fp_ms_disap
0x0013C5E0 - 0x0013CAB8     0x0023C560 - 0x0023CA38     Function:
                                                        fp_ms_apper
0x0013CAC0 - 0x0013CEFC     0x0023CA40 - 0x0023CE7C     Function:
                                                        co_cursor01_disp
0x0013CF00 - 0x0013CF38     0x0023CE80 - 0x0023CEB8     Function:
                                                        co_cursor01_init
0x0013CF40 - 0x0013D180     0x0023CEC0 - 0x0023D100     Function:
                                                        co_button_explain_disp
0x0013D180 - 0x0013D3C0     0x0023D100 - 0x0023D340     Function:
                                                        co_button_disp
0x0013D3C0 - 0x0013D9E8     0x0023D340 - 0x0023D968     Function:
                                                        co_qmenu_disp
0x0013D9F0 - 0x0013DCC0     0x0023D970 - 0x0023DC40     Function:
                                                        co_qmenu_exec
0x0013DCC0 - 0x0013DCD4     0x0023DC40 - 0x0023DC54     Function:
                                                        co_qmenu_exec_func
0x0013DCE0 - 0x0013DCEC     0x0023DC60 - 0x0023DC6C     Function:
                                                        co_qmenu_cursor_get
0x0013DCF0 - 0x0013DD2C     0x0023DC70 - 0x0023DCAC     Function:
                                                        co_qmenu_cursor_dec
0x0013DD30 - 0x0013DD74     0x0023DCB0 - 0x0023DCF4     Function:
                                                        co_qmenu_cursor_inc
0x0013DD80 - 0x0013DDA8     0x0023DD00 - 0x0023DD28     Function:
                                                        co_qmenu_cursor_set
0x0013DDB0 - 0x0013DDC0     0x0023DD30 - 0x0023DD40     Function:
                                                        co_qmenu_close
0x0013DDC0 - 0x0013DDD0     0x0023DD40 - 0x0023DD50     Function:
                                                        co_qmenu_open
0x0013DDD0 - 0x0013DDDC     0x0023DD50 - 0x0023DD5C     Function:
                                                        co_qmenu_get_stat
0x0013DDE0 - 0x0013DDEC     0x0023DD60 - 0x0023DD6C     Function:
                                                        co_qmenu_set_y
0x0013DDF0 - 0x0013DE18     0x0023DD70 - 0x0023DD98     Function:
                                                        co_qmenu_set_width
0x0013DE20 - 0x0013DF38     0x0023DDA0 - 0x0023DEB8     Function:
                                                        co_quick_menu_data_set
0x0013DF40 - 0x0013DFA4     0x0023DEC0 - 0x0023DF24     Function:
                                                        co_quick_menu_disap
0x0013DFB0 - 0x0013E19C     0x0023DF30 - 0x0023E11C     Function:
                                                        co_quick_menu_set
0x0013E1A0 - 0x0013E1AC     0x0023E120 - 0x0023E12C     Function:
                                                        co_quick_menu_init
0x0013E1B0 - 0x0013E1BC     0x0023E130 - 0x0023E13C     Function:
                                                        PointGetHistPoint
0x0013E1C0 - 0x0013E2E0     0x0023E140 - 0x0023E260     Function:
                                                        register_free_play
0x0013E2E0 - 0x0013E314     0x0023E260 - 0x0023E294     Function:
                                                        PointRegisterPoint
0x0013E320 - 0x0013E418     0x0023E2A0 - 0x0023E398     Function:
                                                        PointCalcDispPoint
0x0013E420 - 0x0013E580     0x0023E3A0 - 0x0023E500     Function:
                                                        calc_free_play
0x0013E580 - 0x0013E5B4     0x0023E500 - 0x0023E534     Function:
                                                        PointCalcPoint
0x0013E5C0 - 0x0013E5E4     0x0023E540 - 0x0023E564     Function:
                                                        PointGetDispPoint
0x0013E5F0 - 0x0013E740     0x0023E570 - 0x0023E6C0     Function:
                                                        init_endless_play
0x0013E740 - 0x0013EAF8     0x0023E6C0 - 0x0023EA78     Function:
                                                        init_free_play
0x0013EB00 - 0x0013F2DC     0x0023EA80 - 0x0023F25C     Function:
                                                        PointInitPlay
0x0013F2E0 - 0x0013F34C     0x0023F260 - 0x0023F2CC     Function:
                                                        PointAddTotalPoint
0x0013F350 - 0x0013F35C     0x0023F2D0 - 0x0023F2DC     Function:
                                                        PointGetTotalPoint
0x0013F360 - 0x0013F36C     0x0023F2E0 - 0x0023F2EC     Function:
                                                        PointInitSaveWork
0x0013F370 - 0x0013F540     0x0023F2F0 - 0x0023F4C0     Function:
                                                        dmm_chara
0x0013F540 - 0x0013F5D0     0x0023F4C0 - 0x0023F550     Function:
                                                        NetSysLobbyToAccountConnect
0x0013F5D0 - 0x0013F818     0x0023F550 - 0x0023F798     Function:
                                                        NetSysLobbySelectKey
0x0013F820 - 0x0013FC98     0x0023F7A0 - 0x0023FC18     Function:
                                                        NetSysLobbyMain
0x0013FCA0 - 0x001400E8     0x0023FC20 - 0x00240068     Function:
                                                        NetSysLobbyInit
0x001400F0 - 0x00140128     0x00240070 - 0x002400A8     Function:
                                                        CwsWin_Multi2SetCautionMark
0x00140130 - 0x00140148     0x002400B0 - 0x002400C8     Function:
                                                        CwsWin_Multi2SetWinClut
0x00140150 - 0x00140790     0x002400D0 - 0x00240710     Function:
                                                        CwsWin_Multi2Disp
0x00140790 - 0x001407A4     0x00240710 - 0x00240724     Function:
                                                        CwsWin_Multi2End
0x001407B0 - 0x00140988     0x00240730 - 0x00240908     Function:
                                                        CwsWin_Multi2Main
0x00140990 - 0x00140A4C     0x00240910 - 0x002409CC     Function:
                                                        CwsWin_Multi2Init
0x00140A50 - 0x00140D44     0x002409D0 - 0x00240CC4     Function:
                                                        CwsWin_Multi2Close
0x00140D50 - 0x0014102C     0x00240CD0 - 0x00240FAC     Function:
                                                        CwsWin_Multi2Open
0x00141030 - 0x00141098     0x00240FB0 - 0x00241018     Function:
                                                        CwsWin_Multi2
0x001410A0 - 0x001410F8     0x00241020 - 0x00241078     Function:
                                                        SelectDevice
0x00141100 - 0x001411BC     0x00241080 - 0x0024113C     Function:
                                                        GetDeviceInfo
0x001411C0 - 0x00141228     0x00241140 - 0x002411A8     Function:
                                                        GetDeviceInfoNum
0x00141230 - 0x001412A4     0x002411B0 - 0x00241224     Function:
                                                        DnsLookUpRev
0x001412B0 - 0x00141320     0x00241230 - 0x002412A0     Function:
                                                        DnsLookUp
0x00141320 - 0x00141378     0x002412A0 - 0x002412F8     Function:
                                                        DnsReleaseTicket
0x00141380 - 0x001413F4     0x00241300 - 0x00241374     Function:
                                                        DnsGetTicket
0x00141400 - 0x00141450     0x00241380 - 0x002413D0     Function:
                                                        DnsDisp
0x00141450 - 0x001414F4     0x002413D0 - 0x00241474     Function:
                                                        DnsInit
0x00141500 - 0x00141560     0x00241480 - 0x002414E0     Function:
                                                        DhcpReleaseNb
0x00141560 - 0x001415B0     0x002414E0 - 0x00241530     Function:
                                                        DhcpTimer
0x001415B0 - 0x00141644     0x00241530 - 0x002415C4     Function:
                                                        DhcpGetIfInfo
0x00141650 - 0x001416B0     0x002415D0 - 0x00241630     Function:
                                                        DhcpRequestNb
0x001416B0 - 0x00141718     0x00241630 - 0x00241698     Function:
                                                        DhcpGetGateway
0x00141720 - 0x001417B8     0x002416A0 - 0x00241738     Function:
                                                        DhcpGetDns
0x001417C0 - 0x00141810     0x00241740 - 0x00241790     Function:
                                                        DhcpDisp
0x00141810 - 0x00141860     0x00241790 - 0x002417E0     Function:
                                                        DhcpInit
0x00141860 - 0x001418B0     0x002417E0 - 0x00241830     Function:
                                                        NdgFinish
0x001418B0 - 0x00141900     0x00241830 - 0x00241880     Function:
                                                        NdgStartPollStatus
0x00141900 - 0x00141958     0x00241880 - 0x002418D8     Function:
                                                        NdgStart
0x00141960 - 0x001419B0     0x002418E0 - 0x00241930     Function:
                                                        NdgDisp
0x001419B0 - 0x00141A00     0x00241930 - 0x00241980     Function:
                                                        NdgInit
0x00141A00 - 0x00141ABC     0x00241980 - 0x00241A3C     Function:
                                                        PppStatus
0x00141AC0 - 0x00141B10     0x00241A40 - 0x00241A90     Function:
                                                        PppFinish
0x00141B10 - 0x00141C00     0x00241A90 - 0x00241B80     Function:
                                                        PppStart
0x00141C00 - 0x00141C50     0x00241B80 - 0x00241BD0     Function:
                                                        PppDisp
0x00141C50 - 0x00141CA0     0x00241BD0 - 0x00241C20     Function:
                                                        PppInit
0x00141CA0 - 0x00141CF8     0x00241C20 - 0x00241C78     Function:
                                                        UdpClose
0x00141D00 - 0x00141DD8     0x00241C80 - 0x00241D58     Function:
                                                        UdpRecv
0x00141DE0 - 0x00141E30     0x00241D60 - 0x00241DB0     Function:
                                                        UdpCheckRecv
0x00141E30 - 0x00141EF0     0x00241DB0 - 0x00241E70     Function:
                                                        UdpSend2
0x00141EF0 - 0x00141FA0     0x00241E70 - 0x00241F20     Function:
                                                        UdpSend
0x00141FA0 - 0x00142004     0x00241F20 - 0x00241F84     Function:
                                                        UdpOpen
0x00142010 - 0x00142070     0x00241F90 - 0x00241FF0     Function:
                                                        RouteDel
0x00142070 - 0x001420D0     0x00241FF0 - 0x00242050     Function:
                                                        RouteAdd
0x001420D0 - 0x00142128     0x00242050 - 0x002420A8     Function:
                                                        TcpSendNotifyCheck
0x00142130 - 0x00142188     0x002420B0 - 0x00242108     Function:
                                                        TcpGetEvent
0x00142190 - 0x001421E8     0x00242110 - 0x00242168     Function:
                                                        TcpDelete
0x001421F0 - 0x00142250     0x00242170 - 0x002421D0     Function:
                                                        TcpCancel
0x00142250 - 0x00142370     0x002421D0 - 0x002422F0     Function:
                                                        TcpRecvNb
0x00142370 - 0x00142428     0x002422F0 - 0x002423A8     Function:
                                                        TcpSendNb
0x00142430 - 0x001424CC     0x002423B0 - 0x0024244C     Function:
                                                        TcpStat
0x001424D0 - 0x00142570     0x00242450 - 0x002424F0     Function:
                                                        TcpGetaddr
0x00142570 - 0x001425C8     0x002424F0 - 0x00242548     Function:
                                                        TcpAbort
0x001425D0 - 0x00142628     0x00242550 - 0x002425A8     Function:
                                                        TcpClose
0x00142630 - 0x00142688     0x002425B0 - 0x00242608     Function:
                                                        TcpAccept
0x00142690 - 0x001426F4     0x00242610 - 0x00242674     Function:
                                                        TcpPopen
0x00142700 - 0x00142764     0x00242680 - 0x002426E4     Function:
                                                        TcpOpen
0x00142770 - 0x001427C0     0x002426F0 - 0x00242740     Function:
                                                        Ifdown
0x001427C0 - 0x00142824     0x00242740 - 0x002427A4     Function:
                                                        Ifconfig
0x00142830 - 0x001428C4     0x002427B0 - 0x00242844     Function:
                                                        Getconfig
0x001428D0 - 0x00142920     0x00242850 - 0x002428A0     Function:
                                                        TcpTerminate
0x00142920 - 0x00142970     0x002428A0 - 0x002428F0     Function:
                                                        TcpInitialize
0x00142970 - 0x001429BC     0x002428F0 - 0x0024293C     Function:
                                                        AveTcpRpcInit
0x001429C0 - 0x00142A00     0x00242940 - 0x00242980     Function:
                                                        fp_MgSoloDecJudgeMessageCt
0x00142A00 - 0x00142A18     0x00242980 - 0x00242998     Function:
                                                        fp_MgSoloGetJudgeMessageCt
0x00142A20 - 0x00142A38     0x002429A0 - 0x002429B8     Function:
                                                        fp_MgSoloGetJudgeMessageId
0x00142A40 - 0x00142A68     0x002429C0 - 0x002429E8     Function:
                                                        fp_MgSoloSetJudgeMessage
0x00142A70 - 0x00142B00     0x002429F0 - 0x00242A80     Function:
                                                        fp_MgSoloInit
0x00142B00 - 0x00142CB0     0x00242A80 - 0x00242C30     Function:
                                                        fp_MgSoloDispHandIcon
0x00142CB0 - 0x00142F80     0x00242C30 - 0x00242F00     Function:
                                                        fp_MgSoloDispHandSpot
0x00142F80 - 0x00142F98     0x00242F00 - 0x00242F18     Function:
                                                        fp_MgSoloSetHoldState
0x00142FA0 - 0x00143144     0x00242F20 - 0x002430C4     Function:
                                                        fp_MgSoloSetOkEffect
0x00143150 - 0x00143304     0x002430D0 - 0x00243284     Function:
                                                        fp_MgSoloIsInputHand
0x00143310 - 0x001440E8     0x00243290 - 0x00244068     Function:
                                                        fp_MgSoloAnalyzeSequence
0x001440F0 - 0x001442C4     0x00244070 - 0x00244244     Function:
                                                        fp_MgSoloMakeSequence
0x001442D0 - 0x0014459C     0x00244250 - 0x0024451C     Function:
                                                        fp_MgSoloSetupSequence
0x001445A0 - 0x00144604     0x00244520 - 0x00244584     Function:
                                                        fp_MgSoloSetupTexture
0x00144610 - 0x001447D8     0x00244590 - 0x00244758     Function:
                                                        Blowfish_Init
0x001447E0 - 0x00144894     0x00244760 - 0x00244814     Function:
                                                        Blowfish_Decrypt
0x001448A0 - 0x00144954     0x00244820 - 0x002448D4     Function:
                                                        Blowfish_Encrypt
0x00144960 - 0x00145A78     0x002448E0 - 0x002459F8     Function:
                                                        MD5Transform
0x00145A80 - 0x00145C34     0x00245A00 - 0x00245BB4     Function:
                                                        MD5Final
0x00145C40 - 0x00145D40     0x00245BC0 - 0x00245CC0     Function:
                                                        MD5Update
0x00145D40 - 0x00145D7C     0x00245CC0 - 0x00245CFC     Function:
                                                        MD5Init
0x00145D80 - 0x00145F38     0x00245D00 - 0x00245EB8     Function:
                                                        mio_crypto_body
0x00145F40 - 0x00145F48     0x00245EC0 - 0x00245EC8     Function:
                                                        mio_init_crypto
0x00145F50 - 0x00145F88     0x00245ED0 - 0x00245F08     Function:
                                                        mio_check_bp
0x00145F90 - 0x00146008     0x00245F10 - 0x00245F88     Function:
                                                        mio_get_vstr
0x00146010 - 0x00146090     0x00245F90 - 0x00246010     Function:
                                                        mio_get_strn
0x00146090 - 0x00146168     0x00246010 - 0x002460E8     Function:
                                                        mio_get_u32
0x00146170 - 0x00146238     0x002460F0 - 0x002461B8     Function:
                                                        mio_get_32
0x00146240 - 0x00146288     0x002461C0 - 0x00246208     Function:
                                                        mio_get_u16
0x00146290 - 0x001462D8     0x00246210 - 0x00246258     Function:
                                                        mio_get_16
0x001462E0 - 0x00146320     0x00246260 - 0x002462A0     Function:
                                                        mio_get_u8
0x00146320 - 0x00146360     0x002462A0 - 0x002462E0     Function:
                                                        mio_get_8
0x00146360 - 0x001463CC     0x002462E0 - 0x0024634C     Function:
                                                        mio_set_strn
0x001463D0 - 0x00146478     0x00246350 - 0x002463F8     Function:
                                                        mio_set_u32
0x00146480 - 0x00146528     0x00246400 - 0x002464A8     Function:
                                                        mio_set_32
0x00146530 - 0x00146588     0x002464B0 - 0x00246508     Function:
                                                        mio_set_u16
0x00146590 - 0x001465E8     0x00246510 - 0x00246568     Function:
                                                        mio_set_16
0x001465F0 - 0x00146630     0x00246570 - 0x002465B0     Function:
                                                        mio_set_u8
0x00146630 - 0x00146670     0x002465B0 - 0x002465F0     Function:
                                                        mio_set_8
0x00146670 - 0x00146680     0x002465F0 - 0x00246600     Function:
                                                        mio_unpack_end
0x00146680 - 0x00146690     0x00246600 - 0x00246610     Function:
                                                        mio_unpack_start
0x00146690 - 0x001466A8     0x00246610 - 0x00246628     Function:
                                                        mio_pack_end
0x001466B0 - 0x001466F4     0x00246630 - 0x00246674     Function:
                                                        mio_pack_start
0x00146700 - 0x00146750     0x00246680 - 0x002466D0     Function:
                                                        mio_message_init
0x00146750 - 0x00146958     0x002466D0 - 0x002468D8     Function:
                                                        mio_write_message
0x00146960 - 0x00146E38     0x002468E0 - 0x00246DB8     Function:
                                                        mio_read_message
0x00146E40 - 0x00146E4C     0x00246DC0 - 0x00246DCC     Function:
                                                        namesGetNo
0x00146E50 - 0x00146E5C     0x00246DD0 - 0x00246DDC     Function:
                                                        namesGetYes
0x00146E60 - 0x00146E98     0x00246DE0 - 0x00246E18     Function:
                                                        namesGetMessageTable
0x00146EA0 - 0x00147150     0x00246E20 - 0x002470D0     Function:
                                                        NetGameHelpDisp
0x00147150 - 0x0014716C     0x002470D0 - 0x002470EC     Function:
                                                        NetGameHelpSetMes
0x00147170 - 0x00147328     0x002470F0 - 0x002472A8     Function:
                                                        co_movie_SetDecTag
0x00147330 - 0x00147860     0x002472B0 - 0x002477E0     Function:
                                                        co_movie_disp
0x00147860 - 0x001479C4     0x002477E0 - 0x00247944     Function:
                                                        co_movie_play
0x001479D0 - 0x001479DC     0x00247950 - 0x0024795C     Function:
                                                        co_movie_get_stat
0x001479E0 - 0x00147A00     0x00247960 - 0x00247980     Function:
                                                        co_movie_change_start
0x00147A00 - 0x00147A84     0x00247980 - 0x00247A04     Function:
                                                        co_movie_restart
0x00147A90 - 0x00147AE8     0x00247A10 - 0x00247A68     Function:
                                                        co_movie_stop
0x00147AF0 - 0x00147B70     0x00247A70 - 0x00247AF0     Function:
                                                        co_movie_change_init_th
0x00147B70 - 0x00147DA4     0x00247AF0 - 0x00247D24     Function:
                                                        co_movie_manage
0x00147DB0 - 0x00148010     0x00247D30 - 0x00247F90     Function:
                                                        co_movie_set
0x00148010 - 0x001480CC     0x00247F90 - 0x0024804C     Function:
                                                        co_movie_init
0x001480D0 - 0x00148610     0x00248050 - 0x00248590     Function:
                                                        ComScrollBarDisp
0x00148610 - 0x00148618     0x00248590 - 0x00248598     Function:
                                                        NetWin_BarSetH
0x00148620 - 0x00148628     0x002485A0 - 0x002485A8     Function:
                                                        NetWin_BarSetNow
0x00148630 - 0x00148638     0x002485B0 - 0x002485B8     Function:
                                                        NetWin_BarSetNum
0x00148640 - 0x00148648     0x002485C0 - 0x002485C8     Function:
                                                        NetWin_BarSetMax
0x00148650 - 0x001486C4     0x002485D0 - 0x00248644     Function:
                                                        NetWin_BarDisp
0x001486D0 - 0x001486E4     0x00248650 - 0x00248664     Function:
                                                        NetWin_BarEnd
0x001486F0 - 0x001486F8     0x00248670 - 0x00248678     Function:
                                                        NetWin_BarMain
0x00148700 - 0x00148740     0x00248680 - 0x002486C0     Function:
                                                        NetWin_BarInit
0x00148740 - 0x001487A8     0x002486C0 - 0x00248728     Function:
                                                        NetWin_Bar
0x001487B0 - 0x00148858     0x00248730 - 0x002487D8     Function:
                                                        shop_init_work
0x00148860 - 0x00148AF8     0x002487E0 - 0x00248A78     Function:
                                                        shop_init
0x00148B00 - 0x00148CC0     0x00248A80 - 0x00248C40     Function:
                                                        shop_make_contents_list_other
0x00148CC0 - 0x00148E68     0x00248C40 - 0x00248DE8     Function:
                                                        shop_make_contents_list_custom
0x00148E70 - 0x00149030     0x00248DF0 - 0x00248FB0     Function:
                                                        shop_make_contents_list_info
0x00149030 - 0x001491A8     0x00248FB0 - 0x00249128     Function:
                                                        shop_make_contents_list_outfit
0x001491B0 - 0x00149400     0x00249130 - 0x00249380     Function:
                                                        shop_make_contents_list_course
0x00149400 - 0x00149684     0x00249380 - 0x00249604     Function:
                                                        shop_make_contents_list_music
0x00149690 - 0x0014972C     0x00249610 - 0x002496AC     Function:
                                                        shop_make_contents_list
0x00149730 - 0x001497E0     0x002496B0 - 0x00249760     Function:
                                                        shop_set_step
0x001497E0 - 0x001497E8     0x00249760 - 0x00249768     Function:
                                                        shop_get_work
0x001497F0 - 0x001497F8     0x00249770 - 0x00249778     Function:
                                                        ShopFinish
0x00149800 - 0x00149898     0x00249780 - 0x00249818     Function:
                                                        ShopStep
0x001498A0 - 0x0014991C     0x00249820 - 0x0024989C     Function:
                                                        ShopAddrInit
0x00149920 - 0x00149990     0x002498A0 - 0x00249910     Function:
                                                        ShopInit
0x00149990 - 0x00149D7C     0x00249910 - 0x00249CFC     Function:
                                                        shop_select_info_disp_course_list
0x00149D80 - 0x00149F48     0x00249D00 - 0x00249EC8     Function:
                                                        shop_select_info_disp_course
0x00149F50 - 0x0014A13C     0x00249ED0 - 0x0024A0BC     Function:
                                                        shop_select_info_disp_music
0x0014A140 - 0x0014A388     0x0024A0C0 - 0x0024A308     Function:
                                                        shop_select_info_disp_button
0x0014A390 - 0x0014A55C     0x0024A310 - 0x0024A4DC     Function:
                                                        shop_select_info_disp_th
0x0014A560 - 0x0014A8FC     0x0024A4E0 - 0x0024A87C     Function:
                                                        shop_disp_my_point
0x0014A900 - 0x0014AB24     0x0024A880 - 0x0024AAA4     Function:
                                                        shop_disp_contents_explain_other
0x0014AB30 - 0x0014BA00     0x0024AAB0 - 0x0024B980     Function:
                                                        shop_disp_contents_other
0x0014BA00 - 0x0014BC64     0x0024B980 - 0x0024BBE4     Function:
                                                        shop_disp_contents_explain_custom
0x0014BC70 - 0x0014CA40     0x0024BBF0 - 0x0024C9C0     Function:
                                                        shop_disp_contents_custom
0x0014CA40 - 0x0014D870     0x0024C9C0 - 0x0024D7F0     Function:
                                                        shop_disp_contents_info
0x0014D870 - 0x0014DA58     0x0024D7F0 - 0x0024D9D8     Function:
                                                        shop_disp_contents_explain_outfit
0x0014DA60 - 0x0014E7F8     0x0024D9E0 - 0x0024E778     Function:
                                                        shop_disp_contents_outfit
0x0014E800 - 0x0014EA50     0x0024E780 - 0x0024E9D0     Function:
                                                        shop_disp_contents_explain_course
0x0014EA50 - 0x0014F7F8     0x0024E9D0 - 0x0024F778     Function:
                                                        shop_disp_contents_course
0x0014F800 - 0x0014FB0C     0x0024F780 - 0x0024FA8C     Function:
                                                        shop_disp_contents_explain_music
0x0014FB10 - 0x00150AA0     0x0024FA90 - 0x00250A20     Function:
                                                        shop_disp_contents_music
0x00150AA0 - 0x00150FBC     0x00250A20 - 0x00250F3C     Function:
                                                        shop_disp_contents_explain_frame
0x00150FC0 - 0x00151150     0x00250F40 - 0x002510D0     Function:
                                                        shop_disp_point
0x00151150 - 0x001512D0     0x002510D0 - 0x00251250     Function:
                                                        shop_disp_cursor
0x001512D0 - 0x00151364     0x00251250 - 0x002512E4     Function:
                                                        shop_disp_contents
0x00151370 - 0x00151678     0x002512F0 - 0x002515F8     Function:
                                                        shop_disp_common_scroll_bar
0x00151680 - 0x00151B38     0x00251600 - 0x00251AB8     Function:
                                                        shop_disp_scroll_bar
0x00151B40 - 0x00151E10     0x00251AC0 - 0x00251D90     Function:
                                                        shop_disp_contents_frame
0x00151E10 - 0x00152234     0x00251D90 - 0x002521B4     Function:
                                                        shop_disp_tab
0x00152240 - 0x001525B0     0x002521C0 - 0x00252530     Function:
                                                        shop_disp_title
0x001525B0 - 0x001527E8     0x00252530 - 0x00252768     Function:
                                                        shop_select_confirm_ctrl
0x001527F0 - 0x00152B08     0x00252770 - 0x00252A88     Function:
                                                        shop_select_confirm
0x00152B10 - 0x00152BA8     0x00252A90 - 0x00252B28     Function:
                                                        shop_select_disp
0x00152BB0 - 0x0015310C     0x00252B30 - 0x0025308C     Function:
                                                        shop_select_ctrl
0x00153110 - 0x00153464     0x00253090 - 0x002533E4     Function:
                                                        shop_select
0x00153470 - 0x001534BC     0x002533F0 - 0x0025343C     Function:
                                                        shop_is_fade_off
0x001534C0 - 0x001536A4     0x00253440 - 0x00253624     Function:
                                                        shop_fade_main
0x001536B0 - 0x00153710     0x00253630 - 0x00253690     Function:
                                                        shop_fade_set
0x00153710 - 0x00153738     0x00253690 - 0x002536B8     Function:
                                                        shop_fade_out_init
0x00153740 - 0x00153768     0x002536C0 - 0x002536E8     Function:
                                                        shop_fade_in_init
0x00153770 - 0x001537A8     0x002536F0 - 0x00253728     Function:
                                                        shop_fade_init
0x001537B0 - 0x00153B58     0x00253730 - 0x00253AD8     Function:
                                                        shop_disp_text
0x00153B60 - 0x00153B88     0x00253AE0 - 0x00253B08     Function:
                                                        shop_bgm_set
0x00153B90 - 0x00153BF0     0x00253B10 - 0x00253B70     Function:
                                                        shop_bgm_call
0x00153BF0 - 0x00153C18     0x00253B70 - 0x00253B98     Function:
                                                        shop_bgm_init
0x00153C20 - 0x00153C68     0x00253BA0 - 0x00253BE8     Function:
                                                        shop_multi_win_destroy
0x00153C70 - 0x00153CDC     0x00253BF0 - 0x00253C5C     Function:
                                                        shop_multi_win_init
0x00153CE0 - 0x00153DA0     0x00253C60 - 0x00253D20     Function:
                                                        shop_bind_nm
0x00153DA0 - 0x00153EF0     0x00253D20 - 0x00253E70     Function:
                                                        shop_bind_tex
0x00153EF0 - 0x00153F28     0x00253E70 - 0x00253EA8     Function:
                                                        shop_wait_obj_move
0x00153F30 - 0x00153F48     0x00253EB0 - 0x00253EC8     Function:
                                                        shop_get_obj_frame
0x00153F50 - 0x00153F70     0x00253ED0 - 0x00253EF0     Function:
                                                        shop_get_obj_count
0x00153F70 - 0x00153F94     0x00253EF0 - 0x00253F14     Function:
                                                        shop_set_obj_move
0x00153FA0 - 0x00154004     0x00253F20 - 0x00253F84     Function:
                                                        shop_init_obj_move_work
0x00154010 - 0x00154020     0x00253F90 - 0x00253FA0     Function:
                                                        shop_get_secret_value
0x00154020 - 0x00154030     0x00253FA0 - 0x00253FB0     Function:
                                                        shop_get_secret_no
0x00154030 - 0x00154098     0x00253FB0 - 0x00254018     Function:
                                                        shop_get_disp_num
0x001540A0 - 0x001540A8     0x00254020 - 0x00254028     Function:
                                                        shop_get_contents_num
0x001540B0 - 0x001541B4     0x00254030 - 0x00254134     Function:
                                                        shop_purchase
0x001541C0 - 0x0015425C     0x00254140 - 0x002541DC     Function:
                                                        shop_is_purchasable2
0x00154260 - 0x001542FC     0x002541E0 - 0x0025427C     Function:
                                                        shop_is_purchasable
0x00154300 - 0x00154508     0x00254280 - 0x00254488     Function:
                                                        shop_select_info_ctrl
0x00154510 - 0x001546CC     0x00254490 - 0x0025464C     Function:
                                                        shop_select_info_disp
0x001546D0 - 0x00154828     0x00254650 - 0x002547A8     Function:
                                                        shop_select_info
0x00154830 - 0x00154860     0x002547B0 - 0x002547E0     Function:
                                                        shop_is_info_disp
0x00154860 - 0x00154928     0x002547E0 - 0x002548A8     Function:
                                                        namesMakeChangeMessage
0x00154930 - 0x00154A10     0x002548B0 - 0x00254990     Function:
                                                        namesMakeRegisterMessage
0x00154A10 - 0x00154B08     0x00254990 - 0x00254A88     Function:
                                                        namesMakeAuthMessage
0x00154B10 - 0x00154ED0     0x00254A90 - 0x00254E50     Function:
                                                        dmm_disp_text
0x00154ED0 - 0x00154F24     0x00254E50 - 0x00254EA4     Function:
                                                        set_data_warning_mess
0x00154F30 - 0x00154FF8     0x00254EB0 - 0x00254F78     Function:
                                                        set_data_select_mess
0x00155000 - 0x0015511C     0x00254F80 - 0x0025509C     Function:
                                                        mmenu_logo_disp
0x00155120 - 0x00155188     0x002550A0 - 0x00255108     Function:
                                                        mmenu_logo_disap
0x00155190 - 0x001551B0     0x00255110 - 0x00255130     Function:
                                                        mmenu_logo_exec
0x001551B0 - 0x001554AC     0x00255130 - 0x0025542C     Function:
                                                        mmenu_exp_disp
0x001554B0 - 0x00155614     0x00255430 - 0x00255594     Function:
                                                        mmenu_exp_disap
0x00155620 - 0x001556B4     0x002555A0 - 0x00255634     Function:
                                                        mmenu_exp_exec
0x001556C0 - 0x00155814     0x00255640 - 0x00255794     Function:
                                                        mmenu_exp_apper
0x00155820 - 0x00155C34     0x002557A0 - 0x00255BB4     Function:
                                                        mmenu_pic_disp
0x00155C40 - 0x00155CC0     0x00255BC0 - 0x00255C40     Function:
                                                        mmenu_pic_disap
0x00155CC0 - 0x00155D54     0x00255C40 - 0x00255CD4     Function:
                                                        mmenu_pic_exec
0x00155D60 - 0x00155DE0     0x00255CE0 - 0x00255D60     Function:
                                                        mmenu_pic_apper
0x00155DE0 - 0x00155EA0     0x00255D60 - 0x00255E20     Function:
                                                        mmenu_base_disp
0x00155EA0 - 0x00155FD0     0x00255E20 - 0x00255F50     Function:
                                                        mmenu_base_move
0x00155FD0 - 0x00156290     0x00255F50 - 0x00256210     Function:
                                                        mmenu_item_disp
0x00156290 - 0x001564F8     0x00256210 - 0x00256478     Function:
                                                        mmenu_item_disap
0x00156500 - 0x0015663C     0x00256480 - 0x002565BC     Function:
                                                        mmenu_item_exec
0x00156640 - 0x001568F8     0x002565C0 - 0x00256878     Function:
                                                        mmenu_item_apper
0x00156900 - 0x001569BC     0x00256880 - 0x0025693C     Function:
                                                        mmenu_disap
0x001569C0 - 0x00156B10     0x00256940 - 0x00256A90     Function:
                                                        mmenu_apper
0x00156B10 - 0x00156C10     0x00256A90 - 0x00256B90     Function:
                                                        mmenu_logo
0x00156C10 - 0x00156D48     0x00256B90 - 0x00256CC8     Function:
                                                        dmm_save
0x00156D50 - 0x00156D80     0x00256CD0 - 0x00256D00     Function:
                                                        dmm_copy_savedata
0x00156D80 - 0x00156FB0     0x00256D00 - 0x00256F30     Function:
                                                        dmm_set_default_savedata
0x00156FB0 - 0x00156FBC     0x00256F30 - 0x00256F3C     Function:
                                                        dmm_is_savedata
0x00156FC0 - 0x00157070     0x00256F40 - 0x00256FF0     Function:
                                                        dmm_icon
0x00157070 - 0x00157100     0x00256FF0 - 0x00257080     Function:
                                                        NetWin_SlbySetMaxNum
0x00157100 - 0x00157190     0x00257080 - 0x00257110     Function:
                                                        NetWin_SlbySetNowNum
0x00157190 - 0x001571A4     0x00257110 - 0x00257124     Function:
                                                        NetWin_SlbySetName
0x001571B0 - 0x00157238     0x00257130 - 0x002571B8     Function:
                                                        NetWin_SlbySetSelect
0x00157240 - 0x00157254     0x002571C0 - 0x002571D4     Function:
                                                        NetWin_SlbyEnd
0x00157260 - 0x001572A8     0x002571E0 - 0x00257228     Function:
                                                        NetWin_SlbyMain
0x001572B0 - 0x0015745C     0x00257230 - 0x002573DC     Function:
                                                        NetWin_SlbyInit
0x00157460 - 0x001574C8     0x002573E0 - 0x00257448     Function:
                                                        NetWin_Slby
0x001574D0 - 0x00157504     0x00257450 - 0x00257484     Function:
                                                        NetInterErrGetStatus
0x00157510 - 0x00157520     0x00257490 - 0x002574A0     Function:
                                                        NetInterErrClose
0x00157520 - 0x00157564     0x002574A0 - 0x002574E4     Function:
                                                        NetInterErrOpen
0x00157570 - 0x00157608     0x002574F0 - 0x00257588     Function:
                                                        NetInterErrSet2Code
0x00157610 - 0x00157694     0x00257590 - 0x00257614     Function:
                                                        NetInterErrSet1Code
0x001576A0 - 0x001576FC     0x00257620 - 0x0025767C     Function:
                                                        NetInterErrSet0Code
0x00157700 - 0x0015774C     0x00257680 - 0x002576CC     Function:
                                                        NetInterErrInit
0x00157750 - 0x00157D10     0x002576D0 - 0x00257C90     Function:
                                                        CwsWin_ListbkDisp
0x00157D10 - 0x00157D24     0x00257C90 - 0x00257CA4     Function:
                                                        NetWin_ListbkEnd
0x00157D30 - 0x00157D38     0x00257CB0 - 0x00257CB8     Function:
                                                        NetWin_ListbkMain
0x00157D40 - 0x00157D80     0x00257CC0 - 0x00257D00     Function:
                                                        NetWin_ListbkInit
0x00157D80 - 0x00157DE8     0x00257D00 - 0x00257D68     Function:
                                                        NetWin_Listbk
0x00157DF0 - 0x00157E38     0x00257D70 - 0x00257DB8     Function:
                                                        NetWin_ListselSetSelect
0x00157E40 - 0x00157E48     0x00257DC0 - 0x00257DC8     Function:
                                                        NetWin_ListselSetPlayerListFile
0x00157E50 - 0x00157E64     0x00257DD0 - 0x00257DE4     Function:
                                                        NetWin_ListselSetNumber
0x00157E70 - 0x00157E84     0x00257DF0 - 0x00257E04     Function:
                                                        NetWin_ListselEnd
0x00157E90 - 0x001580C8     0x00257E10 - 0x00258048     Function:
                                                        NetWin_ListselMain
0x001580D0 - 0x001581EC     0x00258050 - 0x0025816C     Function:
                                                        NetWin_ListselInit
0x001581F0 - 0x00158258     0x00258170 - 0x002581D8     Function:
                                                        NetWin_Listsel
0x00158260 - 0x001587BC     0x002581E0 - 0x0025873C     Function:
                                                        rec_nor_item_disp_sub
0x001587C0 - 0x00158A88     0x00258740 - 0x00258A08     Function:
                                                        rec_nor_init
0x00158A90 - 0x00158B60     0x00258A10 - 0x00258AE0     Function:
                                                        Rec_Nor_BoolDelete
0x00158B60 - 0x00158B68     0x00258AE0 - 0x00258AE8     Function:
                                                        RCObj_nor_obj_disp
0x00158B70 - 0x00158B78     0x00258AF0 - 0x00258AF8     Function:
                                                        RCObj_nor_obj_disap
0x00158B80 - 0x00158B88     0x00258B00 - 0x00258B08     Function:
                                                        RCObj_nor_obj_apper
0x00158B90 - 0x00158ED4     0x00258B10 - 0x00258E54     Function:
                                                        RCObj_nor_item_disp
0x00158EE0 - 0x00158FE0     0x00258E60 - 0x00258F60     Function:
                                                        RCObj_nor_item_disap
0x00158FE0 - 0x001590E8     0x00258F60 - 0x00259068     Function:
                                                        RCObj_nor_item_apper
0x001590F0 - 0x001591BC     0x00259070 - 0x0025913C     Function:
                                                        Rec_Nor_Delete
0x001591C0 - 0x001599E8     0x00259140 - 0x00259968     Function:
                                                        Rec_Nor_DetailDisp
0x001599F0 - 0x00159F8C     0x00259970 - 0x00259F0C     Function:
                                                        Rec_Nor
0x00159F90 - 0x0015A2BC     0x00259F10 - 0x0025A23C     Function:
                                                        rec_suv_time_disp
0x0015A2C0 - 0x0015A4D4     0x0025A240 - 0x0025A454     Function:
                                                        rec_suv_item_disp_sub
0x0015A4E0 - 0x0015A500     0x0025A460 - 0x0025A480     Function:
                                                        Rec_Suv_BoolDelete
0x0015A500 - 0x0015A634     0x0025A480 - 0x0025A5B4     Function:
                                                        RCObj_suv_item_disp
0x0015A640 - 0x0015A70C     0x0025A5C0 - 0x0025A68C     Function:
                                                        RCObj_suv_item_disap
0x0015A710 - 0x0015A7FC     0x0025A690 - 0x0025A77C     Function:
                                                        RCObj_suv_item_apper
0x0015A800 - 0x0015A820     0x0025A780 - 0x0025A7A0     Function:
                                                        Rec_Suv_Delete
0x0015A820 - 0x0015A9F0     0x0025A7A0 - 0x0025A970     Function:
                                                        Rec_Suv_DetailDisp
0x0015A9F0 - 0x0015ABB8     0x0025A970 - 0x0025AB38     Function:
                                                        Rec_Suv
0x0015ABC0 - 0x0015ADEC     0x0025AB40 - 0x0025AD6C     Function:
                                                        rec_cmb_item_disp_sub
0x0015ADF0 - 0x0015AE10     0x0025AD70 - 0x0025AD90     Function:
                                                        Rec_Cmb_BoolDelete
0x0015AE10 - 0x0015AF44     0x0025AD90 - 0x0025AEC4     Function:
                                                        RCObj_cmb_item_disp
0x0015AF50 - 0x0015AF58     0x0025AED0 - 0x0025AED8     Function:
                                                        RCObj_cmb_item_disap
0x0015AF60 - 0x0015AF68     0x0025AEE0 - 0x0025AEE8     Function:
                                                        RCObj_cmb_item_apper
0x0015AF70 - 0x0015AF90     0x0025AEF0 - 0x0025AF10     Function:
                                                        Rec_Cmb_Delete
0x0015AF90 - 0x0015B174     0x0025AF10 - 0x0025B0F4     Function:
                                                        Rec_Cmb_DetailDisp
0x0015B180 - 0x0015B348     0x0025B100 - 0x0025B2C8     Function:
                                                        Rec_Cmb
0x0015B350 - 0x0015B358     0x0025B2D0 - 0x0025B2D8     Function:
                                                        NetWin_Listdtl2SetPlayerListFile
0x0015B360 - 0x0015B374     0x0025B2E0 - 0x0025B2F4     Function:
                                                        NetWin_Listdtl2End
0x0015B380 - 0x0015B4A8     0x0025B300 - 0x0025B428     Function:
                                                        NetWin_Listdtl2Main
0x0015B4B0 - 0x0015B688     0x0025B430 - 0x0025B608     Function:
                                                        NetWin_Listdtl2Init
0x0015B690 - 0x0015B6F8     0x0025B610 - 0x0025B678     Function:
                                                        NetWin_Listdtl2
0x0015B700 - 0x0015B708     0x0025B680 - 0x0025B688     Function:
                                                        NetWin_ListdtlSetPlayerListFile
0x0015B710 - 0x0015B758     0x0025B690 - 0x0025B6D8     Function:
                                                        CwsWin_ListdtlNoAlpha
0x0015B760 - 0x0015BD20     0x0025B6E0 - 0x0025BCA0     Function:
                                                        CwsWin_ListdtlDisp
0x0015BD20 - 0x0015BD34     0x0025BCA0 - 0x0025BCB4     Function:
                                                        NetWin_ListdtlEnd
0x0015BD40 - 0x0015BE78     0x0025BCC0 - 0x0025BDF8     Function:
                                                        NetWin_ListdtlMain
0x0015BE80 - 0x0015BF3C     0x0025BE00 - 0x0025BEBC     Function:
                                                        NetWin_ListdtlInit
0x0015BF40 - 0x0015BFA8     0x0025BEC0 - 0x0025BF28     Function:
                                                        NetWin_Listdtl
0x0015BFB0 - 0x0015BFB8     0x0025BF30 - 0x0025BF38     Function:
                                                        NetWin_Listdtl3SetPlayerListFile
0x0015BFC0 - 0x0015BFD4     0x0025BF40 - 0x0025BF54     Function:
                                                        NetWin_Listdtl3End
0x0015BFE0 - 0x0015C258     0x0025BF60 - 0x0025C1D8     Function:
                                                        NetWin_Listdtl3Main
0x0015C260 - 0x0015C6D4     0x0025C1E0 - 0x0025C654     Function:
                                                        NetWin_Listdtl3Init
0x0015C6E0 - 0x0015C748     0x0025C660 - 0x0025C6C8     Function:
                                                        NetWin_Listdtl3
0x0015C750 - 0x0015C764     0x0025C6D0 - 0x0025C6E4     Function:
                                                        NetWin_InfoboardEnd
0x0015C770 - 0x0015C778     0x0025C6F0 - 0x0025C6F8     Function:
                                                        NetWin_InfoboardMain
0x0015C780 - 0x0015C7C0     0x0025C700 - 0x0025C740     Function:
                                                        NetWin_InfoboardInit
0x0015C7C0 - 0x0015C828     0x0025C740 - 0x0025C7A8     Function:
                                                        NetWin_Infoboard
0x0015C830 - 0x0015C93C     0x0025C7B0 - 0x0025C8BC     Function:
                                                        NetGameRCSetNM
0x0015C940 - 0x0015CC30     0x0025C8C0 - 0x0025CBB0     Function:
                                                        NetGameRCRankingKey
0x0015CC30 - 0x0015CFF0     0x0025CBB0 - 0x0025CF70     Function:
                                                        NetGameRCRankingMain
0x0015CFF0 - 0x0015D408     0x0025CF70 - 0x0025D388     Function:
                                                        NetGameRCRankingInit
0x0015D410 - 0x0015D690     0x0025D390 - 0x0025D610     Function:
                                                        NetGameRCSelectKey
0x0015D690 - 0x0015D968     0x0025D610 - 0x0025D8E8     Function:
                                                        NetGameRCSelectMain
0x0015D970 - 0x0015DA24     0x0025D8F0 - 0x0025D9A4     Function:
                                                        NetGameRCSelectInit
0x0015DA30 - 0x0015DD08     0x0025D9B0 - 0x0025DC88     Function:
                                                        NetGameRCKey
0x0015DD10 - 0x0015DEC8     0x0025DC90 - 0x0025DE48     Function:
                                                        NetGameRCMain
0x0015DED0 - 0x0015DF8C     0x0025DE50 - 0x0025DF0C     Function:
                                                        NetGameRCInit2
0x0015DF90 - 0x0015E0B0     0x0025DF10 - 0x0025E030     Function:
                                                        NetGameRCStepout
0x0015E0B0 - 0x0015E140     0x0025E030 - 0x0025E0C0     Function:
                                                        NetGameRCStepin
0x0015E140 - 0x0015E374     0x0025E0C0 - 0x0025E2F4     Function:
                                                        NetGameRCExCursorOn
0x0015E380 - 0x0015E484     0x0025E300 - 0x0025E404     Function:
                                                        NetGameRCExCursorOff
0x0015E490 - 0x0015E6F4     0x0025E410 - 0x0025E674     Function:
                                                        NetGameRCExClose
0x0015E700 - 0x0015E89C     0x0025E680 - 0x0025E81C     Function:
                                                        NetGameRCExOpen
0x0015E8A0 - 0x0015EE24     0x0025E820 - 0x0025EDA4     Function:
                                                        NetGameRCInit
0x0015EE30 - 0x0015F0A4     0x0025EDB0 - 0x0025F024     Function:
                                                        NetGameChallengeCourseConvert
0x0015F0B0 - 0x0015F334     0x0025F030 - 0x0025F2B4     Function:
                                                        NetGameChallengeMain
0x0015F340 - 0x0015F460     0x0025F2C0 - 0x0025F3E0     Function:
                                                        NetGameChallengeInit
0x0015F460 - 0x0015F6F0     0x0025F3E0 - 0x0025F670     Function:
                                                        adv_ds_display_disp
0x0015F6F0 - 0x0015F6F8     0x0025F670 - 0x0025F678     Function:
                                                        adv_ds_display_disap
0x0015F700 - 0x0015F738     0x0025F680 - 0x0025F6B8     Function:
                                                        adv_ds_display_exec
0x0015F740 - 0x0015F784     0x0025F6C0 - 0x0025F704     Function:
                                                        adv_ds_display_apper
0x0015F790 - 0x0015FA28     0x0025F710 - 0x0025F9A8     Function:
                                                        adv_ms_display_disp
0x0015FA30 - 0x0015FA38     0x0025F9B0 - 0x0025F9B8     Function:
                                                        adv_ms_display_disap
0x0015FA40 - 0x0015FA78     0x0025F9C0 - 0x0025F9F8     Function:
                                                        adv_ms_display_exec
0x0015FA80 - 0x0015FAC4     0x0025FA00 - 0x0025FA44     Function:
                                                        adv_ms_display_apper
0x0015FAD0 - 0x0015FEF0     0x0025FA50 - 0x0025FE70     Function:
                                                        adv_name_disp
0x0015FEF0 - 0x001600B0     0x0025FE70 - 0x00260030     Function:
                                                        adv_name_disap
0x001600B0 - 0x001600B8     0x00260030 - 0x00260038     Function:
                                                        adv_name_exec
0x001600C0 - 0x00160320     0x00260040 - 0x002602A0     Function:
                                                        adv_name_apper
0x00160320 - 0x00160700     0x002602A0 - 0x00260680     Function:
                                                        adv_difficulty_item_disp
0x00160700 - 0x00160920     0x00260680 - 0x002608A0     Function:
                                                        adv_difficulty_item_disap
0x00160920 - 0x00160928     0x002608A0 - 0x002608A8     Function:
                                                        adv_difficulty_item_exec
0x00160930 - 0x00160DB8     0x002608B0 - 0x00260D38     Function:
                                                        adv_difficulty_item_apper
0x00160DC0 - 0x00161460     0x00260D40 - 0x002613E0     Function:
                                                        adv_meter_item_disp
0x00161460 - 0x00161650     0x002613E0 - 0x002615D0     Function:
                                                        adv_meter_item_disap
0x00161650 - 0x00161658     0x002615D0 - 0x002615D8     Function:
                                                        adv_meter_item_exec
0x00161660 - 0x001619B8     0x002615E0 - 0x00261938     Function:
                                                        adv_meter_item_apper
0x001619C0 - 0x00161A6C     0x00261940 - 0x002619EC     Function:
                                                        adv_difficulty_sel_finish_all
0x00161A70 - 0x00161A78     0x002619F0 - 0x002619F8     Function:
                                                        adv_difficulty_sel_finish
0x00161A80 - 0x00161EF0     0x00261A00 - 0x00261E70     Function:
                                                        adv_difficulty_sel_step
0x00161EF0 - 0x00161F18     0x00261E70 - 0x00261E98     Function:
                                                        adv_difficulty_sel_init
0x00161F20 - 0x00161F28     0x00261EA0 - 0x00261EA8     Function:
                                                        adv_meter_sel_finish
0x00161F30 - 0x00162408     0x00261EB0 - 0x00262388     Function:
                                                        adv_meter_sel_step
0x00162410 - 0x00162438     0x00262390 - 0x002623B8     Function:
                                                        adv_meter_sel_init
0x00162440 - 0x001625A0     0x002623C0 - 0x00262520     Function:
                                                        adv_btn_disp
0x001625A0 - 0x00162698     0x00262520 - 0x00262618     Function:
                                                        adv_btn_move
0x001626A0 - 0x00162CE8     0x00262620 - 0x00262C68     Function:
                                                        adv_top_item_disp
0x00162CF0 - 0x00162EF0     0x00262C70 - 0x00262E70     Function:
                                                        adv_top_item_disap
0x00162EF0 - 0x00162EF8     0x00262E70 - 0x00262E78     Function:
                                                        adv_top_item_exec
0x00162F00 - 0x00163310     0x00262E80 - 0x00263290     Function:
                                                        adv_top_item_apper
0x00163310 - 0x001633EC     0x00263290 - 0x0026336C     Function:
                                                        adv_topmenu_sel_finish
0x001633F0 - 0x00163734     0x00263370 - 0x002636B4     Function:
                                                        adv_topmenu_sel_step
0x00163740 - 0x00163810     0x002636C0 - 0x00263790     Function:
                                                        adv_topmenu_sel_init
0x00163810 - 0x0016381C     0x00263790 - 0x0026379C     Function:
                                                        adv_topmenu_sel_init_all
0x00163820 - 0x0016383C     0x002637A0 - 0x002637BC     Function:
                                                        EdsSupGetScore
0x00163840 - 0x00163894     0x002637C0 - 0x00263814     Function:
                                                        EdsSupCalcScore
0x001638A0 - 0x001638AC     0x00263820 - 0x0026382C     Function:
                                                        EdsSupGetPlayLevel
0x001638B0 - 0x00163DF4     0x00263830 - 0x00263D74     Function:
                                                        EdsSupScoreCreate
0x00163E00 - 0x00164028     0x00263D80 - 0x00263FA8     Function:
                                                        EdsSupNextStageCreate
0x00164030 - 0x00164088     0x00263FB0 - 0x00264008     Function:
                                                        EdsSupBeforeStageDataSet
0x00164090 - 0x00164160     0x00264010 - 0x002640E0     Function:
                                                        EdsSupGetMipTable
0x00164160 - 0x00164324     0x002640E0 - 0x002642A4     Function:
                                                        EdsSupInitMipTable
0x00164330 - 0x00164508     0x002642B0 - 0x00264488     Function:
                                                        EdsSupGetLevelType
0x00164510 - 0x00164694     0x00264490 - 0x00264614     Function:
                                                        EdsSupTrackSorting
0x001646A0 - 0x001648A0     0x00264620 - 0x00264820     Function:
                                                        EdsInitOrderFlag
0x001648A0 - 0x00164D98     0x00264820 - 0x00264D18     Function:
                                                        EdsSetupParameter
0x00164DA0 - 0x00164F14     0x00264D20 - 0x00264E94     Function:
                                                        EdsResetPlayLevel
0x00164F20 - 0x0016500C     0x00264EA0 - 0x00264F8C     Function:
                                                        adv_endless_setup
0x00165010 - 0x00165104     0x00264F90 - 0x00265084     Function:
                                                        get_bpm_from_dance_num
0x00165110 - 0x00165354     0x00265090 - 0x002652D4     Function:
                                                        set_check_mark
0x00165360 - 0x001655A8     0x002652E0 - 0x00265528     Function:
                                                        disp_batch_yes_no_window
0x001655B0 - 0x0016581C     0x00265530 - 0x0026579C     Function:
                                                        endless_program_title_disp
0x00165820 - 0x00165ABC     0x002657A0 - 0x00265A3C     Function:
                                                        endless_program_title_disap
0x00165AC0 - 0x00165AC8     0x00265A40 - 0x00265A48     Function:
                                                        endless_program_title_exec
0x00165AD0 - 0x00165D68     0x00265A50 - 0x00265CE8     Function:
                                                        endless_program_title_apper
0x00165D70 - 0x00165D78     0x00265CF0 - 0x00265CF8     Function:
                                                        endless_program_cursor_disp
0x00165D80 - 0x00165F74     0x00265D00 - 0x00265EF4     Function:
                                                        endless_program_cursor_disap
0x00165F80 - 0x00165FF4     0x00265F00 - 0x00265F74     Function:
                                                        endless_program_cursor_exec
0x00166000 - 0x001661F0     0x00265F80 - 0x00266170     Function:
                                                        endless_program_cursor_apper
0x001661F0 - 0x00167198     0x00266170 - 0x00267118     Function:
                                                        endless_program_item_disp
0x001671A0 - 0x00167480     0x00267120 - 0x00267400     Function:
                                                        draw_endless_frame
0x00167480 - 0x00167740     0x00267400 - 0x002676C0     Function:
                                                        endless_program_item_disap
0x00167740 - 0x00167BD8     0x002676C0 - 0x00267B58     Function:
                                                        endless_program_item_exec
0x00167BE0 - 0x00168088     0x00267B60 - 0x00268008     Function:
                                                        endless_program_item_apper
0x00168090 - 0x00168810     0x00268010 - 0x00268790     Function:
                                                        endless_menu_item_disp
0x00168810 - 0x00168A20     0x00268790 - 0x002689A0     Function:
                                                        endless_menu_item_disap
0x00168A20 - 0x00168A28     0x002689A0 - 0x002689A8     Function:
                                                        endless_menu_item_exec
0x00168A30 - 0x00168CF0     0x002689B0 - 0x00268C70     Function:
                                                        endless_menu_item_apper
0x00168CF0 - 0x001690A4     0x00268C70 - 0x00269024     Function:
                                                        endless_program_select
0x001690B0 - 0x00169794     0x00269030 - 0x00269714     Function:
                                                        endless_program
0x001697A0 - 0x00169BA8     0x00269720 - 0x00269B28     Function:
                                                        endless_menu_select
0x00169BB0 - 0x00169C04     0x00269B30 - 0x00269B84     Function:
                                                        adv_endless_sel_finish_all
0x00169C10 - 0x00169C18     0x00269B90 - 0x00269B98     Function:
                                                        adv_endless_sel_finish
0x00169C20 - 0x0016A078     0x00269BA0 - 0x00269FF8     Function:
                                                        adv_endless_sel_step
0x0016A080 - 0x0016A2D4     0x0026A000 - 0x0026A254     Function:
                                                        adv_endless_sel_init
0x0016A2E0 - 0x0016A3D4     0x0026A260 - 0x0026A354     Function:
                                                        adv_endless_setup__for_combo_and_survival
0x0016A3E0 - 0x0016AA50     0x0026A360 - 0x0026A9D0     Function:
                                                        extras_main
0x0016AA50 - 0x0016AA5C     0x0026A9D0 - 0x0026A9DC     Function:
                                                        extras_init
0x0016AA60 - 0x0016ABE0     0x0026A9E0 - 0x0026AB60     Function:
                                                        advanced_option_icon_disp
0x0016ABE0 - 0x0016B238     0x0026AB60 - 0x0026B1B8     Function:
                                                        advanced_option_menu_disp
0x0016B240 - 0x0016B274     0x0026B1C0 - 0x0026B1F4     Function:
                                                        advanced_option_disp
0x0016B280 - 0x0016B288     0x0026B200 - 0x0026B208     Function:
                                                        advanced_window_disp
0x0016B290 - 0x0016B4B8     0x0026B210 - 0x0026B438     Function:
                                                        advanced_select_options
0x0016B4C0 - 0x0016B964     0x0026B440 - 0x0026B8E4     Function:
                                                        AdvancedModeSaveDataDefault
0x0016B970 - 0x0016B984     0x0026B8F0 - 0x0026B904     Function:
                                                        EdsGetOptionDefaultStatus
0x0016B990 - 0x0016B9A0     0x0026B910 - 0x0026B920     Function:
                                                        EdsGetSystemDefaultStatus
0x0016B9A0 - 0x0016B9DC     0x0026B920 - 0x0026B95C     Function:
                                                        load_endless_menu_data
0x0016B9E0 - 0x0016B9E8     0x0026B960 - 0x0026B968     Function:
                                                        save_option_data_for_endless
0x0016B9F0 - 0x0016B9F8     0x0026B970 - 0x0026B978     Function:
                                                        load_option_data_for_endless
0x0016BA00 - 0x0016BBC4     0x0026B980 - 0x0026BB44     Function:
                                                        save_option_data_for_nonstop
0x0016BBD0 - 0x0016BC9C     0x0026BB50 - 0x0026BC1C     Function:
                                                        load_option_data_for_nonstop
0x0016BCA0 - 0x0016BCB4     0x0026BC20 - 0x0026BC34     Function:
                                                        get_advanced_tex_id
0x0016BCC0 - 0x0016BE18     0x0026BC40 - 0x0026BD98     Function:
                                                        set_advanced_tex_id
0x0016BE20 - 0x0016BED0     0x0026BDA0 - 0x0026BE50     Function:
                                                        get_nonstop_save_workp
0x0016BED0 - 0x0016BFD8     0x0026BE50 - 0x0026BF58     Function:
                                                        ResetAdvancedModeTex
0x0016BFE0 - 0x0016C194     0x0026BF60 - 0x0026C114     Function:
                                                        advanced_data_load
0x0016C1A0 - 0x0016C1AC     0x0026C120 - 0x0026C12C     Function:
                                                        get_advanced_datap
0x0016C1B0 - 0x0016C52C     0x0026C130 - 0x0026C4AC     Function:
                                                        nonstop_order_info_select
0x0016C530 - 0x0016C710     0x0026C4B0 - 0x0026C690     Function:
                                                        nonstop_order_index_select
0x0016C710 - 0x0016CA40     0x0026C690 - 0x0026C9C0     Function:
                                                        nonstop_course_select
0x0016CA40 - 0x0016CBD8     0x0026C9C0 - 0x0026CB58     Function:
                                                        set_nonstop_course_change
0x0016CBE0 - 0x0016CC68     0x0026CB60 - 0x0026CBE8     Function:
                                                        set_nonstop_course_prim
0x0016CC70 - 0x0016CC7C     0x0026CBF0 - 0x0026CBFC     Function:
                                                        get_nonstop_meter_type
0x0016CC80 - 0x0016CC8C     0x0026CC00 - 0x0026CC0C     Function:
                                                        get_nonstop_course_no
0x0016CC90 - 0x0016CDE8     0x0026CC10 - 0x0026CD68     Function:
                                                        set_nonstop_course_list
0x0016CDF0 - 0x0016DB1C     0x0026CD70 - 0x0026DA9C     Function:
                                                        nonstop_order_item_disp
0x0016DB20 - 0x0016DD38     0x0026DAA0 - 0x0026DCB8     Function:
                                                        nonstop_order_item_disap
0x0016DD40 - 0x0016DD48     0x0026DCC0 - 0x0026DCC8     Function:
                                                        nonstop_order_item_exec
0x0016DD50 - 0x0016E078     0x0026DCD0 - 0x0026DFF8     Function:
                                                        nonstop_order_item_apper
0x0016E080 - 0x0016EB38     0x0026E000 - 0x0026EAB8     Function:
                                                        nonstop_left_item_disp
0x0016EB40 - 0x0016EDCC     0x0026EAC0 - 0x0026ED4C     Function:
                                                        nonstop_left_item_disap
0x0016EDD0 - 0x0016EE08     0x0026ED50 - 0x0026ED88     Function:
                                                        nonstop_left_item_exec
0x0016EE10 - 0x0016F15C     0x0026ED90 - 0x0026F0DC     Function:
                                                        nonstop_left_item_apper
0x0016F160 - 0x0016F828     0x0026F0E0 - 0x0026F7A8     Function:
                                                        nonstop_music_item_disp
0x0016F830 - 0x0016FA60     0x0026F7B0 - 0x0026F9E0     Function:
                                                        nonstop_music_item_disap
0x0016FA60 - 0x0016FDBC     0x0026F9E0 - 0x0026FD3C     Function:
                                                        nonstop_music_item_exec
0x0016FDC0 - 0x00170164     0x0026FD40 - 0x002700E4     Function:
                                                        nonstop_music_item_apper
0x00170170 - 0x00170504     0x002700F0 - 0x00270484     Function:
                                                        nonstop_meter_disp
0x00170510 - 0x001706C8     0x00270490 - 0x00270648     Function:
                                                        nonstop_meter_disap
0x001706D0 - 0x001706D8     0x00270650 - 0x00270658     Function:
                                                        nonstop_meter_exec
0x001706E0 - 0x00170970     0x00270660 - 0x002708F0     Function:
                                                        nonstop_meter_apper
0x00170970 - 0x00170B08     0x002708F0 - 0x00270A88     Function:
                                                        adv_sel1_disp
0x00170B10 - 0x00170EC4     0x00270A90 - 0x00270E44     Function:
                                                        adv_sel0_disp
0x00170ED0 - 0x00171060     0x00270E50 - 0x00270FE0     Function:
                                                        adv_sel0_disap
0x00171060 - 0x00171068     0x00270FE0 - 0x00270FE8     Function:
                                                        adv_sel0_exec
0x00171070 - 0x00171310     0x00270FF0 - 0x00271290     Function:
                                                        adv_sel0_apper
0x00171310 - 0x0017139C     0x00271290 - 0x0027131C     Function:
                                                        adv_nonstop_sel_finish_all
0x001713A0 - 0x001713A8     0x00271320 - 0x00271328     Function:
                                                        adv_nonstop_sel_finish
0x001713B0 - 0x00171EBC     0x00271330 - 0x00271E3C     Function:
                                                        adv_nonstop_sel_step
0x00171EC0 - 0x00171FE4     0x00271E40 - 0x00271F64     Function:
                                                        adv_nonstop_sel_init
0x00171FF0 - 0x001720E4     0x00271F70 - 0x00272064     Function:
                                                        NetWin_InfoselSetPoint
0x001720F0 - 0x0017217C     0x00272070 - 0x002720FC     Function:
                                                        NetWin_InfoselSetDancer
0x00172180 - 0x00172194     0x00272100 - 0x00272114     Function:
                                                        NetWin_InfoselSetName
0x001721A0 - 0x001721B4     0x00272120 - 0x00272134     Function:
                                                        NetWin_InfoselSetNumber
0x001721C0 - 0x001721D4     0x00272140 - 0x00272154     Function:
                                                        NetWin_InfoselEnd
0x001721E0 - 0x001721E8     0x00272160 - 0x00272168     Function:
                                                        NetWin_InfoselMain
0x001721F0 - 0x00172340     0x00272170 - 0x002722C0     Function:
                                                        NetWin_InfoselInit
0x00172340 - 0x001723A8     0x002722C0 - 0x00272328     Function:
                                                        NetWin_Infosel
0x001723B0 - 0x00172434     0x00272330 - 0x002723B4     Function:
                                                        NetWin_RccsselReflash
0x00172440 - 0x00172554     0x002723C0 - 0x002724D4     Function:
                                                        NetWin_RccsselSetPage
0x00172560 - 0x00172568     0x002724E0 - 0x002724E8     Function:
                                                        NetWin_RccsselSetLinePosY
0x00172570 - 0x00172578     0x002724F0 - 0x002724F8     Function:
                                                        NetWin_RccsselSetRcData
0x00172580 - 0x00172B10     0x00272500 - 0x00272A90     Function:
                                                        NetWin_RccsselLineDisp
0x00172B10 - 0x00173130     0x00272A90 - 0x002730B0     Function:
                                                        NetWin_RccsselBoardDisp
0x00173130 - 0x00173144     0x002730B0 - 0x002730C4     Function:
                                                        NetWin_RccsselEnd
0x00173150 - 0x00173470     0x002730D0 - 0x002733F0     Function:
                                                        NetWin_RccsselMain
0x00173470 - 0x0017352C     0x002733F0 - 0x002734AC     Function:
                                                        NetWin_RccsselInit
0x00173530 - 0x00173598     0x002734B0 - 0x00273518     Function:
                                                        NetWin_Rccssel
0x001735A0 - 0x00173750     0x00273520 - 0x002736D0     Function:
                                                        tr_opt_line_disp
0x00173750 - 0x00173A1C     0x002736D0 - 0x0027399C     Function:
                                                        asi_item_value_disp
0x00173A20 - 0x00173D6C     0x002739A0 - 0x00273CEC     Function:
                                                        opt_item_value_disp
0x00173D70 - 0x0017447C     0x00273CF0 - 0x002743FC     Function:
                                                        menu_item_value_disp
0x00174480 - 0x0017463C     0x00274400 - 0x002745BC     Function:
                                                        tr_update_opt_lr
0x00174640 - 0x00174BBC     0x002745C0 - 0x00274B3C     Function:
                                                        tr_update_lr
0x00174BC0 - 0x00174CFC     0x00274B40 - 0x00274C7C     Function:
                                                        tr_menu_disap
0x00174D00 - 0x00174ED0     0x00274C80 - 0x00274E50     Function:
                                                        tr_menu_apper
0x00174ED0 - 0x001751A8     0x00274E50 - 0x00275128     Function:
                                                        TRObj_option_disp
0x001751B0 - 0x00175218     0x00275130 - 0x00275198     Function:
                                                        TRObj_option_func
0x00175220 - 0x00175510     0x002751A0 - 0x00275490     Function:
                                                        TRObj_assist_disp
0x00175510 - 0x00175578     0x00275490 - 0x002754F8     Function:
                                                        TRObj_assist_func
0x00175580 - 0x00175C80     0x00275500 - 0x00275C00     Function:
                                                        TRObj_menu_item_disp
0x00175C80 - 0x00175E2C     0x00275C00 - 0x00275DAC     Function:
                                                        TRObj_menu_item_disap
0x00175E30 - 0x00175FBC     0x00275DB0 - 0x00275F3C     Function:
                                                        TRObj_menu_item_apper
0x00175FC0 - 0x00176594     0x00275F40 - 0x00276514     Function:
                                                        Train_Menu
0x001765A0 - 0x00176880     0x00276520 - 0x00276800     Function:
                                                        tr_tex_init
0x00176880 - 0x00176A04     0x00276800 - 0x00276984     Function:
                                                        TRObj_seq_disp
0x00176A10 - 0x00176B60     0x00276990 - 0x00276AE0     Function:
                                                        TRObj_seq_func
0x00176B60 - 0x00176C08     0x00276AE0 - 0x00276B88     Function:
                                                        TRObj_label_disap
0x00176C10 - 0x00176CB0     0x00276B90 - 0x00276C30     Function:
                                                        TRObj_label_apper
0x00176CB0 - 0x00176CD0     0x00276C30 - 0x00276C50     Function:
                                                        TRObj_win_disp
0x00176CD0 - 0x00177208     0x00276C50 - 0x00277188     Function:
                                                        TRObj_win_func
0x00177210 - 0x00177258     0x00277190 - 0x002771D8     Function:
                                                        tr_obj_disap
0x00177260 - 0x001772EC     0x002771E0 - 0x0027726C     Function:
                                                        tr_obj_set
0x001772F0 - 0x00177538     0x00277270 - 0x002774B8     Function:
                                                        Tr_frame_disp
0x00177540 - 0x00177604     0x002774C0 - 0x00277584     Function:
                                                        Tr_PadLRRepeat
0x00177610 - 0x0017765C     0x00277590 - 0x002775DC     Function:
                                                        Tr_PadRepeat
0x00177660 - 0x001776AC     0x002775E0 - 0x0027762C     Function:
                                                        Tr_PadPush
0x001776B0 - 0x001776FC     0x00277630 - 0x0027767C     Function:
                                                        Tr_PadTrg
0x00177700 - 0x00177708     0x00277680 - 0x00277688     Function:
                                                        Term_Train
0x00177710 - 0x00177C28     0x00277690 - 0x00277BA8     Function:
                                                        Step_Train
0x00177C30 - 0x00177EB8     0x00277BB0 - 0x00277E38     Function:
                                                        Init_Train
0x00177EC0 - 0x0017810C     0x00277E40 - 0x0027808C     Function:
                                                        tr_msel_init
0x00178110 - 0x001783E4     0x00278090 - 0x00278364     Function:
                                                        Tr_ms_disap
0x001783F0 - 0x001786F0     0x00278370 - 0x00278670     Function:
                                                        Tr_ms_apper
0x001786F0 - 0x00178C9C     0x00278670 - 0x00278C1C     Function:
                                                        Train_Msel
0x00178CA0 - 0x001793A8     0x00278C20 - 0x00279328     Function:
                                                        NetWin_VSWinDataSet
0x001793B0 - 0x00179650     0x00279330 - 0x002795D0     Function:
                                                        NetWin_VSWinMoveStr
0x00179650 - 0x00179C10     0x002795D0 - 0x00279B90     Function:
                                                        NetWin_VSWinDispWire2P
0x00179C10 - 0x0017A1D4     0x00279B90 - 0x0027A154     Function:
                                                        NetWin_VSWinDispWire1P
0x0017A1E0 - 0x0017A1F4     0x0027A160 - 0x0027A174     Function:
                                                        NetWin_VSWinEnd
0x0017A200 - 0x0017A4F8     0x0027A180 - 0x0027A478     Function:
                                                        NetWin_VSWinMain
0x0017A500 - 0x0017A590     0x0027A480 - 0x0027A510     Function:
                                                        NetWin_VSWinInit
0x0017A590 - 0x0017A5F8     0x0027A510 - 0x0027A578     Function:
                                                        NetWin_VSWin
0x0017A600 - 0x0017A628     0x0027A580 - 0x0027A5A8     Function:
                                                        dmm_bgm_set
0x0017A630 - 0x0017A690     0x0027A5B0 - 0x0027A610     Function:
                                                        dmm_bgm_call
0x0017A690 - 0x0017A6B8     0x0027A610 - 0x0027A638     Function:
                                                        dmm_bgm_init
0x0017A6C0 - 0x0017A6F8     0x0027A640 - 0x0027A678     Function:
                                                        dmm_get_message_data_addr
0x0017A700 - 0x0017A754     0x0027A680 - 0x0027A6D4     Function:
                                                        dmm_erace_bind
0x0017A760 - 0x0017A7F8     0x0027A6E0 - 0x0027A778     Function:
                                                        dmm_bind_th
0x0017A800 - 0x0017A90C     0x0027A780 - 0x0027A88C     Function:
                                                        dmm_bind_all_tex
0x0017A910 - 0x0017A97C     0x0027A890 - 0x0027A8FC     Function:
                                                        dmm_bind_data_sel_tex
0x0017A980 - 0x0017A990     0x0027A900 - 0x0027A910     Function:
                                                        dmm_set_font
0x0017A990 - 0x0017A9B0     0x0027A910 - 0x0027A930     Function:
                                                        dmm_func_decode_bin
0x0017A9B0 - 0x0017A9E8     0x0027A930 - 0x0027A968     Function:
                                                        dmm_func_prepare_bk
0x0017A9F0 - 0x0017AD18     0x0027A970 - 0x0027AC98     Function:
                                                        dmm_disp_logo
0x0017AD20 - 0x0017AD40     0x0027ACA0 - 0x0027ACC0     Function:
                                                        dmm_get_arrow_pos_pattern
0x0017AD40 - 0x0017AD60     0x0027ACC0 - 0x0027ACE0     Function:
                                                        dmm_get_step_mark_color
0x0017AD60 - 0x0017AD80     0x0027ACE0 - 0x0027AD00     Function:
                                                        dmm_is_life_mode
0x0017AD80 - 0x0017ADE8     0x0027AD00 - 0x0027AD68     Function:
                                                        dmm_is_assigned_subject
0x0017ADF0 - 0x0017AE18     0x0027AD70 - 0x0027AD98     Function:
                                                        dmm_get_minfo_subject_id
0x0017AE20 - 0x0017AE28     0x0027ADA0 - 0x0027ADA8     Function:
                                                        dmm_get_minfo_music_num
0x0017AE30 - 0x0017AE90     0x0027ADB0 - 0x0027AE10     Function:
                                                        dmm_get_wxy_from_subject_id
0x0017AE90 - 0x0017AF20     0x0027AE10 - 0x0027AEA0     Function:
                                                        dmm_get_subject_id_from_wxy
0x0017AF20 - 0x0017AF60     0x0027AEA0 - 0x0027AEE0     Function:
                                                        dmm_func_wait_world_move_count
0x0017AF60 - 0x0017AF68     0x0027AEE0 - 0x0027AEE8     Function:
                                                        dmm_func_get_world_move_count
0x0017AF70 - 0x0017AF78     0x0027AEF0 - 0x0027AEF8     Function:
                                                        dmm_func_set_world_move_count
0x0017AF80 - 0x0017AFA0     0x0027AF00 - 0x0027AF20     Function:
                                                        dmm_func_main_world_move_count
0x0017AFA0 - 0x0017AFAC     0x0027AF20 - 0x0027AF2C     Function:
                                                        dmm_func_init_world_move_count
0x0017AFB0 - 0x0017B038     0x0027AF30 - 0x0027AFB8     Function:
                                                        dmm_wait_obj_move
0x0017B040 - 0x0017B058     0x0027AFC0 - 0x0027AFD8     Function:
                                                        dmm_get_obj_count
0x0017B060 - 0x0017B0D8     0x0027AFE0 - 0x0027B058     Function:
                                                        dmm_set_obj_move
0x0017B0E0 - 0x0017B100     0x0027B060 - 0x0027B080     Function:
                                                        dmm_init_obj_move_work
0x0017B100 - 0x0017B110     0x0027B080 - 0x0027B090     Function:
                                                        dmm_get_obj_move_work
0x0017B110 - 0x0017B138     0x0027B090 - 0x0027B0B8     Function:
                                                        dmm_wait
0x0017B140 - 0x0017B14C     0x0027B0C0 - 0x0027B0CC     Function:
                                                        dmm_set_wait
0x0017B150 - 0x0017B364     0x0027B0D0 - 0x0027B2E4     Function:
                                                        dmm_func_play_course_load
0x0017B370 - 0x0017B6BC     0x0027B2F0 - 0x0027B63C     Function:
                                                        dmm_func_play_pre_load
0x0017B6C0 - 0x0017B6E0     0x0027B640 - 0x0027B660     Function:
                                                        dmm_func_init_play_pre_load
0x0017B6E0 - 0x0017B73C     0x0027B660 - 0x0027B6BC     Function:
                                                        dmm_set_dancer_onoff
0x0017B740 - 0x0017B788     0x0027B6C0 - 0x0027B708     Function:
                                                        dmm_set_movie_onoff
0x0017B790 - 0x0017B910     0x0027B710 - 0x0027B890     Function:
                                                        dmm_func_set_g_game_w
0x0017B910 - 0x0017BB38     0x0027B890 - 0x0027BAB8     Function:
                                                        dmm_func_init_g_game_w
0x0017BB40 - 0x0017BB90     0x0027BAC0 - 0x0027BB10     Function:
                                                        is_dancer_default
0x0017BB90 - 0x0017C014     0x0027BB10 - 0x0027BF94     Function:
                                                        dmm_hide_check
0x0017C020 - 0x0017C054     0x0027BFA0 - 0x0027BFD4     Function:
                                                        dmm_quit_on
0x0017C060 - 0x0017C08C     0x0027BFE0 - 0x0027C00C     Function:
                                                        dmm_quit_off
0x0017C090 - 0x0017C1D4     0x0027C010 - 0x0027C154     Function:
                                                        Tr_bar_digit_disp
0x0017C1E0 - 0x0017C20C     0x0027C160 - 0x0027C18C     Function:
                                                        Tr_get_lr_item_max
0x0017C210 - 0x0017C270     0x0027C190 - 0x0027C1F0     Function:
                                                        Tr_get_str
0x0017C270 - 0x0017C438     0x0027C1F0 - 0x0027C3B8     Function:
                                                        tr_disp_number
0x0017C440 - 0x0017CA18     0x0027C3C0 - 0x0027C998     Function:
                                                        Tr_check_seq_panel_disp
0x0017CA20 - 0x0017CF58     0x0027C9A0 - 0x0027CED8     Function:
                                                        Tr_seq_panel_disp
0x0017CF60 - 0x0017D338     0x0027CEE0 - 0x0027D2B8     Function:
                                                        Tr_freeze_arrow_disp
0x0017D340 - 0x0017D5C4     0x0027D2C0 - 0x0027D544     Function:
                                                        Tr_disp_bar
0x0017D5D0 - 0x0017E898     0x0027D550 - 0x0027E818     Function:
                                                        Tr_bar_disp_one
0x0017E8A0 - 0x0017ED70     0x0027E820 - 0x0027ECF0     Function:
                                                        Tr_disp_bar_number
0x0017ED70 - 0x0017EF20     0x0027ECF0 - 0x0027EEA0     Function:
                                                        Tr_disp_step_zone
0x0017EF20 - 0x0017F820     0x0027EEA0 - 0x0027F7A0     Function:
                                                        Tr_arrow_clut_anim_ck
0x0017F820 - 0x0017FD10     0x0027F7A0 - 0x0027FC90     Function:
                                                        Tr_arrow_clut_anim
0x0017FD10 - 0x0017FD78     0x0027FC90 - 0x0027FCF8     Function:
                                                        Tr_load_seq_th
0x0017FD80 - 0x0017FF70     0x0027FD00 - 0x0027FEF0     Function:
                                                        tr_load_seq_th
0x0017FF70 - 0x00180100     0x0027FEF0 - 0x00280080     Function:
                                                        Tr_load_seq
0x00180100 - 0x001806CC     0x00280080 - 0x0028064C     Function:
                                                        Tr_set_g_game_w
0x001806D0 - 0x00180A08     0x00280650 - 0x00280988     Function:
                                                        tr_play_disp
0x00180A10 - 0x00180AC4     0x00280990 - 0x00280A44     Function:
                                                        tr_chk_play_point
0x00180AD0 - 0x00180F10     0x00280A50 - 0x00280E90     Function:
                                                        tr_chk_assist
0x00180F10 - 0x00180FB0     0x00280E90 - 0x00280F30     Function:
                                                        tr_adjust_seq
0x00180FB0 - 0x001812EC     0x00280F30 - 0x0028126C     Function:
                                                        tr_play_finish
0x001812F0 - 0x00181480     0x00281270 - 0x00281400     Function:
                                                        tr_dance_play
0x00181480 - 0x00181700     0x00281400 - 0x00281680     Function:
                                                        tr_pre_play
0x00181700 - 0x00181C28     0x00281680 - 0x00281BA8     Function:
                                                        tr_play_init
0x00181C30 - 0x00181D64     0x00281BB0 - 0x00281CE4     Function:
                                                        Train_Play
0x00181D70 - 0x00181F78     0x00281CF0 - 0x00281EF8     Function:
                                                        tr_rsck_line_disp
0x00181F80 - 0x0018212C     0x00281F00 - 0x002820AC     Function:
                                                        tr_rs_apper
0x00182130 - 0x0018231C     0x002820B0 - 0x0028229C     Function:
                                                        tr_res_init
0x00182320 - 0x00182328     0x002822A0 - 0x002822A8     Function:
                                                        TRObj_rs_win_disp
0x00182330 - 0x0018233C     0x002822B0 - 0x002822BC     Function:
                                                        TRObj_rs_win_func
0x00182340 - 0x00182564     0x002822C0 - 0x002824E4     Function:
                                                        TRObj_rs_menu_disp
0x00182570 - 0x001825D8     0x002824F0 - 0x00282558     Function:
                                                        TRObj_rs_menu_func
0x001825E0 - 0x001829A4     0x00282560 - 0x00282924     Function:
                                                        Train_Res
0x001829B0 - 0x001829CC     0x00282930 - 0x0028294C     Function:
                                                        NetGamePrgGetWinLoseDraw
0x001829D0 - 0x00182BEC     0x00282950 - 0x00282B6C     Function:
                                                        NetGamePrgGetResult
0x00182BF0 - 0x00182E68     0x00282B70 - 0x00282DE8     Function:
                                                        NetGamePrgGetOption
0x00182E70 - 0x001832D8     0x00282DF0 - 0x00283258     Function:
                                                        NetGamePrgReverseMenu
0x001832E0 - 0x00183410     0x00283260 - 0x00283390     Function:
                                                        NetGamePrgErrorFunc
0x00183410 - 0x0018341C     0x00283390 - 0x0028339C     Function:
                                                        NetWin_BaseSetName
0x00183420 - 0x00183738     0x002833A0 - 0x002836B8     Function:
                                                        NetWin_BaseBoardDisp
0x00183740 - 0x00183754     0x002836C0 - 0x002836D4     Function:
                                                        NetWin_BaseEnd
0x00183760 - 0x00183768     0x002836E0 - 0x002836E8     Function:
                                                        NetWin_BaseMain
0x00183770 - 0x0018382C     0x002836F0 - 0x002837AC     Function:
                                                        NetWin_BaseInit
0x00183830 - 0x00183898     0x002837B0 - 0x00283818     Function:
                                                        NetWin_Base
0x001838A0 - 0x00183A58     0x00283820 - 0x002839D8     Function:
                                                        tr_ck_item_one_move
0x00183A60 - 0x00183C9C     0x002839E0 - 0x00283C1C     Function:
                                                        tr_ck_pad
0x00183CA0 - 0x00183DB0     0x00283C20 - 0x00283D30     Function:
                                                        tr_ck_apper
0x00183DB0 - 0x00184708     0x00283D30 - 0x00284688     Function:
                                                        TRObj_ck_item_disp
0x00184710 - 0x00184A48     0x00284690 - 0x002849C8     Function:
                                                        TRObj_ck_item_disap
0x00184A50 - 0x00184EE4     0x002849D0 - 0x00284E64     Function:
                                                        TRObj_ck_item_exec
0x00184EF0 - 0x00185100     0x00284E70 - 0x00285080     Function:
                                                        TRObj_ck_item_apper
0x00185100 - 0x00185454     0x00285080 - 0x002853D4     Function:
                                                        Train_Chk
0x00185460 - 0x00185474     0x002853E0 - 0x002853F4     Function:
                                                        NetWin_PerUserPointEnd
0x00185480 - 0x00185488     0x00285400 - 0x00285408     Function:
                                                        NetWin_PerUserPointMain
0x00185490 - 0x00185610     0x00285410 - 0x00285590     Function:
                                                        NetWin_PerUserPointInit
0x00185610 - 0x00185678     0x00285590 - 0x002855F8     Function:
                                                        NetWin_PerUserPoint
0x00185680 - 0x00185694     0x00285600 - 0x00285614     Function:
                                                        NetWin_PerHeadEnd
0x001856A0 - 0x00185CF8     0x00285620 - 0x00285C78     Function:
                                                        NetWin_PerHeadMain
0x00185D00 - 0x00185D7C     0x00285C80 - 0x00285CFC     Function:
                                                        NetWin_PerHeadInit
0x00185D80 - 0x00185DE8     0x00285D00 - 0x00285D68     Function:
                                                        NetWin_PerHead
0x00185DF0 - 0x00185E04     0x00285D70 - 0x00285D84     Function:
                                                        NetWin_PerPointEnd
0x00185E10 - 0x00186320     0x00285D90 - 0x002862A0     Function:
                                                        NetWin_PerPointMain
0x00186320 - 0x0018639C     0x002862A0 - 0x0028631C     Function:
                                                        NetWin_PerPointInit
0x001863A0 - 0x00186408     0x00286320 - 0x00286388     Function:
                                                        NetWin_PerPoint
0x00186410 - 0x00186424     0x00286390 - 0x002863A4     Function:
                                                        NetWin_PerRankEnd
0x00186430 - 0x001866D4     0x002863B0 - 0x00286654     Function:
                                                        NetWin_PerRankMain
0x001866E0 - 0x0018675C     0x00286660 - 0x002866DC     Function:
                                                        NetWin_PerRankInit
0x00186760 - 0x001867C8     0x002866E0 - 0x00286748     Function:
                                                        NetWin_PerRank
0x001867D0 - 0x001867E4     0x00286750 - 0x00286764     Function:
                                                        NetWin_PerStatsEnd
0x001867F0 - 0x00186F18     0x00286770 - 0x00286E98     Function:
                                                        NetWin_PerStatsMain
0x00186F20 - 0x00186F9C     0x00286EA0 - 0x00286F1C     Function:
                                                        NetWin_PerStatsInit
0x00186FA0 - 0x00187008     0x00286F20 - 0x00286F88     Function:
                                                        NetWin_PerStats
0x00187010 - 0x001870FC     0x00286F90 - 0x0028707C     Function:
                                                        fp_qm_save_exec
0x00187100 - 0x00187228     0x00287080 - 0x002871A8     Function:
                                                        fp_qm_save_func
0x00187230 - 0x00187264     0x002871B0 - 0x002871E4     Function:
                                                        fp_qm_save_init
0x00187270 - 0x001874B8     0x002871F0 - 0x00287438     Function:
                                                        fp_qm_sort_func
0x001874C0 - 0x001874D0     0x00287440 - 0x00287450     Function:
                                                        fp_qm_sort_ini
0x001874D0 - 0x00187768     0x00287450 - 0x002876E8     Function:
                                                        fp_qmenu_func
0x00187770 - 0x001877DC     0x002876F0 - 0x0028775C     Function:
                                                        NetWin_DHeadSetPoint
0x001877E0 - 0x0018785C     0x00287760 - 0x002877DC     Function:
                                                        NetWin_DHeadSetDancer
0x00187860 - 0x00187874     0x002877E0 - 0x002877F4     Function:
                                                        NetWin_DHeadSetName
0x00187880 - 0x00187894     0x00287800 - 0x00287814     Function:
                                                        NetWin_DHeadSetNumber
0x001878A0 - 0x001878B4     0x00287820 - 0x00287834     Function:
                                                        NetWin_DHeadEnd
0x001878C0 - 0x001878C8     0x00287840 - 0x00287848     Function:
                                                        NetWin_DHeadMain
0x001878D0 - 0x00187A54     0x00287850 - 0x002879D4     Function:
                                                        NetWin_DHeadInit
0x00187A60 - 0x00187AC8     0x002879E0 - 0x00287A48     Function:
                                                        NetWin_DHead
0x00187AD0 - 0x00187B4C     0x00287A50 - 0x00287ACC     Function:
                                                        NetWin_DPointSetDancer
0x00187B50 - 0x00187C44     0x00287AD0 - 0x00287BC4     Function:
                                                        NetWin_DPointSetPoint
0x00187C50 - 0x00187C64     0x00287BD0 - 0x00287BE4     Function:
                                                        NetWin_DPointSetName
0x00187C70 - 0x00187C84     0x00287BF0 - 0x00287C04     Function:
                                                        NetWin_DPointSetNumber
0x00187C90 - 0x00187CA4     0x00287C10 - 0x00287C24     Function:
                                                        NetWin_DPointEnd
0x00187CB0 - 0x00187CB8     0x00287C30 - 0x00287C38     Function:
                                                        NetWin_DPointMain
0x00187CC0 - 0x00187E00     0x00287C40 - 0x00287D80     Function:
                                                        NetWin_DPointInit
0x00187E00 - 0x00187E68     0x00287D80 - 0x00287DE8     Function:
                                                        NetWin_DPoint
0x00187E70 - 0x00187E84     0x00287DF0 - 0x00287E04     Function:
                                                        get_ssq_timing_music_count
0x00187E90 - 0x00187EA4     0x00287E10 - 0x00287E24     Function:
                                                        get_ssq_timing_beat_count
0x00187EB0 - 0x00187EBC     0x00287E30 - 0x00287E3C     Function:
                                                        get_ssq_timing_num
0x00187EC0 - 0x00187ECC     0x00287E40 - 0x00287E4C     Function:
                                                        get_ssq_edit_freeze_addr
0x00187ED0 - 0x00187EDC     0x00287E50 - 0x00287E5C     Function:
                                                        get_ssq_edit_seq_addr
0x00187EE0 - 0x00187F40     0x00287E60 - 0x00287EC0     Function:
                                                        get_ssq_special_note_music_count
0x00187F40 - 0x00187FA0     0x00287EC0 - 0x00287F20     Function:
                                                        get_ssq_special_note_beat_count
0x00187FA0 - 0x00187FD0     0x00287F20 - 0x00287F50     Function:
                                                        init_ssq_info
0x00187FD0 - 0x00188118     0x00287F50 - 0x00288098     Function:
                                                        calc_ssq_music_count_from_beat_count
0x00188120 - 0x0018824C     0x002880A0 - 0x002881CC     Function:
                                                        set_ssq_special_note_info
0x00188250 - 0x001886CC     0x002881D0 - 0x0028864C     Function:
                                                        set_ssq_timing_info
0x001886D0 - 0x00188D88     0x00288650 - 0x00288D08     Function:
                                                        calc_groove_chart_for_edit_data
0x00188D90 - 0x001891A0     0x00288D10 - 0x00289120     Function:
                                                        kn_epad_yesno
0x001891A0 - 0x001894CC     0x00289120 - 0x0028944C     Function:
                                                        ed_edit_pad_menu
0x001894D0 - 0x00189CFC     0x00289450 - 0x00289C7C     Function:
                                                        ed_edit_step
0x00189D00 - 0x0018A13C     0x00289C80 - 0x0028A0BC     Function:
                                                        ed_edit_init
0x0018A140 - 0x0018A540     0x0028A0C0 - 0x0028A4C0     Function:
                                                        edit_menu_item_disp
0x0018A540 - 0x0018A5B0     0x0028A4C0 - 0x0028A530     Function:
                                                        edit_menu_item_dsap
0x0018A5B0 - 0x0018A5B8     0x0028A530 - 0x0028A538     Function:
                                                        edit_menu_item_exec
0x0018A5C0 - 0x0018A708     0x0028A540 - 0x0028A688     Function:
                                                        edit_menu_item_appr
0x0018A710 - 0x0018A77C     0x0028A690 - 0x0028A6FC     Function:
                                                        edit_menu_leftbase_disp
0x0018A780 - 0x0018A7E8     0x0028A700 - 0x0028A768     Function:
                                                        edit_menu_leftbase_dsap
0x0018A7F0 - 0x0018A7F8     0x0028A770 - 0x0028A778     Function:
                                                        edit_menu_leftbase_exec
0x0018A800 - 0x0018A830     0x0028A780 - 0x0028A7B0     Function:
                                                        edit_menu_leftbase_appr
0x0018A830 - 0x0018A858     0x0028A7B0 - 0x0028A7D8     Function:
                                                        ed_menu_fini
0x0018A860 - 0x0018AB5C     0x0028A7E0 - 0x0028AADC     Function:
                                                        ed_menu_step
0x0018AB60 - 0x0018AC40     0x0028AAE0 - 0x0028ABC0     Function:
                                                        ed_menu_init
0x0018AC40 - 0x0018AE18     0x0028ABC0 - 0x0028AD98     Function:
                                                        edit_sel_mainitem_disp
0x0018AE20 - 0x0018B5E0     0x0028ADA0 - 0x0028B560     Function:
                                                        edit_sel_disp_item_sub
0x0018B5E0 - 0x0018B760     0x0028B560 - 0x0028B6E0     Function:
                                                        edit_sel_disp_winbar
0x0018B760 - 0x0018B7A8     0x0028B6E0 - 0x0028B728     Function:
                                                        edit_sel_mainitem_dsap
0x0018B7B0 - 0x0018B8A0     0x0028B730 - 0x0028B820     Function:
                                                        edit_sel_mainitem_exec
0x0018B8A0 - 0x0018B8F4     0x0028B820 - 0x0028B874     Function:
                                                        edit_sel_mainitem_appr
0x0018B900 - 0x0018BDE4     0x0028B880 - 0x0028BD64     Function:
                                                        edit_sel_upitem_disp
0x0018BDF0 - 0x0018BE38     0x0028BD70 - 0x0028BDB8     Function:
                                                        edit_sel_upitem_dsap
0x0018BE40 - 0x0018BE78     0x0028BDC0 - 0x0028BDF8     Function:
                                                        edit_sel_upitem_exec
0x0018BE80 - 0x0018BE8C     0x0028BE00 - 0x0028BE0C     Function:
                                                        edit_sel_upitem_appr
0x0018BE90 - 0x0018C3AC     0x0028BE10 - 0x0028C32C     Function:
                                                        edit_sel_footmark_disp
0x0018C3B0 - 0x0018C3F8     0x0028C330 - 0x0028C378     Function:
                                                        edit_sel_footmark_dsap
0x0018C400 - 0x0018C438     0x0028C380 - 0x0028C3B8     Function:
                                                        edit_sel_footmark_exec
0x0018C440 - 0x0018C44C     0x0028C3C0 - 0x0028C3CC     Function:
                                                        edit_sel_footmark_appr
0x0018C450 - 0x0018C458     0x0028C3D0 - 0x0028C3D8     Function:
                                                        edit_sel_leftbase_disp
0x0018C460 - 0x0018C4E8     0x0028C3E0 - 0x0028C468     Function:
                                                        edit_sel_leftbase_dsap
0x0018C4F0 - 0x0018C4F8     0x0028C470 - 0x0028C478     Function:
                                                        edit_sel_leftbase_exec
0x0018C500 - 0x0018C54C     0x0028C480 - 0x0028C4CC     Function:
                                                        edit_sel_leftbase_appr
0x0018C550 - 0x0018CAB4     0x0028C4D0 - 0x0028CA34     Function:
                                                        ed_select_items
0x0018CAC0 - 0x0018CCFC     0x0028CA40 - 0x0028CC7C     Function:
                                                        ed_select_music
0x0018CD00 - 0x0018CD08     0x0028CC80 - 0x0028CC88     Function:
                                                        ed_select_fini
0x0018CD10 - 0x0018CE50     0x0028CC90 - 0x0028CDD0     Function:
                                                        ed_select_step
0x0018CE50 - 0x0018D030     0x0028CDD0 - 0x0028CFB0     Function:
                                                        ed_select_init
0x0018D030 - 0x0018D068     0x0028CFB0 - 0x0028CFE8     Function:
                                                        el_get_message_str
0x0018D070 - 0x0018D388     0x0028CFF0 - 0x0028D308     Function:
                                                        el_name_diff_disp
0x0018D390 - 0x0018D398     0x0028D310 - 0x0028D318     Function:
                                                        el_name_diff_dsap
0x0018D3A0 - 0x0018D4D0     0x0028D320 - 0x0028D450     Function:
                                                        el_name_diff_exec
0x0018D4D0 - 0x0018D524     0x0028D450 - 0x0028D4A4     Function:
                                                        el_name_diff_appr
0x0018D530 - 0x0018D6C4     0x0028D4B0 - 0x0028D644     Function:
                                                        el_disp_input_name
0x0018D6D0 - 0x0018E2C4     0x0028D650 - 0x0028E244     Function:
                                                        el_name_info_disp
0x0018E2D0 - 0x0018E3D0     0x0028E250 - 0x0028E350     Function:
                                                        el_name_info_dsap
0x0018E3D0 - 0x0018E3D8     0x0028E350 - 0x0028E358     Function:
                                                        el_name_info_exec
0x0018E3E0 - 0x0018E508     0x0028E360 - 0x0028E488     Function:
                                                        el_name_info_appr
0x0018E510 - 0x0018E58C     0x0028E490 - 0x0028E50C     Function:
                                                        el_name_leftbase_disp
0x0018E590 - 0x0018E5F8     0x0028E510 - 0x0028E578     Function:
                                                        el_name_leftbase_dsap
0x0018E600 - 0x0018E608     0x0028E580 - 0x0028E588     Function:
                                                        el_name_leftbase_exec
0x0018E610 - 0x0018E65C     0x0028E590 - 0x0028E5DC     Function:
                                                        el_name_leftbase_appr
0x0018E660 - 0x0018E76C     0x0028E5E0 - 0x0028E6EC     Function:
                                                        el_exist_same_name
0x0018E770 - 0x0018EA28     0x0028E6F0 - 0x0028E9A8     Function:
                                                        el_keyboard_control
0x0018EA30 - 0x0018F0C0     0x0028E9B0 - 0x0028F040     Function:
                                                        el_name_select_footnum
0x0018F0C0 - 0x0018F210     0x0028F040 - 0x0028F190     Function:
                                                        el_name_select_diff
0x0018F210 - 0x0018F5D4     0x0028F190 - 0x0028F554     Function:
                                                        el_name_input_name
0x0018F5E0 - 0x0018FA10     0x0028F560 - 0x0028F990     Function:
                                                        el_name_step
0x0018FA10 - 0x0018FF58     0x0028F990 - 0x0028FED8     Function:
                                                        el_name_init
0x0018FF60 - 0x00190004     0x0028FEE0 - 0x0028FF84     Function:
                                                        el_exec_select_yesno
0x00190010 - 0x00190120     0x0028FF90 - 0x002900A0     Function:
                                                        el_yesno_disp
0x00190120 - 0x00190154     0x002900A0 - 0x002900D4     Function:
                                                        el_yesno_dsap
0x00190160 - 0x001901B4     0x002900E0 - 0x00290134     Function:
                                                        el_yesno_exec
0x001901C0 - 0x00190228     0x00290140 - 0x002901A8     Function:
                                                        el_yesno_appr
0x00190230 - 0x001902DC     0x002901B0 - 0x0029025C     Function:
                                                        el_new_folder_disp
0x001902E0 - 0x00190370     0x00290260 - 0x002902F0     Function:
                                                        el_new_folder_dsap
0x00190370 - 0x00190378     0x002902F0 - 0x002902F8     Function:
                                                        el_new_folder_exec
0x00190380 - 0x00190410     0x00290300 - 0x00290390     Function:
                                                        el_new_folder_appr
0x00190410 - 0x00190868     0x00290390 - 0x002907E8     Function:
                                                        el_disp_music_info
0x00190870 - 0x00190B50     0x002907F0 - 0x00290AD0     Function:
                                                        el_disp_message_all
0x00190B50 - 0x0019116C     0x00290AD0 - 0x002910EC     Function:
                                                        el_main_panel_disp
0x00191170 - 0x00191200     0x002910F0 - 0x00291180     Function:
                                                        el_main_panel_dsap
0x00191200 - 0x00191208     0x00291180 - 0x00291188     Function:
                                                        el_main_panel_exec
0x00191210 - 0x001912A0     0x00291190 - 0x00291220     Function:
                                                        el_main_panel_appr
0x001912A0 - 0x00191964     0x00291220 - 0x002918E4     Function:
                                                        el_folder_menu_disp
0x00191970 - 0x00191A00     0x002918F0 - 0x00291980     Function:
                                                        el_folder_menu_dsap
0x00191A00 - 0x00191A08     0x00291980 - 0x00291988     Function:
                                                        el_folder_menu_exec
0x00191A10 - 0x00191AA0     0x00291990 - 0x00291A20     Function:
                                                        el_folder_menu_appr
0x00191AA0 - 0x0019208C     0x00291A20 - 0x0029200C     Function:
                                                        el_filelist_disp
0x00192090 - 0x001921F8     0x00292010 - 0x00292178     Function:
                                                        el_filelist_dsap
0x00192200 - 0x00192208     0x00292180 - 0x00292188     Function:
                                                        el_filelist_exec
0x00192210 - 0x00192398     0x00292190 - 0x00292318     Function:
                                                        el_filelist_appr
0x001923A0 - 0x001923A8     0x00292320 - 0x00292328     Function:
                                                        el_leftbase_disp
0x001923B0 - 0x00192418     0x00292330 - 0x00292398     Function:
                                                        el_leftbase_dsap
0x00192420 - 0x00192428     0x002923A0 - 0x002923A8     Function:
                                                        el_leftbase_exec
0x00192430 - 0x0019247C     0x002923B0 - 0x002923FC     Function:
                                                        el_leftbase_appr
0x00192480 - 0x00192568     0x00292400 - 0x002924E8     Function:
                                                        el_disp_message
0x00192570 - 0x00192770     0x002924F0 - 0x002926F0     Function:
                                                        el_filemenu_disp
0x00192770 - 0x001928FC     0x002926F0 - 0x0029287C     Function:
                                                        el_filemenu_init
0x00192900 - 0x00192F00     0x00292880 - 0x00292E80     Function:
                                                        el_filemenu_main
0x00192F00 - 0x00193210     0x00292E80 - 0x00293190     Function:
                                                        el_disp_control
0x00193210 - 0x00193B08     0x00293190 - 0x00293A88     Function:
                                                        ed_lrframe_disp
0x00193B10 - 0x00193BA0     0x00293A90 - 0x00293B20     Function:
                                                        ed_lrframe_dsap
0x00193BA0 - 0x00193C7C     0x00293B20 - 0x00293BFC     Function:
                                                        ed_lrframe_exec
0x00193C80 - 0x00193D30     0x00293C00 - 0x00293CB0     Function:
                                                        ed_lrframe_appr
0x006F0100 - 0x006F01D0     0x007F0080 - 0x007F0150     Function:
                                                        init_title_list
0x006F01D0 - 0x006F02BC     0x007F0150 - 0x007F023C     Function:
                                                        init_bar
0x006F02C0 - 0x006F0678     0x007F0240 - 0x007F05F8     Function:
                                                        view_title
0x006F0680 - 0x006F08E0     0x007F0600 - 0x007F0860     Function:
                                                        control_title
0x006F08E0 - 0x006F0AC0     0x007F0860 - 0x007F0A40     Function:
                                                        set_title
0x006F0AC0 - 0x006F0BD0     0x007F0A40 - 0x007F0B50     Function:
                                                        Update_Infosel
0x006F0BD0 - 0x006F0C20     0x007F0B50 - 0x007F0BA0     Function:
                                                        View_Infosel
0x006F0C20 - 0x006F0DA0     0x007F0BA0 - 0x007F0D20     Function:
                                                        Page_Change
0x006F0DA0 - 0x006F0E2C     0x007F0D20 - 0x007F0DAC     Function:
                                                        MoveCursor_Infosel
0x006F0E30 - 0x006F0EC8     0x007F0DB0 - 0x007F0E48     Function:
                                                        CheckMoveCursor_Infosel
0x006F0ED0 - 0x006F1554     0x007F0E50 - 0x007F14D4     Function:
                                                        control_sel
0x006F1560 - 0x006F1B68     0x007F14E0 - 0x007F1AE8     Function:
                                                        Control_Infosel
0x006F1B70 - 0x006F1C2C     0x007F1AF0 - 0x007F1BAC     Function:
                                                        Init_Infosel
0x006F1C30 - 0x006F1E78     0x007F1BB0 - 0x007F1DF8     Function:
                                                        MyRoom_Board_Disp
0x006F1E80 - 0x006F1FE0     0x007F1E00 - 0x007F1F60     Function:
                                                        MyRoom_btn_disp
0x006F1FE0 - 0x006F20D8     0x007F1F60 - 0x007F2058     Function:
                                                        MyRoom_btn_move
0x006F20E0 - 0x006F2180     0x007F2060 - 0x007F2100     Function:
                                                        MyRoom_scr_bar_disp
0x006F2180 - 0x006F21D4     0x007F2100 - 0x007F2154     Function:
                                                        MyRoom_scr_bar_disap
0x006F21E0 - 0x006F223C     0x007F2160 - 0x007F21BC     Function:
                                                        MyRoom_scr_bar_apper
0x006F2240 - 0x006F22E8     0x007F21C0 - 0x007F2268     Function:
                                                        MyRoom_caption_disap
0x006F22F0 - 0x006F2388     0x007F2270 - 0x007F2308     Function:
                                                        MyRoom_caption_apper
0x006F2390 - 0x006F2410     0x007F2310 - 0x007F2390     Function:
                                                        MyRoom_back_disp
0x006F2410 - 0x006F248C     0x007F2390 - 0x007F240C     Function:
                                                        MyRoom_back_disap
0x006F2490 - 0x006F2500     0x007F2410 - 0x007F2480     Function:
                                                        MyRoom_back_apper
0x006F2500 - 0x006F258C     0x007F2480 - 0x007F250C     Function:
                                                        MyRoom_base_disp
0x006F2590 - 0x006F2684     0x007F2510 - 0x007F2604     Function:
                                                        MyRoom_base_disap
0x006F2690 - 0x006F2710     0x007F2610 - 0x007F2690     Function:
                                                        MyRoom_base_apper
0x006F2710 - 0x006F27F0     0x007F2690 - 0x007F2770     Function:
                                                        MyRoom_top_item_disp
0x006F27F0 - 0x006F2924     0x007F2770 - 0x007F28A4     Function:
                                                        MyRoom_top_item_disap
0x006F2930 - 0x006F2978     0x007F28B0 - 0x007F28F8     Function:
                                                        MyRoom_top_item_exec
0x006F2980 - 0x006F2B14     0x007F2900 - 0x007F2A94     Function:
                                                        MyRoom_top_item_apper
0x006F2B20 - 0x006F2B28     0x007F2AA0 - 0x007F2AA8     Function:
                                                        MyRoom_cur_disp
0x006F2B30 - 0x006F2B7C     0x007F2AB0 - 0x007F2AFC     Function:
                                                        MyRoom_cur_exec
0x006F2B80 - 0x006F2BA0     0x007F2B00 - 0x007F2B20     Function:
                                                        MyRoom_win_disp
0x006F2BA0 - 0x006F2D78     0x007F2B20 - 0x007F2CF8     Function:
                                                        MyRoom_win_func
0x006F2D80 - 0x006F2E88     0x007F2D00 - 0x007F2E08     Function:
                                                        MyRoom_fade
0x006F2E90 - 0x006F30CC     0x007F2E10 - 0x007F304C     Function:
                                                        myroom_xmove_update
0x006F30D0 - 0x006F30D8     0x007F3050 - 0x007F3058     Function:
                                                        Update_MyRoom
0x006F30E0 - 0x006F30E8     0x007F3060 - 0x007F3068     Function:
                                                        View_MyRoom
0x006F30F0 - 0x006F317C     0x007F3070 - 0x007F30FC     Function:
                                                        Control_MyRoom
0x006F3180 - 0x006F32D8     0x007F3100 - 0x007F3258     Function:
                                                        Init_MyRoom
0x006F32E0 - 0x006F3564     0x007F3260 - 0x007F34E4     Function:
                                                        MyRoom_Extra_Arrow_OR_Ending_List
0x006F3570 - 0x006F390C     0x007F34F0 - 0x007F388C     Function:
                                                        MyRoom_Credits
0x006F3910 - 0x006F3EA8     0x007F3890 - 0x007F3E28     Function:
                                                        MyRoom_Top
0x006F3EB0 - 0x006F3FA0     0x007F3E30 - 0x007F3F20     Function:
                                                        CheckInfo_Info
0x006F3FA0 - 0x006F3FD4     0x007F3F20 - 0x007F3F54     Function:
                                                        DrawScrollBar_Info
0x006F3FE0 - 0x006F40A0     0x007F3F60 - 0x007F4020     Function:
                                                        decode_text_idm5_th
0x006F40A0 - 0x006F4114     0x007F4020 - 0x007F4094     Function:
                                                        set_select_track_no_by_infotxt_num
0x006F4120 - 0x006F41F4     0x007F40A0 - 0x007F4174     Function:
                                                        sound_poll
0x006F4200 - 0x006F429C     0x007F4180 - 0x007F421C     Function:
                                                        DivideInfoDataIdm5_Info
0x006F42A0 - 0x006F4454     0x007F4220 - 0x007F43D4     Function:
                                                        information_check
0x006F4460 - 0x006F45A4     0x007F43E0 - 0x007F4524     Function:
                                                        init_tex
0x006F45B0 - 0x006F46F4     0x007F4530 - 0x007F4674     Function:
                                                        open_func
0x006F4700 - 0x006F4A60     0x007F4680 - 0x007F49E0     Function:
                                                        init_func
0x006F4A60 - 0x006F4A68     0x007F49E0 - 0x007F49E8     Function:
                                                        Term_Info
0x006F4A70 - 0x006F4D30     0x007F49F0 - 0x007F4CB0     Function:
                                                        Step_Info
0x006F4D30 - 0x006F4DDC     0x007F4CB0 - 0x007F4D5C     Function:
                                                        Init_Info
0x006F4DE0 - 0x006F4E04     0x007F4D60 - 0x007F4D84     Function:
                                                        SetStep_Info
0x006F4E10 - 0x006F4E2C     0x007F4D90 - 0x007F4DAC     Function:
                                                        req_info_doll_chara
0x006F4E30 - 0x006F4E3C     0x007F4DB0 - 0x007F4DBC     Function:
                                                        req_info_doll_in
0x006F4E40 - 0x006F4E4C     0x007F4DC0 - 0x007F4DCC     Function:
                                                        is_info_doll_loading
0x006F4E50 - 0x006F5098     0x007F4DD0 - 0x007F5018     Function:
                                                        View_InfoDollDisp
0x006F50A0 - 0x006F50EC     0x007F5020 - 0x007F506C     Function:
                                                        Init_InfoDollDisp
0x006F50F0 - 0x006F51EC     0x007F5070 - 0x007F516C     Function:
                                                        info_extra_arrow_init
0x006F51F0 - 0x006F5780     0x007F5170 - 0x007F5700     Function:
                                                        info_tdisp_sequence_panel
0x006F5780 - 0x006F5A40     0x007F5700 - 0x007F59C0     Function:
                                                        TrDispBarMenu
0x006F5A40 - 0x006F6030     0x007F59C0 - 0x007F5FB0     Function:
                                                        TrBarDisp
0x006F6030 - 0x006F64C0     0x007F5FB0 - 0x007F6440     Function:
                                                        info_tfunc_arrow_clut_anim
0x006F64C0 - 0x006F6654     0x007F6440 - 0x007F65D4     Function:
                                                        info_tfunc_load_seq
0x006F6660 - 0x006F6838     0x007F65E0 - 0x007F67B8     Function:
                                                        info_tfunc_set_g_game_w
0x006F6840 - 0x006F6BE8     0x007F67C0 - 0x007F6B68     Function:
                                                        TrFreezeArrowDisp
0x006F6BF0 - 0x006F72DC     0x007F6B70 - 0x007F725C     Function:
                                                        draw_ending_list_item
0x006F72E0 - 0x006F7428     0x007F7260 - 0x007F73A8     Function:
                                                        select_ending_list_item
0x006F7430 - 0x006F7998     0x007F73B0 - 0x007F7918     Function:
                                                        draw_dance_master_item
0x006F79A0 - 0x006F7A2C     0x007F7920 - 0x007F79AC     Function:
                                                        init_dance_master_item
0x006F7A30 - 0x006F7BEC     0x007F79B0 - 0x007F7B6C     Function:
                                                        select_dance_master_item
0x006F7BF0 - 0x006F7E6C     0x007F7B70 - 0x007F7DEC     Function:
                                                        draw_question_no
0x006F7E70 - 0x006F810C     0x007F7DF0 - 0x007F808C     Function:
                                                        draw_music_banner
0x006F8110 - 0x006F81E0     0x007F8090 - 0x007F8160     Function:
                                                        init_thumbnail
0x006F81E0 - 0x006F8354     0x007F8160 - 0x007F82D4     Function:
                                                        init_bar
0x006F8360 - 0x006F8754     0x007F82E0 - 0x007F86D4     Function:
                                                        control_move
0x006F8760 - 0x006F87D4     0x007F86E0 - 0x007F8754     Function:
                                                        update_Infoshow
0x006F87E0 - 0x006F9400     0x007F8760 - 0x007F9380     Function:
                                                        draw_Infoshow
0x006F9400 - 0x006F97A8     0x007F9380 - 0x007F9728     Function:
                                                        control_loop
0x006F97B0 - 0x006F9B0C     0x007F9730 - 0x007F9A8C     Function:
                                                        init
0x006F9B10 - 0x006F9D64     0x007F9A90 - 0x007F9CE4     Function:
                                                        main_Infoshow
0x006F9D70 - 0x006F9D98     0x007F9CF0 - 0x007F9D18     Function:
                                                        init_Infoshow
0x006F9DA0 - 0x006FA054     0x007F9D20 - 0x007F9FD4     Function:
                                                        csStaffRollSdMain
0x006FA060 - 0x006FA090     0x007F9FE0 - 0x007FA010     Function:
                                                        csStaffRollFinish
0x006FA090 - 0x006FA5B4     0x007FA010 - 0x007FA534     Function:
                                                        csStaffRollStep
0x006FA5C0 - 0x006FA5D8     0x007FA540 - 0x007FA558     Function:
                                                        csStaffRollInit
0x006FA5E0 - 0x006FAB34     0x007FA560 - 0x007FAAB4     Function:
                                                        DispFFTFlower1
0x006FAB40 - 0x006FB36C     0x007FAAC0 - 0x007FB2EC     Function:
                                                        DispFFTMeter1
0x006FB370 - 0x006FBE4C     0x007FB2F0 - 0x007FBDCC     Function:
                                                        DispFFTWire2
0x006FBE50 - 0x006FC9AC     0x007FBDD0 - 0x007FC92C     Function:
                                                        DispFFTWire1
0x006FC9B0 - 0x006FD288     0x007FC930 - 0x007FD208     Function:
                                                        DispFFTMeter2
0x006FD290 - 0x006FD4B4     0x007FD210 - 0x007FD434     Function:
                                                        StaffRollFFTDisp
0x006FD4C0 - 0x006FD5BC     0x007FD440 - 0x007FD53C     Function:
                                                        EdBkEffectColSet
0x006FD5C0 - 0x006FD74C     0x007FD540 - 0x007FD6CC     Function:
                                                        StaffRollCapScreen
0x006FD750 - 0x006FD7E4     0x007FD6D0 - 0x007FD764     Function:
                                                        StaffRollFFTDispInit
0x006FD7F0 - 0x006FDBDC     0x007FD770 - 0x007FDB5C     Function:
                                                        csStaffRollMovieDraw
0x006FDBE0 - 0x006FDDFC     0x007FDB60 - 0x007FDD7C     Function:
                                                        csStaffRollMovieRead
0x006FDE00 - 0x006FE080     0x007FDD80 - 0x007FE000     Function:
                                                        csStaffRollMovieMain
0x006FE080 - 0x006FE0D8     0x007FE000 - 0x007FE058     Function:
                                                        csStaffRollMovieInit
0x006FE0E0 - 0x006FE0EC     0x007FE060 - 0x007FE06C     Function:
                                                        csStaffRollFadeCheck
0x006FE0F0 - 0x006FE17C     0x007FE070 - 0x007FE0FC     Function:
                                                        csStaffRollFadeDraw
0x006FE180 - 0x006FE360     0x007FE100 - 0x007FE2E0     Function:
                                                        csStaffRollFadeAct
0x006FE360 - 0x006FE528     0x007FE2E0 - 0x007FE4A8     Function:
                                                        csStaffRollFadeStart
0x006FE530 - 0x006FE540     0x007FE4B0 - 0x007FE4C0     Function:
                                                        csStaffRollFadeInit
0x006FE540 - 0x006FE548     0x007FE4C0 - 0x007FE4C8     Function:
                                                        csStaffRollPicGetBase
0x006FE550 - 0x006FE5F8     0x007FE4D0 - 0x007FE578     Function:
                                                        csStaffRollPicActBaseFO
0x006FE600 - 0x006FE748     0x007FE580 - 0x007FE6C8     Function:
                                                        csStaffRollPicDraw_Noise
0x006FE750 - 0x006FEA78     0x007FE6D0 - 0x007FE9F8     Function:
                                                        csStaffRollPicDraw_Picture
0x006FEA80 - 0x006FF21C     0x007FEA00 - 0x007FF19C     Function:
                                                        csStaffRollPicDraw
0x006FF220 - 0x006FF2A8     0x007FF1A0 - 0x007FF228     Function:
                                                        StaffRollTexInit
0x006FF2B0 - 0x006FF2C8     0x007FF230 - 0x007FF248     Function:
                                                        csStaffRollPicStepInit
0x006FF2D0 - 0x006FF450     0x007FF250 - 0x007FF3D0     Function:
                                                        csStaffRollScrlDrawFunc_Copyright
0x006FF450 - 0x006FF56C     0x007FF3D0 - 0x007FF4EC     Function:
                                                        csStaffRollScrlDrawFunc_Tyo
0x006FF570 - 0x006FF6F8     0x007FF4F0 - 0x007FF678     Function:
                                                        csStaffRollScrlDrawFunc_Dolby
0x006FF700 - 0x006FF888     0x007FF680 - 0x007FF808     Function:
                                                        csStaffRollScrlDrawFunc_Xax
0x006FF890 - 0x006FFBD8     0x007FF810 - 0x007FFB58     Function:
                                                        csStaffRollScrlDrawFunc_Konami
0x006FFBE0 - 0x006FFC34     0x007FFB60 - 0x007FFBB4     Function:
                                                        csStaffRollScrlDrawFunc_Name
0x006FFC40 - 0x006FFC94     0x007FFBC0 - 0x007FFC14     Function:
                                                        csStaffRollScrlDrawFunc_Title_E
0x006FFCA0 - 0x006FFCF4     0x007FFC20 - 0x007FFC74     Function:
                                                        csStaffRollScrlDrawFunc_Title_A
0x006FFD00 - 0x006FFD54     0x007FFC80 - 0x007FFCD4     Function:
                                                        csStaffRollScrlDrawFunc_Title_C
0x006FFD60 - 0x006FFDB0     0x007FFCE0 - 0x007FFD30     Function:
                                                        csStaffRollScrlDrawFunc_License
0x006FFDB0 - 0x006FFEF4     0x007FFD30 - 0x007FFE74     Function:
                                                        csStaffRollScrlAct
0x006FFF00 - 0x0070003C     0x007FFE80 - 0x007FFFBC     Function:
                                                        csStaffRollScrlMain
0x00700040 - 0x007000DC     0x007FFFC0 - 0x0080005C     Function:
                                                        csStaffRollScrlInit
0x006F0100 - 0x006F01A0     0x007F0080 - 0x007F0120     Function:
                                                        kn_ldisp_start_exit
0x006F01A0 - 0x006F03CC     0x007F0120 - 0x007F034C     Function:
                                                        kn_ldisp_foot_stage
0x006F03D0 - 0x006F05FC     0x007F0350 - 0x007F057C     Function:
                                                        kn_ldisp_foot_touch
0x006F0600 - 0x006F0A30     0x007F0580 - 0x007F09B0     Function:
                                                        kn_set_ft4_gte
0x006F0A30 - 0x006F0BC0     0x007F09B0 - 0x007F0B40     Function:
                                                        kn_ldisp_face_obj
0x006F0BC0 - 0x006F0FB4     0x007F0B40 - 0x007F0F34     Function:
                                                        kn_ldisp_foot_obj
0x006F0FC0 - 0x006F1190     0x007F0F40 - 0x007F1110     Function:
                                                        kn_ldisp_now_teach
0x006F1190 - 0x006F11A4     0x007F1110 - 0x007F1124     Function:
                                                        kn_ldisp_kanji_font_init
0x006F11B0 - 0x006F11B8     0x007F1130 - 0x007F1138     Function:
                                                        kn_ldisp_reset_font_emi
0x006F11C0 - 0x006F1348     0x007F1140 - 0x007F12C8     Function:
                                                        kn_ldisp_message
0x006F1350 - 0x006F150C     0x007F12D0 - 0x007F148C     Function:
                                                        kn_kanji_font_emi
0x006F1510 - 0x006F1668     0x007F1490 - 0x007F15E8     Function:
                                                        kn_ldisp_lesson_play
0x006F1670 - 0x006F16D4     0x007F15F0 - 0x007F1654     Function:
                                                        LesWinSetType
0x006F16E0 - 0x006F17FC     0x007F1660 - 0x007F177C     Function:
                                                        LesWinSetMode
0x006F1800 - 0x006F18E0     0x007F1780 - 0x007F1860     Function:
                                                        LesWinSetDefaultPartsWH
0x006F18E0 - 0x006F1998     0x007F1860 - 0x007F1918     Function:
                                                        LesWinDefaultAllSet
0x006F19A0 - 0x006F1BA8     0x007F1920 - 0x007F1B28     Function:
                                                        LesWinXYWHMove
0x006F1BB0 - 0x006F2290     0x007F1B30 - 0x007F2210     Function:
                                                        LesWinDisp
0x006F2290 - 0x006F22EC     0x007F2210 - 0x007F226C     Function:
                                                        LesWinDestroy
0x006F22F0 - 0x006F2530     0x007F2270 - 0x007F24B0     Function:
                                                        LesWinClose
0x006F2530 - 0x006F2550     0x007F24B0 - 0x007F24D0     Function:
                                                        LesWinMain
0x006F2550 - 0x006F27C8     0x007F24D0 - 0x007F2748     Function:
                                                        LesWinOpen
0x006F27D0 - 0x006F27DC     0x007F2750 - 0x007F275C     Function:
                                                        LesWinSet
0x006F27E0 - 0x006F283C     0x007F2760 - 0x007F27BC     Function:
                                                        LesWinGetInit
0x006F2840 - 0x006F2900     0x007F27C0 - 0x007F2880     Function:
                                                        LesWinFunc
0x006F2900 - 0x006F2B40     0x007F2880 - 0x007F2AC0     Function:
                                                        kn_lfunc_finger_op
0x006F2B40 - 0x006F2C20     0x007F2AC0 - 0x007F2BA0     Function:
                                                        kn_lfunc_set_play_ct
0x006F2C20 - 0x006F2CD0     0x007F2BA0 - 0x007F2C50     Function:
                                                        kn_lfunc_set_msg_status
0x006F2CD0 - 0x006F2E5C     0x007F2C50 - 0x007F2DDC     Function:
                                                        kn_lfunc_set_foot_status
0x006F2E60 - 0x006F2F28     0x007F2DE0 - 0x007F2EA8     Function:
                                                        kn_lfunc_msg_op
0x006F2F30 - 0x006F3140     0x007F2EB0 - 0x007F30C0     Function:
                                                        kn_lfunc_set_foot_move
0x006F3140 - 0x006F32DC     0x007F30C0 - 0x007F325C     Function:
                                                        kn_lfunc_foot_op
0x006F32E0 - 0x006F3528     0x007F3260 - 0x007F34A8     Function:
                                                        kn_lfunc_chk_timing
0x006F3530 - 0x006F35D0     0x007F34B0 - 0x007F3550     Function:
                                                        kn_lfunc_chk_teach_mode
0x006F35D0 - 0x006F3678     0x007F3550 - 0x007F35F8     Function:
                                                        kn_lfunc_chk_clap
0x006F3680 - 0x006F36A4     0x007F3600 - 0x007F3624     Function:
                                                        kn_lfunc_chk_now_music
0x006F36B0 - 0x006F38E4     0x007F3630 - 0x007F3864     Function:
                                                        kn_lfunc_set_head_data
0x006F38F0 - 0x006F3940     0x007F3870 - 0x007F38C0     Function:
                                                        is_can_play_last_section
0x006F3940 - 0x006F395C     0x007F38C0 - 0x007F38DC     Function:
                                                        SetLessonState
0x006F3960 - 0x006F397C     0x007F38E0 - 0x007F38FC     Function:
                                                        GetLessonState
0x006F3980 - 0x006F3B50     0x007F3900 - 0x007F3AD0     Function:
                                                        init_tex
0x006F3B50 - 0x006F3C34     0x007F3AD0 - 0x007F3BB4     Function:
                                                        init_kanji
0x006F3C40 - 0x006F3D3C     0x007F3BC0 - 0x007F3CBC     Function:
                                                        close_func
0x006F3D40 - 0x006F3EDC     0x007F3CC0 - 0x007F3E5C     Function:
                                                        open_func
0x006F3EE0 - 0x006F410C     0x007F3E60 - 0x007F408C     Function:
                                                        init_func
0x006F4110 - 0x006F4124     0x007F4090 - 0x007F40A4     Function:
                                                        Term_Les
0x006F4130 - 0x006F43A0     0x007F40B0 - 0x007F4320     Function:
                                                        Step_Les
0x006F43A0 - 0x006F4534     0x007F4320 - 0x007F44B4     Function:
                                                        Init_Les
0x006F4540 - 0x006F4564     0x007F44C0 - 0x007F44E4     Function:
                                                        SetStep_Les
0x006F4570 - 0x006F45DC     0x007F44F0 - 0x007F455C     Function:
                                                        kn_lstep_lesson_play
0x006F45E0 - 0x006F47A4     0x007F4560 - 0x007F4724     Function:
                                                        kn_lstep_lesson_play_init
0x006F47B0 - 0x006F4844     0x007F4730 - 0x007F47C4     Function:
                                                        kn_lstep_main_init
0x006F4850 - 0x006F4DC0     0x007F47D0 - 0x007F4D40     Function:
                                                        lesson_data_setup
0x006F4DC0 - 0x006F5134     0x007F4D40 - 0x007F50B4     Function:
                                                        make_ssq_at_lesson
0x006F5140 - 0x006F523C     0x007F50C0 - 0x007F51BC     Function:
                                                        disp_step
0x006F5240 - 0x006F56A8     0x007F51C0 - 0x007F5628     Function:
                                                        play_main
0x006F56B0 - 0x006F57D0     0x007F5630 - 0x007F5750     Function:
                                                        intro_play
0x006F57D0 - 0x006F5DD4     0x007F5750 - 0x007F5D54     Function:
                                                        play_init
0x006F5DE0 - 0x006F5E18     0x007F5D60 - 0x007F5D98     Function:
                                                        Update_LesPlay
0x006F5E20 - 0x006F5E28     0x007F5DA0 - 0x007F5DA8     Function:
                                                        View_LesPlay
0x006F5E30 - 0x006F60C4     0x007F5DB0 - 0x007F6044     Function:
                                                        Control_LesPlay
0x006F60D0 - 0x006F6470     0x007F6050 - 0x007F63F0     Function:
                                                        Init_LesPlay
0x006F6470 - 0x006F65D0     0x007F63F0 - 0x007F6550     Function:
                                                        fp_btn_disp
0x006F65D0 - 0x006F66C8     0x007F6550 - 0x007F6648     Function:
                                                        fp_btn_move
0x006F66D0 - 0x006F6EF4     0x007F6650 - 0x007F6E74     Function:
                                                        les_lv_item_disp
0x006F6F00 - 0x006F7158     0x007F6E80 - 0x007F70D8     Function:
                                                        les_lv_item_disap
0x006F7160 - 0x006F7754     0x007F70E0 - 0x007F76D4     Function:
                                                        les_lv_item_exec
0x006F7760 - 0x006F7B30     0x007F76E0 - 0x007F7AB0     Function:
                                                        les_lv_item_apper
0x006F7B30 - 0x006F7C40     0x007F7AB0 - 0x007F7BC0     Function:
                                                        init_cur
0x006F7C40 - 0x006F7D70     0x007F7BC0 - 0x007F7CF0     Function:
                                                        Update_LesSelLevel
0x006F7D70 - 0x006F7D78     0x007F7CF0 - 0x007F7CF8     Function:
                                                        View_LesSelLevel
0x006F7D80 - 0x006F8100     0x007F7D00 - 0x007F8080     Function:
                                                        Control_LesSelLevel
0x006F8100 - 0x006F819C     0x007F8080 - 0x007F811C     Function:
                                                        Init_LesSelLevel
0x006F81A0 - 0x006F8A8C     0x007F8120 - 0x007F8A0C     Function:
                                                        les_se_item_disp
0x006F8A90 - 0x006F8CD0     0x007F8A10 - 0x007F8C50     Function:
                                                        les_se_item_disap
0x006F8CD0 - 0x006F9340     0x007F8C50 - 0x007F92C0     Function:
                                                        les_se_item_exec
0x006F9340 - 0x006F9680     0x007F92C0 - 0x007F9600     Function:
                                                        les_se_item_apper
0x006F9680 - 0x006F9768     0x007F9600 - 0x007F96E8     Function:
                                                        update_section_banner
0x006F9770 - 0x006F9778     0x007F96F0 - 0x007F96F8     Function:
                                                        DispStatusBar_LesSelSection
0x006F9780 - 0x006F97DC     0x007F9700 - 0x007F975C     Function:
                                                        InitStatusBar_LesSelSection
0x006F97E0 - 0x006F9920     0x007F9760 - 0x007F98A0     Function:
                                                        Update_LesSelSection
0x006F9920 - 0x006F9928     0x007F98A0 - 0x007F98A8     Function:
                                                        View_LesSelSection
0x006F9930 - 0x006F9EFC     0x007F98B0 - 0x007F9E7C     Function:
                                                        Control_LesSelSection
0x006F9F00 - 0x006FA130     0x007F9E80 - 0x007FA0B0     Function:
                                                        Init_LesSelSection
0x006F2BE0 - 0x006F2F58     0x007F2B60 - 0x007F2ED8     Function:
                                                        inet_addr
0x006F2F60 - 0x006F2FBC     0x007F2EE0 - 0x007F2F3C     Function:
                                                        inet_ntoa
0x006F2FC0 - 0x006F2FE4     0x007F2F40 - 0x007F2F64     Function:
                                                        htons
0x006F2FF0 - 0x006F309C     0x007F2F70 - 0x007F301C     Function:
                                                        ktNetDhcpGetGw
0x006F30A0 - 0x006F317C     0x007F3020 - 0x007F30FC     Function:
                                                        ktNetDhcpGetDns
0x006F3180 - 0x006F320C     0x007F3100 - 0x007F318C     Function:
                                                        ktNetDhcpTimer
0x006F3210 - 0x006F32A8     0x007F3190 - 0x007F3228     Function:
                                                        ktNetDhcpRelease
0x006F32B0 - 0x006F3364     0x007F3230 - 0x007F32E4     Function:
                                                        ktNetDhcpRequest
0x006F3370 - 0x006F33FC     0x007F32F0 - 0x007F337C     Function:
                                                        ktNetDhcpEnd
0x006F3400 - 0x006F348C     0x007F3380 - 0x007F340C     Function:
                                                        ktNetDhcpStart
0x006F3490 - 0x006F351C     0x007F3410 - 0x007F349C     Function:
                                                        ktNetEtherEnd
0x006F3520 - 0x006F35AC     0x007F34A0 - 0x007F352C     Function:
                                                        ktNetEtherDown
0x006F35B0 - 0x006F3658     0x007F3530 - 0x007F35D8     Function:
                                                        ktNetEtherUp
0x006F3660 - 0x006F36EC     0x007F35E0 - 0x007F366C     Function:
                                                        ktNetEtherStart
0x006F36F0 - 0x006F37A4     0x007F3670 - 0x007F3724     Function:
                                                        ktNetAVETCPEnd
0x006F37B0 - 0x006F3878     0x007F3730 - 0x007F37F8     Function:
                                                        ktNetAVETCPStart
0x006F3880 - 0x006F3938     0x007F3800 - 0x007F38B8     Function:
                                                        gethostbyname_nb
0x006F3940 - 0x006F39F8     0x007F38C0 - 0x007F3978     Function:
                                                        ioctlsocket
0x006F3A00 - 0x006F3A98     0x007F3980 - 0x007F3A18     Function:
                                                        recvcheck
0x006F3AA0 - 0x006F3BE4     0x007F3A20 - 0x007F3B64     Function:
                                                        recvfrom
0x006F3BF0 - 0x006F3D00     0x007F3B70 - 0x007F3C80     Function:
                                                        sendto
0x006F3D00 - 0x006F3DCC     0x007F3C80 - 0x007F3D4C     Function:
                                                        bind
0x006F3DD0 - 0x006F3E84     0x007F3D50 - 0x007F3E04     Function:
                                                        closesocket
0x006F3E90 - 0x006F3F7C     0x007F3E10 - 0x007F3EFC     Function:
                                                        recv
0x006F3F80 - 0x006F405C     0x007F3F00 - 0x007F3FDC     Function:
                                                        send
0x006F4060 - 0x006F412C     0x007F3FE0 - 0x007F40AC     Function:
                                                        connect
0x006F4130 - 0x006F41E4     0x007F40B0 - 0x007F4164     Function:
                                                        socket
0x006F41F0 - 0x006F427C     0x007F4170 - 0x007F41FC     Function:
                                                        unsetdefaultgw
0x006F4280 - 0x006F430C     0x007F4200 - 0x007F428C     Function:
                                                        setdefaultgw
0x006F4310 - 0x006F432C     0x007F4290 - 0x007F42AC     Function:
                                                        getdnsaddr
0x006F4330 - 0x006F43DC     0x007F42B0 - 0x007F435C     Function:
                                                        setdnsaddr
0x006F43E0 - 0x006F43EC     0x007F4360 - 0x007F436C     Function:
                                                        getmyinetaddr
0x006F43F0 - 0x006F43FC     0x007F4370 - 0x007F437C     Function:
                                                        setmyinetaddr
0x006F4400 - 0x006F4448     0x007F4380 - 0x007F43C8     Function:
                                                        bsdsocket_terminate
0x006F4450 - 0x006F451C     0x007F43D0 - 0x007F449C     Function:
                                                        bsdsocket_init
0x006F4520 - 0x006F452C     0x007F44A0 - 0x007F44AC     Function:
                                                        ddrnet_acc_res_delplayer
0x006F4530 - 0x006F4594     0x007F44B0 - 0x007F4514     Function:
                                                        ddrnet_acc_req_delplayer
0x006F45A0 - 0x006F45AC     0x007F4520 - 0x007F452C     Function:
                                                        ddrnet_acc_res_regplayer
0x006F45B0 - 0x006F4640     0x007F4530 - 0x007F45C0     Function:
                                                        ddrnet_acc_req_regplayer
0x006F4640 - 0x006F479C     0x007F45C0 - 0x007F471C     Function:
                                                        ddrnet_acc_res_playerlist
0x006F47A0 - 0x006F47A8     0x007F4720 - 0x007F4728     Function:
                                                        ddrnet_acc_req_playerlist
0x006F47B0 - 0x006F47D4     0x007F4730 - 0x007F4754     Function:
                                                        ddrnet_res_auth
0x006F47E0 - 0x006F49B0     0x007F4760 - 0x007F4930     Function:
                                                        ddrnet_req_auth
0x006F49B0 - 0x006F4A4C     0x007F4930 - 0x007F49CC     Function:
                                                        ddrnet_res_ccode
0x006F4A50 - 0x006F4A58     0x007F49D0 - 0x007F49D8     Function:
                                                        ddrnet_req_ccode
0x006F4A60 - 0x006F4B3C     0x007F49E0 - 0x007F4ABC     Function:
                                                        ddrnet_rc_res_rcidlist
0x006F4B40 - 0x006F4B48     0x007F4AC0 - 0x007F4AC8     Function:
                                                        ddrnet_rc_req_rcidlist
0x006F4B50 - 0x006F4BCC     0x007F4AD0 - 0x007F4B4C     Function:
                                                        ddrnet_rc_recv_week
0x006F4BD0 - 0x006F4C8C     0x007F4B50 - 0x007F4C0C     Function:
                                                        ddrnet_rc_res_schedule
0x006F4C90 - 0x006F4C98     0x007F4C10 - 0x007F4C18     Function:
                                                        ddrnet_rc_req_schedule
0x006F4CA0 - 0x006F4DCC     0x007F4C20 - 0x007F4D4C     Function:
                                                        ddrnet_res_ranking
0x006F4DD0 - 0x006F4E2C     0x007F4D50 - 0x007F4DAC     Function:
                                                        ddrnet_res_ranking_start
0x006F4E30 - 0x006F4F70     0x007F4DB0 - 0x007F4EF0     Function:
                                                        ddrnet_req_ranking
0x006F4F70 - 0x006F4F7C     0x007F4EF0 - 0x007F4EFC     Function:
                                                        ddrnet_rc_res_regist
0x006F4F80 - 0x006F5024     0x007F4F00 - 0x007F4FA4     Function:
                                                        ddrnet_rc_req_regist
0x006F5030 - 0x006F503C     0x007F4FB0 - 0x007F4FBC     Function:
                                                        ddrnet_rc_res_entry
0x006F5040 - 0x006F50B4     0x007F4FC0 - 0x007F5034     Function:
                                                        ddrnet_rc_req_entry
0x006F50C0 - 0x006F5180     0x007F5040 - 0x007F5100     Function:
                                                        ddrnet_rc_res_trycount
0x006F5180 - 0x006F51E4     0x007F5100 - 0x007F5164     Function:
                                                        ddrnet_rc_req_trycount
0x006F51F0 - 0x006F53B4     0x007F5170 - 0x007F5334     Function:
                                                        ddrnet_rc_res_info
0x006F53C0 - 0x006F5434     0x007F5340 - 0x007F53B4     Function:
                                                        ddrnet_rc_req_info
0x006F5440 - 0x006F54D8     0x007F53C0 - 0x007F5458     Function:
                                                        ddrnet_close_all_connection
0x006F54E0 - 0x006F557C     0x007F5460 - 0x007F54FC     Function:
                                                        ddrnet_close_connection
0x006F5580 - 0x006F55CC     0x007F5500 - 0x007F554C     Function:
                                                        ddrnet_init_blowfish
0x006F55D0 - 0x006F5608     0x007F5550 - 0x007F5588     Function:
                                                        ddrnet_send_message
0x006F5610 - 0x006F56C4     0x007F5590 - 0x007F5644     Function:
                                                        ddrnet_recv_message
0x006F56D0 - 0x006F5750     0x007F5650 - 0x007F56D0     Function:
                                                        ddrnet_disconnect
0x006F5750 - 0x006F5A54     0x007F56D0 - 0x007F59D4     Function:
                                                        ddrnet_connect_nb
0x006F5A60 - 0x006F5ADC     0x007F59E0 - 0x007F5A5C     Function:
                                                        ddrnet_connect_server_by_index
0x006F5AE0 - 0x006F5BE0     0x007F5A60 - 0x007F5B60     Function:
                                                        ddrnet_gate_res_infolist
0x006F5BE0 - 0x006F5BEC     0x007F5B60 - 0x007F5B6C     Function:
                                                        ddrnet_gate_res_infoliststart
0x006F5BF0 - 0x006F5BF8     0x007F5B70 - 0x007F5B78     Function:
                                                        ddrnet_gate_req_infolist
0x006F5C00 - 0x006F5C7C     0x007F5B80 - 0x007F5BFC     Function:
                                                        ddrnet_gate_res_svrtime
0x006F5C80 - 0x006F5C88     0x007F5C00 - 0x007F5C08     Function:
                                                        ddrnet_gate_req_svrtime
0x006F5C90 - 0x006F5DA0     0x007F5C10 - 0x007F5D20     Function:
                                                        ddrnet_gate_res_svrlist
0x006F5DA0 - 0x006F5E80     0x007F5D20 - 0x007F5E00     Function:
                                                        ddrnet_gate_res_svrliststart
0x006F5E80 - 0x006F5E88     0x007F5E00 - 0x007F5E08     Function:
                                                        ddrnet_gate_req_svrlist
0x006F5E90 - 0x006F6A40     0x007F5E10 - 0x007F69C0     Function:
                                                        ddrnet_id_regist_request
0x006F6A40 - 0x006F6B10     0x007F69C0 - 0x007F6A90     Function:
                                                        ddrnet_lobby_res_rulemask
0x006F6B10 - 0x006F6B18     0x007F6A90 - 0x007F6A98     Function:
                                                        ddrnet_lobby_req_rulemask
0x006F6B20 - 0x006F6B2C     0x007F6AA0 - 0x007F6AAC     Function:
                                                        ddrnet_lobby_res_set_ipaddress
0x006F6B30 - 0x006F6BFC     0x007F6AB0 - 0x007F6B7C     Function:
                                                        ddrnet_lobby_req_set_ipaddress
0x006F6C00 - 0x006F6D1C     0x007F6B80 - 0x007F6C9C     Function:
                                                        ddrnet_lobby_res_log_challenge_data
0x006F6D20 - 0x006F6E08     0x007F6CA0 - 0x007F6D88     Function:
                                                        ddrnet_lobby_res_log_challenge_start
0x006F6E10 - 0x006F6E18     0x007F6D90 - 0x007F6D98     Function:
                                                        ddrnet_lobby_req_log_challenge
0x006F6E20 - 0x006F6EFC     0x007F6DA0 - 0x007F6E7C     Function:
                                                        ddrnet_lobby_res_log_point_data
0x006F6F00 - 0x006F6FF0     0x007F6E80 - 0x007F6F70     Function:
                                                        ddrnet_lobby_res_log_point_start
0x006F6FF0 - 0x006F70FC     0x007F6F70 - 0x007F707C     Function:
                                                        ddrnet_lobby_res_log_h2h_data
0x006F7100 - 0x006F71F0     0x007F7080 - 0x007F7170     Function:
                                                        ddrnet_lobby_res_log_h2h_start
0x006F71F0 - 0x006F71F8     0x007F7170 - 0x007F7178     Function:
                                                        ddrnet_lobby_req_log_h2h
0x006F7200 - 0x006F720C     0x007F7180 - 0x007F718C     Function:
                                                        ddrnet_lobby_res_set_option
0x006F7210 - 0x006F721C     0x007F7190 - 0x007F719C     Function:
                                                        ddrnet_lobby_recv_resetroom
0x006F7220 - 0x006F722C     0x007F71A0 - 0x007F71AC     Function:
                                                        ddrnet_lobby_res_set_plopt
0x006F7230 - 0x006F72B0     0x007F71B0 - 0x007F7230     Function:
                                                        ddrnet_lobby_req_set_plopt
0x006F72B0 - 0x006F733C     0x007F7230 - 0x007F72BC     Function:
                                                        ddrnet_lobby_res_get_plopt
0x006F7340 - 0x006F73A4     0x007F72C0 - 0x007F7324     Function:
                                                        ddrnet_lobby_req_get_plopt
0x006F73B0 - 0x006F74D4     0x007F7330 - 0x007F7454     Function:
                                                        ddrnet_lobby_recv_matchmake
0x006F74E0 - 0x006F74EC     0x007F7460 - 0x007F746C     Function:
                                                        ddrnet_lobby_res_confiscate
0x006F74F0 - 0x006F7564     0x007F7470 - 0x007F74E4     Function:
                                                        ddrnet_lobby_req_confiscate
0x006F7570 - 0x006F7610     0x007F74F0 - 0x007F7590     Function:
                                                        ddrnet_lobby_res_endgame
0x006F7610 - 0x006F770C     0x007F7590 - 0x007F768C     Function:
                                                        ddrnet_lobby_req_endgame
0x006F7710 - 0x006F778C     0x007F7690 - 0x007F770C     Function:
                                                        ddrnet_lobby_recv_readystatus
0x006F7790 - 0x006F779C     0x007F7710 - 0x007F771C     Function:
                                                        ddrnet_lobby_res_readystatus
0x006F77A0 - 0x006F7804     0x007F7720 - 0x007F7784     Function:
                                                        ddrnet_lobby_send_readystatus
0x006F7810 - 0x006F78A4     0x007F7790 - 0x007F7824     Function:
                                                        ddrnet_lobby_recv_p2p
0x006F78B0 - 0x006F7948     0x007F7830 - 0x007F78C8     Function:
                                                        ddrnet_lobby_send_p2p
0x006F7950 - 0x006F7B4C     0x007F78D0 - 0x007F7ACC     Function:
                                                        ddrnet_lobby_res_playerinfo
0x006F7B50 - 0x006F7BC0     0x007F7AD0 - 0x007F7B40     Function:
                                                        ddrnet_lobby_req_playerinfo
0x006F7BC0 - 0x006F7BCC     0x007F7B40 - 0x007F7B4C     Function:
                                                        ddrnet_lobby_res_restartautomatch
0x006F7BD0 - 0x006F7BDC     0x007F7B50 - 0x007F7B5C     Function:
                                                        ddrnet_lobby_recv_opponentleaveroom
0x006F7BE0 - 0x006F7C5C     0x007F7B60 - 0x007F7BDC     Function:
                                                        ddrnet_lobby_recv_roomstatusupdate
0x006F7C60 - 0x006F7C6C     0x007F7BE0 - 0x007F7BEC     Function:
                                                        ddrnet_lobby_res_gooutroom
0x006F7C70 - 0x006F7C78     0x007F7BF0 - 0x007F7BF8     Function:
                                                        ddrnet_lobby_req_gooutroom
0x006F7C80 - 0x006F7E90     0x007F7C00 - 0x007F7E10     Function:
                                                        ddrnet_lobby_recv_roomlistupdate
0x006F7E90 - 0x006F7F5C     0x007F7E10 - 0x007F7EDC     Function:
                                                        ddrnet_lobby_recv_roomlistdel
0x006F7F60 - 0x006F7F6C     0x007F7EE0 - 0x007F7EEC     Function:
                                                        ddrnet_lobby_res_createroom
0x006F7F70 - 0x006F807C     0x007F7EF0 - 0x007F7FFC     Function:
                                                        ddrnet_lobby_req_createroom
0x006F8080 - 0x006F81B4     0x007F8000 - 0x007F8134     Function:
                                                        ddrnet_lobby_res_roomlist
0x006F81C0 - 0x006F8210     0x007F8140 - 0x007F8190     Function:
                                                        ddrnet_lobby_res_roomliststart
0x006F8210 - 0x006F8218     0x007F8190 - 0x007F8198     Function:
                                                        ddrnet_lobby_req_roomlist
0x006F8220 - 0x006F8438     0x007F81A0 - 0x007F83B8     Function:
                                                        ddrnet_lobby_recv_blockplistupdate
0x006F8440 - 0x006F85F8     0x007F83C0 - 0x007F8578     Function:
                                                        ddrnet_lobby_res_blockplist
0x006F8600 - 0x006F8658     0x007F8580 - 0x007F85D8     Function:
                                                        ddrnet_lobby_res_blockpliststart
0x006F8660 - 0x006F8668     0x007F85E0 - 0x007F85E8     Function:
                                                        ddenet_lobby_req_blockplist
0x006F8670 - 0x006F867C     0x007F85F0 - 0x007F85FC     Function:
                                                        ddrnet_lobby_res_enterblock
0x006F8680 - 0x006F86E4     0x007F8600 - 0x007F8664     Function:
                                                        ddrnet_lobby_req_enterblock
0x006F86F0 - 0x006F87C4     0x007F8670 - 0x007F8744     Function:
                                                        ddrnet_lobby_res_blocklist
0x006F87D0 - 0x006F87D8     0x007F8750 - 0x007F8758     Function:
                                                        ddrnet_lobby_req_blocklist
0x006F87E0 - 0x006F8898     0x007F8760 - 0x007F8818     Function:
                                                        ddrnet_res_selplayer
0x006F88A0 - 0x006F8904     0x007F8820 - 0x007F8884     Function:
                                                        ddrnet_req_selplayer
0x006F8910 - 0x006F8994     0x007F8890 - 0x007F8914     Function:
                                                        ddrnet_only_get_result
0x006F89A0 - 0x006F89F4     0x007F8920 - 0x007F8974     Function:
                                                        ddrnet_only_request
0x006F8A00 - 0x006F8AA0     0x007F8980 - 0x007F8A20     Function:
                                                        ddrnet_check_recvtime
0x006F8AA0 - 0x006F8B54     0x007F8A20 - 0x007F8AD4     Function:
                                                        ddrnet_send_heartbeat
0x006F8B60 - 0x006F8C20     0x007F8AE0 - 0x007F8BA0     Function:
                                                        ddrnet_get_svrlistindex_by_type
0x006F8C20 - 0x006F9410     0x007F8BA0 - 0x007F9390     Function:
                                                        ddrnet_mproc_lobby
0x006F9410 - 0x006F952C     0x007F9390 - 0x007F94AC     Function:
                                                        ddrnet_mproc_acc
0x006F9530 - 0x006F9648     0x007F94B0 - 0x007F95C8     Function:
                                                        ddrnet_mproc_gate
0x006F9650 - 0x006F9808     0x007F95D0 - 0x007F9788     Function:
                                                        ddrnet_proc_message
0x006F9810 - 0x006F9868     0x007F9790 - 0x007F97E8     Function:
                                                        ddrnet_connect_gate
0x006F9870 - 0x006F9970     0x007F97F0 - 0x007F98F0     Function:
                                                        ddrnet_create
0x006F9970 - 0x006F9AF4     0x007F98F0 - 0x007F9A74     Function:
                                                        change_th
0x006F9B00 - 0x006F9BF4     0x007F9A80 - 0x007F9B74     Function:
                                                        change_main
0x006F9C00 - 0x006F9D84     0x007F9B80 - 0x007F9D04     Function:
                                                        register_th
0x006F9D90 - 0x006F9E84     0x007F9D10 - 0x007F9E04     Function:
                                                        register_main
0x006F9E90 - 0x006FA434     0x007F9E10 - 0x007FA3B4     Function:
                                                        auth_main
0x006FA440 - 0x006FA964     0x007FA3C0 - 0x007FA8E4     Function:
                                                        set_warning_msg
0x006FA970 - 0x006FAA9C     0x007FA8F0 - 0x007FAA1C     Function:
                                                        set_msg
0x006FAAA0 - 0x006FB158     0x007FAA20 - 0x007FB0D8     Function:
                                                        display_at_id_menu
0x006FB160 - 0x006FB5B0     0x007FB0E0 - 0x007FB530     Function:
                                                        disp_auth
0x006FB5B0 - 0x006FB8A0     0x007FB530 - 0x007FB820     Function:
                                                        disp_small_frame
0x006FB8A0 - 0x006FC020     0x007FB820 - 0x007FBFA0     Function:
                                                        display
0x006FC020 - 0x006FC0E4     0x007FBFA0 - 0x007FC064     Function:
                                                        load_https
0x006FC0F0 - 0x006FD740     0x007FC070 - 0x007FD6C0     Function:
                                                        id_menu
0x006FD740 - 0x006FD88C     0x007FD6C0 - 0x007FD80C     Function:
                                                        howto
0x006FD890 - 0x006FDB00     0x007FD810 - 0x007FDA80     Function:
                                                        logout
0x006FDB00 - 0x006FE0D0     0x007FDA80 - 0x007FE050     Function:
                                                        authenticate
0x006FE0D0 - 0x006FE35C     0x007FE050 - 0x007FE2DC     Function:
                                                        init_kb
0x006FE360 - 0x006FEA54     0x007FE2E0 - 0x007FE9D4     Function:
                                                        input_id
0x006FEA60 - 0x006FEE18     0x007FE9E0 - 0x007FED98     Function:
                                                        menu
0x006FEE20 - 0x006FF09C     0x007FEDA0 - 0x007FF01C     Function:
                                                        init
0x006FF0A0 - 0x006FF5E0     0x007FF020 - 0x007FF560     Function:
                                                        NetAuthMain
0x006FF5E0 - 0x006FF5E8     0x007FF560 - 0x007FF568     Function:
                                                        NetAuthGetAddr
0x006FF5F0 - 0x006FF744     0x007FF570 - 0x007FF6C4     Function:
                                                        unload_module_th
0x006FF750 - 0x006FF85C     0x007FF6D0 - 0x007FF7DC     Function:
                                                        ncLibResetMain
0x006FF860 - 0x006FF8E4     0x007FF7E0 - 0x007FF864     Function:
                                                        load_module_th
0x006FF8F0 - 0x006FFC9C     0x007FF870 - 0x007FFC1C     Function:
                                                        ncLibSetMain
0x006FFCA0 - 0x006FFF3C     0x007FFC20 - 0x007FFEBC     Function:
                                                        set_warning_msg
0x006FFF40 - 0x00700174     0x007FFEC0 - 0x008000F4     Function:
                                                        set_msg
0x00700180 - 0x0070081C     0x00800100 - 0x0080079C     Function:
                                                        display
0x00700820 - 0x0070099C     0x008007A0 - 0x0080091C     Function:
                                                        term
0x007009A0 - 0x00700EB0     0x00800920 - 0x00800E30     Function:
                                                        menu
0x00700EB0 - 0x00701270     0x00800E30 - 0x008011F0     Function:
                                                        load_entry_th
0x00701270 - 0x00701758     0x008011F0 - 0x008016D8     Function:
                                                        load_entry
0x00701760 - 0x00701DE8     0x008016E0 - 0x00801D68     Function:
                                                        get_list
0x00701DF0 - 0x00702348     0x00801D70 - 0x008022C8     Function:
                                                        mc_check
0x00702350 - 0x007024D4     0x008022D0 - 0x00802454     Function:
                                                        dev_check
0x007024E0 - 0x00702E94     0x00802460 - 0x00802E14     Function:
                                                        NetCnfMain
0x00702EA0 - 0x00703258     0x00802E20 - 0x008031D8     Function:
                                                        reset_ave_for_dnas_main
0x00703260 - 0x00703278     0x008031E0 - 0x008031F8     Function:
                                                        reset_ave_for_dnas_init
0x00703280 - 0x00703370     0x00803200 - 0x008032F0     Function:
                                                        aton
0x00703370 - 0x00704040     0x008032F0 - 0x00803FC0     Function:
                                                        setup_ave_for_dnas_main
0x00704040 - 0x007040B4     0x00803FC0 - 0x00804034     Function:
                                                        setup_ave_for_dnas_init
0x007040C0 - 0x007043A8     0x00804040 - 0x00804328     Function:
                                                        dnas_th
0x007043B0 - 0x00704924     0x00804330 - 0x008048A4     Function:
                                                        debug_menu
0x00704930 - 0x00704BCC     0x008048B0 - 0x00804B4C     Function:
                                                        set_warning_msg
0x00704BD0 - 0x00704DD8     0x00804B50 - 0x00804D58     Function:
                                                        fake_dnas_func
0x00704DE0 - 0x00705268     0x00804D60 - 0x008051E8     Function:
                                                        dnas_func
0x00705270 - 0x007057FC     0x008051F0 - 0x0080577C     Function:
                                                        dnas_main
0x00705800 - 0x007058DC     0x00805780 - 0x0080585C     Function:
                                                        init
0x007058E0 - 0x00705A80     0x00805860 - 0x00805A00     Function:
                                                        NetDnasMain
0x00705A80 - 0x00705BEC     0x00805A00 - 0x00805B6C     Function:
                                                        event_handler
0x00705BF0 - 0x00705FC4     0x00805B70 - 0x00805F44     Function:
                                                        upnp_test
0x00705FD0 - 0x00706324     0x00805F50 - 0x008062A4     Function:
                                                        set_warning_msg
0x00706330 - 0x00706490     0x008062B0 - 0x00806410     Function:
                                                        NetRouterMain
0x00706490 - 0x0070649C     0x00806410 - 0x0080641C     Function:
                                                        nrmesGetNo
0x007064A0 - 0x007064AC     0x00806420 - 0x0080642C     Function:
                                                        nrmesGetYes
0x007064B0 - 0x007064E8     0x00806430 - 0x00806468     Function:
                                                        nrmesGetMessageTable
0x006F0100 - 0x006F0144     0x007F0080 - 0x007F00C4     Function:
                                                        dmm_sp_connect_hide_check
0x006F0150 - 0x006F01D0     0x007F00D0 - 0x007F0150     Function:
                                                        dmm_event_boot_check
0x006F01D0 - 0x006F0358     0x007F0150 - 0x007F02D8     Function:
                                                        dmm_event_set_fade
0x006F0360 - 0x006F03C0     0x007F02E0 - 0x007F0340     Function:
                                                        dmm_event_wait_count
0x006F03C0 - 0x006F03E0     0x007F0340 - 0x007F0360     Function:
                                                        dmm_event_get_count
0x006F03E0 - 0x006F0400     0x007F0360 - 0x007F0380     Function:
                                                        dmm_event_set_count
0x006F0400 - 0x006F0638     0x007F0380 - 0x007F05B8     Function:
                                                        dmm_event_main
0x006F0640 - 0x006F07E8     0x007F05C0 - 0x007F0768     Function:
                                                        dmm_set_sbj_special_connect_event
0x006F07F0 - 0x006F09A8     0x007F0770 - 0x007F0928     Function:
                                                        dmm_set_sbj_normal_connect_event
0x006F09B0 - 0x006F0D40     0x007F0930 - 0x007F0CC0     Function:
                                                        dmm_event_check
0x006F0D40 - 0x006F0D48     0x007F0CC0 - 0x007F0CC8     Function:
                                                        _dmm_evboot_func_sp_cone01
0x006F0D50 - 0x006F0DCC     0x007F0CD0 - 0x007F0D4C     Function:
                                                        _dmm_evboot_func_sp_cone00
0x006F0DD0 - 0x006F0E30     0x007F0D50 - 0x007F0DB0     Function:
                                                        _dmm_evboot_func_info_chart
0x006F0E30 - 0x006F0E68     0x007F0DB0 - 0x007F0DE8     Function:
                                                        _dmm_evboot_func_info_shop
0x006F0E70 - 0x006F0ED0     0x007F0DF0 - 0x007F0E50     Function:
                                                        _dmm_evboot_func_lastboss
0x006F0ED0 - 0x006F0F30     0x007F0E50 - 0x007F0EB0     Function:
                                                        _dmm_evboot_func_area05
0x006F0F30 - 0x006F0F90     0x007F0EB0 - 0x007F0F10     Function:
                                                        _dmm_evboot_func_area04
0x006F0F90 - 0x006F0FF0     0x007F0F10 - 0x007F0F70     Function:
                                                        _dmm_evboot_func_area03
0x006F0FF0 - 0x006F1050     0x007F0F70 - 0x007F0FD0     Function:
                                                        _dmm_evboot_func_area02
0x006F1050 - 0x006F10C8     0x007F0FD0 - 0x007F1048     Function:
                                                        _dmm_evboot_func_ending_last
0x006F10D0 - 0x006F1168     0x007F1050 - 0x007F10E8     Function:
                                                        _dmm_evboot_func_ending_E01
0x006F1170 - 0x006F1208     0x007F10F0 - 0x007F1188     Function:
                                                        _dmm_evboot_func_ending_D03
0x006F1210 - 0x006F12A8     0x007F1190 - 0x007F1228     Function:
                                                        _dmm_evboot_func_ending_D02
0x006F12B0 - 0x006F1348     0x007F1230 - 0x007F12C8     Function:
                                                        _dmm_evboot_func_ending_D01
0x006F1350 - 0x006F13E8     0x007F12D0 - 0x007F1368     Function:
                                                        _dmm_evboot_func_ending_C04
0x006F13F0 - 0x006F1488     0x007F1370 - 0x007F1408     Function:
                                                        _dmm_evboot_func_ending_C03
0x006F1490 - 0x006F1528     0x007F1410 - 0x007F14A8     Function:
                                                        _dmm_evboot_func_ending_C02
0x006F1530 - 0x006F15C8     0x007F14B0 - 0x007F1548     Function:
                                                        _dmm_evboot_func_ending_C01
0x006F15D0 - 0x006F1668     0x007F1550 - 0x007F15E8     Function:
                                                        _dmm_evboot_func_ending_B05
0x006F1670 - 0x006F1708     0x007F15F0 - 0x007F1688     Function:
                                                        _dmm_evboot_func_ending_B04
0x006F1710 - 0x006F17A8     0x007F1690 - 0x007F1728     Function:
                                                        _dmm_evboot_func_ending_B03
0x006F17B0 - 0x006F1848     0x007F1730 - 0x007F17C8     Function:
                                                        _dmm_evboot_func_ending_B02
0x006F1850 - 0x006F18E8     0x007F17D0 - 0x007F1868     Function:
                                                        _dmm_evboot_func_ending_B01
0x006F18F0 - 0x006F1988     0x007F1870 - 0x007F1908     Function:
                                                        _dmm_evboot_func_ending_A02
0x006F1990 - 0x006F1A28     0x007F1910 - 0x007F19A8     Function:
                                                        _dmm_evboot_func_ending_A01
0x006F1A30 - 0x006F1B7C     0x007F19B0 - 0x007F1AFC     Function:
                                                        _dmm_event_sub_disp_chart
0x006F1B80 - 0x006F1C50     0x007F1B00 - 0x007F1BD0     Function:
                                                        _dmm_event_disp_chart
0x006F1C50 - 0x006F1E98     0x007F1BD0 - 0x007F1E18     Function:
                                                        _dmm_event_func04_sub
0x006F1EA0 - 0x006F1FA0     0x007F1E20 - 0x007F1F20     Function:
                                                        _dmm_event_func04
0x006F1FA0 - 0x006F21A4     0x007F1F20 - 0x007F2124     Function:
                                                        _dmm_event_func03_sub_set_state
0x006F21B0 - 0x006F2400     0x007F2130 - 0x007F2380     Function:
                                                        _dmm_event_func03_sub_disp_area1_start
0x006F2400 - 0x006F2828     0x007F2380 - 0x007F27A8     Function:
                                                        _dmm_event_func03_sub_disp
0x006F2830 - 0x006F2BA4     0x007F27B0 - 0x007F2B24     Function:
                                                        _dmm_event_func03_sub_init
0x006F2BB0 - 0x006F3118     0x007F2B30 - 0x007F3098     Function:
                                                        _dmm_event_func03_sub
0x006F3120 - 0x006F3208     0x007F30A0 - 0x007F3188     Function:
                                                        _dmm_event_func03
0x006F3210 - 0x006F5C20     0x007F3190 - 0x007F5BA0     Function:
                                                        _dmm_event_func02_play_ending_logo
0x006F5C20 - 0x006F5EB4     0x007F5BA0 - 0x007F5E34     Function:
                                                        _dmm_event_func02_ending
0x006F5EC0 - 0x006F6018     0x007F5E40 - 0x007F5F98     Function:
                                                        _dmm_event_func02
0x006F6020 - 0x006F69B8     0x007F5FA0 - 0x007F6938     Function:
                                                        _dmm_event_func01_sub
0x006F69C0 - 0x006F6A90     0x007F6940 - 0x007F6A10     Function:
                                                        _dmm_event_func01
0x006F6A90 - 0x006F72F0     0x007F6A10 - 0x007F7270     Function:
                                                        _dmm_event_func00_sub
0x006F72F0 - 0x006F73C0     0x007F7270 - 0x007F7340     Function:
                                                        _dmm_event_func00
0x006F73C0 - 0x006F7484     0x007F7340 - 0x007F7404     Function:
                                                        dmm_reset_to_playable
0x006F7490 - 0x006F7580     0x007F7410 - 0x007F7500     Function:
                                                        is_check_beat_ok
0x006F7580 - 0x006F7F20     0x007F7500 - 0x007F7EA0     Function:
                                                        dmm_judge_item
0x006F7F20 - 0x006F80D4     0x007F7EA0 - 0x007F8054     Function:
                                                        dmm_judge_subject
0x006F80E0 - 0x006F8648     0x007F8060 - 0x007F85C8     Function:
                                                        dmm_judge
0x006F8650 - 0x006F870C     0x007F85D0 - 0x007F868C     Function:
                                                        dmm_judge_init
0x006F8710 - 0x006F87E0     0x007F8690 - 0x007F8760     Function:
                                                        convert_to_dir
0x006F87E0 - 0x006F8884     0x007F8760 - 0x007F8804     Function:
                                                        dmm_judge_count_note
0x006F8890 - 0x006F8B8C     0x007F8810 - 0x007F8B0C     Function:
                                                        dmm_play_control
0x006F8B90 - 0x006F8E38     0x007F8B10 - 0x007F8DB8     Function:
                                                        dmm_play_disp
0x006F8E40 - 0x006F94C4     0x007F8DC0 - 0x007F9444     Function:
                                                        dmm_dance_play_chain
0x006F94D0 - 0x006F95A0     0x007F9450 - 0x007F9520     Function:
                                                        dmm_dance_play_finish
0x006F95A0 - 0x006F9960     0x007F9520 - 0x007F98E0     Function:
                                                        dmm_dance_play_main
0x006F9960 - 0x006F9A70     0x007F98E0 - 0x007F99F0     Function:
                                                        dmm_dance_play_pre
0x006F9A70 - 0x006F9C20     0x007F99F0 - 0x007F9BA0     Function:
                                                        dmm_dance_play_init
0x006F9C20 - 0x006F9E34     0x007F9BA0 - 0x007F9DB4     Function:
                                                        dmm_play
0x006F9E40 - 0x006FA048     0x007F9DC0 - 0x007F9FC8     Function:
                                                        dmm_course_play_finish
0x006FA050 - 0x006FA2C4     0x007F9FD0 - 0x007FA244     Function:
                                                        dmm_course_play_main
0x006FA2D0 - 0x006FA568     0x007FA250 - 0x007FA4E8     Function:
                                                        dmm_course_play_prepare_main
0x006FA570 - 0x006FA790     0x007FA4F0 - 0x007FA710     Function:
                                                        dmm_course_init
0x006FA790 - 0x006FA9C4     0x007FA710 - 0x007FA944     Function:
                                                        dmm_course_play_prepare_init
0x006FA9D0 - 0x006FAB88     0x007FA950 - 0x007FAB08     Function:
                                                        dmm_course_play_prepare
0x006FAB90 - 0x006FAE9C     0x007FAB10 - 0x007FAE1C     Function:
                                                        dmm_play_course
0x006FAEA0 - 0x006FAECC     0x007FAE20 - 0x007FAE4C     Function:
                                                        _dmm_qmenu_func_return
0x006FAED0 - 0x006FAF68     0x007FAE50 - 0x007FAEE8     Function:
                                                        _dmm_qmenu_func_save
0x006FAF70 - 0x006FB0C4     0x007FAEF0 - 0x007FB044     Function:
                                                        _dmm_qmenu_func_shop
0x006FB0D0 - 0x006FB32C     0x007FB050 - 0x007FB2AC     Function:
                                                        _dmm_qmenu_func_change
0x006FB330 - 0x006FB434     0x007FB2B0 - 0x007FB3B4     Function:
                                                        quick_menu_ctrl
0x006FB440 - 0x006FB478     0x007FB3C0 - 0x007FB3F8     Function:
                                                        get_qmenu_table
0x006FB480 - 0x006FB4A0     0x007FB400 - 0x007FB420     Function:
                                                        get_qmenu_work
0x006FB4A0 - 0x006FB698     0x007FB420 - 0x007FB618     Function:
                                                        quick_menu_main
0x006FB6A0 - 0x006FB6A8     0x007FB620 - 0x007FB628     Function:
                                                        quick_menu_check
0x006FB6B0 - 0x006FB6B8     0x007FB630 - 0x007FB638     Function:
                                                        quick_menu_init
0x006FB6C0 - 0x006FB828     0x007FB640 - 0x007FB7A8     Function:
                                                        dmm_result_retry_ctrl
0x006FB830 - 0x006FBC6C     0x007FB7B0 - 0x007FBBEC     Function:
                                                        dmm_update_save_data
0x006FBC70 - 0x006FC0D0     0x007FBBF0 - 0x007FC050     Function:
                                                        dmm_result_retry
0x006FC0D0 - 0x006FC228     0x007FC050 - 0x007FC1A8     Function:
                                                        dmm_result_data_load
0x006FC230 - 0x006FC348     0x007FC1B0 - 0x007FC2C8     Function:
                                                        dmm_result_init
0x006FC350 - 0x006FC6D8     0x007FC2D0 - 0x007FC658     Function:
                                                        dmm_result
0x006FC6E0 - 0x006FC7B8     0x007FC660 - 0x007FC738     Function:
                                                        dmm_get_disp_subject_num
0x006FC7C0 - 0x006FC7FC     0x007FC740 - 0x007FC77C     Function:
                                                        dmm_get_cur_subject_id
0x006FC800 - 0x006FC9EC     0x007FC780 - 0x007FC96C     Function:
                                                        dmm_disp_message
0x006FC9F0 - 0x006FCAF0     0x007FC970 - 0x007FCA70     Function:
                                                        dmm_disp_count
0x006FCAF0 - 0x006FE8A0     0x007FCA70 - 0x007FE820     Function:
                                                        dmm_disp_subject_info
0x006FE8A0 - 0x006FECA0     0x007FE820 - 0x007FEC20     Function:
                                                        dmm_disp_area_start_info
0x006FECA0 - 0x00700468     0x007FEC20 - 0x008003E8     Function:
                                                        dmm_disp_connect_sub
0x00700470 - 0x007005FC     0x008003F0 - 0x0080057C     Function:
                                                        dmm_disp_connect_light
0x00700600 - 0x00700868     0x00800580 - 0x008007E8     Function:
                                                        dmm_disp_connect
0x00700870 - 0x007016E0     0x008007F0 - 0x00801660     Function:
                                                        dmm_disp_one_panel
0x007016E0 - 0x00701A2C     0x00801660 - 0x008019AC     Function:
                                                        dmm_disp_panel_sub
0x00701A30 - 0x00701BB8     0x008019B0 - 0x00801B38     Function:
                                                        dmm_ctrl_chart
0x00701BC0 - 0x00701F28     0x00801B40 - 0x00801EA8     Function:
                                                        dmm_disp_grid
0x00701F30 - 0x00702050     0x00801EB0 - 0x00801FD0     Function:
                                                        dmm_disp_area
0x00702050 - 0x00702118     0x00801FD0 - 0x00802098     Function:
                                                        dmm_select_disp
0x00702120 - 0x00702CC4     0x008020A0 - 0x00802C44     Function:
                                                        dmm_world_ctrl
0x00702CD0 - 0x00702D24     0x00802C50 - 0x00802CA4     Function:
                                                        dmm_world_ctrl_move_start
0x00702D30 - 0x00702E64     0x00802CB0 - 0x00802DE4     Function:
                                                        dmm_chart_move_max_for_event
0x00702E70 - 0x00702FA4     0x00802DF0 - 0x00802F24     Function:
                                                        dmm_chart_move_max
0x00702FB0 - 0x007033D4     0x00802F30 - 0x00803354     Function:
                                                        dmm_check_old_cursor
0x007033E0 - 0x00703534     0x00803360 - 0x008034B4     Function:
                                                        dmm_set_change_subject
0x00703540 - 0x00703744     0x008034C0 - 0x008036C4     Function:
                                                        dmm_set_subject_info
0x00703750 - 0x00703AA4     0x008036D0 - 0x00803A24     Function:
                                                        dmm_set_panel_disp
0x00703AB0 - 0x00703ABC     0x00803A30 - 0x00803A3C     Function:
                                                        dmm_set_disp_offset
0x00703AC0 - 0x0070467C     0x00803A40 - 0x008045FC     Function:
                                                        dmm_select_ctrl
0x00704680 - 0x00704A78     0x00804600 - 0x008049F8     Function:
                                                        dmm_select_obj_ctrl
0x00704A80 - 0x00704CF0     0x00804A00 - 0x00804C70     Function:
                                                        dmm_select_init
0x00704CF0 - 0x00704F30     0x00804C70 - 0x00804EB0     Function:
                                                        dmm_select_data_load
0x00704F30 - 0x0070552C     0x00804EB0 - 0x008054AC     Function:
                                                        dmm_select
0x00705530 - 0x007056AC     0x008054B0 - 0x0080562C     Function:
                                                        dmm_style_select_menu_ctrl
0x007056B0 - 0x00705A24     0x00805630 - 0x008059A4     Function:
                                                        dmm_style_select_menu
0x00705A30 - 0x00705C20     0x008059B0 - 0x00805BA0     Function:
                                                        dmm_style_finish
0x00705C20 - 0x00705F90     0x00805BA0 - 0x00805F10     Function:
                                                        dmm_style
0x006F0100 - 0x006F0618     0x007F0080 - 0x007F0598     Function:
                                                        OptAdjustMain
0x006F0620 - 0x006F0680     0x007F05A0 - 0x007F0600     Function:
                                                        OptAdjustInit
0x006F0680 - 0x006F0864     0x007F0600 - 0x007F07E4     Function:
                                                        View_OptDoll
0x006F0870 - 0x006F09F8     0x007F07F0 - 0x007F0978     Function:
                                                        OptKConfigSetEditKey
0x006F0A00 - 0x006F0B30     0x007F0980 - 0x007F0AB0     Function:
                                                        OptKConfigGetTblKey
0x006F0B30 - 0x006F0D20     0x007F0AB0 - 0x007F0CA0     Function:
                                                        OptWinKConfigArrow
0x006F0D20 - 0x006F0FBC     0x007F0CA0 - 0x007F0F3C     Function:
                                                        OptWinKConfigBackDisp
0x006F0FC0 - 0x006F155C     0x007F0F40 - 0x007F14DC     Function:
                                                        OptWinKConfigObjDisp
0x006F1560 - 0x006F18F0     0x007F14E0 - 0x007F1870     Function:
                                                        OptKConfigDoubleMain
0x006F18F0 - 0x006F1940     0x007F1870 - 0x007F18C0     Function:
                                                        OptKConfigDoubleInit
0x006F1940 - 0x006F1BD0     0x007F18C0 - 0x007F1B50     Function:
                                                        OptKConfigMain
0x006F1BD0 - 0x006F1C34     0x007F1B50 - 0x007F1BB4     Function:
                                                        OptKConfigInit
0x006F1C40 - 0x006F2000     0x007F1BC0 - 0x007F1F80     Function:
                                                        OptLangMain
0x006F2000 - 0x006F2040     0x007F1F80 - 0x007F1FC0     Function:
                                                        OptLangInit
0x006F2040 - 0x006F2288     0x007F1FC0 - 0x007F2208     Function:
                                                        Option_Board_Disp
0x006F2290 - 0x006F2308     0x007F2210 - 0x007F2288     Function:
                                                        Option_base00_disp
0x006F2310 - 0x006F24C8     0x007F2290 - 0x007F2448     Function:
                                                        Option_base00_disap
0x006F24D0 - 0x006F2794     0x007F2450 - 0x007F2714     Function:
                                                        Option_base00_appear
0x006F27A0 - 0x006F2848     0x007F2720 - 0x007F27C8     Function:
                                                        Option_caption_disap
0x006F2850 - 0x006F28E8     0x007F27D0 - 0x007F2868     Function:
                                                        Option_caption_appear
0x006F28F0 - 0x006F2910     0x007F2870 - 0x007F2890     Function:
                                                        Option_win_disp
0x006F2910 - 0x006F2B90     0x007F2890 - 0x007F2B10     Function:
                                                        Option_win_func
0x006F2B90 - 0x006F2BD8     0x007F2B10 - 0x007F2B58     Function:
                                                        option_obj_disap
0x006F2BE0 - 0x006F2C40     0x007F2B60 - 0x007F2BC0     Function:
                                                        option_obj_set
0x006F2C40 - 0x006F2C70     0x007F2BC0 - 0x007F2BF0     Function:
                                                        OptGetFontSize
0x006F2C70 - 0x006F2D24     0x007F2BF0 - 0x007F2CA4     Function:
                                                        OptPrintFont
0x006F2D30 - 0x006F2D94     0x007F2CB0 - 0x007F2D14     Function:
                                                        OptOutStrGet
0x006F2DA0 - 0x006F2DC8     0x007F2D20 - 0x007F2D48     Function:
                                                        OptOutStrInit
0x006F2DD0 - 0x006F2F84     0x007F2D50 - 0x007F2F04     Function:
                                                        OptInitTex
0x006F2F90 - 0x006F3074     0x007F2F10 - 0x007F2FF4     Function:
                                                        OptInitKanji
0x006F3080 - 0x006F30A8     0x007F3000 - 0x007F3028     Function:
                                                        OptSystemEnd
0x006F30B0 - 0x006F33B0     0x007F3030 - 0x007F3330     Function:
                                                        OptSystemMain
0x006F33B0 - 0x006F3418     0x007F3330 - 0x007F3398     Function:
                                                        OptSystemInit
0x006F3420 - 0x006F3534     0x007F33A0 - 0x007F34B4     Function:
                                                        OptMcLoadExe
0x006F3540 - 0x006F3634     0x007F34C0 - 0x007F35B4     Function:
                                                        OptMcSaveExe
0x006F3640 - 0x006F36C8     0x007F35C0 - 0x007F3648     Function:
                                                        OptMcLoadMain
0x006F36D0 - 0x006F370C     0x007F3650 - 0x007F368C     Function:
                                                        OptMcLoadInit
0x006F3710 - 0x006F3798     0x007F3690 - 0x007F3718     Function:
                                                        OptMcSaveMain
0x006F37A0 - 0x006F37DC     0x007F3720 - 0x007F375C     Function:
                                                        OptMcSaveInit
0x006F37E0 - 0x006F38D4     0x007F3760 - 0x007F3854     Function:
                                                        OptGetMenuHelp
0x006F38E0 - 0x006F42B8     0x007F3860 - 0x007F4238     Function:
                                                        OptMenuModeGetType
0x006F42C0 - 0x006F4380     0x007F4240 - 0x007F4300     Function:
                                                        OptMenuModeGetStLine
0x006F4380 - 0x006F4418     0x007F4300 - 0x007F4398     Function:
                                                        OptMenuModeGetLine
0x006F4420 - 0x006F4938     0x007F43A0 - 0x007F48B8     Function:
                                                        OptMenuModeChangeType
0x006F4940 - 0x006F4DF8     0x007F48C0 - 0x007F4D78     Function:
                                                        OptNextMenuModePAGE
0x006F4E00 - 0x006F53BC     0x007F4D80 - 0x007F533C     Function:
                                                        OptMenuModeSet
0x006F53C0 - 0x006F53C8     0x007F5340 - 0x007F5348     Function:
                                                        OptMenuHelpDisp
0x006F53D0 - 0x006F5648     0x007F5350 - 0x007F55C8     Function:
                                                        OptMenuModeDisp
0x006F5650 - 0x006F5EC4     0x007F55D0 - 0x007F5E44     Function:
                                                        OptMenuMain
0x006F5ED0 - 0x006F5EF0     0x007F5E50 - 0x007F5E70     Function:
                                                        OptMenuInit3
0x006F5EF0 - 0x006F5F18     0x007F5E70 - 0x007F5E98     Function:
                                                        OptMenuInit2
0x006F5F20 - 0x006F5F64     0x007F5EA0 - 0x007F5EE4     Function:
                                                        OptMenuInit
0x006F5F70 - 0x006F6454     0x007F5EF0 - 0x007F63D4     Function:
                                                        OptLeftMenuBoxDisp
0x006F6460 - 0x006F6798     0x007F63E0 - 0x007F6718     Function:
                                                        OptRightMenuCursorDisp
0x006F67A0 - 0x006F68B8     0x007F6720 - 0x007F6838     Function:
                                                        OptWinMenuLineWindowClose
0x006F68C0 - 0x006F76A8     0x007F6840 - 0x007F7628     Function:
                                                        OptWinMenuLineWindowMain
0x006F76B0 - 0x006F775C     0x007F7630 - 0x007F76DC     Function:
                                                        OptWinMenuLineWindowOpen
0x006F7760 - 0x006F78D0     0x007F76E0 - 0x007F7850     Function:
                                                        OptWinMenuLineWindowSet
0x006F78D0 - 0x006F794C     0x007F7850 - 0x007F78CC     Function:
                                                        OptWinSetWML_Str2
0x006F7950 - 0x006F798C     0x007F78D0 - 0x007F790C     Function:
                                                        OptWinMenuLineWindowGetST_Stop
0x006F7990 - 0x006F79A0     0x007F7910 - 0x007F7920     Function:
                                                        OptWinAdjustClose
0x006F79A0 - 0x006F7E08     0x007F7920 - 0x007F7D88     Function:
                                                        OptWinAdjustMain
0x006F7E10 - 0x006F7E20     0x007F7D90 - 0x007F7DA0     Function:
                                                        OptWinAdjustOpen
0x006F7E20 - 0x006F7E28     0x007F7DA0 - 0x007F7DA8     Function:
                                                        OptWinTopBarClose
0x006F7E30 - 0x006F7E38     0x007F7DB0 - 0x007F7DB8     Function:
                                                        OptWinTopBarOpen
0x006F0100 - 0x006F029C     0x007F0080 - 0x007F021C     Function:
                                                        GetKeyRepeat
0x006F02A0 - 0x006F033C     0x007F0220 - 0x007F02BC     Function:
                                                        CheckKeyRepeat
0x006F0340 - 0x006F042C     0x007F02C0 - 0x007F03AC     Function:
                                                        wos_step_func_draw_program
0x006F0430 - 0x006F051C     0x007F03B0 - 0x007F049C     Function:
                                                        wos_step_func_draw_simultaneousstep
0x006F0520 - 0x006F060C     0x007F04A0 - 0x007F058C     Function:
                                                        wos_step_func_draw_workoutstep
0x006F0610 - 0x006F06DC     0x007F0590 - 0x007F065C     Function:
                                                        wos_step_func_draw_goal
0x006F06E0 - 0x006F07C0     0x007F0660 - 0x007F0740     Function:
                                                        wos_step_func_draw_menu
0x006F07C0 - 0x006F156C     0x007F0740 - 0x007F14EC     Function:
                                                        woSettingSheetDraw
0x006F1570 - 0x006F1664     0x007F14F0 - 0x007F15E4     Function:
                                                        wos_step_func_end_wait
0x006F1670 - 0x006F173C     0x007F15F0 - 0x007F16BC     Function:
                                                        wos_step_func_ok
0x006F1740 - 0x006F18C8     0x007F16C0 - 0x007F1848     Function:
                                                        wos_step_func_program
0x006F18D0 - 0x006F1A18     0x007F1850 - 0x007F1998     Function:
                                                        wos_step_func_simultaneousstep
0x006F1A20 - 0x006F1B84     0x007F19A0 - 0x007F1B04     Function:
                                                        wos_step_func_workoutstep
0x006F1B90 - 0x006F1D18     0x007F1B10 - 0x007F1C98     Function:
                                                        wos_step_func_goal
0x006F1D20 - 0x006F1E90     0x007F1CA0 - 0x007F1E10     Function:
                                                        wos_step_func_menu
0x006F1E90 - 0x006F2078     0x007F1E10 - 0x007F1FF8     Function:
                                                        wos_step_func_weight
0x006F2080 - 0x006F20F4     0x007F2000 - 0x007F2074     Function:
                                                        wos_step_func_start_wait
0x006F2100 - 0x006F2184     0x007F2080 - 0x007F2104     Function:
                                                        WorkoutSetting_Term
0x006F2190 - 0x006F25B8     0x007F2110 - 0x007F2538     Function:
                                                        WorkoutSetting_Main
0x006F25C0 - 0x006F2630     0x007F2540 - 0x007F25B0     Function:
                                                        WorkoutSetting_Init
0x006F2630 - 0x006F2658     0x007F25B0 - 0x007F25D8     Function:
                                                        wumSetNormaCalorie
0x006F2660 - 0x006F2688     0x007F25E0 - 0x007F2608     Function:
                                                        wumSetNormaPlayTime
0x006F2690 - 0x006F2744     0x007F2610 - 0x007F26C4     Function:
                                                        wumSetWeight
0x006F2750 - 0x006F27B0     0x007F26D0 - 0x007F2730     Function:
                                                        wumGetUserBlankNoSecond
0x006F27B0 - 0x006F27F8     0x007F2730 - 0x007F2778     Function:
                                                        wumGetUserBlankNoFirst
0x006F2800 - 0x006F2890     0x007F2780 - 0x007F2810     Function:
                                                        wumGetUserPos
0x006F2890 - 0x006F28A4     0x007F2810 - 0x007F2824     Function:
                                                        wumGetUserWork
0x006F28B0 - 0x006F28B8     0x007F2830 - 0x007F2838     Function:
                                                        wumGetUserNum
0x006F28C0 - 0x006F28FC     0x007F2840 - 0x007F287C     Function:
                                                        wumDeleteUser
0x006F2900 - 0x006F2988     0x007F2880 - 0x007F2908     Function:
                                                        wumCreateUser
0x006F2990 - 0x006F29A4     0x007F2910 - 0x007F2924     Function:
                                                        wumGetPlayUserWork
0x006F29B0 - 0x006F29E4     0x007F2930 - 0x007F2964     Function:
                                                        wumSetPlayUserWork
0x006F29F0 - 0x006F2A00     0x007F2970 - 0x007F2980     Function:
                                                        wumSetSystemUserWork
0x006F2A00 - 0x006F2A1C     0x007F2980 - 0x007F299C     Function:
                                                        wumGetSystemUserWork
0x006F2A20 - 0x006F2A28     0x007F29A0 - 0x007F29A8     Function:
                                                        wumInit
0x006F2A30 - 0x006F2A9C     0x007F29B0 - 0x007F2A1C     Function:
                                                        WouFuncDraw
0x006F2AA0 - 0x006F2B04     0x007F2A20 - 0x007F2A84     Function:
                                                        WouFuncAct
0x006F2B10 - 0x006F2B30     0x007F2A90 - 0x007F2AB0     Function:
                                                        WorkoutUser_GetPlayerStatus
0x006F2B30 - 0x006F2B50     0x007F2AB0 - 0x007F2AD0     Function:
                                                        WorkoutUser_SetPlayerStatus
0x006F2B50 - 0x006F2B74     0x007F2AD0 - 0x007F2AF4     Function:
                                                        WorkoutUser_SetFinish
0x006F2B80 - 0x006F2BC0     0x007F2B00 - 0x007F2B40     Function:
                                                        WorkoutUser_IsCreating
0x006F2BC0 - 0x006F2BE0     0x007F2B40 - 0x007F2B60     Function:
                                                        WorkoutUser_GetFuncStep
0x006F2BE0 - 0x006F2C00     0x007F2B60 - 0x007F2B80     Function:
                                                        WorkoutUser_SetNextFunc
0x006F2C00 - 0x006F2CD8     0x007F2B80 - 0x007F2C58     Function:
                                                        WorkoutUser_Term
0x006F2CE0 - 0x006F2EA0     0x007F2C60 - 0x007F2E20     Function:
                                                        WorkoutUser_Main
0x006F2EA0 - 0x006F2FAC     0x007F2E20 - 0x007F2F2C     Function:
                                                        WorkoutUser_Init
0x006F2FB0 - 0x006F2FC0     0x007F2F30 - 0x007F2F40     Function:
                                                        WorkoutUser_DataInit
0x006F2FC0 - 0x006F2FC8     0x007F2F40 - 0x007F2F48     Function:
                                                        wouPleaseWaitTerm
0x006F2FD0 - 0x006F30E4     0x007F2F50 - 0x007F3064     Function:
                                                        wouPleaseWaitDraw
0x006F30F0 - 0x006F34D0     0x007F3070 - 0x007F3450     Function:
                                                        wouPleaseWaitAct
0x006F34D0 - 0x006F34E8     0x007F3450 - 0x007F3468     Function:
                                                        wouPleaseWaitInit
0x006F34F0 - 0x006F3518     0x007F3470 - 0x007F3498     Function:
                                                        wouPressStartSetStatusCloase
0x006F3520 - 0x006F3528     0x007F34A0 - 0x007F34A8     Function:
                                                        wouPressStartTerm
0x006F3530 - 0x006F363C     0x007F34B0 - 0x007F35BC     Function:
                                                        wouPressStartDraw
0x006F3640 - 0x006F37C4     0x007F35C0 - 0x007F3744     Function:
                                                        wouPressStartAct
0x006F37D0 - 0x006F37E8     0x007F3750 - 0x007F3768     Function:
                                                        wouPressStartInit
0x006F37F0 - 0x006F3828     0x007F3770 - 0x007F37A8     Function:
                                                        wouPlayerCardSetStatusOut
0x006F3830 - 0x006F3838     0x007F37B0 - 0x007F37B8     Function:
                                                        wouPlayerCardTerm
0x006F3840 - 0x006F51CC     0x007F37C0 - 0x007F514C     Function:
                                                        wouPlayerCardDraw
0x006F51D0 - 0x006F5408     0x007F5150 - 0x007F5388     Function:
                                                        wouPlayerCardAct
0x006F5410 - 0x006F547C     0x007F5390 - 0x007F53FC     Function:
                                                        wouPlayerCardInit
0x006F5480 - 0x006F5690     0x007F5400 - 0x007F5610     Function:
                                                        wouFontPrint
0x006F5690 - 0x006F56A8     0x007F5610 - 0x007F5628     Function:
                                                        wouScrBarStepOpen
0x006F56B0 - 0x006F56C8     0x007F5630 - 0x007F5648     Function:
                                                        wouScrBarStepFinish
0x006F56D0 - 0x006F58D8     0x007F5650 - 0x007F5858     Function:
                                                        wouScrBarDraw
0x006F58E0 - 0x006F5B98     0x007F5860 - 0x007F5B18     Function:
                                                        wouScrBarAct
0x006F5BA0 - 0x006F5BA8     0x007F5B20 - 0x007F5B28     Function:
                                                        wouUserGuestCautionTerm
0x006F5BB0 - 0x006F5C74     0x007F5B30 - 0x007F5BF4     Function:
                                                        wouUserGuestCautionDraw
0x006F5C80 - 0x006F5F40     0x007F5C00 - 0x007F5EC0     Function:
                                                        wouUserGuestCautionAct
0x006F5F40 - 0x006F5F60     0x007F5EC0 - 0x007F5EE0     Function:
                                                        wouUserGuestCautionInit
0x006F5F60 - 0x006F5F90     0x007F5EE0 - 0x007F5F10     Function:
                                                        wouUserMenuStatusReopen
0x006F5F90 - 0x006F5FD0     0x007F5F10 - 0x007F5F50     Function:
                                                        wouUserMenuIsFinished
0x006F5FD0 - 0x006F5FD8     0x007F5F50 - 0x007F5F58     Function:
                                                        wouUserMenuTerm
0x006F5FE0 - 0x006F6178     0x007F5F60 - 0x007F60F8     Function:
                                                        wouUserMenuDraw
0x006F6180 - 0x006F68B0     0x007F6100 - 0x007F6830     Function:
                                                        wouUserMenuAct
0x006F68B0 - 0x006F68D0     0x007F6830 - 0x007F6850     Function:
                                                        wouUserMenuInit
0x006F68D0 - 0x006F6AB4     0x007F6850 - 0x007F6A34     Function:
                                                        wouCardStatusReopen
0x006F6AC0 - 0x006F6B28     0x007F6A40 - 0x007F6AA8     Function:
                                                        wouCardStatusFinish
0x006F6B30 - 0x006F6D58     0x007F6AB0 - 0x007F6CD8     Function:
                                                        wouCardStatusDelete
0x006F6D60 - 0x006F6F44     0x007F6CE0 - 0x007F6EC4     Function:
                                                        wouCardEntry
0x006F6F50 - 0x006F7018     0x007F6ED0 - 0x007F6F98     Function:
                                                        wouCardEntryUser
0x006F7020 - 0x006F7194     0x007F6FA0 - 0x007F7114     Function:
                                                        wouCardAct
0x006F71A0 - 0x006F7AE4     0x007F7120 - 0x007F7A64     Function:
                                                        wouCardDrawCreate
0x006F7AF0 - 0x006F8434     0x007F7A70 - 0x007F83B4     Function:
                                                        wouCardDrawGuest
0x006F8440 - 0x006FA508     0x007F83C0 - 0x007FA488     Function:
                                                        wouCardDrawUser
0x006FA510 - 0x006FA644     0x007FA490 - 0x007FA5C4     Function:
                                                        wouCardAct_Stay
0x006FA650 - 0x006FA800     0x007FA5D0 - 0x007FA780     Function:
                                                        wouCardAct_Out
0x006FA800 - 0x006FAA1C     0x007FA780 - 0x007FA99C     Function:
                                                        wouCardAct_In
0x006FAA20 - 0x006FAAB8     0x007FA9A0 - 0x007FAA38     Function:
                                                        wouListCursorGetCardNo
0x006FAAC0 - 0x006FAB60     0x007FAA40 - 0x007FAAE0     Function:
                                                        wouListtIsFinished
0x006FAB60 - 0x006FAB68     0x007FAAE0 - 0x007FAAE8     Function:
                                                        wouListTerm
0x006FAB70 - 0x006FAC9C     0x007FAAF0 - 0x007FAC1C     Function:
                                                        wouListDraw
0x006FACA0 - 0x006FB314     0x007FAC20 - 0x007FB294     Function:
                                                        wouListAct
0x006FB320 - 0x006FB430     0x007FB2A0 - 0x007FB3B0     Function:
                                                        wouListInit
0x006FB430 - 0x006FB460     0x007FB3B0 - 0x007FB3E0     Function:
                                                        wouListReopen
0x006FB460 - 0x006FB56C     0x007FB3E0 - 0x007FB4EC     Function:
                                                        wouListNext
0x006FB570 - 0x006FB708     0x007FB4F0 - 0x007FB688     Function:
                                                        wouGuestPlayerDataInit
0x006FB710 - 0x006FB8A0     0x007FB690 - 0x007FB820     Function:
                                                        wouCreatePlayerDataInit
0x006FB8A0 - 0x006FBA00     0x007FB820 - 0x007FB980     Function:
                                                        wouEditPlayerDataInit
0x006FBA00 - 0x006FBFF4     0x007FB980 - 0x007FBF74     Function:
                                                        wouEditFinalAct
0x006FC000 - 0x006FC354     0x007FBF80 - 0x007FC2D4     Function:
                                                        wouEditRegistPassAct
0x006FC360 - 0x006FC610     0x007FC2E0 - 0x007FC590     Function:
                                                        wouEditUsePassAct
0x006FC610 - 0x006FC8A4     0x007FC590 - 0x007FC824     Function:
                                                        wouEditFrameIconDraw
0x006FC8B0 - 0x006FCB84     0x007FC830 - 0x007FCB04     Function:
                                                        wouEditFrameIconAct
0x006FCB90 - 0x006FCF34     0x007FCB10 - 0x007FCEB4     Function:
                                                        wouEditFaceIconDraw
0x006FCF40 - 0x006FD2F4     0x007FCEC0 - 0x007FD274     Function:
                                                        wouEditFaceIconAct
0x006FD300 - 0x006FDAF0     0x007FD280 - 0x007FDA70     Function:
                                                        wouEditSheet_Draw
0x006FDAF0 - 0x006FDDB0     0x007FDA70 - 0x007FDD30     Function:
                                                        wouEditSheet_Act
0x006FDDB0 - 0x006FDE08     0x007FDD30 - 0x007FDD88     Function:
                                                        wouEditStatusFinish
0x006FDE10 - 0x006FDE3C     0x007FDD90 - 0x007FDDBC     Function:
                                                        wouEditTerm
0x006FDE40 - 0x006FDE6C     0x007FDDC0 - 0x007FDDEC     Function:
                                                        wouEditDraw
0x006FDE70 - 0x006FE020     0x007FDDF0 - 0x007FDFA0     Function:
                                                        wouEditAct
0x006FE020 - 0x006FE040     0x007FDFA0 - 0x007FDFC0     Function:
                                                        wouEditEndAct
0x006FE040 - 0x006FE1FC     0x007FDFC0 - 0x007FE17C     Function:
                                                        wouEditInit
0x006FE200 - 0x006FE760     0x007FE180 - 0x007FE6E0     Function:
                                                        wouEnterPasswordDraw
0x006FE760 - 0x006FE7C8     0x007FE6E0 - 0x007FE748     Function:
                                                        wouEnterPasswordIsRegisted
0x006FE7D0 - 0x006FE7F0     0x007FE750 - 0x007FE770     Function:
                                                        wouEnterPasswordIsFinished
0x006FE7F0 - 0x006FEA44     0x007FE770 - 0x007FE9C4     Function:
                                                        wouEnterPasswordAct
0x006FEA50 - 0x006FEA70     0x007FE9D0 - 0x007FE9F0     Function:
                                                        wouEnterPasswordInit
0x006FEA70 - 0x006FEAE4     0x007FE9F0 - 0x007FEA64     Function:
                                                        wouEnterPasswordWarningTerm
0x006FEAF0 - 0x006FEB7C     0x007FEA70 - 0x007FEAFC     Function:
                                                        wouEnterPasswordWarning
0x006FEB80 - 0x006FECA4     0x007FEB00 - 0x007FEC24     Function:
                                                        wouEnterPasswordWarningInit
0x006FECB0 - 0x006FECF0     0x007FEC30 - 0x007FEC70     Function:
                                                        wouEnterPasswordCloseWaiting
0x006FECF0 - 0x006FEDDC     0x007FEC70 - 0x007FED5C     Function:
                                                        wouEnterPasswordEntering
0x006FEDE0 - 0x006FEE00     0x007FED60 - 0x007FED80     Function:
                                                        wouRegisterPasswordGetWord
0x006FEE00 - 0x006FEE68     0x007FED80 - 0x007FEDE8     Function:
                                                        wouRegisterPasswordIsRegisted
0x006FEE70 - 0x006FEE90     0x007FEDF0 - 0x007FEE10     Function:
                                                        wouRegisterPasswordIsFinished
0x006FEE90 - 0x006FEE98     0x007FEE10 - 0x007FEE18     Function:
                                                        wouRegisterPasswordTerm
0x006FEEA0 - 0x006FF7A8     0x007FEE20 - 0x007FF728     Function:
                                                        wouRegisterPasswordDraw
0x006FF7B0 - 0x006FF974     0x007FF730 - 0x007FF8F4     Function:
                                                        wouRegisterPasswordAct
0x006FF980 - 0x006FF9A0     0x007FF900 - 0x007FF920     Function:
                                                        wouRegisterPasswordInit
0x006FF9A0 - 0x006FF9E0     0x007FF920 - 0x007FF960     Function:
                                                        wouRegisterPasswordCloseWaiting
0x006FF9E0 - 0x006FFA54     0x007FF960 - 0x007FF9D4     Function:
                                                        wouRegisterPasswordWarningTerm
0x006FFA60 - 0x006FFAEC     0x007FF9E0 - 0x007FFA6C     Function:
                                                        wouRegisterPasswordWarning
0x006FFAF0 - 0x006FFC14     0x007FFA70 - 0x007FFB94     Function:
                                                        wouRegisterPasswordWarningInit
0x006FFC20 - 0x006FFD08     0x007FFBA0 - 0x007FFC88     Function:
                                                        wouRegisterPasswordRetyping
0x006FFD10 - 0x006FFDC0     0x007FFC90 - 0x007FFD40     Function:
                                                        wouRegisterPasswordEntering
0x006FFDC0 - 0x006FFEA0     0x007FFD40 - 0x007FFE20     Function:
                                                        wouGetPassTyping
0x006FFEA0 - 0x006FFF08     0x007FFE20 - 0x007FFE88     Function:
                                                        woCursorSet
0x006FFF10 - 0x006FFF58     0x007FFE90 - 0x007FFED8     Function:
                                                        woCursorGet
0x006FFF60 - 0x006FFFD0     0x007FFEE0 - 0x007FFF50     Function:
                                                        woCursorDec
0x006FFFD0 - 0x00700048     0x007FFF50 - 0x007FFFC8     Function:
                                                        woCursorInc
0x00700050 - 0x00700164     0x007FFFD0 - 0x008000E4     Function:
                                                        woCursorDraw
0x00700170 - 0x00700198     0x008000F0 - 0x00800118     Function:
                                                        woCursorAct
0x007001A0 - 0x007001C0     0x00800120 - 0x00800140     Function:
                                                        woCursorInit
0x007001C0 - 0x007006F4     0x00800140 - 0x00800674     Function:
                                                        WorkoutMenuDraw
0x00700700 - 0x00700DD0     0x00800680 - 0x00800D50     Function:
                                                        WorkoutMenuAct
0x00700DD0 - 0x00700E70     0x00800D50 - 0x00800DF0     Function:
                                                        WorkoutMenuMain
0x00700E70 - 0x00700EC0     0x00800DF0 - 0x00800E40     Function:
                                                        WorkoutMenuInit
0x00700EC0 - 0x00700F0C     0x00800E40 - 0x00800E8C     Function:
                                                        WorkoutMsgGetStr
0x00700F10 - 0x00701064     0x00800E90 - 0x00800FE4     Function:
                                                        WorkoutMsgSet
0x00701070 - 0x00701088     0x00800FF0 - 0x00801008     Function:
                                                        WorkoutMsgWinClose
0x00701090 - 0x007010A8     0x00801010 - 0x00801028     Function:
                                                        WorkoutMsgWinOpen
0x007010B0 - 0x007010EC     0x00801030 - 0x0080106C     Function:
                                                        WorkoutMsgWinTerm
0x007010F0 - 0x00701174     0x00801070 - 0x008010F4     Function:
                                                        WorkoutMsgWinMain
0x00701180 - 0x007011EC     0x00801100 - 0x0080116C     Function:
                                                        WorkoutMsgWinInit
0x006F0100 - 0x006F0210     0x007F0080 - 0x007F0190     Function:
                                                        trans_title_th
0x006F0210 - 0x006F03C8     0x007F0190 - 0x007F0348     Function:
                                                        rec_tex_init
0x006F03D0 - 0x006F0654     0x007F0350 - 0x007F05D4     Function:
                                                        rec_xmove_update
0x006F0660 - 0x006F0690     0x007F05E0 - 0x007F0610     Function:
                                                        Rec_XMoveSet
0x006F0690 - 0x006F06D8     0x007F0610 - 0x007F0658     Function:
                                                        rec_obj_disap
0x006F06E0 - 0x006F0760     0x007F0660 - 0x007F06E0     Function:
                                                        rec_obj_set
0x006F0760 - 0x006F08A8     0x007F06E0 - 0x007F0828     Function:
                                                        Rec_FontPuts20
0x006F08B0 - 0x006F08CC     0x007F0830 - 0x007F084C     Function:
                                                        Rec_OutStrGet
0x006F08D0 - 0x006F097C     0x007F0850 - 0x007F08FC     Function:
                                                        Rec_PadScroll
0x006F0980 - 0x006F09CC     0x007F0900 - 0x007F094C     Function:
                                                        Rec_PadRepeat
0x006F09D0 - 0x006F0A1C     0x007F0950 - 0x007F099C     Function:
                                                        Rec_PadTrg
0x006F0A20 - 0x006F0A28     0x007F09A0 - 0x007F09A8     Function:
                                                        Term_Reco
0x006F0A30 - 0x006F0F60     0x007F09B0 - 0x007F0EE0     Function:
                                                        Step_Reco
0x006F0F60 - 0x006F0FE0     0x007F0EE0 - 0x007F0F60     Function:
                                                        Init_Reco
0x006F0FE0 - 0x006F1164     0x007F0F60 - 0x007F10E4     Function:
                                                        rec_star_disp
0x006F1170 - 0x006F14C8     0x007F10F0 - 0x007F1448     Function:
                                                        rec_cursor_disp
0x006F14D0 - 0x006F1694     0x007F1450 - 0x007F1614     Function:
                                                        RCObj_erase_disp
0x006F16A0 - 0x006F1A90     0x007F1620 - 0x007F1A10     Function:
                                                        RCObj_erase_func
0x006F1A90 - 0x006F1C6C     0x007F1A10 - 0x007F1BEC     Function:
                                                        RCObj_btn_disp
0x006F1C70 - 0x006F1CC4     0x007F1BF0 - 0x007F1C44     Function:
                                                        RCObj_btn_disap
0x006F1CD0 - 0x006F1D2C     0x007F1C50 - 0x007F1CAC     Function:
                                                        RCObj_btn_apper
0x006F1D30 - 0x006F2014     0x007F1CB0 - 0x007F1F94     Function:
                                                        RCObj_scr_bar_disp
0x006F2020 - 0x006F2074     0x007F1FA0 - 0x007F1FF4     Function:
                                                        RCObj_scr_bar_disap
0x006F2080 - 0x006F20DC     0x007F2000 - 0x007F205C     Function:
                                                        RCObj_scr_bar_apper
0x006F20E0 - 0x006F213C     0x007F2060 - 0x007F20BC     Function:
                                                        RCObj_detail_disp
0x006F2140 - 0x006F2194     0x007F20C0 - 0x007F2114     Function:
                                                        RCObj_detail_disap
0x006F21A0 - 0x006F21FC     0x007F2120 - 0x007F217C     Function:
                                                        RCObj_detail_apper
0x006F2200 - 0x006F2754     0x007F2180 - 0x007F26D4     Function:
                                                        RCObj_cur_disp
0x006F2760 - 0x006F27AC     0x007F26E0 - 0x007F272C     Function:
                                                        RCObj_cur_exec
0x006F27B0 - 0x006F27B8     0x007F2730 - 0x007F2738     Function:
                                                        RCObj_win_disp
0x006F27C0 - 0x006F28F0     0x007F2740 - 0x007F2870     Function:
                                                        RCObj_win_func
0x006F28F0 - 0x006F29F8     0x007F2870 - 0x007F2978     Function:
                                                        RCObj_fade
0x006F2A00 - 0x006F2A3C     0x007F2980 - 0x007F29BC     Function:
                                                        RCObj_fadeset
0x006F2A40 - 0x006F2B00     0x007F29C0 - 0x007F2A80     Function:
                                                        Rec_PutZBuffBoard
0x006F2B00 - 0x006F2D20     0x007F2A80 - 0x007F2CA0     Function:
                                                        Rec_obj_board_disp
0x006F2D20 - 0x006F2DA4     0x007F2CA0 - 0x007F2D24     Function:
                                                        Rec_line_disp
0x006F2DB0 - 0x006F2FF8     0x007F2D30 - 0x007F2F78     Function:
                                                        Rec_Board_Disp
0x006F3000 - 0x006F31D8     0x007F2F80 - 0x007F3158     Function:
                                                        Rec_DetailItemDisp
0x006F31E0 - 0x006F3550     0x007F3160 - 0x007F34D0     Function:
                                                        Rec_DanceLevelDisp
0x006F3550 - 0x006F3698     0x007F34D0 - 0x007F3618     Function:
                                                        Rec_res_slash_disp
0x006F36A0 - 0x006F39BC     0x007F3620 - 0x007F393C     Function:
                                                        Rec_res_time_disp
0x006F39C0 - 0x006F3F4C     0x007F3940 - 0x007F3ECC     Function:
                                                        Rec_res_digit_disp
0x006F3F50 - 0x006F4078     0x007F3ED0 - 0x007F3FF8     Function:
                                                        RCObj_top_btn_disp
0x006F4080 - 0x006F4260     0x007F4000 - 0x007F41E0     Function:
                                                        RCObj_top_exp_disp
0x006F4260 - 0x006F4344     0x007F41E0 - 0x007F42C4     Function:
                                                        RCObj_top_exp_disap
0x006F4350 - 0x006F446C     0x007F42D0 - 0x007F43EC     Function:
                                                        RCObj_top_exp_exec
0x006F4470 - 0x006F44E4     0x007F43F0 - 0x007F4464     Function:
                                                        RCObj_top_exp_apper
0x006F44F0 - 0x006F4598     0x007F4470 - 0x007F4518     Function:
                                                        RCObj_label_disap
0x006F45A0 - 0x006F4648     0x007F4520 - 0x007F45C8     Function:
                                                        RCObj_label_apper
0x006F4650 - 0x006F4938     0x007F45D0 - 0x007F48B8     Function:
                                                        RCObj_base_disp
0x006F4940 - 0x006F4A1C     0x007F48C0 - 0x007F499C     Function:
                                                        RCObj_base_disap
0x006F4A20 - 0x006F4AA0     0x007F49A0 - 0x007F4A20     Function:
                                                        RCObj_base_apper
0x006F4AA0 - 0x006F4D3C     0x007F4A20 - 0x007F4CBC     Function:
                                                        RCObj_top_item_disp
0x006F4D40 - 0x006F4E60     0x007F4CC0 - 0x007F4DE0     Function:
                                                        RCObj_top_item_disap
0x006F4E60 - 0x006F4EA8     0x007F4DE0 - 0x007F4E28     Function:
                                                        RCObj_top_item_exec
0x006F4EB0 - 0x006F5040     0x007F4E30 - 0x007F4FC0     Function:
                                                        RCObj_top_item_apper
0x006F5040 - 0x006F51B0     0x007F4FC0 - 0x007F5130     Function:
                                                        Rec_Top
0x006F51B0 - 0x006F5244     0x007F5130 - 0x007F51C4     Function:
                                                        check_data_enable_hi
0x006F5250 - 0x006F56B8     0x007F51D0 - 0x007F5638     Function:
                                                        rec_hi_item_disp_sub
0x006F56C0 - 0x006F58AC     0x007F5640 - 0x007F582C     Function:
                                                        rec_hi_init
0x006F58B0 - 0x006F5990     0x007F5830 - 0x007F5910     Function:
                                                        Rec_Hi_BoolDelete
0x006F5990 - 0x006F5C50     0x007F5910 - 0x007F5BD0     Function:
                                                        RCObj_hi_obj_disp
0x006F5C50 - 0x006F5DDC     0x007F5BD0 - 0x007F5D5C     Function:
                                                        RCObj_hi_obj_disap
0x006F5DE0 - 0x006F5F54     0x007F5D60 - 0x007F5ED4     Function:
                                                        RCObj_hi_obj_apper
0x006F5F60 - 0x006F62A4     0x007F5EE0 - 0x007F6224     Function:
                                                        RCObj_hi_item_disp
0x006F62B0 - 0x006F63B0     0x007F6230 - 0x007F6330     Function:
                                                        RCObj_hi_item_disap
0x006F63B0 - 0x006F64B8     0x007F6330 - 0x007F6438     Function:
                                                        RCObj_hi_item_apper
0x006F64C0 - 0x006F6564     0x007F6440 - 0x007F64E4     Function:
                                                        Rec_Hi_Delete
0x006F6570 - 0x006F696C     0x007F64F0 - 0x007F68EC     Function:
                                                        Rec_Hi_DetailDisp
0x006F6970 - 0x006F7004     0x007F68F0 - 0x007F6F84     Function:
                                                        Rec_Hi
0x006F7010 - 0x006F756C     0x007F6F90 - 0x007F74EC     Function:
                                                        rec_cha_item_disp_sub
0x006F7570 - 0x006F7588     0x007F74F0 - 0x007F7508     Function:
                                                        rec_cha_init
0x006F7590 - 0x006F7620     0x007F7510 - 0x007F75A0     Function:
                                                        Rec_Cha_BoolDelete
0x006F7620 - 0x006F7928     0x007F75A0 - 0x007F78A8     Function:
                                                        RCObj_cha_obj_disp
0x006F7930 - 0x006F7ABC     0x007F78B0 - 0x007F7A3C     Function:
                                                        RCObj_cha_obj_disap
0x006F7AC0 - 0x006F7C34     0x007F7A40 - 0x007F7BB4     Function:
                                                        RCObj_cha_obj_apper
0x006F7C40 - 0x006F7F84     0x007F7BC0 - 0x007F7F04     Function:
                                                        RCObj_cha_item_disp
0x006F7F90 - 0x006F8090     0x007F7F10 - 0x007F8010     Function:
                                                        RCObj_cha_item_disap
0x006F8090 - 0x006F8198     0x007F8010 - 0x007F8118     Function:
                                                        RCObj_cha_item_apper
0x006F81A0 - 0x006F826C     0x007F8120 - 0x007F81EC     Function:
                                                        Rec_Cha_Delete
0x006F8270 - 0x006F89C0     0x007F81F0 - 0x007F8940     Function:
                                                        Rec_Cha_DetailDisp
0x006F89C0 - 0x006F8F3C     0x007F8940 - 0x007F8EBC     Function:
                                                        Rec_Cha
0x006F8F40 - 0x006F9200     0x007F8EC0 - 0x007F9180     Function:
                                                        rec_end_score_disp
0x006F9200 - 0x006F9454     0x007F9180 - 0x007F93D4     Function:
                                                        rec_end_item_disp_sub
0x006F9460 - 0x006F94E8     0x007F93E0 - 0x007F9468     Function:
                                                        Rec_End_BoolDelete
0x006F94F0 - 0x006F9624     0x007F9470 - 0x007F95A4     Function:
                                                        RCObj_end_item_disp
0x006F9630 - 0x006F96FC     0x007F95B0 - 0x007F967C     Function:
                                                        RCObj_end_item_disap
0x006F9700 - 0x006F97EC     0x007F9680 - 0x007F976C     Function:
                                                        RCObj_end_item_apper
0x006F97F0 - 0x006F9910     0x007F9770 - 0x007F9890     Function:
                                                        Rec_End_Delete
0x006F9910 - 0x006F9CF0     0x007F9890 - 0x007F9C70     Function:
                                                        Rec_End_DetailDisp
0x006F9CF0 - 0x006F9F18     0x007F9C70 - 0x007F9E98     Function:
                                                        Rec_End
0x006F9F20 - 0x006F9FB4     0x007F9EA0 - 0x007F9F34     Function:
                                                        check_data_enable_hand
0x006F9FC0 - 0x006FA3C8     0x007F9F40 - 0x007FA348     Function:
                                                        rec_hand_item_disp_sub
0x006FA3D0 - 0x006FA5CC     0x007FA350 - 0x007FA54C     Function:
                                                        rec_hand_init
0x006FA5D0 - 0x006FA6D0     0x007FA550 - 0x007FA650     Function:
                                                        Rec_Hand_BoolDelete
0x006FA6D0 - 0x006FA8F0     0x007FA650 - 0x007FA870     Function:
                                                        RCObj_hand_obj_disp
0x006FA8F0 - 0x006FAA54     0x007FA870 - 0x007FA9D4     Function:
                                                        RCObj_hand_obj_disap
0x006FAA60 - 0x006FABAC     0x007FA9E0 - 0x007FAB2C     Function:
                                                        RCObj_hand_obj_apper
0x006FABB0 - 0x006FAEF4     0x007FAB30 - 0x007FAE74     Function:
                                                        RCObj_hand_item_disp
0x006FAF00 - 0x006FB000     0x007FAE80 - 0x007FAF80     Function:
                                                        RCObj_hand_item_disap
0x006FB000 - 0x006FB108     0x007FAF80 - 0x007FB088     Function:
                                                        RCObj_hand_item_apper
0x006FB110 - 0x006FB1D0     0x007FB090 - 0x007FB150     Function:
                                                        Rec_Hand_Delete
0x006FB1D0 - 0x006FB5E4     0x007FB150 - 0x007FB564     Function:
                                                        Rec_Hand_DetailDisp
0x006FB5F0 - 0x006FBCA4     0x007FB570 - 0x007FBC24     Function:
                                                        Rec_Hand
</pre>
