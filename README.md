# assembly_game
The game is written in x86 assembly language and  it is a simple game implemented using the DOS interrupt services. It creates a basic game environment where a player (represented by the '@' character) can move up, down, left, and right to avoid enemies (represented by the '&' character) falling from the left of the screen. The game keeps track of the player's score, which increases when enemies reach the right of the screen without colliding with the player.

Here's a brief documentation for the main components of the code:

Initialization:

The program starts with the org 100h directive, indicating the origin point of the program in memory.
The jmp printplayer instruction initiates the game loop by jumping to the printplayer label.
Game Loop:

The printplayer section displays the player's position and updates the screen.
The input section captures keyboard input to move the player.
The update_enemies section updates the positions of the enemies.
The printenemies section displays the enemies on the screen.
Input Handling:

The input section uses the int 16h interrupt to capture keyboard input.
Different key presses (left, right, up, down) lead to corresponding actions to move the player.
Collision Detection:

The checkcollisions section checks for collisions between the player and enemies.
If a collision is detected, the game updates the score and enemy positions accordingly.
Graphics and Screen Handling:

The code uses interrupt 10h to manipulate the video display, including clearing the screen, printing characters, and moving the cursor.
The printax procedure converts a 16-bit value (score) to ASCII and prints it on the screen.
The printmap procedure prints the game map.
Utility Procedures:

clear_screen: Clears the screen.
hidecursor: Hides the cursor on the screen.
resetcursor: Resets the cursor position to (0, 0).
clearkeyboardbuffer: Clears the keyboard buffer.
delay: Introduces a delay in the program execution for a simple form of timing.
Data Section:

Defines character representations for the player and enemies.
Keeps track of player and enemy positions.
Defines a game map and a game over message.
Game Over Handling:

When a collision is detected, the program displays "GAME OVER" and waits for a key press before exiting.
Score Tracking:

The score variable keeps track of the player's score.
Map Design:

The map section defines the game environment with '#' representing walls and empty spaces.
