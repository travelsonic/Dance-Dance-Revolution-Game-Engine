## onimode.c

SCED-52169 - Dancing Stage Fusion - 2004-09-15 Prototype Build
<pre>
struct oni_course
{
	unsigned int course_allnum;
	unsigned int course_defnum;
	signed short avairable_level;
	signed short order;
	signed short start_life;
	signed short flag;
	unsigned int stage;
	signed int single_steps;
	signed int double_steps;
	oni_mode mode[20];
};

struct music_info
{
	char base_name[6];
	signed char kind;
	signed char album;
	signed short dance_num;
	signed short order;
	unsigned int main_track;
	unsigned int select_track;
	unsigned short bpm_max;
	unsigned short bpm_min;
	unsigned short verm_num;
	unsigned short pcseq_num;
	unsigned long hide;
	signed short adjust_mc;
	unsigned int difficulty[2];
	unsigned int special;
	unsigned short max_spm[9];
	unsigned short avg_spm[9];
	unsigned short avg_jpm[9];
	unsigned short chaos_v[9];
	unsigned short freez_v[9];
	char* title;
	char* l_name;
};

struct _tag_cMWMgRunRecord
{
	signed int time;
	unsigned char bcd_time;
	unsigned char bcd_type;
	unsigned char fps;
	char pad[1];
};

struct oni_cource_work
{
	signed int id;
	signed int init_ok;
	oni_course* course[31];
	signed int tex_kind;
	signed int tex_load_step;
	unsigned char seqkind_tab[20];
	signed int dancer_flag;
};

struct _tag_cDDR8Record1
{
	unsigned int Score[10];
	unsigned int Bonus[10];
	unsigned int nPlayed;
	unsigned short LinkNum;
	unsigned short Combo[10];
	unsigned short ComboMax[10];
	unsigned char Level[10];
	unsigned char pad[2];
};

struct _tag_cMWMgRun
{
	_tag_cMWMgRunRecord record;
	char pad[8];
};

struct tm
{
	signed int tm_sec;
	signed int tm_min;
	signed int tm_hour;
	signed int tm_mday;
	signed int tm_mon;
	signed int tm_year;
	signed int tm_wday;
	signed int tm_yday;
	signed int tm_isdst;
};

struct play_hist
{
	signed int music_count;
	unsigned char input[8];
};

struct G_INPUT_W_
{
	_InputData* dp;
	_InputBuffer buffer;
};

struct _InputData
{
	unsigned short player_input[4];
	unsigned short player_input_trigger[4];
	unsigned short player_input_released[4];
	unsigned short etc;
	unsigned short etc_trigger;
	unsigned short etc_released;
	unsigned short padding;
};

struct oni_mode
{
	unsigned int link_num;
	unsigned char seq_kind;
	unsigned char seq_transfer;
	unsigned char sp_music;
	unsigned char add_life;
	struct
	{
		unsigned int hidden : 2;
		unsigned int thinout : 1;
		unsigned int free : 1;
		unsigned int soft : 1;
		unsigned int boost : 2;
		unsigned int speed : 5;
		unsigned int scroll : 2;
		unsigned int freeze : 1;
		unsigned int vivid : 2;
		unsigned int anime : 2;
		unsigned int dark : 1;
		unsigned int pad : 12;
	};
};

struct _tag_cDDR8OniRecord1
{
	unsigned int Time[2];
	unsigned int Score[2];
	unsigned short Combo[2];
	unsigned char Stage[2];
	unsigned char Miss[2];
	unsigned char AllStage[2];
	unsigned char Level[2];
	unsigned char is_first_clear;
	unsigned char is_full_combo_flag[2];
	unsigned char pad[1];
	unsigned short ClearNum[2];
	unsigned char pad2[2];
};

struct G_SYS_W_
{
	G_INPUT_W_ input_w;
	tm start_tm;
	unsigned int v_counter;
	unsigned long v_counter2;
	unsigned int s_counter;
	signed int u_counter;
	signed int read_time;
	unsigned char read_flag;
	unsigned char entry_bit;
	char vpf;
	char pad[2];
};

struct play_mode
{
	unsigned char seq_kind;
	unsigned char seq_transfer;
	unsigned char style;
	unsigned char pccard_seq;
	unsigned char mcard_seq;
	unsigned char padding;
	signed short edseq_id;
	struct
	{
		unsigned int hidden : 3;
		unsigned int thinout : 1;
		unsigned int free : 1;
		unsigned int soft : 1;
		unsigned int boost : 2;
		unsigned int speed : 5;
		unsigned int scroll : 2;
		unsigned int freeze : 1;
		unsigned int vivid : 2;
		unsigned int anime : 2;
		unsigned int dark : 1;
	};
	unsigned int pad : 12;
};

struct _eyetoy_option
{
	char depth;
	char pdf;
	char frame;
	unsigned char bright;
};

struct _mg_block
{
	signed int hi_score;
};

struct eval_w
{
	signed int value_ct[8];
	signed int freez_value_ct[4];
	signed int groov_bonus[6];
	signed int groov_bonus_max[6];
	signed int score;
	signed int bonus;
	signed int max_combo_ct;
	signed int jump_ct;
	signed short dance_level;
	signed short fixed_level;
};

struct note_status
{
	unsigned char state[8];
	unsigned int length[8];
};

struct _mg_coco
{
	signed int hi_score;
};

struct _DDRCommonHeader
{
	unsigned char Type;
	unsigned char Platform;
	unsigned char Hardware;
	unsigned char Version;
	unsigned char Area;
	signed char tmp;
	unsigned short title;
	unsigned int t_info[2];
};

struct _anon0
{
	signed int hi_score;
};

struct _tag_cDDR8Option
{
	unsigned char Sound;
	unsigned char Voice;
	signed char Timing;
	char pad_sound[1];
	char EditKey[24];
	unsigned char KeyConfig[4];
	unsigned char DModeSet;
	unsigned char Vibration;
	unsigned char DPlay;
	char pad_cont[1];
	unsigned char AutoSave;
	unsigned char FolderLoad;
	char pad_mc[2];
	unsigned char Level;
	unsigned char MaxStage[3];
	unsigned char GameOver;
	unsigned char TimeLimit;
	unsigned char EventMode;
	unsigned char DefaultDifficulty;
	unsigned char SongDisp;
	unsigned char BgEffect;
	unsigned char BgBright;
	unsigned char DangerDisplay;
	unsigned char StepMarkColor;
	signed char screen_x;
	signed char screen_y;
	unsigned char FlickerFree;
	unsigned char DietMeasure;
	unsigned char DietDisplay;
	unsigned char DietTime;
	unsigned char DietPlayDefault;
	unsigned char DietWeightUnit;
	char pad_diet[3];
	unsigned char Language;
	char pad_lang[7];
	unsigned char DollDisp;
	unsigned char DollChara[3];
	unsigned char DollGuestNum;
	unsigned char DollSelect;
	char pad_doll[2];
};

struct _tag_cDDR8SaveData
{
	_DDRCommonHeader CommonHeader;
	_tag_cDDR8Option Option;
	_tag_cDDR8Record1 MRecord[60];
	unsigned char Information[256];
	unsigned int nMusic;
	unsigned int nBoot;
	unsigned int nPlayerType[3];
	unsigned int nDifficulty[5];
	signed int nwork[3];
	unsigned char LessonWork[32];
	_tag_cDDR8OniRecord1 OniRecord[12];
	_tag_cDDR8OniRecord1 NonstopRecord[24];
	popular popular;
	G_RANKING_W_ high_score[40];
	unsigned int HideFlag[2];
	unsigned int HideNewFlag[2];
	unsigned int HideDoll[2];
	unsigned int HideNewDoll[2];
	unsigned char HideDollWk[4];
	_EDSSAVE_W EdsRecords;
	_anon3 challenge;
	oni_course oni_order[3];
	oni_course nonstop_order[3];
	oni_course dietprogram_order[3];
	_anon5 diet_calorie_record[2];
	_tag_cMWMgRun mg_run;
	unsigned int nMusic_on_last_unlocked;
	_eyetoy_option eyetoy_option;
	_mg_block mg_block;
	_mg_coco mg_coco;
	_anon0 mg_eat;
	_tag_cDDR8Record1 mg_solo_MRecord[60];
	_anon4 wk_save[2];
};

struct _EDSS_DATA_W
{
	unsigned int score[2];
	signed int combo;
	signed int stage;
};

struct _EDSS_PLAY_W
{
	_EDSS_DATA_W p_single[3];
	_EDSS_DATA_W p_double[3];
};

struct play_w
{
	signed int music_counter;
	signed int beat_counter;
	signed int cur_p_counter;
	signed int last_p_counter;
	signed int begin_beat_count;
	signed int go_beat_count;
	signed int finish_beat_count;
	signed int end_beat_count;
	signed int game_start_music_count;
	signed int game_finish_music_count;
	signed int back_trans_start_music_count;
	signed int last_fs_nct;
	signed short last_input_count[8];
	play_hist history[8];
	signed int cur_his;
	signed int pre_nct;
	signed int cur_nct;
	signed int disp_nct;
	signed int cur_great_combo;
	signed int cur_miss_combo;
	signed int max_great_combo;
	signed int max_miss_combo;
	signed int miss_start_count;
	signed int cur_great_combo_total;
	signed int max_great_combo_total;
	unsigned short input;
	unsigned char dead;
	signed char strictness;
	signed short panel_count[8];
	signed short message_ct;
	signed short message_id;
	signed short meter_cur;
	signed short meter_vol;
	signed short meter_ct;
	signed short offset;
	signed short light_offset;
	signed short meter_state;
	signed short anm_no;
	signed short dance_class;
	signed int bar_start;
	signed int bar_end;
};

struct sequence
{
	signed int beat_count;
	signed short kind;
	signed short next_change;
	signed short music_count;
	signed short judge_count;
	signed short stolen_count;
	signed short op_note_ct;
	unsigned int hold_length[8];
	unsigned char hold_stat[8];
};

struct _EDSSAVE_W
{
	_EDSS_PLAY_W reg[2];
	unsigned int PlayFlag[128];
};

struct _anon1
{
	unsigned char state;
	unsigned char perfect;
	unsigned short play_count;
	unsigned short play_time;
	unsigned short clear_count;
	unsigned short first_clear_count;
	unsigned short first_clear_time;
};

struct _anon2
{
	unsigned char old_stat;
	unsigned char cur_stat;
	unsigned char release_ct;
	unsigned char warning;
};

struct _play_backup_w
{
	eval_w stage_evaluation;
	eval_w total_evaluation;
	play_mode mode;
	play_his his[7];
	unsigned int play_stage;
};

struct _anon3
{
	unsigned char appear;
	unsigned char ending_flag;
	signed char help_count;
	unsigned char pad;
	signed int bonus_count;
	signed int dummy[2];
	_anon1 subject[100];
};

struct _backup_w
{
	_play_backup_w player[2];
	signed char stage;
	signed char start_chip;
	signed char extra_chip;
	signed char use_chip;
	signed char lost_chip;
};

struct _anon4
{
	unsigned char game_over;
	unsigned char calorie_check;
	unsigned char pad[2];
};

struct play_his
{
	signed short music;
	signed short edit_id;
	unsigned char seq_kind;
	signed char roulette;
	signed char extra;
	signed char pad;
};

struct _anon5
{
	unsigned int program_calorie[6];
	unsigned int program_play_count[6];
	unsigned int song_calorie[5][60];
	unsigned int song_play_count[5][60];
};

struct _InputBuffer
{
	unsigned long current_buffer;
	_InputData data[2];
};

struct g_each_w
{
	unsigned int play_time;
	unsigned int game_time;
	unsigned int game_time_total;
	signed char select;
	signed char character;
	signed char costume;
	signed char motiontype;
	signed char loaded_model;
	signed char loaded_texture;
	signed char loaded_motion;
	unsigned char play_disp_flag;
	unsigned char model_disp_flag;
	unsigned char gauge_disp_flag;
	signed short cur_point;
	signed int cur_life;
	unsigned int score;
	unsigned int old_score;
	unsigned int real_score;
	unsigned int bonus;
	unsigned int old_bonus;
	unsigned int max_score;
	unsigned int old_max_score;
	unsigned int max_bonus;
	unsigned int old_max_bonus;
	unsigned int cal;
	unsigned int old_cal;
	unsigned int real_cal;
	unsigned int disp_cal;
	unsigned int average_cal;
	signed int diet_norm_cal;
	signed int diet_norm_minute;
	signed int old_norm_cal;
	signed int old_norm_minute;
	signed int minimum_cal;
	unsigned char add_cal_flg;
	unsigned char chk_cal_flg;
	unsigned char combo_no_disp_flag;
	unsigned char pad;
	unsigned int play_stage;
	unsigned int decode_key1;
	unsigned int decode_key2;
	unsigned int decode_key3;
	signed int used_unfair_command;
	signed int nonstop_dead_flag;
	play_mode mode;
	play_his his[7];
	eval_w stage_evaluation;
	eval_w total_evaluation;
	play_w play_work;
	signed int total_notes;
	signed int total_jump;
	signed int total_freez;
	signed int category;
	signed int total_category;
	sequence sequence_buff[6144];
	signed int total_notes_all;
	signed int total_freez_all;
};

struct popular
{
	signed short cur_c;
	signed short last_c;
	unsigned short count[4][256];
};

struct g_game_w
{
	signed short state;
	signed short genre;
	music_info* mip;
	signed char start_chip;
	signed char extra_chip;
	signed char use_chip;
	signed char lost_chip;
	signed short stage;
	signed short next_stage;
	signed short failed;
	signed short level;
	signed char game_kind;
	signed char world;
	signed char oni_nonstop_course_id;
	signed char event_mode;
	signed char event_two_flag;
	signed char style;
	signed char music_group;
	signed char music_select_mode;
	signed char extra_stage;
	signed char extra_fix;
	signed char final_fix;
	signed char meter_kind;
	signed char roulette_stage;
	signed char edit_total;
	signed char roulette_total;
	signed short music;
	signed char oni_nonstop_mode;
	unsigned char oni_load_step;
	signed char oni_nonstop_difficulty;
	signed char use_oni_gauge;
	signed char beginner_mode;
	signed char beginner_selected;
	signed char freez_selected;
	signed char judge_invalid;
	signed short oni_next_music;
	music_info* oni_next_mip;
	g_each_w player[2];
	signed char music_table[5];
	note_status note_status_table[300];
	_anon2 hc_work[8];
	signed int demoloop_ct;
	signed int mode_quit_ct[2];
	signed int force_exit_ct[2];
	signed int diet_play_time;
	signed int old_play_time;
	signed int menu_num;
	signed int total_stage;
	signed int now_bpm;
	unsigned char* last_data_addr;
	unsigned char edit_name[12];
	unsigned char diet_flg;
	unsigned char workout_step_flg;
	unsigned char auto_play_flg;
	unsigned char caution_flg;
	unsigned char mode_quit_flg;
	unsigned char lib_loaded;
	unsigned char force_exit_flg;
	unsigned char train_state;
	unsigned char lesson_flag;
	unsigned char lesson_auto_play_flag;
	unsigned char lesson_pad[2];
	unsigned char oni_load_start0;
	unsigned char oni_load_start1;
	unsigned char oni_load_end0;
	unsigned char oni_load_end1;
	unsigned char oni_order_step;
	unsigned char oni_order_stage;
	unsigned char oni_order_cursor;
	unsigned char oni_order_top_stage;
	unsigned char oni_order_selopt;
	unsigned char anime1_load_flg;
	unsigned char anime2_load_flg;
	unsigned char temp_sqk[2];
	unsigned char endless_flag;
	unsigned char eyetoy_flag;
	unsigned char challenge_flag;
	unsigned char step_mark_color;
	unsigned char hand_solo_seq_kind;
	unsigned char hand_solo_pad[2];
	unsigned char is_new_clothes;
	unsigned char quick_start;
	unsigned char nononi_msel_flag;
	unsigned char select_randaom_flag;
	unsigned char bar_state;
	signed int rloadtex_step;
	signed int rloadtex_num;
	signed int rloadtex_lang;
	signed int rload_next_step;
	_backup_w backup;
	char quit_course_flag;
	char nonstop_selopt_flag;
	unsigned char dancer_id[3];
	signed int dance_counter;
	signed int event_result_exit_flag;
	signed int party_mode_flag;
};

struct G_RANKING_W_
{
	char name[4];
	unsigned long score;
};
</pre>
SLES-04097 - Dancing Stage Fever - 2003-07-24 Retail Build
<pre>
struct oni_steps
{
	unsigned int link_num;
	unsigned short steps[4][2];
};

struct music_info
{
	char base_name[6];
	signed char kind;
	signed char album;
	signed short dance_num;
	signed short order;
	unsigned short main_track;
	unsigned short select_track;
	unsigned short bpm_max;
	unsigned short bpm_min;
	unsigned short verm_num;
	unsigned short pcseq_num;
	unsigned long hide;
	signed short adjust_mc;
	unsigned int difficulty[2];
	unsigned int special;
	unsigned short max_spm[9];
	unsigned short avg_spm[9];
	unsigned short avg_jpm[9];
	unsigned short chaos_v[9];
	unsigned short freez_v[9];
	char* title;
	char* l_name;
};

struct tm
{
	signed int tm_sec;
	signed int tm_min;
	signed int tm_hour;
	signed int tm_mday;
	signed int tm_mon;
	signed int tm_year;
	signed int tm_wday;
	signed int tm_yday;
	signed int tm_isdst;
};

struct oni_course
{
	unsigned int course_allnum;
	unsigned int course_defnum;
	signed short flag;
	signed short order;
	signed short start_life;
	signed short stage;
	signed int single_steps;
	signed int double_steps;
	signed int hide;
	signed int option;
	oni_mode mode[20];
};

struct note_status
{
	unsigned char state[8];
	unsigned int length[8];
};

struct machine_point_work
{
	unsigned int hide_show;
	unsigned int status;
	unsigned int period_time;
	signed int cur_point;
};

struct oni_mode
{
	unsigned int link_num;
	unsigned char seq_kind;
	unsigned char seq_transfer;
	unsigned char sp_music;
	unsigned char add_life;
	struct
	{
		unsigned int hidden : 2;
		unsigned int thinout : 1;
		unsigned int free : 1;
		unsigned int soft : 1;
		unsigned int boost : 2;
		unsigned int speed : 5;
		unsigned int scroll : 2;
		unsigned int freeze : 1;
		unsigned int vivid : 2;
		unsigned int anime : 2;
		unsigned int dark : 1;
		unsigned int pad : 12;
	};
};

struct _tag_cDDR7OniRecord1
{
	unsigned short Time[4];
	unsigned int Score[4];
	unsigned short Combo[4];
	unsigned char Stage[4];
	unsigned char Miss[4];
	unsigned char Clear[4];
	unsigned char Level[4];
	unsigned char pad[8];
};

struct sequence
{
	signed int beat_count;
	signed short kind;
	signed short next_change;
	signed short music_count;
	signed short judge_count;
	signed short stolen_count;
	signed short op_note_ct;
	unsigned int hold_length[8];
	unsigned char hold_stat[8];
};

struct _tag_cDDR7Option
{
	unsigned char Sound;
	unsigned char Voice;
	signed char Timing;
	char pad_sound[1];
	unsigned char KeyConfig[4];
	unsigned char Vibration;
	unsigned char DPlay;
	char pad_cont[2];
	unsigned char AutoSave;
	unsigned char FolderLoad;
	char pad_mc[2];
	unsigned char Level;
	unsigned char MaxStage[3];
	unsigned char GameOver;
	unsigned char TimeLimit;
	unsigned char EventMode;
	unsigned char DefaultDifficulty;
	char pad_game[8];
	unsigned char BgEffect;
	unsigned char BgBright;
	unsigned char DangerDisplay;
	unsigned char StepMarkColor;
	signed char screen_x;
	signed char screen_y;
	unsigned char FlickerFree;
	unsigned char SongDisplay;
	unsigned char DietMeasure;
	unsigned char DietDisplay;
	unsigned char DietTime;
	unsigned char DietPlayDefault;
	unsigned char DietWeightUnit;
	char pad_diet[3];
	unsigned char Language;
	char pad_lang[7];
	unsigned char DollDisp;
	unsigned char DollGuestNum;
	unsigned char DollChara[3];
	unsigned char bk_red;
	unsigned char bk_green;
	unsigned char bk_blue;
};

struct play_hist
{
	signed int music_count;
	unsigned char input[8];
};

struct eval_w
{
	signed int value_ct[7];
	signed int freez_value_ct[4];
	signed int groov_bonus[6];
	signed int groov_bonus_max[6];
	signed int score;
	signed int max_combo_ct;
	signed int jump_ct;
	signed short dance_level;
	signed short fixed_level;
};

struct _EDSS_DATA_W
{
	unsigned int score[2];
	signed int combo;
	signed int stage;
};

struct popular
{
	signed short cur_c;
	signed short last_c;
	unsigned short count[4][150];
};

struct G_INPUT_W_
{
	_InputData* dp;
	_InputBuffer buffer;
};

struct _InputData
{
	unsigned short player_input[4];
	unsigned short player_input_trigger[4];
	unsigned short player_input_released[4];
	unsigned short etc;
	unsigned short etc_trigger;
	unsigned short etc_released;
	unsigned short padding;
};

struct _EDSS_PLAY_W
{
	_EDSS_DATA_W p_single[3];
	_EDSS_DATA_W p_double[3];
};

struct G_RANKING_W_
{
	char name[4];
	unsigned long score;
};

struct _anon0
{
	unsigned char old_stat;
	unsigned char cur_stat;
	unsigned char release_ct;
	unsigned char warning;
};

struct G_SYS_W_
{
	G_INPUT_W_ input_w;
	tm start_tm;
	unsigned int v_counter;
	unsigned long v_counter2;
	unsigned int s_counter;
	signed int u_counter;
	unsigned char entry_bit;
	char vpf;
	char pad[2];
};

struct play_mode
{
	unsigned char seq_kind;
	unsigned char seq_transfer;
	unsigned char style;
	unsigned char pccard_seq;
	unsigned char mcard_seq;
	unsigned char padding;
	signed short edseq_id;
	struct
	{
		unsigned int hidden : 2;
		unsigned int thinout : 1;
		unsigned int free : 1;
		unsigned int soft : 1;
		unsigned int boost : 2;
		unsigned int speed : 5;
		unsigned int scroll : 2;
		unsigned int freeze : 1;
		unsigned int vivid : 2;
		unsigned int anime : 2;
		unsigned int dark : 1;
		unsigned int pad : 12;
	};
};

struct _EDSSAVE_W
{
	_EDSS_PLAY_W reg[2];
	_EDSS_DATA_W max_point;
	unsigned int PlayFlag[90];
};

struct g_game_w
{
	signed short state;
	signed short genre;
	music_info* mip;
	signed char start_chip;
	signed char extra_chip;
	signed char use_chip;
	signed char lost_chip;
	signed short stage;
	signed short next_stage;
	signed short failed;
	signed short level;
	signed char game_kind;
	signed char world;
	signed char nonstop;
	signed char event_mode;
	signed char style;
	signed char music_group;
	signed char music_select_mode;
	signed char extra_stage;
	signed char extra_fix;
	signed char final_fix;
	signed char meter_kind;
	signed char roulette_stage;
	signed char edit_total;
	signed char roulette_total;
	signed short music;
	signed char oni_mode;
	unsigned char oni_load_step;
	signed short oni_next_music;
	signed char oni_nonstop_difficulty;
	signed char oni_nonstop_option_selected;
	signed char oni_pad[2];
	signed char beginner_mode;
	signed char beginner_selected;
	signed char freez_selected;
	signed char beginner_pad[1];
	music_info* oni_next_mip;
	g_each_w player[2];
	signed char music_table[128];
	note_status note_status_table[300];
	_anon0 hc_work[8];
	signed int demoloop_ct;
	signed int mode_quit_ct[2];
	signed int force_exit_ct[2];
	signed int diet_play_time;
	signed int old_play_time;
	signed int menu_num;
	signed int total_stage;
	signed int now_bpm;
	unsigned char* last_data_addr;
	unsigned char* anime_data_addr;
	unsigned char* anime_buff_addr;
	unsigned char anime_load_flg;
	unsigned char anime1_load_flg;
	unsigned char anime2_load_flg;
	unsigned char edit_name[12];
	unsigned char diet_flg;
	unsigned char auto_play_flg;
	unsigned char caution_flg;
	unsigned char mode_quit_flg;
	unsigned char lib_loaded;
	unsigned char force_exit_flg;
	unsigned char music_stop_flg;
	unsigned char train_state;
	unsigned char lesson_flag;
	unsigned char lesson_auto_play_flag;
	unsigned char lesson_pad[2];
	unsigned char oni_load_start0;
	unsigned char oni_load_start1;
	unsigned char oni_load_end0;
	unsigned char oni_load_end1;
	unsigned char oni_order_step;
	unsigned char oni_order_stage;
	unsigned char oni_order_cursor;
	unsigned char oni_order_top_stage;
	unsigned char temp_sqk[2];
	unsigned char disp_seltu_flag;
	unsigned char temp_pad[1];
	unsigned char endless_flag;
	unsigned char endless_pad[3];
};

struct _anon1
{
	unsigned int program_calorie[9];
	unsigned int program_play_count[9];
	unsigned int song_calorie[4][80];
	unsigned int song_play_count[4][80];
};

struct play_w
{
	signed int music_counter;
	signed int beat_counter;
	signed int cur_p_counter;
	signed int last_p_counter;
	signed int begin_beat_count;
	signed int go_beat_count;
	signed int finish_beat_count;
	signed int end_beat_count;
	signed int game_start_music_count;
	signed int game_finish_music_count;
	signed int back_trans_start_music_count;
	signed int last_fs_nct;
	signed short last_input_count[8];
	play_hist history[8];
	signed int cur_his;
	signed int pre_nct;
	signed int cur_nct;
	signed int disp_nct;
	signed int cur_great_combo;
	signed int cur_miss_combo;
	signed int max_great_combo;
	signed int max_miss_combo;
	signed int miss_start_count;
	unsigned short input;
	unsigned char dead;
	signed char strictness;
	signed short panel_count[8];
	signed short message_ct;
	signed short message_id;
	signed short meter_cur;
	signed short meter_vol;
	signed short meter_ct;
	signed short dance_class;
	signed int bar_start;
	signed int bar_end;
};

struct oni_cource_work
{
	signed int id;
	signed int init_ok;
	oni_course* course[32];
	unsigned char seqkind_tab[20];
};

struct _tag_cDDR7SaveData
{
	_DDRCommonHeader CommonHeader;
	_tag_cDDR7Option Option;
	_tag_cDDR7Record1 MRecord[80];
	unsigned char Information[128];
	unsigned int nMusic;
	unsigned int nBoot;
	unsigned int nPlayerType[3];
	unsigned int nDifficulty[4];
	signed int nwork[3];
	unsigned char LessonWork[32];
	_tag_cDDR7OniRecord1 OniRecord[16];
	unsigned int HideMusic[2];
	popular popular;
	G_RANKING_W_ high_score[30];
	machine_point_work machine_p;
	unsigned int HideFlag;
	unsigned int HideFlagMM;
	unsigned int nHidePointMM;
	unsigned int HideDoll[2];
	_EDSSAVE_W EdsRecords;
	oni_course oni_order[3];
	oni_course dietprogram_order[3];
	_anon1 diet_calorie_record[2];
};

struct play_his
{
	signed short music;
	signed short edit_id;
	unsigned char seq_kind;
	signed char roulette;
	signed char extra;
	signed char pad;
};

struct _InputBuffer
{
	unsigned long current_buffer;
	_InputData data[2];
};

struct g_each_w
{
	unsigned int play_time;
	unsigned int game_time;
	unsigned int game_time_total;
	signed char select;
	signed char character;
	signed char costume;
	signed char motiontype;
	signed char loaded_model;
	signed char loaded_texture;
	signed char loaded_motion;
	unsigned char play_disp_flag;
	unsigned char model_disp_flag;
	unsigned char gauge_disp_flag;
	signed short cur_point;
	signed int cur_life;
	unsigned int score;
	unsigned int old_score;
	unsigned int real_score;
	unsigned int bonus;
	unsigned int old_bonus;
	unsigned int max_score;
	unsigned int old_max_score;
	unsigned int max_bonus;
	unsigned int old_max_bonus;
	unsigned int cal;
	unsigned int old_cal;
	unsigned int real_cal;
	unsigned int disp_cal;
	unsigned int average_cal;
	signed int diet_norm_cal;
	signed int diet_norm_minute;
	signed int old_norm_cal;
	signed int old_norm_minute;
	signed int minimum_cal;
	unsigned char add_cal_flg;
	unsigned char chk_cal_flg;
	unsigned char pad[2];
	unsigned int play_stage;
	unsigned int decode_key1;
	unsigned int decode_key2;
	unsigned int decode_key3;
	play_mode mode;
	play_his his[7];
	eval_w stage_evaluation;
	eval_w total_evaluation;
	play_w play_work;
	signed int total_notes;
	signed int total_jump;
	signed int total_freez;
	signed int category;
	signed int total_category;
	sequence sequence_buff[6144];
};

struct _DDRCommonHeader
{
	unsigned char Type;
	unsigned char Platform;
	unsigned char Hardware;
	unsigned char Version;
	unsigned char Area;
	signed char tmp;
	unsigned short title;
	unsigned int t_info[2];
};

struct _tag_cDDR7Record1
{
	unsigned int Score[8];
	unsigned int Bonus[8];
	unsigned int nPlayed;
	unsigned short LinkNum;
	unsigned short Combo[8];
	unsigned short ComboMax[8];
	unsigned char Level[8];
	unsigned char little_flag;
	char pad[1];
};
</pre>
SLES-51510 - Dancing Stage Megamix - 2003-03-12 Retail Build
<pre>
struct oni_course
{
	unsigned int course_allnum;
	unsigned int course_defnum;
	signed short avairable_level;
	signed short order;
	signed short start_life;
	signed short stage;
	signed int single_steps;
	signed int double_steps;
	oni_mode mode[5];
};

struct G_SYS_W_
{
	G_INPUT_W_ input_w;
	tm start_tm;
	unsigned int v_counter;
	unsigned long v_counter2;
	unsigned int s_counter;
	signed int u_counter;
	unsigned char entry_bit;
	char vpf;
	char pad[2];
};

