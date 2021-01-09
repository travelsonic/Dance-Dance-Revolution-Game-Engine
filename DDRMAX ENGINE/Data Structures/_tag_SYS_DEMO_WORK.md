# _tag_SYS_DEMO_WORK Data Structure

## Definition:
```
struct _tag_SYS_DEMO_WORK{
    int mode;
    int inactive_flag;
    int inactive_counter;
    int gameplay_flag;
    int gameplay_counter;
    int end_screen_request;
    int main_loop_break_request;
    struct{
	      unsigned int lsn;
        unsigned int size;
        char name[16];
        unsigned char date[8];
        unsigned int flag;
	  }
    unsigned short language;
    unsigned short aspect;
    unsigned short playmode;
    unsigned short to_inactive;
    unsigned short to_gameplay;
    unsigned short mediatype;
    unsigned short masterVolScale;
    unsigned short dirSector;
    int why;
};
```
