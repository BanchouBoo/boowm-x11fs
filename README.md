# boowm

## main script
#### basic window controls you can use to build a window manager with
```java
usage: boowm [action] [wid] [args]
	focus                      focus specified window
	map          [true/false]  set window map status
	ignore       [true/false]  set window ignore status
	pos          [int] [int]   set x and y position of window
	move         [int] [int]   add/subtract x and y position from window
	size         [int] [int]   set width and height of window
	stretch      [int] [int]   add/subtract width and height from window
	swap         [wid]         swap the position and size of two windows
	border_width [int]         set the border width of window
	border_color [hex]         set the border color of window
	stack        [raise/lower] move window to the top/bottom of stack

	NOTE: you can use "focused" in place of a window id
```

## extensions

### tags
#### a dwm-like tags system for managing workspaces (very WIP)

### rules
#### event handler for window rules on window creation
Window rules should be an executable script located in `~/.config/boowm/rules` which takes the window id as the first argument. Rules are parsed via the file name itself and should be formatted as `class:instance:title`. You may use wildcards in the filenames as well.

ex: `St:st:*` would match only st windows that do not specify an instance, whereas `St:*:*` would match any st window.

### focuser
#### event handler that focuses windows when created or when the mouse enters them

### addborder
#### event handler to add borders to windows when on creation

### nearsest
#### script to get the nearest window in a direction and prints it to stdout (needs rewrite to be more accurate)
ex: `boowm nearset focused right` would get the window closest to the right of the focused window

`boowm nearest focused right | boowm swap focused` would swap the window to the right of the focused window with the focused window

### cells
#### script for positioning and sizing windows aligned to a grid, with support for gaps in the grid, outer gaps, space for a bar, and configurable cell count on the x and y axis
