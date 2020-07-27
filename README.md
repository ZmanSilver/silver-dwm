# silver-dwm

A customized clone of dwm by suckless. This version of dwm is patched with alpha, uselessgap, centeredmaster, and attachbottom. I've also made a change to only display the status bar on a specified monitor for when you're using multiple displays. By default it's set to the primary monitor but can be changed in config.h by adjusting the STATUSMONITOR definition to the desired output's number as defined by xrandr. I've also included my dwm status script which provides exactly what you see in the screenshot and optionally more. Just run it.

## Screen

![Screenshot](screen.png)

## Dependencies

dwm requires the libx11, libxinerama, libxft, and freetype2 packages.
dwm optionally requires:
-	st: default terminal emulator
-	dmenu: default application launcher
-	ttf-font-awesome: icons used in my custom version

## Installing

	sudo make install

## Uninstalling

	sudo make clean uninstall
