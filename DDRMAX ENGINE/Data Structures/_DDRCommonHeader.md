# _DDRCommonHeader Data Structure

## Definition:
```
struct _DDRCommonHeader {
    unsigned char Type;
    unsigned char Platform;
    unsigned char Hardware;
    unsigned char Version;
    unsigned char Area;
    char tmp;
    unsigned short title;
    unsigned int t_info[2];
};
```

