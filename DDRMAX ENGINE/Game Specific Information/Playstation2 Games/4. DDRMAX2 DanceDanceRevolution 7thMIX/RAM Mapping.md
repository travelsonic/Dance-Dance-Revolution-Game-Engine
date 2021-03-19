Note: This document is far from complete.
<pre>
        RAM ADDRESS(ES):  DESCRIPTION:                                        NOTES:
             0x005674A4:  Current Index In Songwheel Index Array      
             0x005674A8:  Number Of Slots In Song Wheel
0x005675B8 - 0x00567604:  Songwheel Index Array 
0x0056F4C0 - 0x0056F4EB:  g_game_w Structure
             0x0056F4C0:  g_game_w.state
             0x0056F4C2:  g_game_w.genre
             0x0056F4C4:  g_game_w.mip
             0x0056F4C8:  g_game_w.start_chip
             0x0056F4C9:  g_game_w.extra_chip
             0x0056F4CA:  g_game_w.use_chip
             0x0056F4CB:  g_game_w.lost_chip
             0x0056F4CC:  g_game_w.stage
             0x0056F4CE:  g_game_w.next_stage
             0x0056F4D0:  g_game_w.failed
             0x0056F4D2:  g_game_w.level
             0x0056F4D4:  g_game_w.game_kind
             0x0056F4D5:  g_game_w.world
             0x0056F4D6:  g_game_w.nonstop
             0x0056F4D7:  g_game_w.event_mode
             0x0056F4D8:  g_game_w.style
             0x0056F4D9:  g_game_w music_group
             0x0056F4DA:  g_game_w.music_select_mode
             0x0056F4DB:  g_game_w.extra_stage
             0x0056F4DC:  g_game_w.extra_fix
             0x0056F4DD:  g_game_w.final_fix
             0x0056F4DE:  g_game_w.meter_kind
             0x0056F4DF:  g_game_w.roulette_stage
             0x0056F4E0:  g_game_w.edit_total
             0x0056F4E1:  g_game_w.roulette_total
             0x0056F4E2:  g_game_w.music
             0x0056F4E4:  g_game_w.oni_mode
             0x0056F4E5:  g_game_w.oni_load_step
             0x0056F4E6:  g_game_w.oni_next_music
             0x0056F4E8:  g_game_w.oni_next_mip
0x0056F4EC - 0x0057C906:  g_game_w.player[0]                                      player is an array of g_each_w structs
             0x0056F4EC:  g_game_w.player[0].play_time
             0x0056F4F0:  g_game_w.player[0].game_time
             0x0056F4F4:  g_game_w.player[0].game_time_total
             0x0056F4F8:  g_game_w.player[0].select
             0x0056F4F9:  g_game_w.player[0].character
             0x0056F4FA:  g_game_w.player[0].costume
             0x0056F4FB:  g_game_w.player[0].motiontype
             0x0056F4FC:  g_game_w.player[0].loaded_model
             0x0056F4FD:  g_game_w.player[0].loaded_texture
             0x0056F4FE:  g_game_w.player[0].loaded_motion
             0x0056F4FF:  g_game_w.player[0].play_disp_flag
             0x0056F500:  g_game_w.player[0].model_disp_flag
             0x0056F501:  g_game_w.player[0].gauge_disp_flag
             0x0056F502:  g_game_w.player[0].cur_point
             0x0056F504:  g_game_w.player[0].cur_life
             0x0056F508:  g_game_w.player[0].score
             0x0056F50C:  g_game_w.player[0].old_score
             0x0056F510:  g_game_w.player[0].real_score
             0x0056F514:  g_game_w.player[0].bonus
             0x0056F518:  g_game_w.player[0].old_bonus
             0x0056F51C:  g_game_w.player[0].max_score
             0x0056F520:  g_game_w.player[0].old_max_score
             0x0056F524:  g_game_w.player[0].max_bonus
             0x0056F528:  g_game_w.player[0].old_max_bonus
             0x0056F52C:  g_game_w.player[0].cal
             0x0056F530:  g_game_w.player[0].old_cal
             0x0056F534:  g_game_w.player[0].real_cal
             0x0056F538:  g_game_w.player[0].disp_cal
             0x0056F53C:  g_game_w.player[0].average_cal
             0x0056F540:  g_game_w.player[0].diet_norm_cal
             0x0056F544:  g_game_w.player[0].diet_norm_minute
             0x0056F548:  g_game_w.player[0].old_norm_cal
             0x0056F54C:  g_game_w.player[0].old_norm_minute
             0x0056F550:  g_game_w.player[0].minimum_cal
             0x0056F554:  g_game_w.player[0].add_cal_flg
             0x0056F555:  g_game_w.player[0].chk_cal_flg
             0x0056F556:  g_game_w.player[0].pad[0]
             0x0056F557:  g_game_w.player[0].pad[1]
             0x0056F558:  g_game_w.player[0].play_stage
             0x0056F55C:  g_game_w.player[0].decode_key1
             0x0056F560:  g_game_w.player[0].decode_key2
             0x0056F564:  g_game_w.player[0].decode_key3