struct _tag_cDDR7SaveData
{
	_DDRCommonHeader CommonHeader;
	_tag_cDDR7Option Option;
	_tag_cDDR7Record1 MRecord[80];
	unsigned char Information[128];
	unsigned int nMusic;
	unsigned int nBoot;
	unsigned int nPlayerType[3];
	unsigned int nDifficulty[4];
	signed int nwork[3];
	unsigned char LessonWork[32];
	_tag_cDDR7OniRecord1 OniRecord[16];
	unsigned int HideMusic[2];
	popular popular;
	G_RANKING_W_ high_score[30];
	machine_point_work machine_p;
	unsigned int HideFlag;
	unsigned int HideFlagMM;
	unsigned int nHidePointMM;
	_EDSSAVE_W EdsRecords;
	oni_course oni_order[3];
};

struct music_info
{
	char base_name[6];
	signed char kind;
	signed char album;
	signed short dance_num;
	signed short order;
	unsigned short main_track;
	unsigned short select_track;
	unsigned short bpm_max;
	unsigned short bpm_min;
	unsigned short verm_num;
	unsigned short pcseq_num;
	unsigned long hide;
	signed short adjust_mc;
	unsigned int difficulty[2];
	unsigned int special;
	unsigned short max_spm[9];
	unsigned short avg_spm[9];
	unsigned short avg_jpm[9];
	unsigned short chaos_v[9];
	unsigned short freez_v[9];
	char* title;
	char* l_name;
};

struct tm
{
	signed int tm_sec;
	signed int tm_min;
	signed int tm_hour;
	signed int tm_mday;
	signed int tm_mon;
	signed int tm_year;
	signed int tm_wday;
	signed int tm_yday;
	signed int tm_isdst;
};

struct oni_cource_work
{
	signed int id;
	signed int init_ok;
	oni_course* course[32];
};

struct play_his
{
	signed short music;
	signed short edit_id;
	unsigned char seq_kind;
	signed char roulette;
	signed char extra;
	signed char pad;
};

struct oni_steps
{
	unsigned int link_num;
	unsigned short steps[4][2];
};

struct oni_mode
{
	unsigned int link_num;
	unsigned char seq_kind;
	unsigned char seq_transfer;
	unsigned char sp_music;
	unsigned char add_life;
	struct
	{
		unsigned int hidden : 2;
		unsigned int thinout : 1;
		unsigned int free : 1;
		unsigned int soft : 1;
		unsigned int boost : 2;
		unsigned int speed : 5;
		unsigned int scroll : 2;
		unsigned int freeze : 1;
		unsigned int vivid : 2;
		unsigned int anime : 2;
		unsigned int dark : 1;
		unsigned int pad : 12;
	};
};

struct g_each_w
{
	unsigned int play_time;
	unsigned int game_time;
	unsigned int game_time_total;
	signed char select;
	signed char character;
	signed char costume;
	signed char motiontype;
	signed char loaded_model;
	signed char loaded_texture;
	signed char loaded_motion;
	unsigned char play_disp_flag;
	unsigned char model_disp_flag;
	unsigned char gauge_disp_flag;
	signed short cur_point;
	signed int cur_life;
	unsigned int score;
	unsigned int old_score;
	unsigned int real_score;
	unsigned int bonus;
	unsigned int old_bonus;
	unsigned int max_score;
	unsigned int old_max_score;
	unsigned int max_bonus;
	unsigned int old_max_bonus;
	unsigned int cal;
	unsigned int old_cal;
	unsigned int real_cal;
	unsigned int disp_cal;
	unsigned int average_cal;
	signed int diet_norm_cal;
	signed int diet_norm_minute;
	signed int old_norm_cal;
	signed int old_norm_minute;
	signed int minimum_cal;
	unsigned char add_cal_flg;
	unsigned char chk_cal_flg;
	unsigned char pad[2];
	unsigned int play_stage;
	unsigned int decode_key1;
	unsigned int decode_key2;
	unsigned int decode_key3;
	play_mode mode;
	play_his his[7];
	eval_w stage_evaluation;
	eval_w total_evaluation;
	play_w play_work;
	signed int total_notes;
	signed int total_jump;
	signed int total_freez;
	signed int category;
	signed int total_category;
	sequence sequence_buff[6144];
};

struct _tag_cDDR7OniRecord1
{
	unsigned short Time[2];
	unsigned int Score[2];
	unsigned short Combo[2];
	unsigned char Stage[2];
	unsigned char Miss[2];
	unsigned char AllStage[2];
	unsigned char Level[2];
	unsigned char pad[8];
};

struct play_w
{
	signed int music_counter;
	signed int beat_counter;
	signed int cur_p_counter;
	signed int last_p_counter;
	signed int begin_beat_count;
	signed int go_beat_count;
	signed int finish_beat_count;
	signed int end_beat_count;
	signed int game_start_music_count;
	signed int game_finish_music_count;
	signed int back_trans_start_music_count;
	signed int last_fs_nct;
	signed short last_input_count[8];
	play_hist history[8];
	signed int cur_his;
	signed int pre_nct;
	signed int cur_nct;
	signed int disp_nct;
	signed int cur_great_combo;
	signed int cur_miss_combo;
	signed int max_great_combo;
	signed int max_miss_combo;
	signed int miss_start_count;
	unsigned short input;
	unsigned char dead;
	signed char strictness;
	signed short panel_count[8];
	signed short message_ct;
	signed short message_id;
	signed short meter_cur;
	signed short meter_vol;
	signed short meter_ct;
	signed short dance_class;
	signed int bar_start;
	signed int bar_end;
};

struct _InputData
{
	unsigned short player_input[4];
	unsigned short player_input_trigger[4];
	unsigned short player_input_released[4];
	unsigned short etc;
	unsigned short etc_trigger;
	unsigned short etc_released;
	unsigned short padding;
};

struct _InputBuffer
{
	unsigned long current_buffer;
	_InputData data[2];
};

struct _DDRCommonHeader
{
	unsigned char Type;
	unsigned char Platform;
	unsigned char Hardware;
	unsigned char Version;
	unsigned char Area;
	signed char tmp;
	unsigned short title;
	unsigned int t_info[2];
};

struct play_mode
{
	unsigned char seq_kind;
	unsigned char seq_transfer;
	unsigned char style;
	unsigned char pccard_seq;
	unsigned char mcard_seq;
	unsigned char padding;
	signed short edseq_id;
	struct
	{
		unsigned int hidden : 2;
		unsigned int thinout : 1;
		unsigned int free : 1;
		unsigned int soft : 1;
		unsigned int boost : 2;
		unsigned int speed : 5;
		unsigned int scroll : 2;
		unsigned int freeze : 1;
		unsigned int vivid : 2;
		unsigned int anime : 2;
		unsigned int dark : 1;
		unsigned int pad : 12;
	};
};

struct _tag_cDDR7Record1
{
	unsigned int Score[8];
	unsigned int Bonus[8];
	unsigned int nPlayed;
	unsigned short LinkNum;
	unsigned short Combo[8];
	unsigned short ComboMax[8];
	unsigned char Level[8];
	unsigned char little_flag;
	char pad[1];
};

struct machine_point_work
{
	unsigned int hide_show;
	unsigned int status;
	unsigned int period_time;
	signed int cur_point;
};

struct note_status
{
	unsigned char state[8];
	unsigned int length[8];
};

struct eval_w
{
	signed int value_ct[7];
	signed int freez_value_ct[4];
	signed int groov_bonus[6];
	signed int groov_bonus_max[6];
	signed int score;
	signed int max_combo_ct;
	signed int jump_ct;
	signed short dance_level;
	signed short fixed_level;
};

struct _EDSS_DATA_W
{
	unsigned int score[2];
	signed int combo;
	signed int stage;
};

struct _anon0
{
	unsigned char old_stat;
	unsigned char cur_stat;
	unsigned char release_ct;
	unsigned char warning;
};

struct sequence
{
	signed int beat_count;
	signed short kind;
	signed short next_change;
	signed short music_count;
	signed short judge_count;
	signed short stolen_count;
	signed short op_note_ct;
	unsigned int hold_length[8];
	unsigned char hold_stat[8];
};

struct popular
{
	signed short cur_c;
	signed short last_c;
	unsigned short count[4][150];
};

struct play_hist
{
	signed int music_count;
	unsigned char input[8];
};

struct _EDSS_PLAY_W
{
	_EDSS_DATA_W p_single[3];
	_EDSS_DATA_W p_double[3];
};

struct g_game_w
{
	signed short state;
	signed short genre;
	music_info* mip;
	signed char start_chip;
	signed char extra_chip;
	signed char use_chip;
	signed char lost_chip;
	signed short stage;
	signed short next_stage;
	signed short failed;
	signed short level;
	signed char game_kind;
	signed char world;
	signed char nonstop;
	signed char event_mode;
	signed char style;
	signed char music_group;
	signed char music_select_mode;
	signed char extra_stage;
	signed char extra_fix;
	signed char final_fix;
	signed char meter_kind;
	signed char roulette_stage;
	signed char edit_total;
	signed char roulette_total;
	signed short music;
	signed char oni_mode;
	unsigned char oni_load_step;
	signed short oni_next_music;
	signed char beginner_mode;
	signed char beginner_selected;
	signed char freez_selected;
	signed char beginner_pad[1];
	music_info* oni_next_mip;
	g_each_w player[2];
	signed char music_table[128];
	note_status note_status_table[300];
	_anon0 hc_work[8];
	signed int demoloop_ct;
	signed int mode_quit_ct[2];
	signed int force_exit_ct[2];
	signed int diet_play_time;
	signed int old_play_time;
	signed int menu_num;
	signed int total_stage;
	signed int now_bpm;
	unsigned char* last_data_addr;
	unsigned char* anime_data_addr;
	unsigned char* anime_buff_addr;
	unsigned char anime_load_flg;
	unsigned char anime1_load_flg;
	unsigned char anime2_load_flg;
	unsigned char edit_name[12];
	unsigned char diet_flg;
	unsigned char auto_play_flg;
	unsigned char caution_flg;
	unsigned char mode_quit_flg;
	unsigned char lib_loaded;
	unsigned char force_exit_flg;
	unsigned char music_stop_flg;
	unsigned char train_state;
	unsigned char lesson_flag;
	unsigned char lesson_auto_play_flag;
	unsigned char lesson_pad[2];
	unsigned char oni_load_start0;
	unsigned char oni_load_start1;
	unsigned char oni_load_end0;
	unsigned char oni_load_end1;
	unsigned char oni_order_step;
	unsigned char oni_order_stage;
	unsigned char oni_order_cursor;
	unsigned char oni_order_top_stage;
	unsigned char temp_sqk[2];
	unsigned char disp_seltu_flag;
	unsigned char temp_pad[1];
	unsigned char endless_flag;
	unsigned char endless_pad[3];
};

struct G_RANKING_W_
{
	char name[4];
	unsigned long score;
};

struct _EDSSAVE_W
{
	_EDSS_PLAY_W reg[2];
	_EDSS_DATA_W max_point;
	unsigned int PlayFlag[90];
};

struct _tag_cDDR7Option
{
	unsigned char Sound;
	unsigned char Voice;
	signed char Timing;
	char pad_sound[1];
	unsigned char KeyConfig[4];
	unsigned char Vibration;
	unsigned char DPlay;
	char pad_cont[2];
	unsigned char AutoSave;
	unsigned char FolderLoad;
	char pad_mc[2];
	unsigned char Level;
	unsigned char MaxStage[3];
	unsigned char GameOver;
	unsigned char TimeLimit;
	unsigned char EventMode;
	unsigned char DefaultDifficulty;
	char pad_game[8];
	unsigned char BgEffect;
	unsigned char BgBright;
	unsigned char DangerDisplay;
	unsigned char StepMarkColor;
	signed char screen_x;
	signed char screen_y;
	unsigned char FlickerFree;
	unsigned char SongDisplay;
	unsigned char DietMeasure;
	unsigned char DietDisplay;
	unsigned char DietTime;
	unsigned char DietPlayDefault;
	unsigned char DietWeightUnit;
	char pad_diet[3];
	unsigned char Language;
	char pad[15];
};

struct G_INPUT_W_
{
	_InputData* dp;
	_InputBuffer buffer;
};
</pre>
SLES-52598 - Dancing Stage Fusion - 2004-07-08 Prototype Build
<pre>
struct _EDSS_PLAY_W
{
	_EDSS_DATA_W p_single[3];
	_EDSS_DATA_W p_double[3];
};

struct oni_course
{
	unsigned int course_allnum;
	unsigned int course_defnum;
	signed short avairable_level;
	signed short order;
	signed short start_life;
	signed short flag;
	unsigned int stage;
	signed int single_steps;
	signed int double_steps;
	oni_mode mode[20];
};

struct play_w
{
	signed int music_counter;
	signed int beat_counter;
	signed int cur_p_counter;
	signed int last_p_counter;
	signed int begin_beat_count;
	signed int go_beat_count;
	signed int finish_beat_count;
	signed int end_beat_count;
	signed int game_start_music_count;
	signed int game_finish_music_count;
	signed int back_trans_start_music_count;
	signed int last_fs_nct;
	signed short last_input_count[8];
	play_hist history[8];
	signed int cur_his;
	signed int pre_nct;
	signed int cur_nct;
	signed int disp_nct;
	signed int cur_great_combo;
	signed int cur_miss_combo;
	signed int max_great_combo;
	signed int max_miss_combo;
	signed int miss_start_count;
	signed int cur_great_combo_total;
	signed int max_great_combo_total;
	unsigned short input;
	unsigned char dead;
	signed char strictness;
	signed short panel_count[8];
	signed short message_ct;
	signed short message_id;
	signed short meter_cur;
	signed short meter_vol;
	signed short meter_ct;
	signed short offset;
	signed short light_offset;
	signed short meter_state;
	signed short anm_no;
	signed short dance_class;
	signed int bar_start;
	signed int bar_end;
};

struct _EDSSAVE_W
{
	_EDSS_PLAY_W reg[2];
	unsigned int PlayFlag[128];
};

struct music_info
{
	char base_name[6];
	signed char kind;
	signed char album;
	signed short dance_num;
	signed short order;
	unsigned int main_track;
	unsigned int select_track;
	unsigned short bpm_max;
	unsigned short bpm_min;
	unsigned short verm_num;
	unsigned short pcseq_num;
	unsigned long hide;
	signed short adjust_mc;
	unsigned int difficulty[2];
	unsigned int special;
	unsigned short max_spm[9];
	unsigned short avg_spm[9];
	unsigned short avg_jpm[9];
	unsigned short chaos_v[9];
	unsigned short freez_v[9];
	char* title;
	char* l_name;
};

struct sequence
{
	signed int beat_count;
	signed short kind;
	signed short next_change;
	signed short music_count;
	signed short judge_count;
	signed short stolen_count;
	signed short op_note_ct;
	unsigned int hold_length[8];
	unsigned char hold_stat[8];
};

struct _anon0
{
	unsigned char state;
	unsigned char perfect;
	unsigned short play_count;
	unsigned short play_time;
	unsigned short clear_count;
	unsigned short first_clear_count;
	unsigned short first_clear_time;
};

struct _anon1
{
	unsigned char old_stat;
	unsigned char cur_stat;
	unsigned char release_ct;
	unsigned char warning;
};

struct play_mode
{
	unsigned char seq_kind;
	unsigned char seq_transfer;
	unsigned char style;
	unsigned char pccard_seq;
	unsigned char mcard_seq;
	unsigned char padding;
	signed short edseq_id;
	struct
	{
		unsigned int hidden : 3;
		unsigned int thinout : 1;
		unsigned int free : 1;
		unsigned int soft : 1;
		unsigned int boost : 2;
		unsigned int speed : 5;
		unsigned int scroll : 2;
		unsigned int freeze : 1;
		unsigned int vivid : 2;
		unsigned int anime : 2;
		unsigned int dark : 1;
	};
	unsigned int pad : 12;
};

struct _play_backup_w
{
	eval_w stage_evaluation;
	eval_w total_evaluation;
	play_mode mode;
	play_his his[7];
	unsigned int play_stage;
};

struct _anon2
{
	unsigned char appear;
	unsigned char ending_flag;
	signed char help_count;
	unsigned char pad;
	signed int bonus_count;
	signed int dummy[2];
	_anon0 subject[100];
};

struct popular
{
	signed short cur_c;
	signed short last_c;
	unsigned short count[4][256];
};

struct _backup_w
{
	_play_backup_w player[2];
	signed char stage;
	signed char start_chip;
	signed char extra_chip;
	signed char use_chip;
	signed char lost_chip;
};

struct G_RANKING_W_
{
	char name[4];
	unsigned long score;
};

struct oni_cource_work
{
	signed int id;
	signed int init_ok;
	oni_course* course[31];
	signed int tex_kind;
	signed int tex_load_step;
	unsigned char seqkind_tab[20];
	signed int dancer_flag;
};

struct _anon3
{
	unsigned char game_over;
	unsigned char calorie_check;
	unsigned char pad[2];
};

struct _InputData
{
	unsigned short player_input[4];
	unsigned short player_input_trigger[4];
	unsigned short player_input_released[4];
	unsigned short etc;
	unsigned short etc_trigger;
	unsigned short etc_released;
	unsigned short padding;
};

struct play_his
{
	signed short music;
	signed short edit_id;
	unsigned char seq_kind;
	signed char roulette;
	signed char extra;
	signed char pad;
};

struct oni_mode
{
	unsigned int link_num;
	unsigned char seq_kind;
	unsigned char seq_transfer;
	unsigned char sp_music;
	unsigned char add_life;
	struct
	{
		unsigned int hidden : 2;
		unsigned int thinout : 1;
		unsigned int free : 1;
		unsigned int soft : 1;
		unsigned int boost : 2;
		unsigned int speed : 5;
		unsigned int scroll : 2;
		unsigned int freeze : 1;
		unsigned int vivid : 2;
		unsigned int anime : 2;
		unsigned int dark : 1;
		unsigned int pad : 12;
	};
};

struct _anon4
{
	unsigned int program_calorie[6];
	unsigned int program_play_count[6];
	unsigned int song_calorie[5][60];
	unsigned int song_play_count[5][60];
};

struct _InputBuffer
{
	unsigned long current_buffer;
	_InputData data[2];
};

struct g_each_w
{
	unsigned int play_time;
	unsigned int game_time;
	unsigned int game_time_total;
	signed char select;
	signed char character;
	signed char costume;
	signed char motiontype;
	signed char loaded_model;
	signed char loaded_texture;
	signed char loaded_motion;
	unsigned char play_disp_flag;
	unsigned char model_disp_flag;
	unsigned char gauge_disp_flag;
	signed short cur_point;
	signed int cur_life;
	unsigned int score;
	unsigned int old_score;
	unsigned int real_score;
	unsigned int bonus;
	unsigned int old_bonus;
	unsigned int max_score;
	unsigned int old_max_score;
	unsigned int max_bonus;
	unsigned int old_max_bonus;
	unsigned int cal;
	unsigned int old_cal;
	unsigned int real_cal;
	unsigned int disp_cal;
	unsigned int average_cal;
	signed int diet_norm_cal;
	signed int diet_norm_minute;
	signed int old_norm_cal;
	signed int old_norm_minute;
	signed int minimum_cal;
	unsigned char add_cal_flg;
	unsigned char chk_cal_flg;
	unsigned char combo_no_disp_flag;
	unsigned char pad;
	unsigned int play_stage;
	unsigned int decode_key1;
	unsigned int decode_key2;
	unsigned int decode_key3;
	signed int used_unfair_command;
	signed int nonstop_dead_flag;
	play_mode mode;
	play_his his[7];
	eval_w stage_evaluation;
	eval_w total_evaluation;
	play_w play_work;
	signed int total_notes;
	signed int total_jump;
	signed int total_freez;
	signed int category;
	signed int total_category;
	sequence sequence_buff[6144];
	signed int total_notes_all;
	signed int total_freez_all;
};

struct g_game_w
{
	signed short state;
	signed short genre;
	music_info* mip;
	signed char start_chip;
	signed char extra_chip;
	signed char use_chip;
	signed char lost_chip;
	signed short stage;
	signed short next_stage;
	signed short failed;
	signed short level;
	signed char game_kind;
	signed char world;
	signed char oni_nonstop_course_id;
	signed char event_mode;
	signed char event_two_flag;
	signed char style;
	signed char music_group;
	signed char music_select_mode;
	signed char extra_stage;
	signed char extra_fix;
	signed char final_fix;
	signed char meter_kind;
	signed char roulette_stage;
	signed char edit_total;
	signed char roulette_total;
	signed short music;
	signed char oni_nonstop_mode;
	unsigned char oni_load_step;
	signed char oni_nonstop_difficulty;
	signed char use_oni_gauge;
	signed char beginner_mode;
	signed char beginner_selected;
	signed char freez_selected;
	signed char judge_invalid;
	signed short oni_next_music;
	music_info* oni_next_mip;
	g_each_w player[2];
	signed char music_table[128];
	note_status note_status_table[300];
	_anon1 hc_work[8];
	signed int demoloop_ct;
	signed int mode_quit_ct[2];
	signed int force_exit_ct[2];
	signed int diet_play_time;
	signed int old_play_time;
	signed int menu_num;
	signed int total_stage;
	signed int now_bpm;
	unsigned char* last_data_addr;
	unsigned char edit_name[12];
	unsigned char diet_flg;
	unsigned char workout_step_flg;
	unsigned char auto_play_flg;
	unsigned char caution_flg;
	unsigned char mode_quit_flg;
	unsigned char lib_loaded;
	unsigned char force_exit_flg;
	unsigned char train_state;
	unsigned char lesson_flag;
	unsigned char lesson_auto_play_flag;
	unsigned char lesson_pad[2];
	unsigned char oni_load_start0;
	unsigned char oni_load_start1;
	unsigned char oni_load_end0;
	unsigned char oni_load_end1;
	unsigned char oni_order_step;
	unsigned char oni_order_stage;
	unsigned char oni_order_cursor;
	unsigned char oni_order_top_stage;
	unsigned char oni_order_selopt;
	unsigned char anime1_load_flg;
	unsigned char anime2_load_flg;
	unsigned char temp_sqk[2];
	unsigned char endless_flag;
	unsigned char eyetoy_flag;
	unsigned char challenge_flag;
	unsigned char step_mark_color;
	unsigned char hand_solo_seq_kind;
	unsigned char hand_solo_pad[2];
	unsigned char is_new_clothes;
	unsigned char quick_start;
	unsigned char nononi_msel_flag;
	unsigned char select_randaom_flag;
	unsigned char bar_state;
	signed int rloadtex_num;
	signed int rloadtex_lang;
	signed int rload_next_step;
	_backup_w backup;
	char quit_course_flag;
	char nonstop_selopt_flag;
	unsigned char dancer_id[3];
	signed int dance_counter;
	signed int event_result_exit_flag;
	signed int party_mode_flag;
};

struct _tag_cMWMgRunRecord
{
	signed int time;
	unsigned char bcd_time;
	unsigned char bcd_type;
	unsigned char fps;
	char pad[1];
};

struct _tag_cDDR8Record1
{
	unsigned int Score[10];
	unsigned int Bonus[10];
	unsigned int nPlayed;
	unsigned short LinkNum;
	unsigned short Combo[10];
	unsigned short ComboMax[10];
	unsigned char Level[10];
	unsigned char pad[2];
};

struct _tag_cMWMgRun
{
	_tag_cMWMgRunRecord record;
	char pad[8];
};

struct _DDRCommonHeader
{
	unsigned char Type;
	unsigned char Platform;
	unsigned char Hardware;
	unsigned char Version;
	unsigned char Area;
	signed char tmp;
	unsigned short title;
	unsigned int t_info[2];
};

struct tm
{
	signed int tm_sec;
	signed int tm_min;
	signed int tm_hour;
	signed int tm_mday;
	signed int tm_mon;
	signed int tm_year;
	signed int tm_wday;
	signed int tm_yday;
	signed int tm_isdst;
};

struct play_hist
{
	signed int music_count;
	unsigned char input[8];
};

struct _tag_cDDR8OniRecord1
{
	unsigned int Time[2];
	unsigned int Score[2];
	unsigned short Combo[2];
	unsigned char Stage[2];
	unsigned char Miss[2];
	unsigned char AllStage[2];
	unsigned char Level[2];
	unsigned char is_first_clear;
	unsigned char is_full_combo_flag[2];
	unsigned char pad[1];
	unsigned short ClearNum[2];
	unsigned char pad2[2];
};

struct G_INPUT_W_
{
	_InputData* dp;
	_InputBuffer buffer;
};

struct _eyetoy_option
{
	char depth;
	char pdf;
	char frame;
	unsigned char bright;
};

struct G_SYS_W_
{
	G_INPUT_W_ input_w;
	tm start_tm;
	unsigned int v_counter;
	unsigned long v_counter2;
	unsigned int s_counter;
	signed int u_counter;
	signed int read_time;
	unsigned char read_flag;
	unsigned char entry_bit;
	char vpf;
	char pad[2];
};

struct _mg_block
{
	signed int hi_score;
};

struct eval_w
{
	signed int value_ct[8];
	signed int freez_value_ct[4];
	signed int groov_bonus[6];
	signed int groov_bonus_max[6];
	signed int score;
	signed int bonus;
	signed int max_combo_ct;
	signed int jump_ct;
	signed short dance_level;
	signed short fixed_level;
};

struct _mg_coco
{
	signed int hi_score;
};

struct _anon5
{
	signed int hi_score;
};

struct note_status
{
	unsigned char state[8];
	unsigned int length[8];
};

struct _tag_cDDR8Option
{
	unsigned char Sound;
	unsigned char Voice;
	signed char Timing;
	char pad_sound[1];
	char EditKey[24];
	unsigned char KeyConfig[4];
	unsigned char DModeSet;
	unsigned char Vibration;
	unsigned char DPlay;
	char pad_cont[1];
	unsigned char AutoSave;
	unsigned char FolderLoad;
	char pad_mc[2];
	unsigned char Level;
	unsigned char MaxStage[3];
	unsigned char GameOver;
	unsigned char TimeLimit;
	unsigned char EventMode;
	unsigned char DefaultDifficulty;
	unsigned char SongDisp;
	unsigned char BgEffect;
	unsigned char BgBright;
	unsigned char DangerDisplay;
	unsigned char StepMarkColor;
	signed char screen_x;
	signed char screen_y;
	unsigned char FlickerFree;
	unsigned char DietMeasure;
	unsigned char DietDisplay;
	unsigned char DietTime;
	unsigned char DietPlayDefault;
	unsigned char DietWeightUnit;
	char pad_diet[3];
	unsigned char Language;
	char pad_lang[7];
	unsigned char DollDisp;
	unsigned char DollChara[3];
	unsigned char DollGuestNum;
	unsigned char DollSelect;
	char pad_doll[2];
};

struct _tag_cDDR8SaveData
{
	_DDRCommonHeader CommonHeader;
	_tag_cDDR8Option Option;
	_tag_cDDR8Record1 MRecord[60];
	unsigned char Information[256];
	unsigned int nMusic;
	unsigned int nBoot;
	unsigned int nPlayerType[3];
	unsigned int nDifficulty[5];
	signed int nwork[3];
	unsigned char LessonWork[32];
	_tag_cDDR8OniRecord1 OniRecord[12];
	_tag_cDDR8OniRecord1 NonstopRecord[24];
	popular popular;
	G_RANKING_W_ high_score[40];
	unsigned int HideFlag[2];
	unsigned int HideNewFlag[2];
	unsigned int HideDoll[2];
	unsigned int HideNewDoll[2];
	unsigned char HideDollWk[4];
	_EDSSAVE_W EdsRecords;
	_anon2 challenge;
	oni_course oni_order[3];
	oni_course nonstop_order[3];
	oni_course dietprogram_order[3];
	_anon4 diet_calorie_record[2];
	_tag_cMWMgRun mg_run;
	unsigned int nMusic_on_last_unlocked;
	_eyetoy_option eyetoy_option;
	_mg_block mg_block;
	_mg_coco mg_coco;
	_anon5 mg_eat;
	_tag_cDDR8Record1 mg_solo_MRecord[60];
	_anon3 wk_save[2];
};

struct _EDSS_DATA_W
{
	unsigned int score[2];
	signed int combo;
	signed int stage;
};
</pre>
SLES-52598 - Dancing Stage Fusion - 2004-08-25 Prototype Build
<pre>
struct _EDSS_PLAY_W
{
	_EDSS_DATA_W p_single[3];
	_EDSS_DATA_W p_double[3];
};

struct oni_course
{
	unsigned int course_allnum;
	unsigned int course_defnum;
	signed short avairable_level;
	signed short order;
	signed short start_life;
	signed short flag;
	unsigned int stage;
	signed int single_steps;
	signed int double_steps;
	oni_mode mode[20];
};

struct play_w
{
	signed int music_counter;
	signed int beat_counter;
	signed int cur_p_counter;
	signed int last_p_counter;
	signed int begin_beat_count;
	signed int go_beat_count;
	signed int finish_beat_count;
	signed int end_beat_count;
	signed int game_start_music_count;
	signed int game_finish_music_count;
	signed int back_trans_start_music_count;
	signed int last_fs_nct;
	signed short last_input_count[8];
	play_hist history[8];
	signed int cur_his;
	signed int pre_nct;
	signed int cur_nct;
	signed int disp_nct;
	signed int cur_great_combo;
	signed int cur_miss_combo;
	signed int max_great_combo;
	signed int max_miss_combo;
	signed int miss_start_count;
	signed int cur_great_combo_total;
	signed int max_great_combo_total;
	unsigned short input;
	unsigned char dead;
	signed char strictness;
	signed short panel_count[8];
	signed short message_ct;
	signed short message_id;
	signed short meter_cur;
	signed short meter_vol;
	signed short meter_ct;
	signed short offset;
	signed short light_offset;
	signed short meter_state;
	signed short anm_no;
	signed short dance_class;
	signed int bar_start;
	signed int bar_end;
};

struct _EDSSAVE_W
{
	_EDSS_PLAY_W reg[2];
	unsigned int PlayFlag[128];
};

