![dwm logo](https://dwm.suckless.org/dwm.svg)

# dwm - dynamic window manager

dwm is an extremely fast, small, and dynamic window manager for X.

[dwm website](https://dwm.suckless.org)

## Requirements

In order to build dwm you need the Xlib header files.

Neccesary libraries:
- libx11(-dev)
- libxinerama(-dev)
- libxft(-dev)
 

## Installation

Edit config.mk to match your local setup (dwm is installed into
the /usr/local namespace by default).

Afterwards enter the following command to build and install dwm (if
necessary as root):
```console
$ make clean install
```


## Running dwm

Add the following line to your .xinitrc to start dwm using startx:
```
exec dwm
```
In order to connect dwm to a specific display, make sure that
the DISPLAY environment variable is set correctly, e.g.:
```
DISPLAY=foo.bar:1 exec dwm
```
(This will start dwm on display :1 of the host foo.bar.)

In order to display status info in the bar, you can do something
like this in your .xinitrc:
```
while xsetroot -name "`date` `uptime | sed 's/.*,//'`"
do
    sleep 1
done &
exec dwm
```

## Configuration

The configuration of dwm is done by creating a custom config.h
and (re)compiling the source code.

## Additional Stuff

Not necessarily about dwm

### Setting background

Packages:
 - feh

```console
$ feh --bg-scale <image.jpg>
```

add to bashrc/zshrc/whatevershellrc:
```
alias setbg='feh --bg-scale'
```

### Window transparency

Packages:
 - xcompmgr
 - transset-df

```console
$ xcompmgr & # add to .xinitrc
$ transset .50 # or any number
# click the window you want to be transparent
```