0x0056F568 - 0x0056F574:  g_game_w.player[0].mode                                 mode is a play_mode struct
             0x0056F568:  g_game_w.player[0].mode.seq_kind
             0x0056F569:  g_game_w.player[0].mode.seq_transfer
             0x0056F56A:  g_game_w.player[0].mode.style
             0x0056F56B:  g_game_w.player[0].mode.pccard_seq
             0x0056F56C:  g_game_w.player[0].mode.mcard_seq
             0x0056F56D:  g_game_w.player[0].mode.padding
             0x0056F56E:  g_game_w.player[0].mode.edseq_id
             0x0056F570:  g_game_w.player[0].mode.hidden                          Bit field; 2 bits wide
             0x0056F570:  g_game_w.player[0].mode.thinout                         Bit field; 1 bit wide
             0x0056F570:  g_game_w.player[0].mode.free                            Bit field; 1 bit wide
             0x0056F570:  g_game_w.player[0].mode.soft                            Bit field; 1 bit wide
             0x0056F570:  g_game_w.player[0].mode.boost                           Bit field; 2 bits wide
             0x0056F570:  g_game_w.player[0].mode.speed                           Bit field; 5 bits wide
             0x0056F570:  g_game_w.player[0].mode.scroll                          Bit field; 2 bits wide
             0x0056F570:  g_game_w.player[0].mode.freeze                          Bit field; 1 bits wide
             0x0056F570:  g_game_w.player[0].mode.vivid                           Bit field; 2 bits wide
             0x0056F570:  g_game_w.player[0].mode.anime                           Bit field; 2 bits wide
             0x0056F570:  g_game_w.player[0].mode.dark                            Bit field; 1 bit wide
             0x0056F570:  g_game_w.player[0].mode.pad                             Bit field; 12 bits wide
0x0056F574 - 0x0056F5AC:  g_game_w.player[0].his                                  his is an array of play_his structs
             0x0056F574:  g_game_w.player[0].his[0].music
             0x0056F576:  g_game_w.player[0].his[0].edit_id
             0x0056F578:  g_game_w.player[0].his[0].seq_kind
             0x0056F579:  g_game_w.player[0].his[0].roulette
             0x0056F57A:  g_game_w.player[0].his[0].extra
             0x0056F57B:  g_game_w.player[0].his[0].pad
             0x0056F57C:  g_game_w.player[0].his[1].music
             0x0056F57E:  g_game_w.player[0].his[1].edit_id
             0x0056F580:  g_game_w.player[0].his[1].seq_kind
             0x0056F581:  g_game_w.player[0].his[1].roulette
             0x0056F582:  g_game_w.player[0].his[1].extra
             0x0056F583:  g_game_w.player[0].his[1].pad
             0x0056F584:  g_game_w.player[0].his[2].music
             0x0056F586:  g_game_w.player[0].his[2].edit_id
             0x0056F588:  g_game_w.player[0].his[2].seq_kind
             0x0056F589:  g_game_w.player[0].his[2].roulette
             0x0056F58A:  g_game_w.player[0].his[2].extra
             0x0056F58B:  g_game_w.player[0].his[2].pad
             0x0056F58C:  g_game_w.player[0].his[3].music
             0x0056F58E:  g_game_w.player[0].his[3].edit_id
             0x0056F590:  g_game_w.player[0].his[3].seq_kind
             0x0056F591:  g_game_w.player[0].his[3].roulette
             0x0056F592:  g_game_w.player[0].his[3].extra
             0x0056F593:  g_game_w.player[0].his[3].pad    
             0x0056F594:  g_game_w.player[0].his[4].music
             0x0056F596:  g_game_w.player[0].his[4].edit_id
             0x0056F598:  g_game_w.player[0].his[4].seq_kind
             0x0056F599:  g_game_w.player[0].his[4].roulette
             0x0056F59A:  g_game_w.player[0].his[4].extra
             0x0056F59B:  g_game_w.player[0].his[4].pad
             0x0056F59C:  g_game_w.player[0].his[5].music
             0x0056F59E:  g_game_w.player[0].his[5].edit_id
             0x0056F5A0:  g_game_w.player[0].his[5].seq_kind
             0x0056F5A1:  g_game_w.player[0].his[5].roulette
             0x0056F5A2:  g_game_w.player[0].his[5].extra
             0x0056F5A3:  g_game_w.player[0].his[5].pad
             0x0056F5A4:  g_game_w.player[0].his[6].music
             0x0056F5A6:  g_game_w.player[0].his[6].edit_id
             0x0056F5A8:  g_game_w.player[0].his[6].seq_kind
             0x0056F5A9:  g_game_w.player[0].his[6].roulette
             0x0056F5AA:  g_game_w.player[0].his[6].extra
             0x0056F5AB:  g_game_w.player[0].his[6].pad