struct music_info
{
	char base_name[6];
	signed char kind;
	signed char album;
	signed short dance_num;
	signed short order;
	unsigned int main_track;
	unsigned int select_track;
	unsigned short bpm_max;
	unsigned short bpm_min;
	unsigned short verm_num;
	unsigned short pcseq_num;
	unsigned long hide;
	signed short adjust_mc;
	unsigned int difficulty[2];
	unsigned int special;
	unsigned short max_spm[9];
	unsigned short avg_spm[9];
	unsigned short avg_jpm[9];
	unsigned short chaos_v[9];
	unsigned short freez_v[9];
	char* title;
	char* l_name;
};

struct sequence
{
	signed int beat_count;
	signed short kind;
	signed short next_change;
	signed short music_count;
	signed short judge_count;
	signed short stolen_count;
	signed short op_note_ct;
	unsigned int hold_length[8];
	unsigned char hold_stat[8];
};

struct _anon0
{
	unsigned char state;
	unsigned char perfect;
	unsigned short play_count;
	unsigned short play_time;
	unsigned short clear_count;
	unsigned short first_clear_count;
	unsigned short first_clear_time;
};

struct _anon1
{
	unsigned char old_stat;
	unsigned char cur_stat;
	unsigned char release_ct;
	unsigned char warning;
};

struct play_mode
{
	unsigned char seq_kind;
	unsigned char seq_transfer;
	unsigned char style;
	unsigned char pccard_seq;
	unsigned char mcard_seq;
	unsigned char padding;
	signed short edseq_id;
	struct
	{
		unsigned int hidden : 3;
		unsigned int thinout : 1;
		unsigned int free : 1;
		unsigned int soft : 1;
		unsigned int boost : 2;
		unsigned int speed : 5;
		unsigned int scroll : 2;
		unsigned int freeze : 1;
		unsigned int vivid : 2;
		unsigned int anime : 2;
		unsigned int dark : 1;
	};
	unsigned int pad : 12;
};

struct _play_backup_w
{
	eval_w stage_evaluation;
	eval_w total_evaluation;
	play_mode mode;
	play_his his[7];
	unsigned int play_stage;
};

struct _anon2
{
	unsigned char appear;
	unsigned char ending_flag;
	signed char help_count;
	unsigned char pad;
	signed int bonus_count;
	signed int dummy[2];
	_anon0 subject[100];
};

struct popular
{
	signed short cur_c;
	signed short last_c;
	unsigned short count[4][256];
};

struct _backup_w
{
	_play_backup_w player[2];
	signed char stage;
	signed char start_chip;
	signed char extra_chip;
	signed char use_chip;
	signed char lost_chip;
};

struct G_RANKING_W_
{
	char name[4];
	unsigned long score;
};

struct oni_cource_work
{
	signed int id;
	signed int init_ok;
	oni_course* course[31];
	signed int tex_kind;
	signed int tex_load_step;
	unsigned char seqkind_tab[20];
	signed int dancer_flag;
};

struct _anon3
{
	unsigned char game_over;
	unsigned char calorie_check;
	unsigned char pad[2];
};

struct _InputData
{
	unsigned short player_input[4];
	unsigned short player_input_trigger[4];
	unsigned short player_input_released[4];
	unsigned short etc;
	unsigned short etc_trigger;
	unsigned short etc_released;
	unsigned short padding;
};

struct play_his
{
	signed short music;
	signed short edit_id;
	unsigned char seq_kind;
	signed char roulette;
	signed char extra;
	signed char pad;
};

struct oni_mode
{
	unsigned int link_num;
	unsigned char seq_kind;
	unsigned char seq_transfer;
	unsigned char sp_music;
	unsigned char add_life;
	struct
	{
		unsigned int hidden : 2;
		unsigned int thinout : 1;
		unsigned int free : 1;
		unsigned int soft : 1;
		unsigned int boost : 2;
		unsigned int speed : 5;
		unsigned int scroll : 2;
		unsigned int freeze : 1;
		unsigned int vivid : 2;
		unsigned int anime : 2;
		unsigned int dark : 1;
		unsigned int pad : 12;
	};
};

struct _anon4
{
	unsigned int program_calorie[6];
	unsigned int program_play_count[6];
	unsigned int song_calorie[5][60];
	unsigned int song_play_count[5][60];
};

struct _InputBuffer
{
	unsigned long current_buffer;
	_InputData data[2];
};

struct g_each_w
{
	unsigned int play_time;
	unsigned int game_time;
	unsigned int game_time_total;
	signed char select;
	signed char character;
	signed char costume;
	signed char motiontype;
	signed char loaded_model;
	signed char loaded_texture;
	signed char loaded_motion;
	unsigned char play_disp_flag;
	unsigned char model_disp_flag;
	unsigned char gauge_disp_flag;
	signed short cur_point;
	signed int cur_life;
	unsigned int score;
	unsigned int old_score;
	unsigned int real_score;
	unsigned int bonus;
	unsigned int old_bonus;
	unsigned int max_score;
	unsigned int old_max_score;
	unsigned int max_bonus;
	unsigned int old_max_bonus;
	unsigned int cal;
	unsigned int old_cal;
	unsigned int real_cal;
	unsigned int disp_cal;
	unsigned int average_cal;
	signed int diet_norm_cal;
	signed int diet_norm_minute;
	signed int old_norm_cal;
	signed int old_norm_minute;
	signed int minimum_cal;
	unsigned char add_cal_flg;
	unsigned char chk_cal_flg;
	unsigned char combo_no_disp_flag;
	unsigned char pad;
	unsigned int play_stage;
	unsigned int decode_key1;
	unsigned int decode_key2;
	unsigned int decode_key3;
	signed int used_unfair_command;
	signed int nonstop_dead_flag;
	play_mode mode;
	play_his his[7];
	eval_w stage_evaluation;
	eval_w total_evaluation;
	play_w play_work;
	signed int total_notes;
	signed int total_jump;
	signed int total_freez;
	signed int category;
	signed int total_category;
	sequence sequence_buff[6144];
	signed int total_notes_all;
	signed int total_freez_all;
};

struct g_game_w
{
	signed short state;
	signed short genre;
	music_info* mip;
	signed char start_chip;
	signed char extra_chip;
	signed char use_chip;
	signed char lost_chip;
	signed short stage;
	signed short next_stage;
	signed short failed;
	signed short level;
	signed char game_kind;
	signed char world;
	signed char oni_nonstop_course_id;
	signed char event_mode;
	signed char event_two_flag;
	signed char style;
	signed char music_group;
	signed char music_select_mode;
	signed char extra_stage;
	signed char extra_fix;
	signed char final_fix;
	signed char meter_kind;
	signed char roulette_stage;
	signed char edit_total;
	signed char roulette_total;
	signed short music;
	signed char oni_nonstop_mode;
	unsigned char oni_load_step;
	signed char oni_nonstop_difficulty;
	signed char use_oni_gauge;
	signed char beginner_mode;
	signed char beginner_selected;
	signed char freez_selected;
	signed char judge_invalid;
	signed short oni_next_music;
	music_info* oni_next_mip;
	g_each_w player[2];
	signed char music_table[128];
	note_status note_status_table[300];
	_anon1 hc_work[8];
	signed int demoloop_ct;
	signed int mode_quit_ct[2];
	signed int force_exit_ct[2];
	signed int diet_play_time;
	signed int old_play_time;
	signed int menu_num;
	signed int total_stage;
	signed int now_bpm;
	unsigned char* last_data_addr;
	unsigned char edit_name[12];
	unsigned char diet_flg;
	unsigned char workout_step_flg;
	unsigned char auto_play_flg;
	unsigned char caution_flg;
	unsigned char mode_quit_flg;
	unsigned char lib_loaded;
	unsigned char force_exit_flg;
	unsigned char train_state;
	unsigned char lesson_flag;
	unsigned char lesson_auto_play_flag;
	unsigned char lesson_pad[2];
	unsigned char oni_load_start0;
	unsigned char oni_load_start1;
	unsigned char oni_load_end0;
	unsigned char oni_load_end1;
	unsigned char oni_order_step;
	unsigned char oni_order_stage;
	unsigned char oni_order_cursor;
	unsigned char oni_order_top_stage;
	unsigned char oni_order_selopt;
	unsigned char anime1_load_flg;
	unsigned char anime2_load_flg;
	unsigned char temp_sqk[2];
	unsigned char endless_flag;
	unsigned char eyetoy_flag;
	unsigned char challenge_flag;
	unsigned char step_mark_color;
	unsigned char hand_solo_seq_kind;
	unsigned char hand_solo_pad[2];
	unsigned char is_new_clothes;
	unsigned char quick_start;
	unsigned char nononi_msel_flag;
	unsigned char select_randaom_flag;
	unsigned char bar_state;
	signed int rloadtex_num;
	signed int rloadtex_lang;
	signed int rload_next_step;
	_backup_w backup;
	char quit_course_flag;
	char nonstop_selopt_flag;
	unsigned char dancer_id[3];
	signed int dance_counter;
	signed int event_result_exit_flag;
	signed int party_mode_flag;
};

struct _tag_cMWMgRunRecord
{
	signed int time;
	unsigned char bcd_time;
	unsigned char bcd_type;
	unsigned char fps;
	char pad[1];
};

struct _tag_cDDR8Record1
{
	unsigned int Score[10];
	unsigned int Bonus[10];
	unsigned int nPlayed;
	unsigned short LinkNum;
	unsigned short Combo[10];
	unsigned short ComboMax[10];
	unsigned char Level[10];
	unsigned char pad[2];
};

struct _tag_cMWMgRun
{
	_tag_cMWMgRunRecord record;
	char pad[8];
};

struct _DDRCommonHeader
{
	unsigned char Type;
	unsigned char Platform;
	unsigned char Hardware;
	unsigned char Version;
	unsigned char Area;
	signed char tmp;
	unsigned short title;
	unsigned int t_info[2];
};

struct tm
{
	signed int tm_sec;
	signed int tm_min;
	signed int tm_hour;
	signed int tm_mday;
	signed int tm_mon;
	signed int tm_year;
	signed int tm_wday;
	signed int tm_yday;
	signed int tm_isdst;
};

struct play_hist
{
	signed int music_count;
	unsigned char input[8];
};

struct _tag_cDDR8OniRecord1
{
	unsigned int Time[2];
	unsigned int Score[2];
	unsigned short Combo[2];
	unsigned char Stage[2];
	unsigned char Miss[2];
	unsigned char AllStage[2];
	unsigned char Level[2];
	unsigned char is_first_clear;
	unsigned char is_full_combo_flag[2];
	unsigned char pad[1];
	unsigned short ClearNum[2];
	unsigned char pad2[2];
};

struct G_INPUT_W_
{
	_InputData* dp;
	_InputBuffer buffer;
};

struct _eyetoy_option
{
	char depth;
	char pdf;
	char frame;
	unsigned char bright;
};

struct G_SYS_W_
{
	G_INPUT_W_ input_w;
	tm start_tm;
	unsigned int v_counter;
	unsigned long v_counter2;
	unsigned int s_counter;
	signed int u_counter;
	signed int read_time;
	unsigned char read_flag;
	unsigned char entry_bit;
	char vpf;
	char pad[2];
};

struct _mg_block
{
	signed int hi_score;
};

struct eval_w
{
	signed int value_ct[8];
	signed int freez_value_ct[4];
	signed int groov_bonus[6];
	signed int groov_bonus_max[6];
	signed int score;
	signed int bonus;
	signed int max_combo_ct;
	signed int jump_ct;
	signed short dance_level;
	signed short fixed_level;
};

struct _mg_coco
{
	signed int hi_score;
};

struct _anon5
{
	signed int hi_score;
};

struct note_status
{
	unsigned char state[8];
	unsigned int length[8];
};

struct _tag_cDDR8Option
{
	unsigned char Sound;
	unsigned char Voice;
	signed char Timing;
	char pad_sound[1];
	char EditKey[24];
	unsigned char KeyConfig[4];
	unsigned char DModeSet;
	unsigned char Vibration;
	unsigned char DPlay;
	char pad_cont[1];
	unsigned char AutoSave;
	unsigned char FolderLoad;
	char pad_mc[2];
	unsigned char Level;
	unsigned char MaxStage[3];
	unsigned char GameOver;
	unsigned char TimeLimit;
	unsigned char EventMode;
	unsigned char DefaultDifficulty;
	unsigned char SongDisp;
	unsigned char BgEffect;
	unsigned char BgBright;
	unsigned char DangerDisplay;
	unsigned char StepMarkColor;
	signed char screen_x;
	signed char screen_y;
	unsigned char FlickerFree;
	unsigned char DietMeasure;
	unsigned char DietDisplay;
	unsigned char DietTime;
	unsigned char DietPlayDefault;
	unsigned char DietWeightUnit;
	char pad_diet[3];
	unsigned char Language;
	char pad_lang[7];
	unsigned char DollDisp;
	unsigned char DollChara[3];
	unsigned char DollGuestNum;
	unsigned char DollSelect;
	char pad_doll[2];
};

struct _tag_cDDR8SaveData
{
	_DDRCommonHeader CommonHeader;
	_tag_cDDR8Option Option;
	_tag_cDDR8Record1 MRecord[60];
	unsigned char Information[256];
	unsigned int nMusic;
	unsigned int nBoot;
	unsigned int nPlayerType[3];
	unsigned int nDifficulty[5];
	signed int nwork[3];
	unsigned char LessonWork[32];
	_tag_cDDR8OniRecord1 OniRecord[12];
	_tag_cDDR8OniRecord1 NonstopRecord[24];
	popular popular;
	G_RANKING_W_ high_score[40];
	unsigned int HideFlag[2];
	unsigned int HideNewFlag[2];
	unsigned int HideDoll[2];
	unsigned int HideNewDoll[2];
	unsigned char HideDollWk[4];
	_EDSSAVE_W EdsRecords;
	_anon2 challenge;
	oni_course oni_order[3];
	oni_course nonstop_order[3];
	oni_course dietprogram_order[3];
	_anon4 diet_calorie_record[2];
	_tag_cMWMgRun mg_run;
	unsigned int nMusic_on_last_unlocked;
	_eyetoy_option eyetoy_option;
	_mg_block mg_block;
	_mg_coco mg_coco;
	_anon5 mg_eat;
	_tag_cDDR8Record1 mg_solo_MRecord[60];
	_anon3 wk_save[2];
};

struct _EDSS_DATA_W
{
	unsigned int score[2];
	signed int combo;
	signed int stage;
};
</pre>
SLPM-62427 - DanceDanceRevolution Party Collection - 2003-10-06 Retail Build
<pre>
struct oni_course
{
	unsigned int course_allnum;
	unsigned int course_defnum;
	signed short avairable_level;
	signed short order;
	signed short start_life;
	signed short flag;
	unsigned int stage;
	signed int single_steps;
	signed int double_steps;
	oni_mode mode[20];
};

struct oni_mode
{
	unsigned int link_num;
	unsigned char seq_kind;
	unsigned char seq_transfer;
	unsigned char sp_music;
	unsigned char add_life;
	struct
	{
		unsigned int hidden : 2;
		unsigned int thinout : 1;
		unsigned int free : 1;
		unsigned int soft : 1;
		unsigned int boost : 2;
		unsigned int speed : 5;
		unsigned int scroll : 2;
		unsigned int freeze : 1;
		unsigned int vivid : 2;
		unsigned int anime : 2;
		unsigned int dark : 1;
		unsigned int pad : 12;
	};
};

struct _tag_cDDRB2SaveData
{
	_DDRCommonHeader CommonHeader;
	_tag_cDDRB2Option Option;
	_tag_cDDRB2Record1 MRecord[60];
	unsigned char Information[256];
	unsigned int nMusic;
	unsigned int nBoot;
	unsigned int nPlayerType[3];
	unsigned int nDifficulty[5];
	signed int hNum;
	signed int nwork[3];
	unsigned char LessonWork[32];
	_tag_cDDRB2OniRecord1 OniRecord[17];
	_tag_cDDRB2OniRecord1 NonstopRecord[32];
	popular popular;
	G_RANKING_W_ high_score[40];
	unsigned int HideFlag[2];
	unsigned int HideDoll[2];
	unsigned char HideDollWk[4];
	_EDSSAVE_W EdsRecords;
	oni_course oni_order[3];
	oni_course nonstop_order[3];
	oni_course dietprogram_order[3];
	_anon1 diet_calorie_record[2];
	unsigned int nMusic_on_last_unlocked;
};

struct note_status
{
	unsigned char state[8];
	unsigned int length[8];
};

struct play_mode
{
	unsigned char seq_kind;
	unsigned char seq_transfer;
	unsigned char style;
	unsigned char pccard_seq;
	unsigned char mcard_seq;
	unsigned char padding;
	signed short edseq_id;
	struct
	{
		unsigned int hidden : 2;
		unsigned int thinout : 1;
		unsigned int free : 1;
		unsigned int soft : 1;
		unsigned int boost : 2;
		unsigned int speed : 5;
		unsigned int scroll : 2;
		unsigned int freeze : 1;
		unsigned int vivid : 2;
		unsigned int anime : 2;
		unsigned int dark : 1;
		unsigned int pad : 12;
	};
};

struct tm
{
	signed int tm_sec;
	signed int tm_min;
	signed int tm_hour;
	signed int tm_mday;
	signed int tm_mon;
	signed int tm_year;
	signed int tm_wday;
	signed int tm_yday;
	signed int tm_isdst;
};

struct play_hist
{
	signed int music_count;
	unsigned char input[8];
};

struct oni_steps
{
	unsigned int link_num;
	unsigned short steps[4][2];
};

struct music_info
{
	char base_name[6];
	signed char kind;
	signed char album;
	signed short dance_num;
	signed short order;
	unsigned short main_track;
	unsigned short select_track;
	unsigned short bpm_max;
	unsigned short bpm_min;
	unsigned short verm_num;
	unsigned short pcseq_num;
	unsigned long hide;
	signed short adjust_mc;
	unsigned int difficulty[2];
	unsigned int special;
	unsigned short max_spm[9];
	unsigned short avg_spm[9];
	unsigned short avg_jpm[9];
	unsigned short chaos_v[9];
	unsigned short freez_v[9];
	char* title;
	char* l_name;
};

struct g_game_w
{
	signed short state;
	signed short genre;
	music_info* mip;
	signed char start_chip;
	signed char extra_chip;
	signed char use_chip;
	signed char lost_chip;
	signed short stage;
	signed short next_stage;
	signed short failed;
	signed short level;
	signed char game_kind;
	signed char world;
	signed char oni_nonstop_course_id;
	signed char event_mode;
	signed char event_two_flag;
	signed char style;
	signed char music_group;
	signed char music_select_mode;
	signed char extra_stage;
	signed char extra_fix;
	signed char final_fix;
	signed char meter_kind;
	signed char roulette_stage;
	signed char edit_total;
	signed char roulette_total;
	signed short music;
	signed char oni_nonstop_mode;
	unsigned char oni_load_step;
	signed char oni_nonstop_difficulty;
	signed char oni_pad;
	signed char beginner_mode;
	signed char beginner_selected;
	signed char freez_selected;
	signed char beginner_pad[1];
	signed short oni_next_music;
	music_info* oni_next_mip;
	g_each_w player[2];
	signed char music_table[49];
	note_status note_status_table[300];
	_anon2 hc_work[8];
	signed int demoloop_ct;
	signed int mode_quit_ct[2];
	signed int force_exit_ct[2];
	signed int diet_play_time;
	signed int old_play_time;
	signed int menu_num;
	signed int total_stage;
	signed int now_bpm;
	unsigned char* last_data_addr;
	unsigned char edit_name[12];
	unsigned char diet_flg;
	unsigned char auto_play_flg;
	unsigned char caution_flg;
	unsigned char mode_quit_flg;
	unsigned char lib_loaded;
	unsigned char force_exit_flg;
	unsigned char music_stop_flg;
	unsigned char train_state;
	unsigned char lesson_flag;
	unsigned char lesson_auto_play_flag;
	unsigned char lesson_pad[2];
	unsigned char oni_load_start0;
	unsigned char oni_load_start1;
	unsigned char oni_load_end0;
	unsigned char oni_load_end1;
	unsigned char oni_order_step;
	unsigned char oni_order_stage;
	unsigned char oni_order_cursor;
	unsigned char oni_order_top_stage;
	unsigned char oni_order_selopt;
	unsigned char anime1_load_flg;
	unsigned char anime2_load_flg;
	unsigned char temp_sqk[2];
	unsigned char endless_flag;
	unsigned char endless_pad[3];
	signed char __pad[2];
	signed int rloadtex_num;
	signed int rload_next_step;
	char extra_ver;
	char nonstop_selopt_flag;
	unsigned char dancer_id[3];
};

struct G_INPUT_W_
{
	_InputData* dp;
	_InputBuffer buffer;
};

struct _InputData
{
	unsigned short player_input[4];
	unsigned short player_input_trigger[4];
	unsigned short player_input_released[4];
	unsigned short etc;
	unsigned short etc_trigger;
	unsigned short etc_released;
	unsigned short padding;
};

struct G_SYS_W_
{
	G_INPUT_W_ input_w;
	tm start_tm;
	unsigned int v_counter;
	unsigned long v_counter2;
	unsigned int s_counter;
	signed int u_counter;
	signed int read_time;
	unsigned char read_flag;
	unsigned char entry_bit;
	char vpf;
	char pad[2];
};

struct sequence
{
	signed int beat_count;
	signed short kind;
	signed short next_change;
	signed short music_count;
	signed short judge_count;
	signed short stolen_count;
	signed short op_note_ct;
	unsigned int hold_length[8];
	unsigned char hold_stat[8];
};

struct oni_cource_work
{
	signed int id;
	signed int init_ok;
	oni_course* course[42];
	signed int tex_kind;
	signed int tex_load_step;
	unsigned char seqkind_tab[20];
	signed int dancer_flag;
};

struct play_his
{
	signed short music;
	signed short edit_id;
	unsigned char seq_kind;
	signed char roulette;
	signed char extra;
	signed char pad;
};

struct popular
{
	signed short cur_c;
	signed short last_c;
	unsigned short count[4][256];
};

struct G_RANKING_W_
{
	char name[4];
	unsigned long score;
};

struct g_each_w
{
	unsigned int play_time;
	unsigned int game_time;
	unsigned int game_time_total;
	signed char select;
	signed char character;
	signed char costume;
	signed char motiontype;
	signed char loaded_model;
	signed char loaded_texture;
	signed char loaded_motion;
	unsigned char play_disp_flag;
	unsigned char model_disp_flag;
	unsigned char gauge_disp_flag;
	signed short cur_point;
	signed int cur_life;
	unsigned int score;
	unsigned int old_score;
	unsigned int real_score;
	unsigned int bonus;
	unsigned int old_bonus;
	unsigned int max_score;
	unsigned int old_max_score;
	unsigned int max_bonus;
	unsigned int old_max_bonus;
	unsigned int cal;
	unsigned int old_cal;
	unsigned int real_cal;
	unsigned int disp_cal;
	unsigned int average_cal;
	signed int diet_norm_cal;
	signed int diet_norm_minute;
	signed int old_norm_cal;
	signed int old_norm_minute;
	signed int minimum_cal;
	unsigned char add_cal_flg;
	unsigned char chk_cal_flg;
	unsigned char pad[2];
	unsigned int play_stage;
	unsigned int decode_key1;
	unsigned int decode_key2;
	unsigned int decode_key3;
	signed int used_unfair_command;
	signed int nonstop_dead_flag;
	play_mode mode;
	play_his his[7];
	eval_w stage_evaluation;
	eval_w total_evaluation;
	play_w play_work;
	signed int total_notes;
	signed int total_jump;
	signed int total_freez;
	signed int category;
	signed int total_category;
	sequence sequence_buff[6144];
};

struct _tag_cDDRB2Record1
{
	unsigned int Score[10];
	unsigned int Bonus[10];
	unsigned int nPlayed;
	unsigned short LinkNum;
	unsigned short Combo[10];
	unsigned short ComboMax[10];
	unsigned char Level[10];
	unsigned char pad[2];
};

struct play_w
{
	signed int music_counter;
	signed int beat_counter;
	signed int cur_p_counter;
	signed int last_p_counter;
	signed int begin_beat_count;
	signed int go_beat_count;
	signed int finish_beat_count;
	signed int end_beat_count;
	signed int game_start_music_count;
	signed int game_finish_music_count;
	signed int back_trans_start_music_count;
	signed int last_fs_nct;
	signed short last_input_count[8];
	play_hist history[8];
	signed int cur_his;
	signed int pre_nct;
	signed int cur_nct;
	signed int disp_nct;
	signed int cur_great_combo;
	signed int cur_miss_combo;
	signed int max_great_combo;
	signed int max_miss_combo;
	signed int miss_start_count;
	signed int cur_great_combo_total;
	signed int max_great_combo_total;
	unsigned short input;
	unsigned char dead;
	signed char strictness;
	signed short panel_count[8];
	signed short message_ct;
	signed short message_id;
	signed short meter_cur;
	signed short meter_vol;
	signed short meter_ct;
	signed short dance_class;
	signed int bar_start;
	signed int bar_end;
};

struct _InputBuffer
{
	unsigned long current_buffer;
	_InputData data[2];
};

struct _tag_cDDRB2OniRecord1
{
	unsigned int Time[2];
	unsigned int Score[2];
	unsigned short Combo[2];
	unsigned char Stage[2];
	unsigned char Miss[2];
	unsigned char AllStage[2];
	unsigned char Level[2];
	unsigned char is_first_clear;
	unsigned char pad[3];
	unsigned short ClearNum[2];
	unsigned char pad2[2];
};

struct _DDRCommonHeader
{
	unsigned char Type;
	unsigned char Platform;
	unsigned char Hardware;
	unsigned char Version;
	unsigned char Area;
	signed char tmp;
	unsigned short title;
	unsigned int t_info[2];
};

struct _EDSS_DATA_W
{
	unsigned int score[2];
	signed int combo;
	signed int stage;
};

struct _tag_cDDRB2Option
{
	unsigned char Sound;
	unsigned char Voice;
	signed char Timing;
	char pad_sound[1];
	char EditKey[24];
	unsigned char KeyConfig[4];
	unsigned char DModeSet;
	unsigned char Vibration;
	unsigned char DPlay;
	char pad_cont[1];
	unsigned char AutoSave;
	unsigned char FolderLoad;
	char pad_mc[2];
	unsigned char Level;
	unsigned char MaxStage[3];
	unsigned char GameOver;
	unsigned char TimeLimit;
	unsigned char EventMode;
	unsigned char DefaultDifficulty;
	char pad_game[8];
	unsigned char BgEffect;
	unsigned char BgBright;
	unsigned char DangerDisplay;
	unsigned char StepMarkColor;
	signed char screen_x;
	signed char screen_y;
	unsigned char FlickerFree;
	char pad_graphic[1];
	unsigned char DietMeasure;
	unsigned char DietDisplay;
	unsigned char DietTime;
	unsigned char DietPlayDefault;
	unsigned char DietWeightUnit;
	char pad_diet[3];
	unsigned char Language;
	char pad_lang[7];
	unsigned char DollDisp;
	unsigned char DollChara[3];
	unsigned char DollGuestNum;
	unsigned char DollSelect;
	char pad[2];
};

struct eval_w
{
	signed int value_ct[8];
	signed int freez_value_ct[4];
	signed int groov_bonus[6];
	signed int groov_bonus_max[6];
	signed int score;
	signed int max_combo_ct;
	signed int jump_ct;
	signed short dance_level;
	signed short fixed_level;
};

struct _EDSS_PLAY_W
{
	_EDSS_DATA_W p_single[3];
	_EDSS_DATA_W p_double[3];
};

struct _EDSSAVE_W
{
	_EDSS_PLAY_W reg[2];
	_EDSS_DATA_W max_point;
	unsigned int PlayFlag[128];
};

struct _anon0
{
	struct
	{
		unsigned long number : 16;
		unsigned long sector : 24;
		unsigned long size : 24;
	};
};

struct _anon1
{
	unsigned int program_calorie[8];
	unsigned int program_play_count[8];
	unsigned int song_calorie[5][60];
	unsigned int song_play_count[5][60];
};

struct _anon2
{
	unsigned char old_stat;
	unsigned char cur_stat;
	unsigned char release_ct;
	unsigned char warning;
};
</pre>
SLPM-65277 - DDRMAX2 -DanceDanceRevolution 7thMIX- 2003-02-06 Retail Build
<pre>
struct oni_steps
{
	unsigned int link_num;
	unsigned short steps[4][2];
};

struct oni_course
{
	unsigned int course_allnum;
	unsigned int course_defnum;
	signed short avairable_level;
	signed short order;
	signed short start_life;
	signed short stage;
	signed int single_steps;
	signed int double_steps;
	oni_mode mode[20];
};

struct tm
{
	signed int tm_sec;
	signed int tm_min;
	signed int tm_hour;
	signed int tm_mday;
	signed int tm_mon;
	signed int tm_year;
	signed int tm_wday;
	signed int tm_yday;
	signed int tm_isdst;
};

struct oni_mode
{
	unsigned int link_num;
	unsigned char seq_kind;
	unsigned char seq_transfer;
	unsigned char sp_music;
	unsigned char add_life;
	struct
	{
		unsigned int hidden : 2;
		unsigned int thinout : 1;
		unsigned int free : 1;
		unsigned int soft : 1;
		unsigned int boost : 2;
		unsigned int speed : 5;
		unsigned int scroll : 2;
		unsigned int freeze : 1;
		unsigned int vivid : 2;
		unsigned int anime : 2;
		unsigned int dark : 1;
		unsigned int pad : 12;
	};
};

struct note_status
{
	unsigned char state[8];
	unsigned int length[8];
};

struct _DDRCommonHeader
{
	unsigned char Type;
	unsigned char Platform;
	unsigned char Hardware;
	unsigned char Version;
	unsigned char Area;
	signed char tmp;
	unsigned short title;
	unsigned int t_info[2];
};

struct music_info
{
	char base_name[6];
	signed char kind;
	signed char album;
	signed short dance_num;
	signed short order;
	unsigned short main_track;
	unsigned short select_track;
	unsigned short bpm_max;
	unsigned short bpm_min;
	unsigned short verm_num;
	unsigned short pcseq_num;
	unsigned long hide;
	signed short adjust_mc;
	unsigned int difficulty[2];
	unsigned int special;
	unsigned short max_spm[8];
	unsigned short avg_spm[8];
	unsigned short avg_jpm[8];
	unsigned short chaos_v[8];
	unsigned short freez_v[8];
	char* title;
	char* l_name;
};

