# oni_steps Data Structure

## Definition:
```
struct oni_steps{
    unsigned int link_num;
    unsigned short[2][] steps;   // NOTE: 2nd element is blank because it depends on the game, and number of difficulties
};
```

## Structure Data Members:
### link_num
***Data Type:** unsigned int
***Purpose:*** 
I need to figure out how to describe the link_num, sorry folks.

### steps
***Data Type:** unsigned short[2][]
***Purpose:*** 
A 2-dimensional array that holds the maximum step counts for each song.

The first dimension is for the style - with element 0 being single, 1 being doubles.
In the definition above, the 2nd dimension I left blank because it depends on the game.

In MAX, for instance, there are 3 difficulties, MAX2 4, EXTREME onward 5.

So in MAX it'd be "unsigned short[2][3] steps."  In MAX2, it'd be "unsigned short [2][4],"
and in extreme onward, it'd be "unsigned short[2][5] steps."