0x0056F5AC - 0x0056F618:  g_game_w.player[0].stage_evaluation                     stage_evaluation is an eval_w struct
             0x0056F5AC:  g_game_w.player[0].stage_evaluation.value_ct[0]         PERFECT!! step count
             0x0056F5B0:  g_game_w.player[0].stage_evaluation.value_ct[1]         GREAT!! step count
             0x0056F5B4:  g_game_w.player[0].stage_evaluation.value_ct[2]         GOOD!! step count
             0x0056F5B8:  g_game_w.player[0].stage_evaluation.value_ct[3]         BOO!! step count
             0x0056F5BC:  g_game_w.player[0].stage_evaluation.value_ct[4]         Miss.. step count
             0x0056F5C0:  g_game_w.player[0].stage_evaluation.value_ct[5]
             0x0056F5C4:  g_game_w.player[0].stage_evaluation.value_ct[6]
             0x0056F5C8:  g_game_w.player[0].stage_evaluation.freez_value_ct[0]   O.K Count
             0x0056F5CC:  g_game_w.player[0].stage_evaluation.freez_value_ct[1]   N.Gs from hitting the freeze, then dropping it
             0x0056F5D0:  g_game_w.player[0].stage_evaluation.freez_value_ct[2]
             0x0056F5D4:  g_game_w.player[0].stage_evaluation.freez_value_ct[3]   Repeat of N.G count
             0x0056F5D8:  g_game_w.player[0].stage_evaluation.groov_bonus[0]
             0x0056F5DC:  g_game_w.player[0].stage_evaluation.groov_bonus[1]
             0x0056F5E0:  g_game_w.player[0].stage_evaluation.groov_bonus[2]
             0x0056F5E4:  g_game_w.player[0].stage_evaluation.groov_bonus[3]
             0x0056F5E8:  g_game_w.player[0].stage_evaluation.groov_bonus[4]
             0x0056F5EC:  g_game_w.player[0].stage_evaluation.groov_bonus[5]
             0x0056F5F0:  g_game_w.player[0].stage_evaluation.groov_bonus_max[0]
             0x0056F5F4:  g_game_w.player[0].stage_evaluation.groov_bonus_max[1]
             0x0056F5F8:  g_game_w.player[0].stage_evaluation.groov_bonus_max[2]
             0x0056F5FC:  g_game_w.player[0].stage_evaluation.groov_bonus_max[3]
             0x0056F600:  g_game_w.player[0].stage_evaluation.groov_bonus_max[4]
             0x0056F604:  g_game_w.player[0].stage_evaluation.groov_bonus_max[5]
             0x0056F608:  g_game_w.player[0].stage_evaluation.score
             0x0056F60C:  g_game_w.player[0].stage_evaluation.max_combo_ct
             0x0056F610:  g_game_w.player[0].stage_evaluation.jump_ct
             0x0056F614:  g_game_w.player[0].stage_evaluation.dance_level
             0x0056F616:  g_game_w.player[0].stage_evaluation.fixed_level