struct _tag_cDDR7Record1
{
	unsigned int Score[8];
	unsigned int Bonus[8];
	unsigned int nPlayed;
	unsigned short LinkNum;
	unsigned short Combo[8];
	unsigned short ComboMax[8];
	unsigned char Level[8];
	char pad[2];
};

struct play_hist
{
	signed int music_count;
	unsigned char input[8];
};

struct sequence
{
	signed int beat_count;
	signed short kind;
	signed short next_change;
	signed short music_count;
	signed short judge_count;
	signed short stolen_count;
	signed short op_note_ct;
	unsigned int hold_length[8];
	unsigned char hold_stat[8];
};

struct eval_w
{
	signed int value_ct[7];
	signed int freez_value_ct[4];
	signed int groov_bonus[6];
	signed int groov_bonus_max[6];
	signed int score;
	signed int max_combo_ct;
	signed int jump_ct;
	signed short dance_level;
	signed short fixed_level;
};

struct G_INPUT_W_
{
	_InputData* dp;
	_InputBuffer buffer;
};

struct _tag_cDDR7OniRecord1
{
	unsigned int Time[2];
	unsigned short Score[2];
	unsigned short Combo[2];
	unsigned char Stage[2];
	unsigned char Miss[2];
	unsigned char AllStage[2];
	unsigned char pad[10];
};

struct _InputData
{
	unsigned short player_input[4];
	unsigned short player_input_trigger[4];
	unsigned short player_input_released[4];
	unsigned short etc;
	unsigned short etc_trigger;
	unsigned short etc_released;
	unsigned short padding;
};

struct machine_point_work
{
	unsigned int hide_show;
	unsigned int status;
	unsigned int period_time;
	signed int cur_point;
};

struct G_SYS_W_
{
	G_INPUT_W_ input_w;
	tm start_tm;
	unsigned int v_counter;
	unsigned long v_counter2;
	unsigned int s_counter;
	signed int u_counter;
	unsigned char entry_bit;
	char vpf;
	char pad[2];
};

struct oni_cource_work
{
	signed int id;
	signed int init_ok;
	oni_course* course[32];
};

struct _anon0
{
	unsigned char old_stat;
	unsigned char cur_stat;
	unsigned char release_ct;
	unsigned char warning;
};

struct _EDSS_DATA_W
{
	unsigned int score[2];
	signed int combo;
	signed int stage;
};

struct play_mode
{
	unsigned char seq_kind;
	unsigned char seq_transfer;
	unsigned char style;
	unsigned char pccard_seq;
	unsigned char mcard_seq;
	unsigned char padding;
	signed short edseq_id;
	struct
	{
		unsigned int hidden : 2;
		unsigned int thinout : 1;
		unsigned int free : 1;
		unsigned int soft : 1;
		unsigned int boost : 2;
		unsigned int speed : 5;
		unsigned int scroll : 2;
		unsigned int freeze : 1;
		unsigned int vivid : 2;
		unsigned int anime : 2;
		unsigned int dark : 1;
		unsigned int pad : 12;
	};
};

struct g_game_w
{
	signed short state;
	signed short genre;
	music_info* mip;
	signed char start_chip;
	signed char extra_chip;
	signed char use_chip;
	signed char lost_chip;
	signed short stage;
	signed short next_stage;
	signed short failed;
	signed short level;
	signed char game_kind;
	signed char world;
	signed char nonstop;
	signed char event_mode;
	signed char style;
	signed char music_group;
	signed char music_select_mode;
	signed char extra_stage;
	signed char extra_fix;
	signed char final_fix;
	signed char meter_kind;
	signed char roulette_stage;
	signed char edit_total;
	signed char roulette_total;
	signed short music;
	signed char oni_mode;
	unsigned char oni_load_step;
	signed short oni_next_music;
	music_info* oni_next_mip;
	g_each_w player[2];
	signed char music_table[128];
	note_status note_status_table[300];
	_anon0 hc_work[8];
	signed int demoloop_ct;
	signed int mode_quit_ct[2];
	signed int force_exit_ct[2];
	signed int diet_play_time;
	signed int old_play_time;
	signed int menu_num;
	signed int total_stage;
	signed int now_bpm;
	unsigned char* last_data_addr;
	unsigned char edit_name[12];
	unsigned char diet_flg;
	unsigned char auto_play_flg;
	unsigned char caution_flg;
	unsigned char mode_quit_flg;
	unsigned char lib_loaded;
	unsigned char force_exit_flg;
	unsigned char music_stop_flg;
	unsigned char train_state;
	unsigned char lesson_flag;
	unsigned char lesson_auto_play_flag;
	unsigned char lesson_pad[2];
	unsigned char oni_load_start0;
	unsigned char oni_load_start1;
	unsigned char oni_load_end0;
	unsigned char oni_load_end1;
	unsigned char oni_order_step;
	unsigned char oni_order_stage;
	unsigned char oni_order_cursor;
	unsigned char oni_order_top_stage;
	unsigned char temp_sqk[2];
	unsigned char temp_pad[2];
	unsigned char endless_flag;
	unsigned char endless_pad[3];
};

struct _EDSS_PLAY_W
{
	_EDSS_DATA_W p_single[3];
	_EDSS_DATA_W p_double[3];
};

struct play_w
{
	signed int music_counter;
	signed int beat_counter;
	signed int cur_p_counter;
	signed int last_p_counter;
	signed int begin_beat_count;
	signed int go_beat_count;
	signed int finish_beat_count;
	signed int end_beat_count;
	signed int game_start_music_count;
	signed int game_finish_music_count;
	signed int back_trans_start_music_count;
	signed int last_fs_nct;
	signed short last_input_count[8];
	play_hist history[8];
	signed int cur_his;
	signed int pre_nct;
	signed int cur_nct;
	signed int disp_nct;
	signed int cur_great_combo;
	signed int cur_miss_combo;
	signed int max_great_combo;
	signed int max_miss_combo;
	signed int miss_start_count;
	unsigned short input;
	unsigned char dead;
	signed char strictness;
	signed short panel_count[8];
	signed short message_ct;
	signed short message_id;
	signed short meter_cur;
	signed short meter_vol;
	signed short meter_ct;
	signed short dance_class;
	signed int bar_start;
	signed int bar_end;
};

struct _EDSSAVE_W
{
	_EDSS_PLAY_W reg[2];
	_EDSS_DATA_W max_point;
	unsigned int PlayFlag[90];
};

struct _tag_cDDR7Option
{
	unsigned char Sound;
	unsigned char Voice;
	signed char Timing;
	char pad_sound[1];
	unsigned char KeyConfig[4];
	unsigned char Vibration;
	unsigned char DPlay;
	char pad_cont[2];
	unsigned char AutoSave;
	unsigned char FolderLoad;
	char pad_mc[2];
	unsigned char Level;
	unsigned char MaxStage[3];
	unsigned char GameOver;
	unsigned char TimeLimit;
	unsigned char EventMode;
	unsigned char DefaultDifficulty;
	char pad_game[8];
	unsigned char BgEffect;
	unsigned char BgBright;
	unsigned char DangerDisplay;
	unsigned char StepMarkColor;
	signed char screen_x;
	signed char screen_y;
	unsigned char FlickerFree;
	char pad_graphic[1];
	unsigned char DietMeasure;
	unsigned char DietDisplay;
	unsigned char DietTime;
	unsigned char DietPlayDefault;
	unsigned char DietWeightUnit;
	char pad_diet[3];
	unsigned char Language;
	char pad[15];
};

struct _InputBuffer
{
	unsigned long current_buffer;
	_InputData data[2];
};

struct popular
{
	signed short cur_c;
	signed short last_c;
	unsigned short count[4][150];
};

struct _tag_cDDR7SaveData
{
	_DDRCommonHeader CommonHeader;
	_tag_cDDR7Option Option;
	_tag_cDDR7Record1 MRecord[80];
	unsigned char Information[128];
	unsigned int nMusic;
	unsigned int nBoot;
	unsigned int nPlayerType[3];
	unsigned int nDifficulty[4];
	unsigned int HideFlag2;
	unsigned int nwork_pad[2];
	unsigned char LessonWork[32];
	_tag_cDDR7OniRecord1 OniRecord[32];
	unsigned int HideMusic[2];
	popular popular;
	G_RANKING_W_ high_score[30];
	machine_point_work machine_p;
	unsigned int HideFlag;
	_EDSSAVE_W EdsRecords;
	oni_course oni_order[3];
};

struct play_his
{
	signed short music;
	signed short edit_id;
	unsigned char seq_kind;
	signed char roulette;
	signed char extra;
	signed char pad;
};

struct G_RANKING_W_
{
	char name[4];
	unsigned long score;
};

struct g_each_w
{
	unsigned int play_time;
	unsigned int game_time;
	unsigned int game_time_total;
	signed char select;
	signed char character;
	signed char costume;
	signed char motiontype;
	signed char loaded_model;
	signed char loaded_texture;
	signed char loaded_motion;
	unsigned char play_disp_flag;
	unsigned char model_disp_flag;
	unsigned char gauge_disp_flag;
	signed short cur_point;
	signed int cur_life;
	unsigned int score;
	unsigned int old_score;
	unsigned int real_score;
	unsigned int bonus;
	unsigned int old_bonus;
	unsigned int max_score;
	unsigned int old_max_score;
	unsigned int max_bonus;
	unsigned int old_max_bonus;
	unsigned int cal;
	unsigned int old_cal;
	unsigned int real_cal;
	unsigned int disp_cal;
	unsigned int average_cal;
	signed int diet_norm_cal;
	signed int diet_norm_minute;
	signed int old_norm_cal;
	signed int old_norm_minute;
	signed int minimum_cal;
	unsigned char add_cal_flg;
	unsigned char chk_cal_flg;
	unsigned char pad[2];
	unsigned int play_stage;
	unsigned int decode_key1;
	unsigned int decode_key2;
	unsigned int decode_key3;
	play_mode mode;
	play_his his[7];
	eval_w stage_evaluation;
	eval_w total_evaluation;
	play_w play_work;
	signed int total_notes;
	signed int total_jump;
	signed int total_freez;
	signed int category;
	signed int total_category;
	sequence sequence_buff[6144];
};
</pre>
SLPM-65358 - DanceDanceRevolution EXTREME - 2003-07-24 Retail Build
<pre>
struct oni_course
{
	unsigned int course_allnum;
	unsigned int course_defnum;
	signed short avairable_level;
	signed short order;
	signed short start_life;
	signed short flag;
	unsigned int stage;
	signed int single_steps;
	signed int double_steps;
	oni_mode mode[20];
};

struct oni_mode
{
	unsigned int link_num;
	unsigned char seq_kind;
	unsigned char seq_transfer;
	unsigned char sp_music;
	unsigned char add_life;
	struct
	{
		unsigned int hidden : 2;
		unsigned int thinout : 1;
		unsigned int free : 1;
		unsigned int soft : 1;
		unsigned int boost : 2;
		unsigned int speed : 5;
		unsigned int scroll : 2;
		unsigned int freeze : 1;
		unsigned int vivid : 2;
		unsigned int anime : 2;
		unsigned int dark : 1;
		unsigned int pad : 12;
	};
};

struct tm
{
	signed int tm_sec;
	signed int tm_min;
	signed int tm_hour;
	signed int tm_mday;
	signed int tm_mon;
	signed int tm_year;
	signed int tm_wday;
	signed int tm_yday;
	signed int tm_isdst;
};

struct play_mode
{
	unsigned char seq_kind;
	unsigned char seq_transfer;
	unsigned char style;
	unsigned char pccard_seq;
	unsigned char mcard_seq;
	unsigned char padding;
	signed short edseq_id;
	struct
	{
		unsigned int hidden : 2;
		unsigned int thinout : 1;
		unsigned int free : 1;
		unsigned int soft : 1;
		unsigned int boost : 2;
		unsigned int speed : 5;
		unsigned int scroll : 2;
		unsigned int freeze : 1;
		unsigned int vivid : 2;
		unsigned int anime : 2;
		unsigned int dark : 1;
		unsigned int pad : 12;
	};
};

struct music_info
{
	char base_name[6];
	signed char kind;
	signed char album;
	signed short dance_num;
	signed short order;
	unsigned short main_track;
	unsigned short select_track;
	unsigned short bpm_max;
	unsigned short bpm_min;
	unsigned short verm_num;
	unsigned short pcseq_num;
	unsigned long hide;
	signed short adjust_mc;
	unsigned int difficulty[2];
	unsigned int special;
	unsigned short max_spm[9];
	unsigned short avg_spm[9];
	unsigned short avg_jpm[9];
	unsigned short chaos_v[9];
	unsigned short freez_v[9];
	char* title;
	char* l_name;
};

struct oni_cource_work
{
	signed int id;
	signed int init_ok;
	oni_course* course[75];
	signed int tex_kind;
	signed int tex_load_step;
	unsigned char seqkind_tab[20];
	signed int dancer_flag;
};

struct oni_steps
{
	unsigned int link_num;
	unsigned short steps[4][2];
};

struct _EDSS_DATA_W
{
	unsigned int score[2];
	signed int combo;
	signed int stage;
};

struct eval_w
{
	signed int value_ct[8];
	signed int freez_value_ct[4];
	signed int groov_bonus[6];
	signed int groov_bonus_max[6];
	signed int score;
	signed int max_combo_ct;
	signed int jump_ct;
	signed short dance_level;
	signed short fixed_level;
};

struct _tag_cDDR8Option
{
	unsigned char Sound;
	unsigned char Voice;
	signed char Timing;
	char pad_sound[1];
	unsigned char KeyConfig[4];
	unsigned char Vibration;
	unsigned char DPlay;
	char pad_cont[2];
	unsigned char AutoSave;
	unsigned char FolderLoad;
	char pad_mc[2];
	unsigned char Level;
	unsigned char MaxStage[3];
	unsigned char GameOver;
	unsigned char TimeLimit;
	unsigned char EventMode;
	unsigned char DefaultDifficulty;
	char pad_game[8];
	unsigned char BgEffect;
	unsigned char BgBright;
	unsigned char DangerDisplay;
	unsigned char StepMarkColor;
	signed char screen_x;
	signed char screen_y;
	unsigned char FlickerFree;
	char pad_graphic[1];
	unsigned char DietMeasure;
	unsigned char DietDisplay;
	unsigned char DietTime;
	unsigned char DietPlayDefault;
	unsigned char DietWeightUnit;
	char pad_diet[3];
	unsigned char Language;
	char pad_lang[7];
	unsigned char DollDisp;
	unsigned char DollGuestNum;
	unsigned char DollChara[3];
	char pad[3];
};

struct _EDSS_PLAY_W
{
	_EDSS_DATA_W p_single[3];
	_EDSS_DATA_W p_double[3];
};

struct note_status
{
	unsigned char state[8];
	unsigned int length[8];
};

struct play_hist
{
	signed int music_count;
	unsigned char input[8];
};

struct _EDSSAVE_W
{
	_EDSS_PLAY_W reg[2];
	_EDSS_DATA_W max_point;
	unsigned int PlayFlag[128];
};

struct G_INPUT_W_
{
	_InputData* dp;
	_InputBuffer buffer;
};

struct _InputData
{
	unsigned short player_input[4];
	unsigned short player_input_trigger[4];
	unsigned short player_input_released[4];
	unsigned short etc;
	unsigned short etc_trigger;
	unsigned short etc_released;
	unsigned short padding;
};

struct _anon0
{
	unsigned int program_calorie[13];
	unsigned int program_play_count[13];
	unsigned int song_calorie[5][120];
	unsigned int song_play_count[5][120];
};

struct G_SYS_W_
{
	G_INPUT_W_ input_w;
	tm start_tm;
	unsigned int v_counter;
	unsigned long v_counter2;
	unsigned int s_counter;
	signed int u_counter;
	signed int read_time;
	unsigned char read_flag;
	unsigned char entry_bit;
	char vpf;
	char pad[2];
};

struct sequence
{
	signed int beat_count;
	signed short kind;
	signed short next_change;
	signed short music_count;
	signed short judge_count;
	signed short stolen_count;
	signed short op_note_ct;
	unsigned int hold_length[8];
	unsigned char hold_stat[8];
};

struct popular
{
	signed short cur_c;
	signed short last_c;
	unsigned short count[4][256];
};

struct G_RANKING_W_
{
	char name[4];
	unsigned long score;
};

struct _anon1
{
	unsigned char old_stat;
	unsigned char cur_stat;
	unsigned char release_ct;
	unsigned char warning;
};

struct _tag_cDDR8SaveData
{
	_DDRCommonHeader CommonHeader;
	_tag_cDDR8Option Option;
	_tag_cDDR8Record1 MRecord[120];
	unsigned char Information[256];
	unsigned int nMusic;
	unsigned int nBoot;
	unsigned int nPlayerType[3];
	unsigned int nDifficulty[5];
	signed int nwork[3];
	unsigned char LessonWork[32];
	_tag_cDDR8OniRecord1 OniRecord[33];
	_tag_cDDR8OniRecord1 NonstopRecord[56];
	popular popular;
	G_RANKING_W_ high_score[40];
	unsigned int HideFlag[2];
	unsigned int HideDoll[2];
	unsigned char HideDollWk[4];
	_EDSSAVE_W EdsRecords;
	oni_course oni_order[3];
	oni_course nonstop_order[3];
	oni_course dietprogram_order[3];
	_anon0 diet_calorie_record[2];
	unsigned int nMusic_on_last_unlocked;
};

struct _tag_cDDR8OniRecord1
{
	unsigned int Time[2];
	unsigned int Score[2];
	unsigned short Combo[2];
	unsigned char Stage[2];
	unsigned char Miss[2];
	unsigned char AllStage[2];
	unsigned char Level[2];
	unsigned char is_first_clear;
	unsigned char pad[3];
	unsigned short ClearNum[2];
	unsigned char pad2[2];
};

struct g_game_w
{
	signed short state;
	signed short genre;
	music_info* mip;
	signed char start_chip;
	signed char extra_chip;
	signed char use_chip;
	signed char lost_chip;
	signed short stage;
	signed short next_stage;
	signed short failed;
	signed short level;
	signed char game_kind;
	signed char world;
	signed char oni_nonstop_course_id;
	signed char event_mode;
	signed char event_two_flag;
	signed char style;
	signed char music_group;
	signed char music_select_mode;
	signed char extra_stage;
	signed char extra_fix;
	signed char final_fix;
	signed char meter_kind;
	signed char roulette_stage;
	signed char edit_total;
	signed char roulette_total;
	signed short music;
	signed char oni_nonstop_mode;
	unsigned char oni_load_step;
	signed char oni_nonstop_difficulty;
	signed char oni_pad;
	signed char beginner_mode;
	signed char beginner_selected;
	signed char freez_selected;
	signed char beginner_pad[1];
	signed short oni_next_music;
	music_info* oni_next_mip;
	g_each_w player[2];
	signed char music_table[128];
	note_status note_status_table[300];
	_anon1 hc_work[8];
	signed int demoloop_ct;
	signed int mode_quit_ct[2];
	signed int force_exit_ct[2];
	signed int diet_play_time;
	signed int old_play_time;
	signed int menu_num;
	signed int total_stage;
	signed int now_bpm;
	unsigned char* last_data_addr;
	unsigned char edit_name[12];
	unsigned char diet_flg;
	unsigned char auto_play_flg;
	unsigned char caution_flg;
	unsigned char mode_quit_flg;
	unsigned char lib_loaded;
	unsigned char force_exit_flg;
	unsigned char music_stop_flg;
	unsigned char train_state;
	unsigned char lesson_flag;
	unsigned char lesson_auto_play_flag;
	unsigned char lesson_pad[2];
	unsigned char oni_load_start0;
	unsigned char oni_load_start1;
	unsigned char oni_load_end0;
	unsigned char oni_load_end1;
	unsigned char oni_order_step;
	unsigned char oni_order_stage;
	unsigned char oni_order_cursor;
	unsigned char oni_order_top_stage;
	unsigned char anime1_load_flg;
	unsigned char anime2_load_flg;
	unsigned char temp_sqk[2];
	unsigned char endless_flag;
	unsigned char endless_pad[3];
	signed char __pad[2];
	signed int rloadtex_num;
	signed int rload_next_step;
	char nonstop_selopt_flag;
};

struct play_w
{
	signed int music_counter;
	signed int beat_counter;
	signed int cur_p_counter;
	signed int last_p_counter;
	signed int begin_beat_count;
	signed int go_beat_count;
	signed int finish_beat_count;
	signed int end_beat_count;
	signed int game_start_music_count;
	signed int game_finish_music_count;
	signed int back_trans_start_music_count;
	signed int last_fs_nct;
	signed short last_input_count[8];
	play_hist history[8];
	signed int cur_his;
	signed int pre_nct;
	signed int cur_nct;
	signed int disp_nct;
	signed int cur_great_combo;
	signed int cur_miss_combo;
	signed int max_great_combo;
	signed int max_miss_combo;
	signed int miss_start_count;
	signed int cur_great_combo_total;
	signed int max_great_combo_total;
	unsigned short input;
	unsigned char dead;
	signed char strictness;
	signed short panel_count[8];
	signed short message_ct;
	signed short message_id;
	signed short meter_cur;
	signed short meter_vol;
	signed short meter_ct;
	signed short dance_class;
	signed int bar_start;
	signed int bar_end;
};

struct _InputBuffer
{
	unsigned long current_buffer;
	_InputData data[2];
};

struct play_his
{
	signed short music;
	signed short edit_id;
	unsigned char seq_kind;
	signed char roulette;
	signed char extra;
	signed char pad;
};

struct _tag_cDDR8Record1
{
	unsigned int Score[10];
	unsigned int Bonus[10];
	unsigned int nPlayed;
	unsigned short LinkNum;
	unsigned short Combo[10];
	unsigned short ComboMax[10];
	unsigned char Level[10];
	unsigned char pad[2];
};

struct g_each_w
{
	unsigned int play_time;
	unsigned int game_time;
	unsigned int game_time_total;
	signed char select;
	signed char character;
	signed char costume;
	signed char motiontype;
	signed char loaded_model;
	signed char loaded_texture;
	signed char loaded_motion;
	unsigned char play_disp_flag;
	unsigned char model_disp_flag;
	unsigned char gauge_disp_flag;
	signed short cur_point;
	signed int cur_life;
	unsigned int score;
	unsigned int old_score;
	unsigned int real_score;
	unsigned int bonus;
	unsigned int old_bonus;
	unsigned int max_score;
	unsigned int old_max_score;
	unsigned int max_bonus;
	unsigned int old_max_bonus;
	unsigned int cal;
	unsigned int old_cal;
	unsigned int real_cal;
	unsigned int disp_cal;
	unsigned int average_cal;
	signed int diet_norm_cal;
	signed int diet_norm_minute;
	signed int old_norm_cal;
	signed int old_norm_minute;
	signed int minimum_cal;
	unsigned char add_cal_flg;
	unsigned char chk_cal_flg;
	unsigned char pad[2];
	unsigned int play_stage;
	unsigned int decode_key1;
	unsigned int decode_key2;
	unsigned int decode_key3;
	signed int used_unfair_command;
	signed int nonstop_dead_flag;
	play_mode mode;
	play_his his[7];
	eval_w stage_evaluation;
	eval_w total_evaluation;
	play_w play_work;
	signed int total_notes;
	signed int total_jump;
	signed int total_freez;
	signed int category;
	signed int total_category;
	sequence sequence_buff[6144];
};

struct _DDRCommonHeader
{
	unsigned char Type;
	unsigned char Platform;
	unsigned char Hardware;
	unsigned char Version;
	unsigned char Area;
	signed char tmp;
	unsigned short title;
	unsigned int t_info[2];
};

struct _anon2
{
	struct
	{
		unsigned long number : 16;
		unsigned long sector : 24;
		unsigned long size : 24;
	};
};
</pre>
SLPM-65775 - DDR Festival -DanceDanceRevolution- - 2004-09-30 Retail Build
<pre>
struct oni_course
{
	unsigned int course_allnum;
	unsigned int course_defnum;
	signed short avairable_level;
	signed short order;
	signed short start_life;
	signed short flag;
	unsigned int stage;
	signed int single_steps;
	signed int double_steps;
	oni_mode mode[20];
};

struct oni_mode
{
	unsigned int link_num;
	unsigned char seq_kind;
	unsigned char seq_transfer;
	unsigned char sp_music;
	unsigned char add_life;
	struct
	{
		unsigned int hidden : 2;
		unsigned int thinout : 1;
		unsigned int free : 1;
		unsigned int soft : 1;
		unsigned int boost : 2;
		unsigned int speed : 5;
		unsigned int scroll : 2;
		unsigned int freeze : 1;
		unsigned int vivid : 2;
		unsigned int anime : 2;
		unsigned int dark : 1;
		unsigned int pad : 12;
	};
};

struct music_info
{
	char base_name[6];
	signed char kind;
	signed char album;
	signed short dance_num;
	signed short order;
	unsigned int main_track;
	unsigned int select_track;
	unsigned short bpm_max;
	unsigned short bpm_min;
	unsigned short verm_num;
	unsigned short pcseq_num;
	unsigned long hide;
	signed short adjust_mc;
	unsigned int difficulty[2];
	unsigned int special;
	unsigned short max_spm[9];
	unsigned short avg_spm[9];
	unsigned short avg_jpm[9];
	unsigned short chaos_v[9];
	unsigned short freez_v[9];
	char* title;
	char* l_name;
};

struct _anon0
{
	unsigned int program_calorie[6];
	unsigned int program_play_count[6];
	unsigned int song_calorie[5][80];
	unsigned int song_play_count[5][80];
};

struct play_w
{
	signed int music_counter;
	signed int beat_counter;
	signed int cur_p_counter;
	signed int last_p_counter;
	signed int begin_beat_count;
	signed int go_beat_count;
	signed int finish_beat_count;
	signed int end_beat_count;
	signed int game_start_music_count;
	signed int game_finish_music_count;
	signed int back_trans_start_music_count;
	signed int last_fs_nct;
	signed short last_input_count[8];
	play_hist history[8];
	signed int cur_his;
	signed int pre_nct;
	signed int cur_nct;
	signed int disp_nct;
	signed int cur_great_combo;
	signed int cur_miss_combo;
	signed int max_great_combo;
	signed int max_miss_combo;
	signed int miss_start_count;
	signed int cur_great_combo_total;
	signed int max_great_combo_total;
	unsigned short input;
	unsigned char dead;
	signed char strictness;
	signed short panel_count[8];
	signed short message_ct;
	signed short message_id;
	signed short meter_cur;
	signed short meter_vol;
	signed short meter_ct;
	signed short offset;
	signed short light_offset;
	signed short meter_state;
	signed short anm_no;
	signed short dance_class;
	signed int bar_start;
	signed int bar_end;
};

struct eval_w
{
	signed int value_ct[8];
	signed int freez_value_ct[4];
	signed int groov_bonus[6];
	signed int groov_bonus_max[6];
	signed int score;
	signed int bonus;
	signed int max_combo_ct;
	signed int jump_ct;
	signed short dance_level;
	signed short fixed_level;
};

struct oni_cource_work
{
	signed int id;
	signed int init_ok;
	oni_course* course[37];
	signed int tex_kind;
	signed int tex_load_step;
	unsigned char seqkind_tab[20];
	signed int dancer_flag;
};

struct sequence
{
	signed int beat_count;
	signed short kind;
	signed short next_change;
	signed short music_count;
	signed short judge_count;
	signed short stolen_count;
	signed short op_note_ct;
	unsigned int hold_length[8];
	unsigned char hold_stat[8];
};

struct play_mode
{
	unsigned char seq_kind;
	unsigned char seq_transfer;
	unsigned char style;
	unsigned char pccard_seq;
	unsigned char mcard_seq;
	unsigned char padding;
	signed short edseq_id;
	struct
	{
		unsigned int hidden : 3;
		unsigned int thinout : 1;
		unsigned int free : 1;
		unsigned int soft : 1;
		unsigned int boost : 2;
		unsigned int speed : 5;
		unsigned int scroll : 2;
		unsigned int freeze : 1;
		unsigned int vivid : 2;
		unsigned int anime : 2;
		unsigned int dark : 1;
	};
	unsigned int pad : 12;
};

struct popular
{
	signed short cur_c;
	signed short last_c;
	unsigned short count[4][256];
};

struct _anon1
{
	struct
	{
		unsigned long number : 16;
		unsigned long sector : 24;
		unsigned long size : 24;
	};
};

struct G_RANKING_W_
{
	char name[4];
	unsigned long score;
};

struct _tag_cMWMgRunRecord
{
	signed int time;
	unsigned char bcd_time;
	unsigned char bcd_type;
	unsigned char fps;
	char pad[1];
};

struct _tag_cDDR8Record1
{
	unsigned int Score[10];
	unsigned int Bonus[10];
	unsigned int nPlayed;
	unsigned short LinkNum;
	unsigned short Combo[10];
	unsigned short ComboMax[10];
	unsigned char Level[10];
	unsigned char pad[2];
};

struct _tag_cMWMgRun
{
	_tag_cMWMgRunRecord record;
	char pad[8];
};

struct _tag_cDDR8OniRecord1
{
	unsigned int Time[2];
	unsigned int Score[2];
	unsigned short Combo[2];
	unsigned char Stage[2];
	unsigned char Miss[2];
	unsigned char AllStage[2];
	unsigned char Level[2];
	unsigned char is_first_clear;
	unsigned char is_full_combo_flag[2];
	unsigned char pad[1];
	unsigned short ClearNum[2];
	unsigned char pad2[2];
};

struct _eyetoy_option
{
	char depth;
	char pdf;
	char frame;
	unsigned char bright;
};

struct _InputData
{
	unsigned short player_input[4];
	unsigned short player_input_trigger[4];
	unsigned short player_input_released[4];
	unsigned short etc;
	unsigned short etc_trigger;
	unsigned short etc_released;
	unsigned short padding;
};

struct _anon2
{
	unsigned char old_stat;
	unsigned char cur_stat;
	unsigned char release_ct;
	unsigned char warning;
};

struct _mg_block
{
	signed int hi_score;
};

struct _DDRCommonHeader
{
	unsigned char Type;
	unsigned char Platform;
	unsigned char Hardware;
	unsigned char Version;
	unsigned char Area;
	signed char tmp;
	unsigned short title;
	unsigned int t_info[2];
};

