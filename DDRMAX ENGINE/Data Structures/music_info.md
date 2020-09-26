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

## Structure Data Members:
### base_name
This 6 byte array of characters denotes the shortened song name used for identification, as well as indicating what folder to use to load game data from in the case of system573 mixes.

### kind
TODO: Find out what this byte actually is used for.

### album
This single byte indicates which music icon is seen rotating at the upper-right corner of the song banner on the music select screen.

The specific values, and which icon it corresponds to does depend on the game - as some games have more categories than others, and some games might have their icons in different places in one mix from in another mix as a result.

### dance_num
TODO: Find out what this 2-byte value actually determines, and how it impacts music loading, and music select display related matters.

### order
TODO: Find out what this 2-byte value actually determines, and how it impacts music loading, and music select display related matters.

### main_track
TODO: Figure out what this is for

### select_track
This 2-byte value contains an index to an array of sound files - including sfx, announcer lines, background music in game menus, and
music preview tracks.  In Playstation2 mixes, at least, this value is not actually stored with the music_info data - instead, it seems 
that the data is taken from an array of indexes.

### bpm_max
Used for display purposes on the music select screen, this is the maximum BPM that the song reaches.

### bpm_min
Used for display purposes on the music select screen, this is the minimum BPM that the song reaches.

### vern_num
TODO: Figure out what this is for

### pcseq_num
TODO: Figure out what this is for

### hide
This 4 byte value determines how many unlock points are needed before this song can be selected on the music select screen.

### adjust_mc
TODO: Figure out what this value actually does

### difficulty
This pair of 4-byte values determines the foot ratings for each difficulty, with the first unsigned long belonging to single
chart difficulties, and the second belonging to doubles chart difficulties.

Each difficulty is given a single nibble (4 bits), allowing for a maximum foot rating of 15 (0xFF).  A chart not existing for a 
particular difficulty is denoted by that difficulty's foot rating being 0 (0x0), which also makes it unselectable on the music
select screen.

Each difficulty only taking up 1 nibble means that no modifications to the structure definition was needed going from having 3 difficulties (Light, Standard, Heavy) in MAX AC, to 4 difficulties (Light, Standard, Heavy, Oni) in MAX2 AC, to 5 difficulties (Beginner, Light, Standard, Heavy, Oni) in Extreme AC.

## special
TODO: Figure out what this value actually does

## max_spm
TODO: Figure out what this is for

## avg_spm
TODO: Figure out what this is for

## avg_jpm
TODO: Figure out what this is for

## chaos_v
TODO: Figure out what this is for

## freeze_v
TODO: Figure out what this is for

## title
TODO: Figure out what this is for

## l_name
TODO: Figure out what this is for
