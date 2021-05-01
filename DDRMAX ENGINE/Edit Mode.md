# Note:
This, like the SSQ document, is more or less gonna be a brainfart filled thing full of observations 
from trying to look at, and fiddle with edit mode in the Playstation2 mixes.

### Memory:
The game stores data for the edit-in-progress in 2 memory locations; 
one region used for non-freeze step data, and the other for freeze 
step data.

The region of memory used for freeze step data is 0x81C, or 2,076
bytes long, and the region used for non-freeze step data is 0x810,
or 2,064 bytes long.

There is also a region of memory that is used for stepdata playback,
where the data is converted from the layout/format used in the editor, 
to the SSQ format.

##
###