struct _play_backup_w
{
	eval_w stage_evaluation;
	eval_w total_evaluation;
	play_mode mode;
	play_his his[7];
	unsigned int play_stage;
};

struct _InputBuffer
{
	unsigned long current_buffer;
	_InputData data[2];
};

struct _mg_coco
{
	signed int hi_score;
};

struct _anon3
{
	signed int hi_score;
};

struct _tag_cDDR8Option
{
	unsigned char Sound;
	unsigned char Voice;
	signed char Timing;
	char pad_sound[1];
	char EditKey[24];
	unsigned char KeyConfig[4];
	unsigned char DModeSet;
	unsigned char Vibration;
	unsigned char DPlay;
	char pad_cont[1];
	unsigned char AutoSave;
	unsigned char FolderLoad;
	char pad_mc[2];
	unsigned char Level;
	unsigned char MaxStage[3];
	unsigned char GameOver;
	unsigned char TimeLimit;
	unsigned char EventMode;
	unsigned char DefaultDifficulty;
	char pad_game[8];
	unsigned char BgEffect;
	unsigned char BgBright;
	unsigned char DangerDisplay;
	unsigned char StepMarkColor;
	signed char screen_x;
	signed char screen_y;
	unsigned char FlickerFree;
	char pad_graphic[1];
	unsigned char DietMeasure;
	unsigned char DietDisplay;
	unsigned char DietTime;
	unsigned char DietPlayDefault;
	unsigned char DietWeightUnit;
	char pad_diet[3];
	unsigned char Language;
	char pad_lang[7];
	unsigned char DollDisp;
	unsigned char DollChara[3];
	unsigned char DollGuestNum;
	unsigned char DollSelect;
	char pad[2];
};

struct _backup_w
{
	_play_backup_w player[2];
	signed char stage;
	signed char start_chip;
	signed char extra_chip;
	signed char use_chip;
	signed char lost_chip;
};

struct _tag_cDDRFInfoData
{
	unsigned char Information[256];
	signed int UnlockedNum[256];
	signed int unum;
	char pad[12];
};

struct _EDSS_DATA_W
{
	unsigned int score[2];
	signed int combo;
	signed int stage;
};

struct play_his
{
	signed short music;
	signed short edit_id;
	unsigned char seq_kind;
	signed char roulette;
	signed char extra;
	signed char pad;
};

struct _EDSS_PLAY_W
{
	_EDSS_DATA_W p_single[3];
	_EDSS_DATA_W p_double[3];
};

struct _tag_cDDR8SaveData
{
	_DDRCommonHeader CommonHeader;
	_tag_cDDR8Option Option;
	_tag_cDDR8Record1 MRecord[80];
	_tag_cDDRFInfoData InfoData;
	unsigned int nMusic;
	unsigned int nBoot;
	unsigned int nPlayerType[3];
	unsigned int nDifficulty[5];
	signed int nwork[3];
	unsigned char LessonWork[32];
	_tag_cDDR8OniRecord1 OniRecord[15];
	_tag_cDDR8OniRecord1 NonstopRecord[30];
	popular popular;
	G_RANKING_W_ high_score[40];
	unsigned int HideFlag[3];
	unsigned int HideNewFlag[3];
	unsigned int HideDoll[2];
	unsigned int HideNewDoll[2];
	unsigned char HideDollWk[4];
	_EDSSAVE_W EdsRecords;
	_anon8 challenge;
	oni_course oni_order[3];
	oni_course nonstop_order[3];
	oni_course dietprogram_order[3];
	_anon0 diet_calorie_record[2];
	_tag_cMWMgRun mg_run;
	unsigned int nMusic_on_last_unlocked;
	_eyetoy_option eyetoy_option;
	_mg_block mg_block;
	_mg_coco mg_coco;
	_anon3 mg_eat;
	_tag_cDDR8Record1 mg_solo_MRecord[80];
	_anon9 wk_save[2];
};

struct _EDSSAVE_W
{
	_EDSS_PLAY_W reg[2];
	unsigned int PlayFlag[128];
};

struct tm
{
	signed int tm_sec;
	signed int tm_min;
	signed int tm_hour;
	signed int tm_mday;
	signed int tm_mon;
	signed int tm_year;
	signed int tm_wday;
	signed int tm_yday;
	signed int tm_isdst;
};

struct play_hist
{
	signed int music_count;
	unsigned char input[8];
};

struct g_each_w
{
	unsigned int play_time;
	unsigned int game_time;
	unsigned int game_time_total;
	signed char select;
	signed char character;
	signed char costume;
	signed char motiontype;
	signed char loaded_model;
	signed char loaded_texture;
	signed char loaded_motion;
	unsigned char play_disp_flag;
	unsigned char model_disp_flag;
	unsigned char gauge_disp_flag;
	signed short cur_point;
	signed int cur_life;
	unsigned int score;
	unsigned int old_score;
	unsigned int real_score;
	unsigned int bonus;
	unsigned int old_bonus;
	unsigned int max_score;
	unsigned int old_max_score;
	unsigned int max_bonus;
	unsigned int old_max_bonus;
	unsigned int cal;
	unsigned int old_cal;
	unsigned int real_cal;
	unsigned int disp_cal;
	unsigned int average_cal;
	signed int diet_norm_cal;
	signed int diet_norm_minute;
	signed int old_norm_cal;
	signed int old_norm_minute;
	signed int minimum_cal;
	unsigned char add_cal_flg;
	unsigned char chk_cal_flg;
	unsigned char combo_no_disp_flag;
	unsigned char pad;
	unsigned int play_stage;
	unsigned int decode_key1;
	unsigned int decode_key2;
	unsigned int decode_key3;
	signed int used_unfair_command;
	signed int nonstop_dead_flag;
	play_mode mode;
	play_his his[7];
	eval_w stage_evaluation;
	eval_w total_evaluation;
	play_w play_work;
	signed int total_notes;
	signed int total_jump;
	signed int total_freez;
	signed int category;
	signed int total_category;
	sequence sequence_buff[6144];
	signed int total_notes_all;
	signed int total_freez_all;
};

struct G_INPUT_W_
{
	_InputData* dp;
	_InputBuffer buffer;
};

union _anon4
{
	signed int id;
	float fd;
};

struct _anon5
{
	_anon7 line_a[8];
	_anon7 line_b[8];
	_anon7 line_c[8];
	signed int num;
};

struct _anon6
{
	unsigned char state;
	unsigned char perfect;
	unsigned short play_count;
	unsigned short play_time;
	unsigned short clear_count;
	unsigned short first_clear_count;
	unsigned short first_clear_time;
};

struct G_SYS_W_
{
	G_INPUT_W_ input_w;
	tm start_tm;
	unsigned int v_counter;
	unsigned long v_counter2;
	unsigned int s_counter;
	signed int u_counter;
	signed int read_time;
	signed int start_time;
	unsigned char read_flag;
	unsigned char entry_bit;
	char vpf;
	char pad[2];
};

struct _anon7
{
	_anon4 x0;
	_anon4 y0;
	unsigned int z0;
	unsigned char r0;
	unsigned char g0;
	unsigned char b0;
	unsigned char a0;
};

struct g_game_w
{
	signed short state;
	signed short genre;
	music_info* mip;
	signed char start_chip;
	signed char extra_chip;
	signed char use_chip;
	signed char lost_chip;
	signed short stage;
	signed short next_stage;
	signed short failed;
	signed short level;
	signed char game_kind;
	signed char world;
	signed char oni_nonstop_course_id;
	signed char event_mode;
	signed char event_two_flag;
	signed char style;
	signed char music_group;
	signed char music_select_mode;
	signed char extra_stage;
	signed char extra_fix;
	signed char final_fix;
	signed char meter_kind;
	signed char roulette_stage;
	signed char edit_total;
	signed char roulette_total;
	signed short music;
	signed char oni_nonstop_mode;
	unsigned char oni_load_step;
	signed char oni_nonstop_difficulty;
	signed char use_oni_gauge;
	signed char beginner_mode;
	signed char beginner_selected;
	signed char freez_selected;
	signed char judge_invalid;
	signed short oni_next_music;
	music_info* oni_next_mip;
	g_each_w player[2];
	signed char music_table[128];
	note_status note_status_table[300];
	_anon2 hc_work[8];
	signed int demoloop_ct;
	signed int mode_quit_ct[2];
	signed int force_exit_ct[2];
	signed int diet_play_time;
	signed int old_play_time;
	signed int menu_num;
	signed int total_stage;
	signed int now_bpm;
	unsigned char* last_data_addr;
	unsigned char edit_name[12];
	unsigned char diet_flg;
	unsigned char workout_step_flg;
	unsigned char auto_play_flg;
	unsigned char caution_flg;
	unsigned char mode_quit_flg;
	unsigned char lib_loaded;
	unsigned char force_exit_flg;
	unsigned char train_state;
	unsigned char lesson_flag;
	unsigned char lesson_auto_play_flag;
	unsigned char lesson_pad[2];
	unsigned char oni_load_start0;
	unsigned char oni_load_start1;
	unsigned char oni_load_end0;
	unsigned char oni_load_end1;
	unsigned char oni_order_step;
	unsigned char oni_order_stage;
	unsigned char oni_order_cursor;
	unsigned char oni_order_top_stage;
	unsigned char oni_order_selopt;
	unsigned char anime1_load_flg;
	unsigned char anime2_load_flg;
	unsigned char temp_sqk[2];
	unsigned char endless_flag;
	unsigned char eyetoy_flag;
	unsigned char challenge_flag;
	unsigned char step_mark_color;
	unsigned char hand_solo_seq_kind;
	unsigned char is_course_exit;
	unsigned char to_opt_select;
	unsigned char is_new_clothes;
	unsigned char mode_select_beginner;
	unsigned char nononi_msel_flag;
	unsigned char select_randaom_flag;
	unsigned char lib_sel_num;
	unsigned int bar_state;
	signed int rloadtex_num;
	signed int rload_next_step;
	_backup_w backup;
	char quit_course_flag;
	char nonstop_selopt_flag;
	unsigned char dancer_id[3];
	_anon5 line_data[16];
	signed int line_speed;
	signed int bk_ef_kind;
	signed int bk_ef_colset[3];
	signed int bk_ef_type;
	signed int bk_ef_reset;
	signed int event_result_exit_flag;
	signed int party_mode_flag;
	signed int eyetoy_catchy_flag;
	signed int eyetoy_movie_flag;
};

struct _anon8
{
	unsigned char appear;
	unsigned char ending_flag;
	signed char help_count;
	unsigned char pad;
	signed int bonus_count;
	signed int dummy[2];
	_anon6 subject[100];
};

struct note_status
{
	unsigned char state[8];
	unsigned int length[8];
};

struct _anon9
{
	unsigned char game_over;
	unsigned char calorie_check;
	unsigned char pad[2];
};
</pre>
SLUS-20437 - DDRMAX -DanceDanceRevolution- - 2002-09-15 Retail Build
<pre>
struct oni_course
{
	unsigned int course_allnum;
	unsigned int course_defnum;
	signed short avairable_level;
	signed short order;
	signed short start_life;
	signed short pad;
	signed int single_steps;
	signed int double_steps;
	char* coursename;
	oni_mode mode[1];
};

struct oni_cource_work
{
	signed int id;
	signed int init_ok;
	oni_course* course[64];
};

struct music_info
{
	char base_name[6];
	signed char kind;
	signed char album;
	signed short dance_num;
	signed short order;
	unsigned short main_track;
	unsigned short select_track;
	unsigned short bpm_max;
	unsigned short bpm_min;
	unsigned short verm_num;
	unsigned short pcseq_num;
	unsigned long hide;
	signed short adjust_mc;
	unsigned int difficulty[2];
	unsigned int special;
	unsigned short max_spm[6];
	unsigned short avg_spm[6];
	unsigned short avg_jpm[6];
	unsigned short chaos_v[6];
	unsigned short freez_v[6];
	char* title;
	char* l_name;
};

struct _anon0
{
	unsigned char old_stat;
	unsigned char cur_stat;
	unsigned char release_ct;
	unsigned char warning;
};

struct play_mode
{
	unsigned char seq_kind;
	unsigned char seq_transfer;
	unsigned char style;
	unsigned char pccard_seq;
	unsigned char mcard_seq;
	signed short edseq_id;
	struct
	{
		unsigned int hidden : 2;
		unsigned int thinout : 1;
		unsigned int free : 1;
		unsigned int soft : 1;
		unsigned int boost : 1;
		unsigned int speed : 5;
		unsigned int scroll : 2;
		unsigned int freeze : 1;
		unsigned int vivid : 2;
		unsigned int anime : 2;
		unsigned int pad : 14;
	};
};

struct play_w
{
	signed int music_counter;
	signed int beat_counter;
	signed int cur_p_counter;
	signed int last_p_counter;
	signed int begin_beat_count;
	signed int go_beat_count;
	signed int finish_beat_count;
	signed int end_beat_count;
	signed int game_start_music_count;
	signed int game_finish_music_count;
	signed int back_trans_start_music_count;
	signed int last_fs_nct;
	signed short last_input_count[8];
	play_hist history[8];
	signed int cur_his;
	signed int pre_nct;
	signed int cur_nct;
	signed int disp_nct;
	signed int cur_great_combo;
	signed int cur_miss_combo;
	signed int max_great_combo;
	signed int max_miss_combo;
	signed int miss_start_count;
	unsigned short input;
	unsigned char dead;
	signed char strictness;
	signed short panel_count[8];
	signed short message_ct;
	signed short message_id;
	signed short meter_cur;
	signed short meter_vol;
	signed short meter_ct;
	signed short dance_class;
	signed int bar_start;
	signed int bar_end;
};

struct g_game_w
{
	signed short state;
	signed short genre;
	music_info* mip;
	signed char start_chip;
	signed char extra_chip;
	signed char use_chip;
	signed char lost_chip;
	signed short stage;
	signed short next_stage;
	signed short failed;
	signed short level;
	signed char game_kind;
	signed char world;
	signed char nonstop;
	signed char event_mode;
	signed char style;
	signed char music_group;
	signed char music_select_mode;
	signed char extra_stage;
	signed char extra_fix;
	signed char final_fix;
	signed char meter_kind;
	signed char roulette_stage;
	signed char edit_total;
	signed char roulette_total;
	signed short music;
	signed char oni_mode;
	unsigned char oni_load_step;
	signed short oni_next_music;
	music_info* oni_next_mip;
	g_each_w player[2];
	signed char music_table[128];
	note_status note_status_table[300];
	_anon0 hc_work[8];
	signed int demoloop_ct;
	signed int mode_quit_ct[2];
	signed int force_exit_ct[2];
	signed int diet_play_time;
	signed int old_play_time;
	signed int menu_num;
	signed int total_stage;
	signed int now_bpm;
	unsigned char* last_data_addr;
	unsigned char edit_name[12];
	unsigned char diet_flg;
	unsigned char auto_play_flg;
	unsigned char caution_flg;
	unsigned char mode_quit_flg;
	unsigned char lib_loaded;
	unsigned char force_exit_flg;
	unsigned char music_stop_flg;
	unsigned char train_state;
	unsigned char lesson_flag;
	unsigned char lesson_auto_play_flag;
	unsigned char oni_bk_bright;
	unsigned char cs_pad[1];
	unsigned char oni_load_start0;
	unsigned char oni_load_start1;
	unsigned char oni_load_end0;
	unsigned char oni_load_end1;
};

struct play_his
{
	signed short music;
	signed int edit_id;
	unsigned char seq_kind;
	signed char roulette;
	signed char extra;
	signed char pad;
};

struct oni_mode
{
	music_info* mip;
	unsigned char seq_kind;
	unsigned char seq_transfer;
	unsigned char sp_music;
	unsigned char add_life;
	struct
	{
		unsigned int hidden : 2;
		unsigned int thinout : 1;
		unsigned int free : 1;
		unsigned int soft : 1;
		unsigned int boost : 1;
		unsigned int speed : 5;
		unsigned int scroll : 2;
		unsigned int freeze : 1;
		unsigned int vivid : 2;
		unsigned int anime : 2;
		unsigned int pad : 14;
	};
};

struct g_each_w
{
	unsigned int play_time;
	unsigned int game_time;
	unsigned int game_time_total;
	signed char select;
	signed char character;
	signed char costume;
	signed char motiontype;
	signed char loaded_model;
	signed char loaded_texture;
	signed char loaded_motion;
	unsigned char play_disp_flag;
	unsigned char model_disp_flag;
	unsigned char gauge_disp_flag;
	signed short cur_point;
	signed int cur_life;
	unsigned int score;
	unsigned int old_score;
	unsigned int real_score;
	unsigned int bonus;
	unsigned int old_bonus;
	unsigned int max_score;
	unsigned int old_max_score;
	unsigned int max_bonus;
	unsigned int old_max_bonus;
	unsigned int cal;
	unsigned int old_cal;
	unsigned int real_cal;
	unsigned int disp_cal;
	unsigned int average_cal;
	signed int diet_norm_cal;
	signed int diet_norm_minute;
	signed int old_norm_cal;
	signed int old_norm_minute;
	signed int minimum_cal;
	unsigned char add_cal_flg;
	unsigned char chk_cal_flg;
	unsigned char pad[2];
	unsigned int play_stage;
	unsigned int decode_key1;
	unsigned int decode_key2;
	unsigned int decode_key3;
	play_mode mode;
	play_his his[7];
	eval_w stage_evaluation;
	eval_w total_evaluation;
	play_w play_work;
	signed int total_notes;
	signed int total_jump;
	signed int total_freez;
	signed int category;
	signed int total_category;
	sequence sequence_buff[6144];
};

struct G_INPUT_W_
{
	_InputData* dp;
	_InputBuffer buffer;
};

struct _InputData
{
	unsigned short player_input[4];
	unsigned short player_input_trigger[4];
	unsigned short player_input_released[4];
	unsigned short etc;
	unsigned short etc_trigger;
	unsigned short etc_released;
	unsigned short padding;
};

struct note_status
{
	unsigned char state[8];
	unsigned int length[8];
};

struct G_SYS_W_
{
	G_INPUT_W_ input_w;
	tm start_tm;
	unsigned int v_counter;
	unsigned int s_counter;
	signed int u_counter;
	unsigned char entry_bit;
	char vpf;
	char pad[2];
};

struct tm
{
	signed int tm_sec;
	signed int tm_min;
	signed int tm_hour;
	signed int tm_mday;
	signed int tm_mon;
	signed int tm_year;
	signed int tm_wday;
	signed int tm_yday;
	signed int tm_isdst;
};

struct sequence
{
	signed int beat_count;
	signed short kind;
	signed short next_change;
	signed short music_count;
	signed short judge_count;
	signed short stolen_count;
	signed short op_note_ct;
	unsigned int hold_length[8];
	unsigned char hold_stat[8];
};

struct play_hist
{
	signed int music_count;
	unsigned char input[8];
};

struct _InputBuffer
{
	unsigned long current_buffer;
	_InputData data[2];
};

struct eval_w
{
	signed int value_ct[7];
	signed int freez_value_ct[3];
	signed int groov_bonus[6];
	signed int groov_bonus_max[6];
	signed int score;
	signed int max_combo_ct;
	signed int jump_ct;
	signed short dance_level;
	signed short fixed_level;
};
</pre>
SLUS-20711 - DDRMAX2 -DanceDanceRevolution- - 2003-07-22 Retail Build
<pre>
struct oni_mode
{
	unsigned int link_num;
	unsigned char seq_kind;
	unsigned char seq_transfer;
	unsigned char sp_music;
	unsigned char add_life;
	struct
	{
		unsigned int hidden : 2;
		unsigned int thinout : 1;
		unsigned int free : 1;
		unsigned int soft : 1;
		unsigned int boost : 2;
		unsigned int speed : 5;
		unsigned int scroll : 2;
		unsigned int freeze : 1;
		unsigned int vivid : 2;
		unsigned int anime : 2;
		unsigned int dark : 1;
		unsigned int pad : 12;
	};
};

struct _tag_cDDR7SaveData
{
	_DDRCommonHeader CommonHeader;
	_tag_cDDR7Option Option;
	_tag_cDDR7Record1 MRecord[80];
	unsigned char Information[144];
	unsigned int nMusic;
	unsigned int nBoot;
	unsigned int nPlayerType[3];
	unsigned int nDifficulty[5];
	signed int nwork[2];
	unsigned char LessonWork[32];
	_tag_cDDR7OniRecord1 OniRecord[32];
	popular popular;
	G_RANKING_W_ high_score[30];
	machine_point_work machine_p;
	unsigned int HideMusic[4];
	unsigned int HideFlag[4];
	unsigned int HideDoll[2];
	_EDSSAVE_W EdsRecords;
	oni_course oni_order[3];
	oni_course dietprogram_order[3];
	_anon1 diet_calorie_record[2];
};

struct oni_cource_work
{
	signed int id;
	signed int init_ok;
	oni_course* course[32];
	unsigned char seqkind_tab[20];
};

struct play_mode
{
	unsigned char seq_kind;
	unsigned char seq_transfer;
	unsigned char style;
	unsigned char pccard_seq;
	unsigned char mcard_seq;
	unsigned char padding;
	signed short edseq_id;
	struct
	{
		unsigned int hidden : 2;
		unsigned int thinout : 1;
		unsigned int free : 1;
		unsigned int soft : 1;
		unsigned int boost : 2;
		unsigned int speed : 5;
		unsigned int scroll : 2;
		unsigned int freeze : 1;
		unsigned int vivid : 2;
		unsigned int anime : 2;
		unsigned int dark : 1;
		unsigned int pad : 12;
	};
};

struct tm
{
	signed int tm_sec;
	signed int tm_min;
	signed int tm_hour;
	signed int tm_mday;
	signed int tm_mon;
	signed int tm_year;
	signed int tm_wday;
	signed int tm_yday;
	signed int tm_isdst;
};

struct oni_course
{
	unsigned int course_allnum;
	unsigned int course_defnum;
	signed short flag;
	signed short order;
	signed short start_life;
	signed short stage;
	signed int single_steps;
	signed int double_steps;
	signed int hide;
	signed int option;
	oni_mode mode[20];
};

struct music_info
{
	char base_name[6];
	signed char kind;
	signed char album;
	signed short dance_num;
	signed short order;
	unsigned short main_track;
	unsigned short select_track;
	unsigned short bpm_max;
	unsigned short bpm_min;
	unsigned short verm_num;
	unsigned short pcseq_num;
	unsigned long hide;
	signed short adjust_mc;
	unsigned int difficulty[2];
	unsigned int special;
	unsigned short max_spm[9];
	unsigned short avg_spm[9];
	unsigned short avg_jpm[9];
	unsigned short chaos_v[9];
	unsigned short freez_v[9];
	char* title;
	char* l_name;
};

struct _anon0
{
	unsigned char old_stat;
	unsigned char cur_stat;
	unsigned char release_ct;
	unsigned char warning;
};

struct _tag_cDDR7OniRecord1
{
	unsigned int Score[4];
	unsigned short Time[4];
	unsigned short Combo[4];
	unsigned short Miss[4];
	unsigned char Stage[4];
	unsigned char Clear[4];
	unsigned char Level[4];
	unsigned char is_first_clear;
	unsigned char pad[3];
};

struct _tag_cDDR7Record1
{
	unsigned int Score[10];
	unsigned int Bonus[10];
	unsigned int nPlayed;
	unsigned short LinkNum;
	unsigned short Combo[10];
	unsigned short ComboMax[10];
	unsigned char Level[10];
	unsigned char little_flag[2];
	char pad[6];
};

struct play_w
{
	signed int music_counter;
	signed int beat_counter;
	signed int cur_p_counter;
	signed int last_p_counter;
	signed int begin_beat_count;
	signed int go_beat_count;
	signed int finish_beat_count;
	signed int end_beat_count;
	signed int game_start_music_count;
	signed int game_finish_music_count;
	signed int back_trans_start_music_count;
	signed int last_fs_nct;
	signed short last_input_count[8];
	play_hist history[8];
	signed int cur_his;
	signed int pre_nct;
	signed int cur_nct;
	signed int disp_nct;
	signed int cur_great_combo;
	signed int cur_miss_combo;
	signed int max_great_combo;
	signed int max_miss_combo;
	signed int miss_start_count;
	unsigned short input;
	unsigned char dead;
	signed char strictness;
	signed short panel_count[8];
	signed short message_ct;
	signed short message_id;
	signed short meter_cur;
	signed short meter_vol;
	signed short meter_ct;
	signed short dance_class;
	signed int bar_start;
	signed int bar_end;
};

struct g_game_w
{
	signed short state;
	signed short genre;
	music_info* mip;
	signed char start_chip;
	signed char extra_chip;
	signed char use_chip;
	signed char lost_chip;
	signed short stage;
	signed short next_stage;
	signed short failed;
	signed short level;
	signed char game_kind;
	signed char world;
	signed char nonstop;
	signed char event_mode;
	signed char style;
	signed char music_group;
	signed char music_select_mode;
	signed char extra_stage;
	signed char extra_fix;
	signed char final_fix;
	signed char meter_kind;
	signed char roulette_stage;
	signed char edit_total;
	signed char roulette_total;
	signed short music;
	signed char oni_mode;
	unsigned char oni_load_step;
	signed short oni_next_music;
	signed char oni_nonstop_difficulty;
	signed char oni_nonstop_option_selected;
	signed char oni_pad[2];
	signed char beginner_mode;
	signed char beginner_selected;
	signed char freez_selected;
	signed char beginner_pad[1];
	music_info* oni_next_mip;
	g_each_w player[2];
	signed char music_table[128];
	note_status note_status_table[300];
	_anon0 hc_work[8];
	signed int demoloop_ct;
	signed int mode_quit_ct[2];
	signed int force_exit_ct[2];
	signed int diet_play_time;
	signed int old_play_time;
	signed int menu_num;
	signed int total_stage;
	signed int now_bpm;
	unsigned char* last_data_addr;
	unsigned char* anime_data_addr;
	unsigned char* anime_buff_addr;
	unsigned char anime_load_flg;
	unsigned char anime1_load_flg;
	unsigned char anime2_load_flg;
	unsigned char edit_name[12];
	unsigned char diet_flg;
	unsigned char auto_play_flg;
	unsigned char caution_flg;
	unsigned char mode_quit_flg;
	unsigned char lib_loaded;
	unsigned char force_exit_flg;
	unsigned char music_stop_flg;
	unsigned char train_state;
	unsigned char lesson_flag;
	unsigned char lesson_auto_play_flag;
	unsigned char lesson_pad[2];
	unsigned char oni_load_start0;
	unsigned char oni_load_start1;
	unsigned char oni_load_end0;
	unsigned char oni_load_end1;
	unsigned char oni_order_step;
	unsigned char oni_order_stage;
	unsigned char oni_order_cursor;
	unsigned char oni_order_top_stage;
	unsigned char temp_sqk[2];
	unsigned char disp_seltu_flag;
	unsigned char temp_pad[1];
	unsigned char endless_flag;
	unsigned char endless_pad[3];
};

struct _InputData
{
	unsigned short player_input[4];
	unsigned short player_input_trigger[4];
	unsigned short player_input_released[4];
	unsigned short etc;
	unsigned short etc_trigger;
	unsigned short etc_released;
	unsigned short padding;
};

struct popular
{
	signed short cur_c;
	signed short last_c;
	unsigned short count[4][150];
};

struct _InputBuffer
{
	unsigned long current_buffer;
	_InputData data[2];
};

struct G_RANKING_W_
{
	char name[4];
	unsigned long score;
};

struct play_his
{
	signed short music;
	signed short edit_id;
	unsigned char seq_kind;
	signed char roulette;
	signed char extra;
	signed char pad;
};

struct oni_steps
{
	unsigned int link_num;
	unsigned short steps[4][2];
};

struct g_each_w
{
	unsigned int play_time;
	unsigned int game_time;
	unsigned int game_time_total;
	signed char select;
	signed char character;
	signed char costume;
	signed char motiontype;
	signed char loaded_model;
	signed char loaded_texture;
	signed char loaded_motion;
	unsigned char play_disp_flag;
	unsigned char model_disp_flag;
	unsigned char gauge_disp_flag;
	signed short cur_point;
	signed int cur_life;
	unsigned int score;
	unsigned int old_score;
	unsigned int real_score;
	unsigned int bonus;
	unsigned int old_bonus;
	unsigned int max_score;
	unsigned int old_max_score;
	unsigned int max_bonus;
	unsigned int old_max_bonus;
	unsigned int cal;
	unsigned int old_cal;
	unsigned int real_cal;
	unsigned int disp_cal;
	unsigned int average_cal;
	signed int diet_norm_cal;
	signed int diet_norm_minute;
	signed int old_norm_cal;
	signed int old_norm_minute;
	signed int minimum_cal;
	unsigned char add_cal_flg;
	unsigned char chk_cal_flg;
	unsigned char pad[2];
	unsigned int play_stage;
	unsigned int decode_key1;
	unsigned int decode_key2;
	unsigned int decode_key3;
	play_mode mode;
	play_his his[7];
	eval_w stage_evaluation;
	eval_w total_evaluation;
	play_w play_work;
	signed int total_notes;
	signed int total_jump;
	signed int total_freez;
	signed int category;
	signed int total_category;
	sequence sequence_buff[6144];
};

struct _tag_cDDR7Option
{
	unsigned char Sound;
	unsigned char Voice;
	signed char Timing;
	char pad_sound[1];
	unsigned char KeyConfig[4];
	unsigned char Vibration;
	unsigned char DPlay;
	char pad_cont[2];
	unsigned char AutoSave;
	unsigned char FolderLoad;
	char pad_mc[2];
	unsigned char Level;
	unsigned char MaxStage[3];
	unsigned char GameOver;
	unsigned char TimeLimit;
	unsigned char EventMode;
	unsigned char DefaultDifficulty;
	char pad_game[8];
	unsigned char BgEffect;
	unsigned char BgBright;
	unsigned char DangerDisplay;
	unsigned char StepMarkColor;
	signed char screen_x;
	signed char screen_y;
	unsigned char FlickerFree;
	unsigned char SongDisplay;
	unsigned char DietMeasure;
	unsigned char DietDisplay;
	unsigned char DietTime;
	unsigned char DietPlayDefault;
	unsigned char DietWeightUnit;
	char pad_diet[3];
	unsigned char Language;
	char pad_lang[7];
	unsigned char DollDisp;
	unsigned char DollGuestNum;
	unsigned char DollChara[3];
	char pad[3];
};

