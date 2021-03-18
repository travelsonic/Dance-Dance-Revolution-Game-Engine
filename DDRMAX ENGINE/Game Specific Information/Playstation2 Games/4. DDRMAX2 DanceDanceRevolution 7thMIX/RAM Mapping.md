Note: This document is far from complete.
<pre>
        RAM ADDRESS(ES):  DESCRIPTION:                              NOTES:
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
0x0056F4EC - 0x0057C906:  g_game_w.player[0]                            player is a 2-element array of g_each_w structs
             0x00589D20:  g_game_w.player[1]
0x0056F5AC - 0x0056F5C4:  Step Quality Counters:
             0x0056F5AC:  Player 1 Perfect Count
             0x0056F5B0:  Player 1 Great Count
             0x0056F5B4:  Player 1 Good Count
             0x0056F5B8:  Player 1 Boo Count
             0x0056F5BC:  Player 1 Miss Count
             0x0056F5C4:  Elapsed Step Count
             0x0056F5C8:  Player 1 0.K Count
             0x0056F5D4:  Player 1 O.K Count Repeated
             0x0056F5F0:  Player 1 Stream Level Bar Value
             0x0056F5F4:  Player 1 Voltage Level Bar Value
             0x0056F5F8:  Player 1 Air Level Bar Value
             0x0056F5FC:  Player 1 Chaos Level Bar Value
             0x0056F600:  Player 1 Freeze Level Bar Value
             0x0056F608:  Player 1 Displayed High Score
             0x0056F60C:  Player 1 Previous Max Combo
             0x005C3844:  Player 2 Perfect Count
             0x005C3848:  Player 2 Great Count
             0x005C384C:  Player 2 Good Count
             0x005C3850:  Player 2 Boo Count
             0x005C3854:  Player 2 Miss Count
0x00653510 - 0x00653D4C:  Edit Mode Freeze Step Values
0x00653D50 - 0x0065455C:  Edit Mode Non-Freeze Step Values
             0x00654578:  Edit Mode Selection Starting Beat
             0x0065457C:  Edit Mode Selection Ending Beat
             0x00654594:  Edit Mode Step Count
             0x0065459C:  Edit Mode Current Beat For Editing
             0x00685FBC:  Training Mode Bar Start, Bar End, And Music Speed
</pre>

