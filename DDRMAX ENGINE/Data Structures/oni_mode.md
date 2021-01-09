# oni_mode Data Structure

## Definition:
```
struct oni_mode{
    unsigned int link_num;
    unsigned char seq_kind;
    unsigned char seq_transfer;
    unsigned char sp_music;
    unsigned char add_life;
    unsigned int hidden:2;
    unsigned int thinout:1;
    unsigned int free:1;
    unsigned int soft:1;
    unsigned int boost:2;
    unsigned int speed:5;
    unsigned int scroll:2;
    unsigned int freeze:1;
    unsigned int vivid:2;
    unsigned int anime:2;
    unsigned int dark:1;
    unsigned int pad:12;
};
```