struct note_status
{
	unsigned char state[8];
	unsigned int length[8];
};

struct _EDSS_DATA_W
{
	unsigned int score[2];
	signed int combo;
	signed int stage;
};

struct _DDRCommonHeader
{
	unsigned char Type;
	unsigned char Platform;
	unsigned char Hardware;
	unsigned char Version;
	unsigned char Area;
	signed char tmp;
	unsigned short title;
	unsigned int t_info[2];
};

struct _EDSS_PLAY_W
{
	_EDSS_DATA_W p_single[3];
	_EDSS_DATA_W p_double[3];
};

struct sequence
{
	signed int beat_count;
	signed short kind;
	signed short next_change;
	signed short music_count;
	signed short judge_count;
	signed short stolen_count;
	signed short op_note_ct;
	unsigned int hold_length[8];
	unsigned char hold_stat[8];
};

struct _EDSSAVE_W
{
	_EDSS_PLAY_W reg[2];
	_EDSS_DATA_W max_point;
	unsigned int PlayFlag[90];
};

struct play_hist
{
	signed int music_count;
	unsigned char input[8];
};

struct _anon1
{
	unsigned int program_calorie[9];
	unsigned int program_play_count[9];
	unsigned int song_calorie[5][80];
	unsigned int song_play_count[5][80];
};

struct machine_point_work
{
	unsigned int hide_show[2];
	unsigned int status;
	unsigned int period_time;
	signed int cur_point;
};

struct eval_w
{
	signed int value_ct[7];
	signed int freez_value_ct[4];
	signed int groov_bonus[6];
	signed int groov_bonus_max[6];
	signed int score;
	signed int max_combo_ct;
	signed int jump_ct;
	signed short dance_level;
	signed short fixed_level;
};

struct G_INPUT_W_
{
	_InputData* dp;
	_InputBuffer buffer;
};

struct G_SYS_W_
{
	G_INPUT_W_ input_w;
	tm start_tm;
	unsigned int v_counter;
	unsigned long v_counter2;
	unsigned int s_counter;
	signed int u_counter;
	unsigned char entry_bit;
	char vpf;
	char pad[2];
};
</pre>
SLUS-20916 - Dance Dance Revolution EXTREME - 2004-05-10 Prototype Build
<pre>
struct oni_course
{
	unsigned int course_allnum;
	unsigned int course_defnum;
	signed short avairable_level;
	signed short order;
	signed short start_life;
	signed short flag;
	unsigned int stage;
	signed int single_steps;
	signed int double_steps;
	oni_mode mode[20];
};

struct _tag_cDDR8SaveData
{
	_DDRCommonHeader CommonHeader;
	_tag_cDDR8Option Option;
	_tag_cDDR8Record1 MRecord[80];
	unsigned char Information[256];
	unsigned int nMusic;
	unsigned int nBoot;
	unsigned int nPlayerType[3];
	unsigned int nDifficulty[5];
	signed int nwork[3];
	unsigned char LessonWork[32];
	_tag_cDDR8OniRecord1 OniRecord[3];
	_tag_cDDR8OniRecord1 NonstopRecord[6];
	popular popular;
	G_RANKING_W_ high_score[40];
	unsigned int HideFlag[2];
	unsigned int HideDoll[2];
	unsigned char HideDollWk[4];
	_EDSSAVE_W EdsRecords;
	_anon1 challenge;
	oni_course oni_order[1];
	oni_course nonstop_order[1];
	oni_course dietprogram_order[1];
	_anon3 diet_calorie_record[2];
	_tag_cMWMgRun mg_run;
	unsigned int nMusic_on_last_unlocked;
	_eyetoy_option eyetoy_option;
	_mg_block mg_block;
	_mg_coco mg_coco;
	_tag_cDDR8Record1 mg_solo_MRecord[80];
	_anon2 wk_save[2];
};

struct play_his
{
	signed short music;
	signed short edit_id;
	unsigned char seq_kind;
	signed char roulette;
	signed char extra;
	signed char pad;
};

struct _tag_cDDR8Option
{
	unsigned char Sound;
	unsigned char Voice;
	signed char Timing;
	char pad_sound[1];
	char EditKey[24];
	unsigned char KeyConfig[4];
	unsigned char DModeSet;
	unsigned char Vibration;
	unsigned char DPlay;
	char pad_cont[2];
	unsigned char AutoSave;
	unsigned char FolderLoad;
	char pad_mc[2];
	unsigned char Level;
	unsigned char MaxStage[3];
	unsigned char GameOver;
	unsigned char TimeLimit;
	unsigned char EventMode;
	unsigned char DefaultDifficulty;
	char pad_game[8];
	unsigned char BgEffect;
	unsigned char BgBright;
	unsigned char DangerDisplay;
	unsigned char StepMarkColor;
	signed char screen_x;
	signed char screen_y;
	unsigned char FlickerFree;
	char pad_graphic[1];
	unsigned char DietMeasure;
	unsigned char DietDisplay;
	unsigned char DietTime;
	unsigned char DietPlayDefault;
	unsigned char DietWeightUnit;
	char pad_diet[3];
	unsigned char Language;
	char pad_lang[7];
	unsigned char DollDisp;
	unsigned char DollChara[3];
	unsigned char DollGuestNum;
	unsigned char DollSelect;
	char pad[2];
};

struct _EDSS_DATA_W
{
	unsigned int score[2];
	signed int combo;
	signed int stage;
};

struct _InputData
{
	unsigned short player_input[4];
	unsigned short player_input_trigger[4];
	unsigned short player_input_released[4];
	unsigned short etc;
	unsigned short etc_trigger;
	unsigned short etc_released;
	unsigned short padding;
};

struct sequence
{
	signed int beat_count;
	signed short kind;
	signed short next_change;
	signed short music_count;
	signed short judge_count;
	signed short stolen_count;
	signed short op_note_ct;
	unsigned int hold_length[8];
	unsigned char hold_stat[8];
};

struct g_each_w
{
	unsigned int play_time;
	unsigned int game_time;
	unsigned int game_time_total;
	signed char select;
	signed char character;
	signed char costume;
	signed char motiontype;
	signed char loaded_model;
	signed char loaded_texture;
	signed char loaded_motion;
	unsigned char play_disp_flag;
	unsigned char model_disp_flag;
	unsigned char gauge_disp_flag;
	signed short cur_point;
	signed int cur_life;
	unsigned int score;
	unsigned int old_score;
	unsigned int real_score;
	unsigned int bonus;
	unsigned int old_bonus;
	unsigned int max_score;
	unsigned int old_max_score;
	unsigned int max_bonus;
	unsigned int old_max_bonus;
	unsigned int cal;
	unsigned int old_cal;
	unsigned int real_cal;
	unsigned int disp_cal;
	unsigned int average_cal;
	signed int diet_norm_cal;
	signed int diet_norm_minute;
	signed int old_norm_cal;
	signed int old_norm_minute;
	signed int minimum_cal;
	unsigned char add_cal_flg;
	unsigned char chk_cal_flg;
	unsigned char pad[2];
	unsigned int play_stage;
	unsigned int decode_key1;
	unsigned int decode_key2;
	unsigned int decode_key3;
	signed int used_unfair_command;
	signed int nonstop_dead_flag;
	play_mode mode;
	play_his his[7];
	eval_w stage_evaluation;
	eval_w total_evaluation;
	play_w play_work;
	signed int total_notes;
	signed int total_jump;
	signed int total_freez;
	signed int category;
	signed int total_category;
	sequence sequence_buff[6144];
};

struct _EDSS_PLAY_W
{
	_EDSS_DATA_W p_single[3];
	_EDSS_DATA_W p_double[3];
};

struct _InputBuffer
{
	unsigned long current_buffer;
	_InputData data[2];
};

struct music_info
{
	char base_name[6];
	signed char kind;
	signed char album;
	signed short dance_num;
	signed short order;
	unsigned int main_track;
	unsigned int select_track;
	unsigned short bpm_max;
	unsigned short bpm_min;
	unsigned short verm_num;
	unsigned short pcseq_num;
	unsigned long hide;
	signed short adjust_mc;
	unsigned int difficulty[2];
	unsigned int special;
	unsigned short max_spm[9];
	unsigned short avg_spm[9];
	unsigned short avg_jpm[9];
	unsigned short chaos_v[9];
	unsigned short freez_v[9];
	char* title;
	char* l_name;
};

struct popular
{
	signed short cur_c;
	signed short last_c;
	unsigned short count[4][256];
};

struct oni_mode
{
	unsigned int link_num;
	unsigned char seq_kind;
	unsigned char seq_transfer;
	unsigned char sp_music;
	unsigned char add_life;
	struct
	{
		unsigned int hidden : 2;
		unsigned int thinout : 1;
		unsigned int free : 1;
		unsigned int soft : 1;
		unsigned int boost : 2;
		unsigned int speed : 5;
		unsigned int scroll : 2;
		unsigned int freeze : 1;
		unsigned int vivid : 2;
		unsigned int anime : 2;
		unsigned int dark : 1;
		unsigned int pad : 12;
	};
};

struct _EDSSAVE_W
{
	_EDSS_PLAY_W reg[2];
	unsigned int PlayFlag[128];
};

struct G_RANKING_W_
{
	char name[4];
	unsigned long score;
};

struct play_mode
{
	unsigned char seq_kind;
	unsigned char seq_transfer;
	unsigned char style;
	unsigned char pccard_seq;
	unsigned char mcard_seq;
	unsigned char padding;
	signed short edseq_id;
	struct
	{
		unsigned int hidden : 3;
		unsigned int thinout : 1;
		unsigned int free : 1;
		unsigned int soft : 1;
		unsigned int boost : 2;
		unsigned int speed : 5;
		unsigned int scroll : 2;
		unsigned int freeze : 1;
		unsigned int vivid : 2;
		unsigned int anime : 2;
		unsigned int dark : 1;
	};
	unsigned int pad : 12;
};

struct _anon0
{
	unsigned char state;
	unsigned char pad[3];
	signed int play_count;
	signed int clear_count;
};

struct _anon1
{
	unsigned char appear;
	unsigned char ending_flag;
	unsigned char pad[2];
	signed int bonus_count;
	unsigned int play_time[2];
	_anon0 subject[100];
};

struct play_hist
{
	signed int music_count;
	unsigned char input[8];
};

struct tm
{
	signed int tm_sec;
	signed int tm_min;
	signed int tm_hour;
	signed int tm_mday;
	signed int tm_mon;
	signed int tm_year;
	signed int tm_wday;
	signed int tm_yday;
	signed int tm_isdst;
};

struct note_status
{
	unsigned char state[8];
	unsigned int length[8];
};

struct G_INPUT_W_
{
	_InputData* dp;
	_InputBuffer buffer;
};

struct oni_cource_work
{
	signed int id;
	signed int init_ok;
	oni_course* course[9];
	signed int tex_kind;
	signed int tex_load_step;
	unsigned char seqkind_tab[20];
	signed int dancer_flag;
};

struct _anon2
{
	unsigned char game_over;
	unsigned char calorie_check;
	unsigned char pad[2];
};

struct G_SYS_W_
{
	G_INPUT_W_ input_w;
	tm start_tm;
	unsigned int v_counter;
	unsigned long v_counter2;
	unsigned int s_counter;
	signed int u_counter;
	signed int read_time;
	unsigned char read_flag;
	unsigned char entry_bit;
	char vpf;
	char pad[2];
};

struct eval_w
{
	signed int value_ct[8];
	signed int freez_value_ct[4];
	signed int groov_bonus[6];
	signed int groov_bonus_max[6];
	signed int score;
	signed int max_combo_ct;
	signed int jump_ct;
	signed short dance_level;
	signed short fixed_level;
};

struct _anon3
{
	unsigned int program_calorie[2];
	unsigned int program_play_count[2];
	unsigned int song_calorie[5][80];
	unsigned int song_play_count[5][80];
};

struct _DDRCommonHeader
{
	unsigned char Type;
	unsigned char Platform;
	unsigned char Hardware;
	unsigned char Version;
	unsigned char Area;
	signed char tmp;
	unsigned short title;
	unsigned int t_info[2];
};

struct _tag_cMWMgRunRecord
{
	signed int time;
	unsigned char bcd_time;
	unsigned char bcd_type;
	unsigned char fps;
	char pad[1];
};

struct _anon4
{
	struct
	{
		unsigned long number : 16;
		unsigned long sector : 24;
		unsigned long size : 24;
	};
};

struct _tag_cMWMgRun
{
	_tag_cMWMgRunRecord record;
	char pad[8];
};

struct _tag_cDDR8Record1
{
	unsigned int Score[10];
	unsigned int Bonus[10];
	unsigned int nPlayed;
	unsigned short LinkNum;
	unsigned short Combo[10];
	unsigned short ComboMax[10];
	unsigned char Level[10];
	unsigned char pad[2];
};

struct play_w
{
	signed int music_counter;
	signed int beat_counter;
	signed int cur_p_counter;
	signed int last_p_counter;
	signed int begin_beat_count;
	signed int go_beat_count;
	signed int finish_beat_count;
	signed int end_beat_count;
	signed int game_start_music_count;
	signed int game_finish_music_count;
	signed int back_trans_start_music_count;
	signed int last_fs_nct;
	signed short last_input_count[8];
	play_hist history[8];
	signed int cur_his;
	signed int pre_nct;
	signed int cur_nct;
	signed int disp_nct;
	signed int cur_great_combo;
	signed int cur_miss_combo;
	signed int max_great_combo;
	signed int max_miss_combo;
	signed int miss_start_count;
	signed int cur_great_combo_total;
	signed int max_great_combo_total;
	unsigned short input;
	unsigned char dead;
	signed char strictness;
	signed short panel_count[8];
	signed short message_ct;
	signed short message_id;
	signed short meter_cur;
	signed short meter_vol;
	signed short meter_ct;
	signed short offset;
	signed short light_offset;
	signed short meter_state;
	signed short anm_no;
	signed short dance_class;
	signed int bar_start;
	signed int bar_end;
};

struct _tag_cDDR8OniRecord1
{
	unsigned int Time[2];
	unsigned int Score[2];
	unsigned short Combo[2];
	unsigned char Stage[2];
	unsigned char Miss[2];
	unsigned char AllStage[2];
	unsigned char Level[2];
	unsigned char is_first_clear;
	unsigned char pad[3];
	unsigned short ClearNum[2];
	unsigned char pad2[2];
};

struct _anon5
{
	unsigned char old_stat;
	unsigned char cur_stat;
	unsigned char release_ct;
	unsigned char warning;
};

struct _eyetoy_option
{
	char depth;
	char pdf;
	char frame;
	unsigned char bright;
};

struct _mg_block
{
	signed int hi_score;
};

struct g_game_w
{
	signed short state;
	signed short genre;
	music_info* mip;
	signed char start_chip;
	signed char extra_chip;
	signed char use_chip;
	signed char lost_chip;
	signed short stage;
	signed short next_stage;
	signed short failed;
	signed short level;
	signed char game_kind;
	signed char world;
	signed char oni_nonstop_course_id;
	signed char event_mode;
	signed char event_two_flag;
	signed char style;
	signed char music_group;
	signed char music_select_mode;
	signed char extra_stage;
	signed char extra_fix;
	signed char final_fix;
	signed char meter_kind;
	signed char roulette_stage;
	signed char edit_total;
	signed char roulette_total;
	signed short music;
	signed char oni_nonstop_mode;
	unsigned char oni_load_step;
	signed char oni_nonstop_difficulty;
	signed char use_oni_gauge;
	signed char beginner_mode;
	signed char beginner_selected;
	signed char freez_selected;
	signed char beginner_pad[1];
	signed short oni_next_music;
	music_info* oni_next_mip;
	g_each_w player[2];
	signed char music_table[128];
	note_status note_status_table[300];
	_anon5 hc_work[8];
	signed int demoloop_ct;
	signed int mode_quit_ct[2];
	signed int force_exit_ct[2];
	signed int diet_play_time;
	signed int old_play_time;
	signed int menu_num;
	signed int total_stage;
	signed int now_bpm;
	unsigned char* last_data_addr;
	unsigned char edit_name[12];
	unsigned char diet_flg;
	unsigned char auto_play_flg;
	unsigned char caution_flg;
	unsigned char mode_quit_flg;
	unsigned char lib_loaded;
	unsigned char force_exit_flg;
	unsigned char train_state;
	unsigned char lesson_flag;
	unsigned char lesson_auto_play_flag;
	unsigned char lesson_pad[2];
	unsigned char oni_load_start0;
	unsigned char oni_load_start1;
	unsigned char oni_load_end0;
	unsigned char oni_load_end1;
	unsigned char oni_order_step;
	unsigned char oni_order_stage;
	unsigned char oni_order_cursor;
	unsigned char oni_order_top_stage;
	unsigned char oni_order_selopt;
	unsigned char anime1_load_flg;
	unsigned char anime2_load_flg;
	unsigned char temp_sqk[2];
	unsigned char endless_flag;
	unsigned char eyetoy_flag;
	unsigned char challenge_flag;
	unsigned char step_mark_color;
	unsigned char hand_solo_seq_kind;
	unsigned char hand_solo_pad[3];
	unsigned char nononi_msel_flag;
	unsigned char select_randaom_flag;
	unsigned char bar_state;
	unsigned char sel_pad[1];
	signed int rloadtex_num;
	signed int rload_next_step;
	char nonstop_selopt_flag;
	unsigned char dancer_id[3];
};

struct _mg_coco
{
	signed int hi_score;
};
</pre>
SLUS-20916 - Dance Dance Revolution EXTREME - 2004-07-09 Retail Build
<pre>
struct oni_course
{
	unsigned int course_allnum;
	unsigned int course_defnum;
	signed short avairable_level;
	signed short order;
	signed short start_life;
	signed short flag;
	unsigned int stage;
	signed int single_steps;
	signed int double_steps;
	oni_mode mode[20];
};

struct music_info
{
	char base_name[6];
	signed char kind;
	signed char album;
	signed short dance_num;
	signed short order;
	unsigned int main_track;
	unsigned int select_track;
	unsigned short bpm_max;
	unsigned short bpm_min;
	unsigned short verm_num;
	unsigned short pcseq_num;
	unsigned long hide;
	signed short adjust_mc;
	unsigned int difficulty[2];
	unsigned int special;
	unsigned short max_spm[9];
	unsigned short avg_spm[9];
	unsigned short avg_jpm[9];
	unsigned short chaos_v[9];
	unsigned short freez_v[9];
	char* title;
	char* l_name;
};

struct _tag_cDDR8OniRecord1
{
	unsigned int Time[2];
	unsigned int Score[2];
	unsigned short Combo[2];
	unsigned char Stage[2];
	unsigned char Miss[2];
	unsigned char AllStage[2];
	unsigned char Level[2];
	unsigned char is_first_clear;
	unsigned char is_full_combo_flag[2];
	unsigned char pad[1];
	unsigned short ClearNum[2];
	unsigned char pad2[2];
};

struct note_status
{
	unsigned char state[8];
	unsigned int length[8];
};

struct _eyetoy_option
{
	char depth;
	char pdf;
	char frame;
	unsigned char bright;
};

struct g_game_w
{
	signed short state;
	signed short genre;
	music_info* mip;
	signed char start_chip;
	signed char extra_chip;
	signed char use_chip;
	signed char lost_chip;
	signed short stage;
	signed short next_stage;
	signed short failed;
	signed short level;
	signed char game_kind;
	signed char world;
	signed char oni_nonstop_course_id;
	signed char event_mode;
	signed char event_two_flag;
	signed char style;
	signed char music_group;
	signed char music_select_mode;
	signed char extra_stage;
	signed char extra_fix;
	signed char final_fix;
	signed char meter_kind;
	signed char roulette_stage;
	signed char edit_total;
	signed char roulette_total;
	signed short music;
	signed char oni_nonstop_mode;
	unsigned char oni_load_step;
	signed char oni_nonstop_difficulty;
	signed char use_oni_gauge;
	signed char beginner_mode;
	signed char beginner_selected;
	signed char freez_selected;
	signed char judge_invalid;
	signed short oni_next_music;
	music_info* oni_next_mip;
	g_each_w player[2];
	signed char music_table[128];
	note_status note_status_table[300];
	_anon4 hc_work[8];
	signed int demoloop_ct;
	signed int mode_quit_ct[2];
	signed int force_exit_ct[2];
	signed int diet_play_time;
	signed int old_play_time;
	signed int menu_num;
	signed int total_stage;
	signed int now_bpm;
	unsigned char* last_data_addr;
	unsigned char edit_name[12];
	unsigned char diet_flg;
	unsigned char workout_step_flg;
	unsigned char auto_play_flg;
	unsigned char caution_flg;
	unsigned char mode_quit_flg;
	unsigned char lib_loaded;
	unsigned char force_exit_flg;
	unsigned char train_state;
	unsigned char lesson_flag;
	unsigned char lesson_auto_play_flag;
	unsigned char lesson_pad[2];
	unsigned char oni_load_start0;
	unsigned char oni_load_start1;
	unsigned char oni_load_end0;
	unsigned char oni_load_end1;
	unsigned char oni_order_step;
	unsigned char oni_order_stage;
	unsigned char oni_order_cursor;
	unsigned char oni_order_top_stage;
	unsigned char oni_order_selopt;
	unsigned char anime1_load_flg;
	unsigned char anime2_load_flg;
	unsigned char temp_sqk[2];
	unsigned char endless_flag;
	unsigned char eyetoy_flag;
	unsigned char challenge_flag;
	unsigned char step_mark_color;
	unsigned char hand_solo_seq_kind;
	unsigned char hand_solo_pad[3];
	unsigned char nononi_msel_flag;
	unsigned char select_randaom_flag;
	unsigned char bar_state;
	unsigned char sel_pad[1];
	signed int rloadtex_num;
	signed int rload_next_step;
	_backup_w backup;
	char quit_course_flag;
	char nonstop_selopt_flag;
	unsigned char dancer_id[3];
	_anon9 line_data[16];
	signed int line_speed;
	signed int bk_ef_kind;
	signed int bk_ef_colset[3];
	signed int bk_ef_type;
	signed int bk_ef_reset;
	signed int event_result_exit_flag;
	signed int party_mode_flag;
};

struct _DDRCommonHeader
{
	unsigned char Type;
	unsigned char Platform;
	unsigned char Hardware;
	unsigned char Version;
	unsigned char Area;
	signed char tmp;
	unsigned short title;
	unsigned int t_info[2];
};

struct _mg_block
{
	signed int hi_score;
};

struct _mg_coco
{
	signed int hi_score;
};

struct sequence
{
	signed int beat_count;
	signed short kind;
	signed short next_change;
	signed short music_count;
	signed short judge_count;
	signed short stolen_count;
	signed short op_note_ct;
	unsigned int hold_length[8];
	unsigned char hold_stat[8];
};

struct _anon0
{
	signed int hi_score;
};

struct _tag_cDDR8Option
{
	unsigned char Sound;
	unsigned char Voice;
	signed char Timing;
	char pad_sound[1];
	char EditKey[24];
	unsigned char KeyConfig[4];
	unsigned char DModeSet;
	unsigned char Vibration;
	unsigned char DPlay;
	char pad_cont[2];
	unsigned char AutoSave;
	unsigned char FolderLoad;
	char pad_mc[2];
	unsigned char Level;
	unsigned char MaxStage[3];
	unsigned char GameOver;
	unsigned char TimeLimit;
	unsigned char EventMode;
	unsigned char DefaultDifficulty;
	char pad_game[8];
	unsigned char BgEffect;
	unsigned char BgBright;
	unsigned char DangerDisplay;
	unsigned char StepMarkColor;
	signed char screen_x;
	signed char screen_y;
	unsigned char FlickerFree;
	char pad_graphic[1];
	unsigned char DietMeasure;
	unsigned char DietDisplay;
	unsigned char DietTime;
	unsigned char DietPlayDefault;
	unsigned char DietWeightUnit;
	char pad_diet[3];
	unsigned char Language;
	char pad_lang[7];
	unsigned char DollDisp;
	unsigned char DollChara[3];
	unsigned char DollGuestNum;
	unsigned char DollSelect;
	char pad[2];
};

struct play_w
{
	signed int music_counter;
	signed int beat_counter;
	signed int cur_p_counter;
	signed int last_p_counter;
	signed int begin_beat_count;
	signed int go_beat_count;
	signed int finish_beat_count;
	signed int end_beat_count;
	signed int game_start_music_count;
	signed int game_finish_music_count;
	signed int back_trans_start_music_count;
	signed int last_fs_nct;
	signed short last_input_count[8];
	play_hist history[8];
	signed int cur_his;
	signed int pre_nct;
	signed int cur_nct;
	signed int disp_nct;
	signed int cur_great_combo;
	signed int cur_miss_combo;
	signed int max_great_combo;
	signed int max_miss_combo;
	signed int miss_start_count;
	signed int cur_great_combo_total;
	signed int max_great_combo_total;
	unsigned short input;
	unsigned char dead;
	signed char strictness;
	signed short panel_count[8];
	signed short message_ct;
	signed short message_id;
	signed short meter_cur;
	signed short meter_vol;
	signed short meter_ct;
	signed short offset;
	signed short light_offset;
	signed short meter_state;
	signed short anm_no;
	signed short dance_class;
	signed int bar_start;
	signed int bar_end;
};

struct _tag_cDDR8SaveData
{
	_DDRCommonHeader CommonHeader;
	_tag_cDDR8Option Option;
	_tag_cDDR8Record1 MRecord[80];
	unsigned char Information[256];
	unsigned int nMusic;
	unsigned int nBoot;
	unsigned int nPlayerType[3];
	unsigned int nDifficulty[5];
	signed int nwork[3];
	unsigned char LessonWork[32];
	_tag_cDDR8OniRecord1 OniRecord[20];
	_tag_cDDR8OniRecord1 NonstopRecord[38];
	popular popular;
	G_RANKING_W_ high_score[40];
	unsigned int HideFlag[3];
	unsigned int HideNewFlag[3];
	unsigned int HideDoll[2];
	unsigned int HideNewDoll[2];
	unsigned char HideDollWk[4];
	_EDSSAVE_W EdsRecords;
	_anon2 challenge;
	oni_course oni_order[3];
	oni_course nonstop_order[3];
	oni_course dietprogram_order[3];
	_anon7 diet_calorie_record[2];
	_tag_cMWMgRun mg_run;
	unsigned int nMusic_on_last_unlocked;
	_eyetoy_option eyetoy_option;
	_mg_block mg_block;
	_mg_coco mg_coco;
	_anon0 mg_eat;
	_tag_cDDR8Record1 mg_solo_MRecord[80];
	_anon5 wk_save[2];
};

struct _EDSS_DATA_W
{
	unsigned int score[2];
	signed int combo;
	signed int stage;
};

struct eval_w
{
	signed int value_ct[8];
	signed int freez_value_ct[4];
	signed int groov_bonus[6];
	signed int groov_bonus_max[6];
	signed int score;
	signed int bonus;
	signed int max_combo_ct;
	signed int jump_ct;
	signed short dance_level;
	signed short fixed_level;
};

struct _EDSS_PLAY_W
{
	_EDSS_DATA_W p_single[3];
	_EDSS_DATA_W p_double[3];
};

struct _EDSSAVE_W
{
	_EDSS_PLAY_W reg[2];
	unsigned int PlayFlag[128];
};

struct oni_mode
{
	unsigned int link_num;
	unsigned char seq_kind;
	unsigned char seq_transfer;
	unsigned char sp_music;
	unsigned char add_life;
	struct
	{
		unsigned int hidden : 2;
		unsigned int thinout : 1;
		unsigned int free : 1;
		unsigned int soft : 1;
		unsigned int boost : 2;
		unsigned int speed : 5;
		unsigned int scroll : 2;
		unsigned int freeze : 1;
		unsigned int vivid : 2;
		unsigned int anime : 2;
		unsigned int dark : 1;
		unsigned int pad : 12;
	};
};

struct _anon1
{
	unsigned char state;
	unsigned char perfect;
	unsigned short play_count;
	unsigned short play_time;
	unsigned short clear_count;
	unsigned short first_clear_count;
	unsigned short first_clear_time;
};

struct oni_cource_work
{
	signed int id;
	signed int init_ok;
	oni_course* course[46];
	signed int tex_kind;
	signed int tex_load_step;
	unsigned char seqkind_tab[20];
	signed int dancer_flag;
};

struct play_mode
{
	unsigned char seq_kind;
	unsigned char seq_transfer;
	unsigned char style;
	unsigned char pccard_seq;
	unsigned char mcard_seq;
	unsigned char padding;
	signed short edseq_id;
	struct
	{
		unsigned int hidden : 3;
		unsigned int thinout : 1;
		unsigned int free : 1;
		unsigned int soft : 1;
		unsigned int boost : 2;
		unsigned int speed : 5;
		unsigned int scroll : 2;
		unsigned int freeze : 1;
		unsigned int vivid : 2;
		unsigned int anime : 2;
		unsigned int dark : 1;
	};
	unsigned int pad : 12;
};

struct _anon2
{
	unsigned char appear;
	unsigned char ending_flag;
	signed char help_count;
	unsigned char pad;
	signed int bonus_count;
	signed int dummy[2];
	_anon1 subject[100];
};

struct _InputData
{
	unsigned short player_input[4];
	unsigned short player_input_trigger[4];
	unsigned short player_input_released[4];
	unsigned short etc;
	unsigned short etc_trigger;
	unsigned short etc_released;
	unsigned short padding;
};

union _anon3
{
	signed int id;
	float fd;
};

struct _anon4
{
	unsigned char old_stat;
	unsigned char cur_stat;
	unsigned char release_ct;
	unsigned char warning;
};

struct _anon5
{
	unsigned char game_over;
	unsigned char calorie_check;
	unsigned char pad[2];
};

struct _InputBuffer
{
	unsigned long current_buffer;
	_InputData data[2];
};

struct _anon6
{
	_anon3 x0;
	_anon3 y0;
	unsigned int z0;
	unsigned char r0;
	unsigned char g0;
	unsigned char b0;
	unsigned char a0;
};

struct _play_backup_w
{
	eval_w stage_evaluation;
	eval_w total_evaluation;
	play_mode mode;
	play_his his[7];
	unsigned int play_stage;
};