0x0056F618 - 0x0056F684:  g_game_w.player[0].total_evaluation                     also an eval_w struct
             0x0056F618:  g_game_w.player[0].total_evaluation.value_ct[0]
             0x0056F61C:  g_game_w.player[0].total_evaluation.value_ct[1]
             0x0056F620:  g_game_w.player[0].total_evaluation.value_ct[2]
             0x0056F624:  g_game_w.player[0].total_evaluation.value_ct[3]
             0x0056F628:  g_game_w.player[0].total_evaluation.value_ct[4]
             0x0056F62C:  g_game_w.player[0].total_evaluation.value_ct[5]
             0x0056F630:  g_game_w.player[0].total_evaluation.value_ct[6]
             0x0056F634:  g_game_w.player[0].total_evaluation.freez_value_ct[0]
             0x0056F638:  g_game_w.player[0].total_evaluation.freez_value_ct[1]
             0x0056F63C:  g_game_w.player[0].total_evaluation.freez_value_ct[2]
             0x0056F640:  g_game_w.player[0].total_evaluation.freez_value_ct[3]
             0x0056F644:  g_game_w.player[0].total_evaluation.groov_bonus[0]
             0x0056F648:  g_game_w.player[0].total_evaluation.groov_bonus[1]
             0x0056F64C:  g_game_w.player[0].total_evaluation.groov_bonus[2]
             0x0056F650:  g_game_w.player[0].total_evaluation.groov_bonus[3]
             0x0056F654:  g_game_w.player[0].total_evaluation.groov_bonus[4]
             0x0056F658:  g_game_w.player[0].total_evaluation.groov_bonus[5]
             0x0056F65C:  g_game_w.player[0].total_evaluation.groov_bonus_max[0]
             0x0056F660:  g_game_w.player[0].total_evaluation.groov_bonus_max[1]
             0x0056F664:  g_game_w.player[0].total_evaluation.groov_bonus_max[2]
             0x0056F668:  g_game_w.player[0].total_evaluation.groov_bonus_max[3]
             0x0056F66C:  g_game_w.player[0].total_evaluation.groov_bonus_max[4]
             0x0056F670:  g_game_w.player[0].total_evaluation.groov_bonus_max[5]
             0x0056F674:  g_game_w.player[0].total_evaluation.score
             0x0056F678:  g_game_w.player[0].total_evaluation.max_combo_ct
             0x0056F67C:  g_game_w.player[0].total_evaluation.jump_ct
             0x0056F680:  g_game_w.player[0].total_evaluation.dance_level
             0x0056F682:  g_game_w.player[0].total_evaluation.fixed_level
0x0056F684 - 0x0056F770:  g_game_w.player[0].play_work                            play_work is a play_w struct
             0x0056F684:  g_game_w.player[0].play_work.music_counter
             0x0056F688:  g_game_w.player[0].play_work.beat_counter
             0x0056F68C:  g_game_w.player[0].play_work.cur_p_counter
             0x0056F690:  g_game_w.player[0].play_work.last_p_counter
             0x0056F694:  g_game_w.player[0].play_work.begin_beat_count
             0x0056F698:  g_game_w.player[0].play_work.go_beat_count
             0x0056F69C:  g_game_w.player[0].play_work.finish_beat_count
             0x0056F6A0:  g_game_w.player[0].play_work.end_beat_count
             0x0056F6A4:  g_game_w.player[0].play_work.game_start_music_count
             0x0056F6A8:  g_game_w.player[0].play_work.game_finish_music_count
             0x0056F6AC:  g_game_w.player[0].play_work.back_trans_start_music_count
             0x0056F6B0:  g_game_w.player[0].play_work.last_fs_nct
             0x0056F6B4:  g_game_w.player[0].play_work.last_input_count[0]
             0x0056F6B6:  g_game_w.player[0].play_work.last_input_count[1]
             0x0056F6B8:  g_game_w.player[0].play_work.last_input_count[2]
             0x0056F6BA:  g_game_w.player[0].play_work.last_input_count[3]
             0x0056F6BC:  g_game_w.player[0].play_work.last_input_count[4]
             0x0056F6BE:  g_game_w.player[0].play_work.last_input_count[5]
             0x0056F6C0:  g_game_w.player[0].play_work.last_input_count[6]
             0x0056F6C4:  g_game_w.player[0].play_work.last_input_count[7]
