Quick and dirty test demonstrating both qt5 widgets rendering direct to linux framebuffer (/dev/fb1 SPI TFT) reacting to linux key events.
Also tests audio subsystem by playing sound effects on keypresses (Qt5 build currently requires pulseaudio for the multimedia module, needs
a recompile to directly support alsa).


Qt5 / C++ Version
-----------------

To build:

> qmake ; make

To run:

> QT_QPA_PLATFORM=linuxfb:fb=/dev/fb1 ./qt5-keypad 

Or run as root and redirect output to /dev/tty1 to turn off blinking console cursor:

> QT_QPA_PLATFORM=linuxfb:fb=/dev/fb1 ./qt5-keypad > /dev/tty1


You might need to start pulseaudio daemon before running:

> pulseaudio -D


Python3 / PyQt5 Version
-----------------------

More or less the same demo implemented in PyQt5 just because.

Pre-requisites:

> sudo apt install python3-pyqt5
> sudo apt install python3-pyqt5.qtmultimedia


Run similarly to compiled C++ version.  Make sure pulseaudio is running first.

> QT_QPA_PLATFORM=linuxfb:fb=/dev/fb1 python3 pyqt5-keypad.py


Includes sounds downloaded from Freesound
-----------------------------------------
jalastram ( https://freesound.org/people/jalastram/ )

You can find this pack online at: https://freesound.org/people/jalastram/packs/19798/

Attribution: http://creativecommons.org/licenses/by/3.0/
