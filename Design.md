6170_PSET_1.2
=============

Design Decisions:

I did not have any overarching class (a "board" or "cell" class.)  Instead, I took the following steps:

-I augmented each cell on the grid with two fields, one to track its current life state and one to track what its life state would be in the next iteration.

-I did most calculation with functions that iterated over all cells through x and y coordinates.

Another way of doing this would have been to create abstract data types to represent the board.  
This would have allowed me to manipulate the data inside one of these classes, rather than inside DOM objects.  
I didn't do this because I didn't feel like there was enough data involved for it to be necessary.

In order to allow the user to play and pause the game, and implement the varying-speed-of-operation feature, I wound up using two global variables:

- play_active is true if the game is playing, false if the game is paused.
- play_delay, an integer bounded between 1 and 25, tracks how long the game should wait between turns.

Implementing this without global variables would have been difficult to do, especially if the goal was to let the user alter the speed while the game was running.
I decided that using a limited number of global variables, with clear names unlikely to be used in other contexts, was OK.