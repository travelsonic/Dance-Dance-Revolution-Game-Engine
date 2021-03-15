# eval_w Data Structure

## Definition:
```
struct eval_w{
    int value_ct[7];
    int freez_value_ct[4];
    int groove_bonus[6];
    int groov_bonus_max[6];
    int score;
    int max_combo_ct;
    int jump_ct;
    short dance_level;
    short fixed_level;
};
```

## Structure Data Members:
### value_ct
***Data Type:** int[7]* 

***Purpose:*** 

This array stores the number of steps that fall into each of the timing judgment categories.
Each value gets its own 4-byte integer.

***Array elements & what they store:***
```
Element:   Data:
0          Perfect Count      
1          Great Count    
2          Good Count    
3          Boo Count    
4          Miss Count    
5          TODO: Find what this element is used for
6          Elapsed step count?  TODO: Find out with certainty what this array element is used for
```


### freez_value_ct
***Data Type:** unsigned int[4]*

***Purpose:*** 

TODO: Find out what this is actually used for.


### groov_bonus
***Data Type:** int[6]*

***Purpose:*** 

TODO: Find out what this is actually used for.


### groov_bonus_max
***Data Type:** int[6]*

***Purpose:*** 

TODO: Find out what this is actually used for.


### score
***Data Type:** int*

***Purpose:*** 

TODO: Figure out what this is for


### max_combo_ct
***Data Type:** int*

***Purpose:*** 

TODO: Figure out what this is for


### jump_ct
***Data Type:** int*

***Purpose:*** 

TODO: Figure out what this is for


### dance_level
***Data Type:** short*

***Purpose:*** 

TODO: Figure out what this is for


### fixed_level
***Data Type:** short*

***Purpose:*** 

TODO: Figure out what this is for
