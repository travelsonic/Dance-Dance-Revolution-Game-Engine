# music_info Data Structure
## What Is it:
A structure that containes metadata pertaining to each song in the game.  Most of it is used in the displaying of information about a song on the music select screen - as well as where the song appears on the song wheel.  There are data members though that seem to actually determines what music data (and relevant data like background music sequences, static background images, etc) are loaded upon song selection.

## Definition:*
```
typedef struct music_info{
    char base_name[6];
    char kind;
    char album;
    short dance_num;
    short order;
    unsigned short main_track;
    unsigned short select_track;
    unsigned short bpm_max;
    unsigned short bpm_min;
    unsigned short vern_num;
    unsigned short pcseq_num;
    unsigned long hide;
    short adjust_mc;
    unsigned int difficulty[2];
    unsigned int special;
    unsigned short max_spm[8];
    unsigned short avg_spm[8];
    unsigned short avg_jpm[8];
    unsigned short chaos_v[8];
    unsigned short freeze_v[8];
    char* title;
    char* l_name;
}music_info;
```

*HUGE shoutout to Root670 for actually extracting the symbols found in the DWARF debugging 
data that is left in each Playstation2 executable, making this possible.