struct _anon7
{
	unsigned int program_calorie[6];
	unsigned int program_play_count[6];
	unsigned int song_calorie[5][80];
	unsigned int song_play_count[5][80];
};

struct _anon8
{
	struct
	{
		unsigned long number : 16;
		unsigned long sector : 24;
		unsigned long size : 24;
	};
};

struct popular
{
	signed short cur_c;
	signed short last_c;
	unsigned short count[4][256];
};

struct G_RANKING_W_
{
	char name[4];
	unsigned long score;
};

struct _backup_w
{
	_play_backup_w player[2];
	signed char stage;
	signed char start_chip;
	signed char extra_chip;
	signed char use_chip;
	signed char lost_chip;
};

struct _tag_cMWMgRunRecord
{
	signed int time;
	unsigned char bcd_time;
	unsigned char bcd_type;
	unsigned char fps;
	char pad[1];
};

struct play_his
{
	signed short music;
	signed short edit_id;
	unsigned char seq_kind;
	signed char roulette;
	signed char extra;
	signed char pad;
};

struct _tag_cDDR8Record1
{
	unsigned int Score[10];
	unsigned int Bonus[10];
	unsigned int nPlayed;
	unsigned short LinkNum;
	unsigned short Combo[10];
	unsigned short ComboMax[10];
	unsigned char Level[10];
	unsigned char pad[2];
};

struct play_hist
{
	signed int music_count;
	unsigned char input[8];
};

struct tm
{
	signed int tm_sec;
	signed int tm_min;
	signed int tm_hour;
	signed int tm_mday;
	signed int tm_mon;
	signed int tm_year;
	signed int tm_wday;
	signed int tm_yday;
	signed int tm_isdst;
};

struct _tag_cMWMgRun
{
	_tag_cMWMgRunRecord record;
	char pad[8];
};

struct G_INPUT_W_
{
	_InputData* dp;
	_InputBuffer buffer;
};

struct g_each_w
{
	unsigned int play_time;
	unsigned int game_time;
	unsigned int game_time_total;
	signed char select;
	signed char character;
	signed char costume;
	signed char motiontype;
	signed char loaded_model;
	signed char loaded_texture;
	signed char loaded_motion;
	unsigned char play_disp_flag;
	unsigned char model_disp_flag;
	unsigned char gauge_disp_flag;
	signed short cur_point;
	signed int cur_life;
	unsigned int score;
	unsigned int old_score;
	unsigned int real_score;
	unsigned int bonus;
	unsigned int old_bonus;
	unsigned int max_score;
	unsigned int old_max_score;
	unsigned int max_bonus;
	unsigned int old_max_bonus;
	unsigned int cal;
	unsigned int old_cal;
	unsigned int real_cal;
	unsigned int disp_cal;
	unsigned int average_cal;
	signed int diet_norm_cal;
	signed int diet_norm_minute;
	signed int old_norm_cal;
	signed int old_norm_minute;
	signed int minimum_cal;
	unsigned char add_cal_flg;
	unsigned char chk_cal_flg;
	unsigned char combo_no_disp_flag;
	unsigned char pad;
	unsigned int play_stage;
	unsigned int decode_key1;
	unsigned int decode_key2;
	unsigned int decode_key3;
	signed int used_unfair_command;
	signed int nonstop_dead_flag;
	play_mode mode;
	play_his his[7];
	eval_w stage_evaluation;
	eval_w total_evaluation;
	play_w play_work;
	signed int total_notes;
	signed int total_jump;
	signed int total_freez;
	signed int category;
	signed int total_category;
	sequence sequence_buff[6144];
	signed int total_notes_all;
	signed int total_freez_all;
};

struct G_SYS_W_
{
	G_INPUT_W_ input_w;
	tm start_tm;
	unsigned int v_counter;
	unsigned long v_counter2;
	unsigned int s_counter;
	signed int u_counter;
	signed int read_time;
	unsigned char read_flag;
	unsigned char entry_bit;
	char vpf;
	char pad[2];
};

struct _anon9
{
	_anon6 line_a[8];
	_anon6 line_b[8];
	_anon6 line_c[8];
	signed int num;
};
</pre>
SLUS-20916 - Dance Dance Revolution EXTREME - 2004-07-12 Prototype Build
<pre>
struct oni_cource_work
{
	signed int id;
	signed int init_ok;
	oni_course* course[46];
	signed int tex_kind;
	signed int tex_load_step;
	unsigned char seqkind_tab[20];
	signed int dancer_flag;
};

struct _tag_cMWMgRun
{
	_tag_cMWMgRunRecord record;
	char pad[8];
};

struct oni_course
{
	unsigned int course_allnum;
	unsigned int course_defnum;
	signed short avairable_level;
	signed short order;
	signed short start_life;
	signed short flag;
	unsigned int stage;
	signed int single_steps;
	signed int double_steps;
	oni_mode mode[20];
};

struct oni_mode
{
	unsigned int link_num;
	unsigned char seq_kind;
	unsigned char seq_transfer;
	unsigned char sp_music;
	unsigned char add_life;
	struct
	{
		unsigned int hidden : 2;
		unsigned int thinout : 1;
		unsigned int free : 1;
		unsigned int soft : 1;
		unsigned int boost : 2;
		unsigned int speed : 5;
		unsigned int scroll : 2;
		unsigned int freeze : 1;
		unsigned int vivid : 2;
		unsigned int anime : 2;
		unsigned int dark : 1;
		unsigned int pad : 12;
	};
};

struct G_INPUT_W_
{
	_InputData* dp;
	_InputBuffer buffer;
};

struct _InputData
{
	unsigned short player_input[4];
	unsigned short player_input_trigger[4];
	unsigned short player_input_released[4];
	unsigned short etc;
	unsigned short etc_trigger;
	unsigned short etc_released;
	unsigned short padding;
};

struct g_each_w
{
	unsigned int play_time;
	unsigned int game_time;
	unsigned int game_time_total;
	signed char select;
	signed char character;
	signed char costume;
	signed char motiontype;
	signed char loaded_model;
	signed char loaded_texture;
	signed char loaded_motion;
	unsigned char play_disp_flag;
	unsigned char model_disp_flag;
	unsigned char gauge_disp_flag;
	signed short cur_point;
	signed int cur_life;
	unsigned int score;
	unsigned int old_score;
	unsigned int real_score;
	unsigned int bonus;
	unsigned int old_bonus;
	unsigned int max_score;
	unsigned int old_max_score;
	unsigned int max_bonus;
	unsigned int old_max_bonus;
	unsigned int cal;
	unsigned int old_cal;
	unsigned int real_cal;
	unsigned int disp_cal;
	unsigned int average_cal;
	signed int diet_norm_cal;
	signed int diet_norm_minute;
	signed int old_norm_cal;
	signed int old_norm_minute;
	signed int minimum_cal;
	unsigned char add_cal_flg;
	unsigned char chk_cal_flg;
	unsigned char combo_no_disp_flag;
	unsigned char pad;
	unsigned int play_stage;
	unsigned int decode_key1;
	unsigned int decode_key2;
	unsigned int decode_key3;
	signed int used_unfair_command;
	signed int nonstop_dead_flag;
	play_mode mode;
	play_his his[7];
	eval_w stage_evaluation;
	eval_w total_evaluation;
	play_w play_work;
	signed int total_notes;
	signed int total_jump;
	signed int total_freez;
	signed int category;
	signed int total_category;
	sequence sequence_buff[6144];
	signed int total_notes_all;
	signed int total_freez_all;
};

struct play_mode
{
	unsigned char seq_kind;
	unsigned char seq_transfer;
	unsigned char style;
	unsigned char pccard_seq;
	unsigned char mcard_seq;
	unsigned char padding;
	signed short edseq_id;
	struct
	{
		unsigned int hidden : 3;
		unsigned int thinout : 1;
		unsigned int free : 1;
		unsigned int soft : 1;
		unsigned int boost : 2;
		unsigned int speed : 5;
		unsigned int scroll : 2;
		unsigned int freeze : 1;
		unsigned int vivid : 2;
		unsigned int anime : 2;
		unsigned int dark : 1;
	};
	unsigned int pad : 12;
};

struct G_SYS_W_
{
	G_INPUT_W_ input_w;
	tm start_tm;
	unsigned int v_counter;
	unsigned long v_counter2;
	unsigned int s_counter;
	signed int u_counter;
	signed int read_time;
	unsigned char read_flag;
	unsigned char entry_bit;
	char vpf;
	char pad[2];
};

struct _tag_cDDR8OniRecord1
{
	unsigned int Time[2];
	unsigned int Score[2];
	unsigned short Combo[2];
	unsigned char Stage[2];
	unsigned char Miss[2];
	unsigned char AllStage[2];
	unsigned char Level[2];
	unsigned char is_first_clear;
	unsigned char is_full_combo_flag[2];
	unsigned char pad[1];
	unsigned short ClearNum[2];
	unsigned char pad2[2];
};

struct _anon0
{
	_anon8 line_a[8];
	_anon8 line_b[8];
	_anon8 line_c[8];
	signed int num;
};

struct music_info
{
	char base_name[6];
	signed char kind;
	signed char album;
	signed short dance_num;
	signed short order;
	unsigned int main_track;
	unsigned int select_track;
	unsigned short bpm_max;
	unsigned short bpm_min;
	unsigned short verm_num;
	unsigned short pcseq_num;
	unsigned long hide;
	signed short adjust_mc;
	unsigned int difficulty[2];
	unsigned int special;
	unsigned short max_spm[9];
	unsigned short avg_spm[9];
	unsigned short avg_jpm[9];
	unsigned short chaos_v[9];
	unsigned short freez_v[9];
	char* title;
	char* l_name;
};

struct _eyetoy_option
{
	char depth;
	char pdf;
	char frame;
	unsigned char bright;
};

struct note_status
{
	unsigned char state[8];
	unsigned int length[8];
};

struct g_game_w
{
	signed short state;
	signed short genre;
	music_info* mip;
	signed char start_chip;
	signed char extra_chip;
	signed char use_chip;
	signed char lost_chip;
	signed short stage;
	signed short next_stage;
	signed short failed;
	signed short level;
	signed char game_kind;
	signed char world;
	signed char oni_nonstop_course_id;
	signed char event_mode;
	signed char event_two_flag;
	signed char style;
	signed char music_group;
	signed char music_select_mode;
	signed char extra_stage;
	signed char extra_fix;
	signed char final_fix;
	signed char meter_kind;
	signed char roulette_stage;
	signed char edit_total;
	signed char roulette_total;
	signed short music;
	signed char oni_nonstop_mode;
	unsigned char oni_load_step;
	signed char oni_nonstop_difficulty;
	signed char use_oni_gauge;
	signed char beginner_mode;
	signed char beginner_selected;
	signed char freez_selected;
	signed char judge_invalid;
	signed short oni_next_music;
	music_info* oni_next_mip;
	g_each_w player[2];
	signed char music_table[128];
	note_status note_status_table[300];
	_anon6 hc_work[8];
	signed int demoloop_ct;
	signed int mode_quit_ct[2];
	signed int force_exit_ct[2];
	signed int diet_play_time;
	signed int old_play_time;
	signed int menu_num;
	signed int total_stage;
	signed int now_bpm;
	unsigned char* last_data_addr;
	unsigned char edit_name[12];
	unsigned char diet_flg;
	unsigned char workout_step_flg;
	unsigned char auto_play_flg;
	unsigned char caution_flg;
	unsigned char mode_quit_flg;
	unsigned char lib_loaded;
	unsigned char force_exit_flg;
	unsigned char train_state;
	unsigned char lesson_flag;
	unsigned char lesson_auto_play_flag;
	unsigned char lesson_pad[2];
	unsigned char oni_load_start0;
	unsigned char oni_load_start1;
	unsigned char oni_load_end0;
	unsigned char oni_load_end1;
	unsigned char oni_order_step;
	unsigned char oni_order_stage;
	unsigned char oni_order_cursor;
	unsigned char oni_order_top_stage;
	unsigned char oni_order_selopt;
	unsigned char anime1_load_flg;
	unsigned char anime2_load_flg;
	unsigned char temp_sqk[2];
	unsigned char endless_flag;
	unsigned char eyetoy_flag;
	unsigned char challenge_flag;
	unsigned char step_mark_color;
	unsigned char hand_solo_seq_kind;
	unsigned char hand_solo_pad[3];
	unsigned char nononi_msel_flag;
	unsigned char select_randaom_flag;
	unsigned char bar_state;
	unsigned char sel_pad[1];
	signed int rloadtex_num;
	signed int rload_next_step;
	_backup_w backup;
	char quit_course_flag;
	char nonstop_selopt_flag;
	unsigned char dancer_id[3];
	_anon0 line_data[16];
	signed int line_speed;
	signed int bk_ef_kind;
	signed int bk_ef_colset[3];
	signed int bk_ef_type;
	signed int bk_ef_reset;
	signed int event_result_exit_flag;
	signed int party_mode_flag;
};

struct _DDRCommonHeader
{
	unsigned char Type;
	unsigned char Platform;
	unsigned char Hardware;
	unsigned char Version;
	unsigned char Area;
	signed char tmp;
	unsigned short title;
	unsigned int t_info[2];
};

struct _mg_block
{
	signed int hi_score;
};

struct sequence
{
	signed int beat_count;
	signed short kind;
	signed short next_change;
	signed short music_count;
	signed short judge_count;
	signed short stolen_count;
	signed short op_note_ct;
	unsigned int hold_length[8];
	unsigned char hold_stat[8];
};

struct _mg_coco
{
	signed int hi_score;
};

struct _anon1
{
	signed int hi_score;
};

struct _tag_cDDR8Option
{
	unsigned char Sound;
	unsigned char Voice;
	signed char Timing;
	char pad_sound[1];
	char EditKey[24];
	unsigned char KeyConfig[4];
	unsigned char DModeSet;
	unsigned char Vibration;
	unsigned char DPlay;
	char pad_cont[2];
	unsigned char AutoSave;
	unsigned char FolderLoad;
	char pad_mc[2];
	unsigned char Level;
	unsigned char MaxStage[3];
	unsigned char GameOver;
	unsigned char TimeLimit;
	unsigned char EventMode;
	unsigned char DefaultDifficulty;
	char pad_game[8];
	unsigned char BgEffect;
	unsigned char BgBright;
	unsigned char DangerDisplay;
	unsigned char StepMarkColor;
	signed char screen_x;
	signed char screen_y;
	unsigned char FlickerFree;
	char pad_graphic[1];
	unsigned char DietMeasure;
	unsigned char DietDisplay;
	unsigned char DietTime;
	unsigned char DietPlayDefault;
	unsigned char DietWeightUnit;
	char pad_diet[3];
	unsigned char Language;
	char pad_lang[7];
	unsigned char DollDisp;
	unsigned char DollChara[3];
	unsigned char DollGuestNum;
	unsigned char DollSelect;
	char pad[2];
};

struct _tag_cDDR8SaveData
{
	_DDRCommonHeader CommonHeader;
	_tag_cDDR8Option Option;
	_tag_cDDR8Record1 MRecord[80];
	unsigned char Information[256];
	unsigned int nMusic;
	unsigned int nBoot;
	unsigned int nPlayerType[3];
	unsigned int nDifficulty[5];
	signed int nwork[3];
	unsigned char LessonWork[32];
	_tag_cDDR8OniRecord1 OniRecord[20];
	_tag_cDDR8OniRecord1 NonstopRecord[38];
	popular popular;
	G_RANKING_W_ high_score[40];
	unsigned int HideFlag[3];
	unsigned int HideNewFlag[3];
	unsigned int HideDoll[2];
	unsigned int HideNewDoll[2];
	unsigned char HideDollWk[4];
	_EDSSAVE_W EdsRecords;
	_anon3 challenge;
	oni_course oni_order[3];
	oni_course nonstop_order[3];
	oni_course dietprogram_order[3];
	_anon9 diet_calorie_record[2];
	_tag_cMWMgRun mg_run;
	unsigned int nMusic_on_last_unlocked;
	_eyetoy_option eyetoy_option;
	_mg_block mg_block;
	_mg_coco mg_coco;
	_anon1 mg_eat;
	_tag_cDDR8Record1 mg_solo_MRecord[80];
	_anon7 wk_save[2];
};

struct play_w
{
	signed int music_counter;
	signed int beat_counter;
	signed int cur_p_counter;
	signed int last_p_counter;
	signed int begin_beat_count;
	signed int go_beat_count;
	signed int finish_beat_count;
	signed int end_beat_count;
	signed int game_start_music_count;
	signed int game_finish_music_count;
	signed int back_trans_start_music_count;
	signed int last_fs_nct;
	signed short last_input_count[8];
	play_hist history[8];
	signed int cur_his;
	signed int pre_nct;
	signed int cur_nct;
	signed int disp_nct;
	signed int cur_great_combo;
	signed int cur_miss_combo;
	signed int max_great_combo;
	signed int max_miss_combo;
	signed int miss_start_count;
	signed int cur_great_combo_total;
	signed int max_great_combo_total;
	unsigned short input;
	unsigned char dead;
	signed char strictness;
	signed short panel_count[8];
	signed short message_ct;
	signed short message_id;
	signed short meter_cur;
	signed short meter_vol;
	signed short meter_ct;
	signed short offset;
	signed short light_offset;
	signed short meter_state;
	signed short anm_no;
	signed short dance_class;
	signed int bar_start;
	signed int bar_end;
};

struct _EDSS_DATA_W
{
	unsigned int score[2];
	signed int combo;
	signed int stage;
};

struct _EDSS_PLAY_W
{
	_EDSS_DATA_W p_single[3];
	_EDSS_DATA_W p_double[3];
};

struct eval_w
{
	signed int value_ct[8];
	signed int freez_value_ct[4];
	signed int groov_bonus[6];
	signed int groov_bonus_max[6];
	signed int score;
	signed int bonus;
	signed int max_combo_ct;
	signed int jump_ct;
	signed short dance_level;
	signed short fixed_level;
};

struct _EDSSAVE_W
{
	_EDSS_PLAY_W reg[2];
	unsigned int PlayFlag[128];
};

struct _anon2
{
	unsigned char state;
	unsigned char perfect;
	unsigned short play_count;
	unsigned short play_time;
	unsigned short clear_count;
	unsigned short first_clear_count;
	unsigned short first_clear_time;
};

struct _anon3
{
	unsigned char appear;
	unsigned char ending_flag;
	signed char help_count;
	unsigned char pad;
	signed int bonus_count;
	signed int dummy[2];
	_anon2 subject[100];
};

union _anon4
{
	signed int id;
	float fd;
};

struct _anon5
{
	struct
	{
		unsigned long number : 16;
		unsigned long sector : 24;
		unsigned long size : 24;
	};
};

struct _anon6
{
	unsigned char old_stat;
	unsigned char cur_stat;
	unsigned char release_ct;
	unsigned char warning;
};

struct _anon7
{
	unsigned char game_over;
	unsigned char calorie_check;
	unsigned char pad[2];
};

struct _anon8
{
	_anon4 x0;
	_anon4 y0;
	unsigned int z0;
	unsigned char r0;
	unsigned char g0;
	unsigned char b0;
	unsigned char a0;
};

struct _InputBuffer
{
	unsigned long current_buffer;
	_InputData data[2];
};

struct popular
{
	signed short cur_c;
	signed short last_c;
	unsigned short count[4][256];
};

struct _anon9
{
	unsigned int program_calorie[6];
	unsigned int program_play_count[6];
	unsigned int song_calorie[5][80];
	unsigned int song_play_count[5][80];
};

struct _play_backup_w
{
	eval_w stage_evaluation;
	eval_w total_evaluation;
	play_mode mode;
	play_his his[7];
	unsigned int play_stage;
};

struct G_RANKING_W_
{
	char name[4];
	unsigned long score;
};

struct _backup_w
{
	_play_backup_w player[2];
	signed char stage;
	signed char start_chip;
	signed char extra_chip;
	signed char use_chip;
	signed char lost_chip;
};

struct _tag_cMWMgRunRecord
{
	signed int time;
	unsigned char bcd_time;
	unsigned char bcd_type;
	unsigned char fps;
	char pad[1];
};

struct play_his
{
	signed short music;
	signed short edit_id;
	unsigned char seq_kind;
	signed char roulette;
	signed char extra;
	signed char pad;
};

struct _tag_cDDR8Record1
{
	unsigned int Score[10];
	unsigned int Bonus[10];
	unsigned int nPlayed;
	unsigned short LinkNum;
	unsigned short Combo[10];
	unsigned short ComboMax[10];
	unsigned char Level[10];
	unsigned char pad[2];
};

struct tm
{
	signed int tm_sec;
	signed int tm_min;
	signed int tm_hour;
	signed int tm_mday;
	signed int tm_mon;
	signed int tm_year;
	signed int tm_wday;
	signed int tm_yday;
	signed int tm_isdst;
};

struct play_hist
{
	signed int music_count;
	unsigned char input[8];
};
</pre>
SLUS-21174 - DanceDanceRevolution EXTREME 2 - 2005-06-10 Prototype Build
<pre>
struct oni_course
{
	unsigned int course_allnum;
	unsigned int course_defnum;
	signed short avairable_level;
	signed short order;
	signed short start_life;
	signed short flag;
	unsigned int stage;
	signed int single_steps;
	signed int double_steps;
	oni_mode mode[20];
};

struct music_info
{
	char base_name[6];
	signed char kind;
	signed char album;
	signed short dance_num;
	signed short order;
	unsigned int main_track;
	unsigned int select_track;
	unsigned short bpm_max;
	unsigned short bpm_min;
	unsigned short verm_num;
	unsigned short pcseq_num;
	unsigned long hide;
	signed short adjust_mc;
	unsigned int difficulty[2];
	unsigned int special;
	unsigned short max_spm[9];
	unsigned short avg_spm[9];
	unsigned short avg_jpm[9];
	unsigned short chaos_v[9];
	unsigned short freez_v[9];
	char* title;
	char* l_name;
};

struct _tag_cPointSaveWork
{
	signed int total_point;
	signed int max_total_point;
};

struct _tag_cDDRFInfoData
{
	unsigned char Information[256];
	signed int UnlockedNum[256];
	signed int unum;
	char pad[12];
};

struct _EDSS_PLAY_W
{
	_EDSS_DATA_W p_single[3];
	_EDSS_DATA_W p_double[3];
};

struct play_w
{
	signed int music_counter;
	signed int beat_counter;
	signed int cur_p_counter;
	signed int last_p_counter;
	signed int begin_beat_count;
	signed int go_beat_count;
	signed int finish_beat_count;
	signed int end_beat_count;
	signed int game_start_music_count;
	signed int game_finish_music_count;
	signed int back_trans_start_music_count;
	signed int last_fs_nct;
	signed short last_input_count[8];
	play_hist history[8];
	signed int cur_his;
	signed int pre_nct;
	signed int cur_nct;
	signed int disp_nct;
	signed int cur_great_combo;
	signed int cur_miss_combo;
	signed int max_great_combo;
	signed int max_miss_combo;
	signed int miss_start_count;
	signed int cur_great_combo_total;
	signed int max_great_combo_total;
	unsigned short input;
	unsigned char dead;
	signed char strictness;
	signed short panel_count[8];
	signed short message_ct;
	signed short message_id;
	signed short meter_cur;
	signed short meter_vol;
	signed short meter_ct;
	signed short offset;
	signed short light_offset;
	signed short meter_state;
	signed short anm_no;
	signed short dance_class;
	signed int bar_start;
	signed int bar_end;
	_anon14 extra_arrow;
};

struct oni_mode
{
	unsigned int link_num;
	unsigned char seq_kind;
	unsigned char seq_transfer;
	unsigned char sp_music;
	unsigned char add_life;
	struct
	{
		unsigned int speed : 4;
		unsigned int boost : 2;
		unsigned int hidden : 3;
		unsigned int turn : 2;
		unsigned int thinout : 2;
		unsigned int dark : 2;
		unsigned int simultaneous : 3;
		unsigned int scroll : 2;
		unsigned int freeze : 2;
		unsigned int free : 1;
		unsigned int soft : 1;
		unsigned int vivid : 2;
		unsigned int anime : 2;
		unsigned int pad : 4;
	};
};

struct sequence
{
	signed int beat_count;
	signed short kind;
	signed short next_change;
	signed short music_count;
	signed short judge_count;
	signed short stolen_count;
	signed short op_note_ct;
	unsigned int hold_length[8];
	unsigned char hold_stat[8];
};

struct _EDS_OPTION_DATA
{
	struct
	{
		unsigned int speed : 4;
		unsigned int boost : 2;
		unsigned int hidden : 2;
		unsigned int turn : 2;
		unsigned int thinout : 2;
		unsigned int dark : 2;
		unsigned int simultaneous : 3;
		unsigned int scroll : 2;
		unsigned int freeze : 2;
		unsigned int player : 1;
		unsigned int step : 3;
		unsigned int stage : 4;
		unsigned int pad : 3;
	};
};

struct popular
{
	signed short cur_c;
	signed short last_c;
	unsigned short count[4][256];
};

struct _tag_cDDR8SaveData
{
	_DDRCommonHeader CommonHeader;
	_tag_cDDR8Option Option;
	_tag_cDDR8Record1 MRecord[80];
	_tag_cDDRFInfoData InfoData;
	unsigned int nMusic;
	unsigned int nBoot;
	unsigned int nPlayerType[3];
	unsigned int nDifficulty[5];
	unsigned int ArrowType;
	signed int nwork[2];
	unsigned char LessonWork[32];
	_tag_cDDR8OniRecord1 OniRecord[78];
	_tag_cDDR8OniRecord1 NonstopRecord[78];
	popular popular;
	unsigned int HideAppFlag[8];
	unsigned int HideAppNewFlag[8];
	unsigned int HideFlag[8];
	unsigned int HideNewFlag[8];
	_EDSSAVE_W EdsRecords;
	_anon7 dmm;
	oni_mode nonstop_course[39];
	oni_course nonstop_order[10];
	unsigned int nMusic_on_last_unlocked;
	_eyetoy_option eyetoy_option;
	_tag_cDDR8Record1 mg_solo_MRecord[80];
	_anon13 wk_save[2];
	signed int workout_user_num;
	_anon11 workout_user[10];
	_tag_cPointSaveWork point_work;
	_tag_cNetSaveWork net_work;
};

struct _tag_cDDR8OniRecord1
{
	unsigned int Time[2];
	unsigned int Score[2];
	unsigned short Combo[2];
	unsigned char Stage[2];
	unsigned char Miss[2];
	unsigned char AllStage[2];
	unsigned char Level[2];
	unsigned char is_first_clear;
	unsigned char is_full_combo_flag[2];
	unsigned char pad[1];
	unsigned short ClearNum[2];
	unsigned char pad2[2];
};

struct oni_cource_work
{
	signed int id;
	signed int init_ok;
	oni_course* course[41];
	signed int tex_kind;
	signed int tex_load_step;
	unsigned char seqkind_tab[20];
	signed int dancer_flag;
};

struct play_mode
{
	unsigned char seq_kind;
	unsigned char seq_transfer;
	unsigned char style;
	unsigned char pccard_seq;
	unsigned char mcard_seq;
	unsigned char padding;
	signed short edseq_id;
	struct
	{
		unsigned int hidden : 3;
		unsigned int thinout : 1;
		unsigned int free : 1;
		unsigned int soft : 1;
		unsigned int boost : 2;
		unsigned int speed : 5;
		unsigned int scroll : 2;
		unsigned int freeze : 1;
		unsigned int vivid : 2;
		unsigned int anime : 2;
		unsigned int dark : 1;
		unsigned int simultaneous : 2;
	};
};

struct _EDS_RANK_DATA
{
	struct
	{
		unsigned int single_normal : 8;
		unsigned int single_difficult : 8;
		unsigned int double_normal : 8;
		unsigned int double_difficult : 8;
	};
};

struct _EDS_NONSTOP_SAVE_W
{
	signed int music_id;
	_EDS_RANK_DATA recourd[2];
	_EDS_OPTION_DATA flag[2];
};

struct _anon0
{
	unsigned char old_stat;
	unsigned char cur_stat;
	unsigned char release_ct;
	unsigned char warning;
};

struct _DDRCommonHeader
{
	unsigned char Type;
	unsigned char Platform;
	unsigned char Hardware;
	unsigned char Version;
	unsigned char Area;
	signed char tmp;
	unsigned short title;
	unsigned int t_info[2];
};

struct _EDSSAVE_W
{
	_EDSS_PLAY_W reg[2];
	unsigned int PlayFlag[128];
	_EDS_OPTION_DATA option;
	_EDS_NONSTOP_SAVE_W NonstopData[39];
	_EDS_NONSTOP_SAVE_W NonstopOrderData[20][10];
};

struct _tag_cNetSaveWork
{
	unsigned char last_konami_id[32];
	unsigned char auto_router_support;
	unsigned char auto_router_support_flag;
	unsigned short udp_port;
	char pad[28];
};

union _anon1
{
	signed int id;
	float fd;
};

struct play_hist
{
	signed int music_count;
	unsigned char input[8];
};

struct _anon2
{
	unsigned int program_calorie[24];
	unsigned int program_play_count[24];
	unsigned int song_calorie[5][80];
	unsigned int song_play_count[5][80];
};

struct _tag_cDDR8Record1
{
	unsigned int Score[10];
	unsigned int Bonus[10];
	unsigned int nPlayed;
	unsigned short LinkNum;
	unsigned short Combo[10];
	unsigned short ComboMax[10];
	unsigned char Level[10];
	unsigned char pad[2];
};

struct _anon3
{
	_anon4 line_a[8];
	_anon4 line_b[8];
	_anon4 line_c[8];
	signed int num;
};

struct _anon4
{
	_anon1 x0;
	_anon1 y0;
	unsigned int z0;
	unsigned char r0;
	unsigned char g0;
	unsigned char b0;
	unsigned char a0;
};

struct play_his
{
	signed short music;
	signed short edit_id;
	unsigned char seq_kind;
	signed char roulette;
	signed char extra;
	signed char pad;
};

struct _anon5
{
	unsigned char cone_state[8];
	unsigned char state;
	unsigned char perfect;
	unsigned short play_count;
	unsigned short play_time;
	unsigned short clear_count;
	unsigned short first_clear_count;
	unsigned short first_clear_time;
};