0x0056F6C6 - 0x0056F726:  g_game_w.player[0].play_work.history                    history is an array of play_hist structs                   
             0x0056F6C6:  g_game_w.player[0].play_work.history[0].music_count                 
             0x0056F6C8:  g_game_w.player[0].play_work.history[0].input[0]     
             0x0056F6C9:  g_game_w.player[0].play_work.history[0].input[1]     
             0x0056F6CA:  g_game_w.player[0].play_work.history[0].input[2]     
             0x0056F6CB:  g_game_w.player[0].play_work.history[0].input[3]     
             0x0056F6CC:  g_game_w.player[0].play_work.history[0].input[4]     
             0x0056F6CD:  g_game_w.player[0].play_work.history[0].input[5]     
             0x0056F6CE:  g_game_w.player[0].play_work.history[0].input[6]     
             0x0056F6CF:  g_game_w.player[0].play_work.history[0].input[7]                   
             0x0056F6D0:  g_game_w.player[0].play_work.history[1].music_count                 
             0x0056F6D2:  g_game_w.player[0].play_work.history[1].input[0]     
             0x0056F6D3:  g_game_w.player[0].play_work.history[1].input[1]     
             0x0056F6D4:  g_game_w.player[0].play_work.history[1].input[2]     
             0x0056F6D5:  g_game_w.player[0].play_work.history[1].input[3]     
             0x0056F6D6:  g_game_w.player[0].play_work.history[1].input[4]     
             0x0056F6D7:  g_game_w.player[0].play_work.history[1].input[5]     
             0x0056F6D8:  g_game_w.player[0].play_work.history[1].input[6]     
             0x0056F6D9:  g_game_w.player[0].play_work.history[1].input[7]
             0x0056F6DA:  g_game_w.player[0].play_work.history[2].music_count                 
             0x0056F6EC:  g_game_w.player[0].play_work.history[2].input[0]     
             0x0056F6ED:  g_game_w.player[0].play_work.history[2].input[1]     
             0x0056F6EE:  g_game_w.player[0].play_work.history[2].input[2]     
             0x0056F6EF:  g_game_w.player[0].play_work.history[2].input[3]     
             0x0056F6F0:  g_game_w.player[0].play_work.history[2].input[4]     
             0x0056F6F1:  g_game_w.player[0].play_work.history[2].input[5]     
             0x0056F6F2:  g_game_w.player[0].play_work.history[2].input[6]     
             0x0056F6F3:  g_game_w.player[0].play_work.history[2].input[7]
             0x0056F6F4:  g_game_w.player[0].play_work.history[3].music_count    
             0x0056F6F6:  g_game_w.player[0].play_work.history[3].input[0]
             0x0056F6F7:  g_game_w.player[0].play_work.history[3].input[1]
             0x0056F6F8:  g_game_w.player[0].play_work.history[3].input[2]
             0x0056F6F9:  g_game_w.player[0].play_work.history[3].input[3]
             0x0056F6FA:  g_game_w.player[0].play_work.history[3].input[4]
             0x0056F6FB:  g_game_w.player[0].play_work.history[3].input[5]
             0x0056F6FC:  g_game_w.player[0].play_work.history[3].input[6] 
             0x0056F6FD:  g_game_w.player[0].play_work.history[3].input[7]
             0x0056F6FE:  g_game_w.player[0].play_work.history[4].music_count    
             0x0056F700:  g_game_w.player[0].play_work.history[4].input[0]
             0x0056F701:  g_game_w.player[0].play_work.history[4].input[1]
             0x0056F702:  g_game_w.player[0].play_work.history[4].input[2]
             0x0056F703:  g_game_w.player[0].play_work.history[4].input[3]
             0x0056F704:  g_game_w.player[0].play_work.history[4].input[4]
             0x0056F705:  g_game_w.player[0].play_work.history[4].input[5]
             0x0056F706:  g_game_w.player[0].play_work.history[4].input[6] 
             0x0056F707:  g_game_w.player[0].play_work.history[4].input[7]
             0x0056F708:  g_game_w.player[0].play_work.history[5].music_count    
             0x0056F70A:  g_game_w.player[0].play_work.history[5].input[0]
             0x0056F70B:  g_game_w.player[0].play_work.history[5].input[1]
             0x0056F70C:  g_game_w.player[0].play_work.history[5].input[2]
             0x0056F70D:  g_game_w.player[0].play_work.history[5].input[3]
             0x0056F70E:  g_game_w.player[0].play_work.history[5].input[4]
             0x0056F70F:  g_game_w.player[0].play_work.history[5].input[5]
             0x0056F710:  g_game_w.player[0].play_work.history[5].input[6] 
             0x0056F711:  g_game_w.player[0].play_work.history[5].input[7]
             0x0056F712:  g_game_w.player[0].play_work.history[6].music_count    
             0x0056F714:  g_game_w.player[0].play_work.history[6].input[0]
             0x0056F715:  g_game_w.player[0].play_work.history[6].input[1]
             0x0056F716:  g_game_w.player[0].play_work.history[6].input[2]
             0x0056F717:  g_game_w.player[0].play_work.history[6].input[3]
             0x0056F718:  g_game_w.player[0].play_work.history[6].input[4]
             0x0056F719:  g_game_w.player[0].play_work.history[6].input[5]
             0x0056F71A:  g_game_w.player[0].play_work.history[6].input[6] 
             0x0056F71B:  g_game_w.player[0].play_work.history[6].input[7]
             0x0056F71C:  g_game_w.player[0].play_work.history[7].music_count    
             0x0056F71E:  g_game_w.player[0].play_work.history[7].input[0]
             0x0056F71F:  g_game_w.player[0].play_work.history[7].input[1]
             0x0056F720:  g_game_w.player[0].play_work.history[7].input[2]
             0x0056F721:  g_game_w.player[0].play_work.history[7].input[3]
             0x0056F722:  g_game_w.player[0].play_work.history[7].input[4]
             0x0056F723:  g_game_w.player[0].play_work.history[7].input[5]
             0x0056F724:  g_game_w.player[0].play_work.history[7].input[6] 
             0x0056F725:  g_game_w.player[0].play_work.history[7].input[7]
             0x0056F726:  g_game_w.player[0].play_work.cur_his
             0x0056F72A:  g_game_w.player[0].play_work.pre_nct
             0x0056F72E:  g_game_w.player[0].play_work.cur_nct
             0x0056F732:  g_game_w.player[0].play_work.disp_nct
             0x0056F736:  g_game_w.player[0].play_work.cur_great_combo
             0x0056F73A:  g_game_w.player[0].play_work.cur_miss_combo
             0x0056F73E:  g_game_w.player[0].play_work.max_great_combo
             0x0056F742:  g_game_w.player[0].play_work.max_miss_combo
             0x0056F746:  g_game_w.player[0].play_work.miss_start_count
             0x0056F74A:  g_game_w.player[0].play_work.input
             0x0056F74B:  g_game_w.player[0].play_work.dead
             0x0056F74C:  g_game_w.player[0].play_work.strictness
             0x0056F74D:  g_game_w.player[0].play_work.panel_count[0]
             0x0056F74F:  g_game_w.player[0].play_work.panel_count[1]
             0x0056F751:  g_game_w.player[0].play_work.panel_count[2]
             0x0056F753:  g_game_w.player[0].play_work.panel_count[3]
             0x0056F755:  g_game_w.player[0].play_work.panel_count[4]
             0x0056F757:  g_game_w.player[0].play_work.panel_count[5]
             0x0056F759:  g_game_w.player[0].play_work.panel_count[6]
             0x0056F75B:  g_game_w.player[0].play_work.panel_count[7]
0x00653510 - 0x00653D4C:  Edit Mode Freeze Step Values
0x00653D50 - 0x0065455C:  Edit Mode Non-Freeze Step Values
             0x00654578:  Edit Mode Selection Starting Beat
             0x0065457C:  Edit Mode Selection Ending Beat
             0x00654594:  Edit Mode Step Count
             0x0065459C:  Edit Mode Current Beat For Editing
             0x00685FBC:  Training Mode Bar Start, Bar End, And Music Speed
</pre>

