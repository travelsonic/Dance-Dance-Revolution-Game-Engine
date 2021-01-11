# music_info Data Structure
## What Is it:
A structure that containes metadata pertaining to each song in the game.  Most of it is used in the displaying of information about a song on the music select screen - as well as where the song appears on the song wheel.  There are data members though that seem to actually determines what music data (and relevant data like background music sequences, static background images, etc) are loaded upon song selection.

## Definition:*
```
struct music_info{
    char base_name[6];
    char kind;
    char album;
    short dance_num;
    short order;
    unsigned short main_track;
    unsigned short select_track;
    unsigned short bpm_max;
    unsigned short bpm_min;
    unsigned short verm_num;
    unsigned short pcseq_num;
    unsigned long hide;
    int adjust_mc;
    unsigned int difficulty[2];  
    unsigned int special;
    unsigned short max_spm[];   // NOTE:  These variables are being declared here 
    unsigned short avg_spm[];   //        without a length. In actuality, these  
    unsigned short avg_jpm[];   //        arrays are of a fixed length.  How long
    unsigned short chaos_v[];   //        they are is dependent on the game, and how 
    unsigned short freez_v[];   //        and how many difficulties are present. 
    char* title;
    char* l_name;
};
```

*HUGE shoutout to Root670 for actually extracting the symbols found in the DWARF debugging 
data that is left in each Playstation2 executable, making this possible.

## Structure Data Members:
### base_name
***Data Type:** char[6]* 

***Purpose:*** 

This 6 byte array of characters denotes the shortened song name used for identification, as well as indicating what folder to use to load game data from in the case of system573 mixes.

This array is 6 bytes long, though it appears that the names used don't exceed 5 characters - which means at least 2 possibilities (IMO) - the 6th element is used for a null terminator, OR it is there in case it is ever needed.  More research, of course, is needed.

### kind

***Data Type:** char* 

***Purpose:*** 

TODO: Find out what this byte actually is used for.


### album

***Data Type:** char* 

***Purpose:*** 

This single byte indicates which music icon is seen rotating at the upper-right corner of the song banner on the music select screen.

The specific values, and which icon it corresponds to does depend on the game - as some games have more categories than others, and some games might have their icons in different places in one mix from in another mix as a result.


### dance_num

***Data Type:** short* 

***Purpose:*** 

TODO: Find out what this 2-byte value actually determines, and how it impacts music loading, and music select display related matters.


### order

***Data Type:** short* 

***Purpose:*** 

TODO: Find out what this 2-byte value actually determines, and how it impacts music loading, and music select display related matters.


### main_track

***Data Type:** unsigned short* 

***Purpose:*** 

TODO: Figure out what this is for


### select_track

***Data Type:** unsigned short* 

***Purpose:*** 

This 2-byte value contains an index to an array of sound files - including sfx, announcer lines, background music in game menus, and
music preview tracks.  In Playstation2 mixes, at least, this value is not actually stored with the music_info data - instead, it seems 
that the data is taken from an array of indexes.


### bpm_max

***Data Type:** unsigned short* 

***Purpose:*** 

Used for display purposes on the music select screen, this is the maximum BPM that the song reaches.


### bpm_min

***Data Type:** unsigned short* 

***Purpose:*** 

Used for display purposes on the music select screen, this is the minimum BPM that the song reaches.


### verm_num

***Data Type:** unsigned short* 

***Purpose:*** 

TODO: Figure out what this is for


### pcseq_num

***Data Type:** unsigned short* 

***Purpose:*** 

TODO: Figure out what this is for


### hide

***Data Type:** unsigned long* 

***Purpose:*** 

This 4 byte value determines how many unlock points are needed before this song can be selected on the music select screen.


### adjust_mc

***Purpose:*** 

***Data Type:** int* 

TODO: Figure out what this value actually does


### difficulty

***Data Type:** unsigned int[2]* 

***Purpose:*** 

This pair of 4-byte values determines the foot ratings for each difficulty, with the first unsigned long belonging to single
chart difficulties, and the second belonging to doubles chart difficulties.

Each difficulty is given a single nibble (4 bits), allowing for a maximum foot rating of 15 (0x0F).  A chart not existing for a 
particular difficulty is denoted by that difficulty's foot rating being 0 (0x00), which also makes it unselectable on the music
select screen.

Each difficulty only taking up 1 nibble means that no modifications to this data member was needed going from having 3 difficulties (Light, Standard, Heavy) in MAX AC, to 4 difficulties (Light, Standard, Heavy, Oni) in MAX2 AC, to 5 difficulties (Beginner, Light, Standard, Heavy, Oni) in Extreme AC.  This is because, of course, a 32-bit DWord consists of 4 bytes, or 8 nibbles.  Theoretically, this means that there is enough space to support 8 difficulties worth of foot ratings per play style (that is, 8 for singles, AND 8 for doubles, since singles and doubles get their own 32-bit dword to store foot rating information in).


## special

***Data Type:** unsigned int* 

***Purpose:*** 

TODO: Figure out what this value actually does


## max_spm

***Data Type:** unsigned short[] - array length depends on the game* 

***Purpose:*** 

TODO: Figure out what this is for


## avg_spm

***Data Type:** unsigned short[] - array length depends on the game* 

***Purpose:*** 

TODO: Figure out what this is for


## avg_jpm

***Data Type:** unsigned short[] - array length depends on the game* 

***Purpose:*** 

TODO: Figure out what this is for


## chaos_v

***Data Type:** unsigned short[] - array length depends on the game* 

***Purpose:*** 

[Groove radar Chaos](https://dancedancerevolution.fandom.com/wiki/Groove_Radar#Chaos) values - there is 1 value for each single chart difficulty, and 1 for each doubles chart difficulty.


## freeze_v

***Data Type:** unsigned short[] - array length depends on the game* 

***Purpose:*** 

[Groove radar Freeze](https://dancedancerevolution.fandom.com/wiki/Groove_Radar#Freeze) values - there is 1 value for each single chart difficulty, and 1 for each doubles chart difficulty.


## title

***Data Type:** char** 

***Purpose:*** 

TODO: Figure out what this is for


## l_name

***Data Type:** char** 

***Purpose:*** 

TODO: Figure out what this is for
