# Edit Mode:
## Note:
This, like the SSQ document, is more or less gonna be a brainfart filled thing full of observations 
from trying to look at, and fiddle with edit mode in the Playstation2 mixes.

## Memory:
The game stores data for the edit-in-progress in 2 memory locations; 
one region used for non-freeze step data, and the other for freeze 
step data.

The region of memory used for freeze step data is 0x81C, or 2,076
bytes long, and the region used for non-freeze step data is 0x810,
or 2,064 bytes long.

There is also a region of memory that is used for stepdata playback,
where the data is converted from the layout/format used in the editor, 
to the SSQ format.

## Note Placement:
The editor, "out of the box," allows you to place 1/4th, 1/8th, and 1/4th
notes.  This limitation appears to be on the level of the editor itself, and
not from the SSQ format itself.

Another strictly editor imposed limitation is with regards to how many arrows
you can place on a beat.  When placing an arrow, the game checks how many arrows
are on the beat already, and if that value is not < 2, the beat is cleared prior
to the placement of said arrow.  The game checks this arrow quantity in two spots,
one for non-freeze step placement, and one for freeze step placement.


#
##
###