struct _anon6
{
	signed int date;
	struct
	{
		unsigned int weight : 12;
		unsigned int calorie : 20;
	};
	struct
	{
		unsigned int play_count : 12;
		unsigned int play_time : 20;
	};
};

struct g_game_w
{
	signed short state;
	signed short genre;
	music_info* mip;
	signed short stage;
	signed short next_stage;
	signed short failed;
	signed short level;
	signed char game_kind;
	signed char world;
	signed char oni_nonstop_course_id;
	signed char event_mode;
	signed char event_two_flag;
	signed char style;
	signed char music_group;
	signed char music_select_mode;
	signed char meter_kind;
	signed short music;
	signed char oni_nonstop_mode;
	unsigned char oni_load_step;
	signed char oni_nonstop_difficulty;
	signed char use_oni_gauge;
	signed char beginner_mode;
	signed char beginner_selected;
	signed char freez_selected;
	signed char judge_invalid;
	signed short oni_next_music;
	music_info* oni_next_mip;
	g_each_w player[2];
	signed char music_table[128];
	note_status note_status_table[300];
	_anon0 hc_work[8];
	signed int mode_quit_ct[2];
	signed int force_exit_ct[2];
	signed int workout_play_time;
	signed int old_play_time;
	signed int menu_num;
	signed int total_stage;
	signed int now_bpm;
	unsigned char* last_data_addr;
	unsigned char edit_name[12];
	unsigned char workout_flg;
	unsigned char workout_step_flg;
	unsigned char auto_play_flg[2];
	unsigned char caution_flg;
	unsigned char mode_quit_flg;
	unsigned char lib_loaded;
	unsigned char force_exit_flg;
	unsigned char train_state;
	unsigned char padding[3];
	struct
	{
		unsigned int lesson_flag : 8;
		unsigned int lesson_auto_play_flag : 8;
		unsigned int lesson_skip_selecter_flag : 1;
	};
	unsigned int dmm_retry;
	unsigned char oni_load_start0;
	unsigned char oni_load_start1;
	unsigned char oni_load_end0;
	unsigned char oni_load_end1;
	unsigned char oni_order_step;
	unsigned char oni_order_stage;
	unsigned char oni_order_cursor;
	unsigned char oni_order_top_stage;
	unsigned char oni_order_selopt;
	unsigned char anime1_load_flg;
	unsigned char anime2_load_flg;
	unsigned char temp_sqk[2];
	unsigned char endless_flag;
	unsigned char eyetoy_flag;
	unsigned char dancemaster_flag;
	unsigned char step_mark_color;
	unsigned char hand_solo_seq_kind;
	unsigned char is_course_exit;
	unsigned char to_opt_select;
	unsigned char is_new_clothes;
	unsigned char nononi_msel_flag;
	unsigned char select_randaom_flag;
	unsigned char fp_cur_back_flag;
	unsigned char lib_sel_num;
	unsigned int bar_state;
	signed int rloadtex_num;
	signed int rload_next_step;
	char quit_course_flag;
	char nonstop_selopt_flag;
	unsigned char dancer_id[3];
	_anon3 line_data[16];
	signed int line_speed;
	signed int bk_ef_kind;
	signed int bk_ef_colset[3];
	signed int bk_ef_type;
	signed int bk_ef_reset;
	signed int event_result_exit_flag;
	signed int network_flag;
	signed int read_end_flag;
	signed int online_play_mode;
	signed int advance_flag;
	signed int advance_mode;
	signed int endless_select_difficulty;
	signed int nonstop_dance_meter;
	signed int network_get_data;
	signed int network_get_data_step;
	signed int network_start_data_step;
};

struct g_each_w
{
	unsigned int play_time;
	unsigned int game_time;
	unsigned int game_time_total;
	signed char select;
	signed char character;
	signed char costume;
	signed char motiontype;
	signed char loaded_model;
	signed char loaded_texture;
	signed char loaded_motion;
	unsigned char play_disp_flag;
	unsigned char model_disp_flag;
	unsigned char gauge_disp_flag;
	signed short cur_point;
	signed int cur_life;
	unsigned int score;
	unsigned int old_score;
	unsigned int real_score;
	unsigned int bonus;
	unsigned int old_bonus;
	unsigned int challenge_score;
	unsigned int real_challenge_score;
	unsigned int cal;
	unsigned int old_cal;
	unsigned int real_cal;
	unsigned int disp_cal;
	unsigned int average_cal;
	signed int workout_norm_cal;
	signed int workout_norm_minute;
	signed int old_norm_cal;
	signed int old_norm_minute;
	signed int minimum_cal;
	unsigned char add_cal_flg;
	unsigned char chk_cal_flg;
	unsigned char combo_no_disp_flag;
	unsigned char pad;
	unsigned int play_stage;
	unsigned int decode_key1;
	unsigned int decode_key2;
	unsigned int decode_key3;
	signed int used_unfair_command;
	signed int nonstop_dead_flag;
	play_mode mode;
	play_his his[7];
	eval_w stage_evaluation;
	eval_w total_evaluation;
	play_w play_work;
	signed int total_notes;
	signed int total_jump;
	signed int total_freez;
	signed int category;
	signed int total_category;
	signed int ck_freeze_seq_pos[2];
	sequence sequence_buff[6144];
	signed int total_notes_all;
	signed int total_freez_all;
	unsigned char name[20];
	char winlose_flag;
};

struct _anon7
{
	unsigned char evboot[24];
	unsigned char is_savedata;
	signed char max_area;
	signed char disp_type;
	char pading;
	unsigned char dancer_use_cnt[24];
	signed int cur_cursor;
	unsigned int all_clear_count;
	unsigned int all_play_time;
	signed int route[200];
	_anon5 subject[200];
};

union _anon8
{
	unsigned int ui;
	_anon9 s;
};

struct _anon9
{
	unsigned char d[4];
};

struct _anon10
{
	signed int weight;
	signed int lbs;
	signed int norm_type;
	signed int norm_time;
	signed int norm_calorie;
	signed int workout_step;
	signed int simultaneous_step;
	_anon6 history[400];
	signed int check_sum_val;
};

struct _anon11
{
	struct
	{
		unsigned int uno : 8;
		unsigned int ino : 8;
		unsigned int frame_no : 8;
		unsigned int f_passuse : 1;
		unsigned int f_enable : 1;
		unsigned int f_program_free : 1;
	};
	_anon8 userpass;
	_anon10 pwork;
	_anon2 workout_calorie_record;
	oni_course program_order;
};

struct _anon12
{
	struct
	{
		unsigned long number : 16;
		unsigned long sector : 24;
		unsigned long size : 24;
	};
};

struct _anon13
{
	unsigned char game_over;
	unsigned char calorie_check;
	unsigned char pad[2];
};

struct _anon14
{
	signed int state;
	signed int music_count;
	signed int dir;
	signed int effect_count;
	signed int id;
};

struct note_status
{
	unsigned char state[8];
	unsigned int length[8];
};

struct _tag_cDDR8Option
{
	unsigned char Sound;
	unsigned char Voice;
	signed char Timing;
	char pad_sound[1];
	char EditKey[24];
	unsigned char KeyConfig[4];
	unsigned char DModeSet;
	unsigned char Vibration;
	unsigned char DPlay;
	char pad_cont[1];
	unsigned char AutoSave;
	unsigned char FolderLoad;
	char pad_mc[2];
	unsigned char Level;
	unsigned char MaxStage[3];
	unsigned char GameOver;
	unsigned char TimeLimit;
	unsigned char EventMode;
	unsigned char DefaultDifficulty;
	char pad_game[8];
	unsigned char BgEffect;
	unsigned char BgBright;
	unsigned char DangerDisplay;
	unsigned char StepMarkColor;
	signed char screen_x;
	signed char screen_y;
	unsigned char FlickerFree;
	unsigned char MarvellousDisplay;
	unsigned char WorkoutMeasure;
	unsigned char WorkoutDisplay;
	unsigned char WorkoutTime;
	unsigned char WorkoutPlayDefault;
	unsigned char WorkoutWeightUnit;
	char pad_workout[3];
	unsigned char Language;
	char pad_lang[2];
	unsigned char NetworkAutomatic;
	unsigned int NetworkUdpPort;
	unsigned char DollDisp;
	unsigned char DollChara[3];
	unsigned char DollGuestNum;
	unsigned char DollSelect;
	char pad[2];
};

struct eval_w
{
	signed int value_ct[8];
	signed int freez_value_ct[4];
	signed int score;
	signed int bonus;
	signed int max_combo_ct;
	signed short dance_level;
	signed short fixed_level;
};

struct _eyetoy_option
{
	char depth;
	char pdf;
	char frame;
	unsigned char bright;
};

struct _EDSS_DATA_W
{
	unsigned int score[2];
	signed int combo;
	signed int stage;
};
</pre>
SLUS-29037 - DDRMAX -DanceDanceRevolution- - 2002-08-06 Prototype Build
<pre>
struct oni_mode
{
	music_info* mip;
	unsigned char seq_kind;
	unsigned char seq_transfer;
	unsigned char sp_music;
	unsigned char add_life;
	struct
	{
		unsigned int hidden : 2;
		unsigned int thinout : 1;
		unsigned int free : 1;
		unsigned int soft : 1;
		unsigned int boost : 1;
		unsigned int speed : 5;
		unsigned int scroll : 2;
		unsigned int freeze : 1;
		unsigned int vivid : 2;
		unsigned int anime : 2;
		unsigned int pad : 14;
	};
};

struct music_info
{
	char base_name[6];
	signed char kind;
	signed char album;
	signed short dance_num;
	signed short order;
	unsigned short main_track;
	unsigned short select_track;
	unsigned short bpm_max;
	unsigned short bpm_min;
	unsigned short verm_num;
	unsigned short pcseq_num;
	unsigned long hide;
	signed short adjust_mc;
	unsigned int difficulty[2];
	unsigned int special;
	unsigned short max_spm[6];
	unsigned short avg_spm[6];
	unsigned short avg_jpm[6];
	unsigned short chaos_v[6];
	unsigned short freez_v[6];
	char* title;
	char* l_name;
};

struct oni_cource_work
{
	signed int id;
	signed int init_ok;
	oni_course* course[64];
};

struct oni_course
{
	unsigned int course_allnum;
	unsigned int course_defnum;
	signed short avairable_level;
	signed short order;
	signed short start_life;
	signed short pad;
	signed int single_steps;
	signed int double_steps;
	char* coursename;
	oni_mode mode[1];
};

struct note_status
{
	unsigned char state[8];
	unsigned int length[8];
};

struct G_INPUT_W_
{
	_InputData* dp;
	_InputBuffer buffer;
};

struct _InputData
{
	unsigned short player_input[4];
	unsigned short player_input_trigger[4];
	unsigned short player_input_released[4];
	unsigned short etc;
	unsigned short etc_trigger;
	unsigned short etc_released;
	unsigned short padding;
};

struct eval_w
{
	signed int value_ct[7];
	signed int freez_value_ct[3];
	signed int groov_bonus[6];
	signed int groov_bonus_max[6];
	signed int score;
	signed int max_combo_ct;
	signed int jump_ct;
	signed short dance_level;
	signed short fixed_level;
};

struct G_SYS_W_
{
	G_INPUT_W_ input_w;
	tm start_tm;
	unsigned int v_counter;
	unsigned int s_counter;
	signed int u_counter;
	unsigned char entry_bit;
	char vpf;
	char pad[2];
};

struct sequence
{
	signed int beat_count;
	signed short kind;
	signed short next_change;
	signed short music_count;
	signed short judge_count;
	signed short stolen_count;
	signed short op_note_ct;
	unsigned int hold_length[8];
	unsigned char hold_stat[8];
};

struct play_hist
{
	signed int music_count;
	unsigned char input[8];
};

struct _InputBuffer
{
	unsigned long current_buffer;
	_InputData data[2];
};

struct _anon0
{
	unsigned char old_stat;
	unsigned char cur_stat;
	unsigned char release_ct;
	unsigned char warning;
};

struct play_mode
{
	unsigned char seq_kind;
	unsigned char seq_transfer;
	unsigned char style;
	unsigned char pccard_seq;
	unsigned char mcard_seq;
	signed short edseq_id;
	struct
	{
		unsigned int hidden : 2;
		unsigned int thinout : 1;
		unsigned int free : 1;
		unsigned int soft : 1;
		unsigned int boost : 1;
		unsigned int speed : 5;
		unsigned int scroll : 2;
		unsigned int freeze : 1;
		unsigned int vivid : 2;
		unsigned int anime : 2;
		unsigned int pad : 14;
	};
};

struct g_game_w
{
	signed short state;
	signed short genre;
	music_info* mip;
	signed char start_chip;
	signed char extra_chip;
	signed char use_chip;
	signed char lost_chip;
	signed short stage;
	signed short next_stage;
	signed short failed;
	signed short level;
	signed char game_kind;
	signed char world;
	signed char nonstop;
	signed char event_mode;
	signed char style;
	signed char music_group;
	signed char music_select_mode;
	signed char extra_stage;
	signed char extra_fix;
	signed char final_fix;
	signed char meter_kind;
	signed char roulette_stage;
	signed char edit_total;
	signed char roulette_total;
	signed short music;
	signed char oni_mode;
	unsigned char oni_load_step;
	signed short oni_next_music;
	music_info* oni_next_mip;
	g_each_w player[2];
	signed char music_table[128];
	note_status note_status_table[300];
	_anon0 hc_work[8];
	signed int demoloop_ct;
	signed int mode_quit_ct[2];
	signed int force_exit_ct[2];
	signed int diet_play_time;
	signed int old_play_time;
	signed int menu_num;
	signed int total_stage;
	signed int now_bpm;
	unsigned char* last_data_addr;
	unsigned char edit_name[12];
	unsigned char diet_flg;
	unsigned char auto_play_flg;
	unsigned char caution_flg;
	unsigned char mode_quit_flg;
	unsigned char lib_loaded;
	unsigned char force_exit_flg;
	unsigned char music_stop_flg;
	unsigned char train_state;
	unsigned char lesson_flag;
	unsigned char lesson_auto_play_flag;
	unsigned char oni_bk_bright;
	unsigned char cs_pad[1];
};

struct tm
{
	signed int tm_sec;
	signed int tm_min;
	signed int tm_hour;
	signed int tm_mday;
	signed int tm_mon;
	signed int tm_year;
	signed int tm_wday;
	signed int tm_yday;
	signed int tm_isdst;
};

struct play_his
{
	signed short music;
	signed int edit_id;
	unsigned char seq_kind;
	signed char roulette;
	signed char extra;
	signed char pad;
};

struct play_w
{
	signed int music_counter;
	signed int beat_counter;
	signed int cur_p_counter;
	signed int last_p_counter;
	signed int begin_beat_count;
	signed int go_beat_count;
	signed int finish_beat_count;
	signed int end_beat_count;
	signed int game_start_music_count;
	signed int game_finish_music_count;
	signed int back_trans_start_music_count;
	signed int last_fs_nct;
	signed short last_input_count[8];
	play_hist history[8];
	signed int cur_his;
	signed int pre_nct;
	signed int cur_nct;
	signed int disp_nct;
	signed int cur_great_combo;
	signed int cur_miss_combo;
	signed int max_great_combo;
	signed int max_miss_combo;
	signed int miss_start_count;
	unsigned short input;
	unsigned char dead;
	signed char strictness;
	signed short panel_count[8];
	signed short message_ct;
	signed short message_id;
	signed short meter_cur;
	signed short meter_vol;
	signed short meter_ct;
	signed short dance_class;
	signed int bar_start;
	signed int bar_end;
};

struct g_each_w
{
	unsigned int play_time;
	unsigned int game_time;
	unsigned int game_time_total;
	signed char select;
	signed char character;
	signed char costume;
	signed char motiontype;
	signed char loaded_model;
	signed char loaded_texture;
	signed char loaded_motion;
	unsigned char play_disp_flag;
	unsigned char model_disp_flag;
	unsigned char gauge_disp_flag;
	signed short cur_point;
	signed int cur_life;
	unsigned int score;
	unsigned int old_score;
	unsigned int real_score;
	unsigned int bonus;
	unsigned int old_bonus;
	unsigned int max_score;
	unsigned int old_max_score;
	unsigned int max_bonus;
	unsigned int old_max_bonus;
	unsigned int cal;
	unsigned int old_cal;
	unsigned int real_cal;
	unsigned int disp_cal;
	unsigned int average_cal;
	signed int diet_norm_cal;
	signed int diet_norm_minute;
	signed int old_norm_cal;
	signed int old_norm_minute;
	signed int minimum_cal;
	unsigned char add_cal_flg;
	unsigned char chk_cal_flg;
	unsigned char pad[2];
	unsigned int play_stage;
	unsigned int decode_key1;
	unsigned int decode_key2;
	unsigned int decode_key3;
	play_mode mode;
	play_his his[7];
	eval_w stage_evaluation;
	eval_w total_evaluation;
	play_w play_work;
	signed int total_notes;
	signed int total_jump;
	signed int total_freez;
	signed int category;
	signed int total_category;
	sequence sequence_buff[6144];
};
</pre>
SLUS-29074 - DDRMAX2 -DanceDanceRevolution- - 2003-08-01 Prototype Build
<pre>
struct tm
{
	signed int tm_sec;
	signed int tm_min;
	signed int tm_hour;
	signed int tm_mday;
	signed int tm_mon;
	signed int tm_year;
	signed int tm_wday;
	signed int tm_yday;
	signed int tm_isdst;
};

struct music_info
{
	char base_name[6];
	signed char kind;
	signed char album;
	signed short dance_num;
	signed short order;
	unsigned short main_track;
	unsigned short select_track;
	unsigned short bpm_max;
	unsigned short bpm_min;
	unsigned short verm_num;
	unsigned short pcseq_num;
	unsigned long hide;
	signed short adjust_mc;
	unsigned int difficulty[2];
	unsigned int special;
	unsigned short max_spm[9];
	unsigned short avg_spm[9];
	unsigned short avg_jpm[9];
	unsigned short chaos_v[9];
	unsigned short freez_v[9];
	char* title;
	char* l_name;
};

struct oni_steps
{
	unsigned int link_num;
	unsigned short steps[4][2];
};

struct oni_course
{
	unsigned int course_allnum;
	unsigned int course_defnum;
	signed short flag;
	signed short order;
	signed short start_life;
	signed short stage;
	signed int single_steps;
	signed int double_steps;
	signed int hide;
	signed int option;
	oni_mode mode[20];
};

struct _tag_cDDR7OniRecord1
{
	unsigned int Score[4];
	unsigned short Time[4];
	unsigned short Combo[4];
	unsigned short Miss[4];
	unsigned char Stage[4];
	unsigned char Clear[4];
	unsigned char Level[4];
	unsigned char is_first_clear;
	unsigned char pad[3];
};

struct oni_mode
{
	unsigned int link_num;
	unsigned char seq_kind;
	unsigned char seq_transfer;
	unsigned char sp_music;
	unsigned char add_life;
	struct
	{
		unsigned int hidden : 2;
		unsigned int thinout : 1;
		unsigned int free : 1;
		unsigned int soft : 1;
		unsigned int boost : 2;
		unsigned int speed : 5;
		unsigned int scroll : 2;
		unsigned int freeze : 1;
		unsigned int vivid : 2;
		unsigned int anime : 2;
		unsigned int dark : 1;
		unsigned int pad : 12;
	};
};

struct _tag_cDDR7Option
{
	unsigned char Sound;
	unsigned char Voice;
	signed char Timing;
	char pad_sound[1];
	unsigned char KeyConfig[4];
	unsigned char Vibration;
	unsigned char DPlay;
	char pad_cont[2];
	unsigned char AutoSave;
	unsigned char FolderLoad;
	char pad_mc[2];
	unsigned char Level;
	unsigned char MaxStage[3];
	unsigned char GameOver;
	unsigned char TimeLimit;
	unsigned char EventMode;
	unsigned char DefaultDifficulty;
	char pad_game[8];
	unsigned char BgEffect;
	unsigned char BgBright;
	unsigned char DangerDisplay;
	unsigned char StepMarkColor;
	signed char screen_x;
	signed char screen_y;
	unsigned char FlickerFree;
	unsigned char SongDisplay;
	unsigned char DietMeasure;
	unsigned char DietDisplay;
	unsigned char DietTime;
	unsigned char DietPlayDefault;
	unsigned char DietWeightUnit;
	char pad_diet[3];
	unsigned char Language;
	char pad_lang[7];
	unsigned char DollDisp;
	unsigned char DollGuestNum;
	unsigned char DollChara[3];
	char pad[3];
};

struct note_status
{
	unsigned char state[8];
	unsigned int length[8];
};

struct _EDSS_DATA_W
{
	unsigned int score[2];
	signed int combo;
	signed int stage;
};

struct _DDRCommonHeader
{
	unsigned char Type;
	unsigned char Platform;
	unsigned char Hardware;
	unsigned char Version;
	unsigned char Area;
	signed char tmp;
	unsigned short title;
	unsigned int t_info[2];
};

struct _EDSS_PLAY_W
{
	_EDSS_DATA_W p_single[3];
	_EDSS_DATA_W p_double[3];
};

struct play_mode
{
	unsigned char seq_kind;
	unsigned char seq_transfer;
	unsigned char style;
	unsigned char pccard_seq;
	unsigned char mcard_seq;
	unsigned char padding;
	signed short edseq_id;
	struct
	{
		unsigned int hidden : 2;
		unsigned int thinout : 1;
		unsigned int free : 1;
		unsigned int soft : 1;
		unsigned int boost : 2;
		unsigned int speed : 5;
		unsigned int scroll : 2;
		unsigned int freeze : 1;
		unsigned int vivid : 2;
		unsigned int anime : 2;
		unsigned int dark : 1;
		unsigned int pad : 12;
	};
};

struct sequence
{
	signed int beat_count;
	signed short kind;
	signed short next_change;
	signed short music_count;
	signed short judge_count;
	signed short stolen_count;
	signed short op_note_ct;
	unsigned int hold_length[8];
	unsigned char hold_stat[8];
};

struct oni_cource_work
{
	signed int id;
	signed int init_ok;
	oni_course* course[32];
	unsigned char seqkind_tab[20];
};

struct _EDSSAVE_W
{
	_EDSS_PLAY_W reg[2];
	_EDSS_DATA_W max_point;
	unsigned int PlayFlag[90];
};

struct eval_w
{
	signed int value_ct[7];
	signed int freez_value_ct[4];
	signed int groov_bonus[6];
	signed int groov_bonus_max[6];
	signed int score;
	signed int max_combo_ct;
	signed int jump_ct;
	signed short dance_level;
	signed short fixed_level;
};

struct play_hist
{
	signed int music_count;
	unsigned char input[8];
};

struct _anon0
{
	unsigned int program_calorie[9];
	unsigned int program_play_count[9];
	unsigned int song_calorie[5][80];
	unsigned int song_play_count[5][80];
};

struct machine_point_work
{
	unsigned int hide_show[2];
	unsigned int status;
	unsigned int period_time;
	signed int cur_point;
};

struct G_INPUT_W_
{
	_InputData* dp;
	_InputBuffer buffer;
};

struct _InputData
{
	unsigned short player_input[4];
	unsigned short player_input_trigger[4];
	unsigned short player_input_released[4];
	unsigned short etc;
	unsigned short etc_trigger;
	unsigned short etc_released;
	unsigned short padding;
};

struct _anon1
{
	unsigned char old_stat;
	unsigned char cur_stat;
	unsigned char release_ct;
	unsigned char warning;
};

struct G_SYS_W_
{
	G_INPUT_W_ input_w;
	tm start_tm;
	unsigned int v_counter;
	unsigned long v_counter2;
	unsigned int s_counter;
	signed int u_counter;
	unsigned char entry_bit;
	char vpf;
	char pad[2];
};

struct _tag_cDDR7SaveData
{
	_DDRCommonHeader CommonHeader;
	_tag_cDDR7Option Option;
	_tag_cDDR7Record1 MRecord[80];
	unsigned char Information[144];
	unsigned int nMusic;
	unsigned int nBoot;
	unsigned int nPlayerType[3];
	unsigned int nDifficulty[5];
	signed int nwork[2];
	unsigned char LessonWork[32];
	_tag_cDDR7OniRecord1 OniRecord[32];
	popular popular;
	G_RANKING_W_ high_score[30];
	machine_point_work machine_p;
	unsigned int HideMusic[4];
	unsigned int HideFlag[4];
	unsigned int HideDoll[2];
	_EDSSAVE_W EdsRecords;
	oni_course oni_order[3];
	oni_course dietprogram_order[3];
	_anon0 diet_calorie_record[2];
};

struct g_game_w
{
	signed short state;
	signed short genre;
	music_info* mip;
	signed char start_chip;
	signed char extra_chip;
	signed char use_chip;
	signed char lost_chip;
	signed short stage;
	signed short next_stage;
	signed short failed;
	signed short level;
	signed char game_kind;
	signed char world;
	signed char nonstop;
	signed char event_mode;
	signed char style;
	signed char music_group;
	signed char music_select_mode;
	signed char extra_stage;
	signed char extra_fix;
	signed char final_fix;
	signed char meter_kind;
	signed char roulette_stage;
	signed char edit_total;
	signed char roulette_total;
	signed short music;
	signed char oni_mode;
	unsigned char oni_load_step;
	signed short oni_next_music;
	signed char oni_nonstop_difficulty;
	signed char oni_nonstop_option_selected;
	signed char oni_pad[2];
	signed char beginner_mode;
	signed char beginner_selected;
	signed char freez_selected;
	signed char beginner_pad[1];
	music_info* oni_next_mip;
	g_each_w player[2];
	signed char music_table[128];
	note_status note_status_table[300];
	_anon1 hc_work[8];
	signed int demoloop_ct;
	signed int mode_quit_ct[2];
	signed int force_exit_ct[2];
	signed int diet_play_time;
	signed int old_play_time;
	signed int menu_num;
	signed int total_stage;
	signed int now_bpm;
	unsigned char* last_data_addr;
	unsigned char* anime_data_addr;
	unsigned char* anime_buff_addr;
	unsigned char anime_load_flg;
	unsigned char anime1_load_flg;
	unsigned char anime2_load_flg;
	unsigned char edit_name[12];
	unsigned char diet_flg;
	unsigned char auto_play_flg;
	unsigned char caution_flg;
	unsigned char mode_quit_flg;
	unsigned char lib_loaded;
	unsigned char force_exit_flg;
	unsigned char music_stop_flg;
	unsigned char train_state;
	unsigned char lesson_flag;
	unsigned char lesson_auto_play_flag;
	unsigned char lesson_pad[2];
	unsigned char oni_load_start0;
	unsigned char oni_load_start1;
	unsigned char oni_load_end0;
	unsigned char oni_load_end1;
	unsigned char oni_order_step;
	unsigned char oni_order_stage;
	unsigned char oni_order_cursor;
	unsigned char oni_order_top_stage;
	unsigned char temp_sqk[2];
	unsigned char disp_seltu_flag;
	unsigned char temp_pad[1];
	unsigned char endless_flag;
	unsigned char endless_pad[3];
};

struct _tag_cDDR7Record1
{
	unsigned int Score[10];
	unsigned int Bonus[10];
	unsigned int nPlayed;
	unsigned short LinkNum;
	unsigned short Combo[10];
	unsigned short ComboMax[10];
	unsigned char Level[10];
	unsigned char little_flag[2];
	char pad[6];
};

struct play_w
{
	signed int music_counter;
	signed int beat_counter;
	signed int cur_p_counter;
	signed int last_p_counter;
	signed int begin_beat_count;
	signed int go_beat_count;
	signed int finish_beat_count;
	signed int end_beat_count;
	signed int game_start_music_count;
	signed int game_finish_music_count;
	signed int back_trans_start_music_count;
	signed int last_fs_nct;
	signed short last_input_count[8];
	play_hist history[8];
	signed int cur_his;
	signed int pre_nct;
	signed int cur_nct;
	signed int disp_nct;
	signed int cur_great_combo;
	signed int cur_miss_combo;
	signed int max_great_combo;
	signed int max_miss_combo;
	signed int miss_start_count;
	unsigned short input;
	unsigned char dead;
	signed char strictness;
	signed short panel_count[8];
	signed short message_ct;
	signed short message_id;
	signed short meter_cur;
	signed short meter_vol;
	signed short meter_ct;
	signed short dance_class;
	signed int bar_start;
	signed int bar_end;
};

struct popular
{
	signed short cur_c;
	signed short last_c;
	unsigned short count[4][150];
};

struct play_his
{
	signed short music;
	signed short edit_id;
	unsigned char seq_kind;
	signed char roulette;
	signed char extra;
	signed char pad;
};

struct _InputBuffer
{
	unsigned long current_buffer;
	_InputData data[2];
};

struct G_RANKING_W_
{
	char name[4];
	unsigned long score;
};

struct g_each_w
{
	unsigned int play_time;
	unsigned int game_time;
	unsigned int game_time_total;
	signed char select;
	signed char character;
	signed char costume;
	signed char motiontype;
	signed char loaded_model;
	signed char loaded_texture;
	signed char loaded_motion;
	unsigned char play_disp_flag;
	unsigned char model_disp_flag;
	unsigned char gauge_disp_flag;
	signed short cur_point;
	signed int cur_life;
	unsigned int score;
	unsigned int old_score;
	unsigned int real_score;
	unsigned int bonus;
	unsigned int old_bonus;
	unsigned int max_score;
	unsigned int old_max_score;
	unsigned int max_bonus;
	unsigned int old_max_bonus;
	unsigned int cal;
	unsigned int old_cal;
	unsigned int real_cal;
	unsigned int disp_cal;
	unsigned int average_cal;
	signed int diet_norm_cal;
	signed int diet_norm_minute;
	signed int old_norm_cal;
	signed int old_norm_minute;
	signed int minimum_cal;
	unsigned char add_cal_flg;
	unsigned char chk_cal_flg;
	unsigned char pad[2];
	unsigned int play_stage;
	unsigned int decode_key1;
	unsigned int decode_key2;
	unsigned int decode_key3;
	play_mode mode;
	play_his his[7];
	eval_w stage_evaluation;
	eval_w total_evaluation;
	play_w play_work;
	signed int total_notes;
	signed int total_jump;
	signed int total_freez;
	signed int category;
	signed int total_category;
	sequence sequence_buff[6144];
};
</pre>
