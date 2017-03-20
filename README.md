###ansiterm

Proper configurations for viewing ANSI art or telnetting/SSHing to BBSes in
xterm and macOS Terminal.app.

Includes `dos437`, a BDF pixel-for-pixel translation of the DOS 437 codepage
font, with a converted TrueType version.

![https://i.imgur.com/eUMMpQW.png](https://i.imgur.com/eUMMpQW.png)

####xterm

Convert the BDF font to a PCF font (if necessary) and then install it:

- `bdftopcf dos437.bdf > font/dos437.pcf`
- `sudo cp font/dos437.pcf /usr/X11R6/lib/X11/fonts/misc/`
- `cd /usr/X11R6/lib/X11/fonts/misc/; sudo mkfontdir`

Then run `ansiterm.sh` to launch xterm with proper colors and the `dos437`
font.  For tiling window managers, make sure the resulting xterm window is
exactly 80 characters wide.

####Terminal.app

Install the TTF font (double-click it to open it in font book, and then click
install) and then install the terminal settings profile by double clicking
it.

Verify that the font used is `dos437` in 8pt, antialias is off, the character
encoding is "western (ascii)", and the terminal is 80x24.


In either xterm or Terminal.app, ANSI art files should display properly with
cat.  BBSes should display fine through the standard telnet or SSH programs.
