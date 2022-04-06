# ANSI Escape Codes
ANSI escape codes are special sequences of characters that start with the Escape
character (\x1B) which can be used to send commands to the terminal by including
them in the strings you print. These commands are used for purposes such as
formatting text, moving the cursor, and clearing the screen. This file lists the
escape codes supported by the TI-84PCEP's and how to use them.

## Change Color
This escape code can change the colors of the text and background for anything
printed after it. Both the text and background colors are specified using the
same color IDs, which are decimal numbers ranging from 0 to 15.

### Sequences
- `\x1B[m` sets the text color to black and the background color to white.
- `\x1B[𝘛𝘌𝘟𝘛m` sets the text color as specified and sets the background color
  to white.
- `\x1B[𝘛𝘌𝘟𝘛;𝘉𝘈𝘊𝘒𝘎𝘙𝘖𝘜𝘕𝘋m` sets the text and background colors as specified.

### Color IDs
- `0`: black
- `1`: red
- `2`: green
- `3`: yellow
- `4`: blue
- `5`: magenta
- `6`: aqua
- `7`: white
- `8`: light gray
- `9`: gray
- `10`: dark gray
- `11`: brown
- `12`: orange
- `13`: purple
- `14`: navy
- `15`: light blue

## Clear Terminal
This escape code clears the terminal of all text and moves the cursor to (0, 0).
The screen is filled with white, not the current background color.

### Sequences
- `\x1B[2J` clears the terminal of all text and moves the cursor to (0, 0).

## Set Cursor Position
This escape code can set the cursor position relative to the top-left corner of
the terminal. The coordinates are specified as decimal numbers. Unlike in a
typical terminal, the coordinates start at (0, 0) and both coordinates have to
be specified.

When coordinates that would place the cursor off-screen are used, the numbers
are modulus operation-ed by the corresponding dimension of the terminal, so for
example, specifying 35 for the horizontal coordinate would cause the cursor to
actually be moved to horizontal position 3 because `35 % 32 == 3`. In other
words, the coordinates wrap around Pac-Man style.

By default, the `print` function adds a new line at the end of the string, so
you should usually specify `end = ""` when working with this escape code to
avoid weirdness.

### Sequences
- `\x1B[𝘝𝘌𝘙𝘛𝘐𝘊𝘈𝘓;𝘏𝘖𝘙𝘐𝘡𝘖𝘕𝘛𝘈𝘓H` moves the cursor the the specified coordinates.
