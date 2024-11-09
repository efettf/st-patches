netwmicon
=========

Description
-----------
Enables to set \_NET\_WM\_ICON with a png-image.

Generally the icon of an application is defined by its desktop-entry. The patch
[desktopentry](../desktopentry) serves this purpose. Unfortunately, some
programs like [tint2](https://gitlab.com/o9000/tint2) or
[alttab](https://github.com/sagb/alttab) can't make use of the desktop-entry and
rely instead on a hardcoded icon which has to be defined by the application
itself with the window-propery \_NET\_WM\_ICON. Since st doesn't define
\_NET\_WM\_ICON this programs can't display the correct icon for st even if a
desktop-entry exists. This patch solves this problem.

Dependencies
------------
- gd

Defining an icon
----------------
By default each time st starts it will search for a file with the name *st.png*
under */usr/local/share/pixmaps/*. If you put an image with this name in the
root-directory of the st-repository and call `make install` the image will be
installed in */usr/local/share/pixmaps/* automatically. Otherwise you have to
put the file there manually. You can try it out with this icon [st.png](st.png)
(credit: [flat-remix](https://github.com/daniruiz/flat-remix)).

Using with desktopentry
-----------------------
If you use the [desktopentry](../desktopentry)-patch you should adjust the icon
in the file *st.desktop* by replacing the line `Icon=utilities-terminal` with
`Icon=st`.

Most programs which use the desktop-file to determine the icon should be able to
find *st.png* under */usr/local/share/pixmaps/*. If not report it to me and try
changing in *confing.mk* the line `ICONPREFIX = $(PREFIX)/share/pixmaps` to
`ICONPREFIX = $(PREFIX)/share/icons/hicolor/256x256/apps/` and install the icon
there.

Call to action
--------------
Maybe somebody would like to create an icon with the st-logo so we could add it
here instead of using the icon from flat-remix.

Credits
-------
The code for loading and transforming the image to an appropriate format is in
large part from [xseticon](https://www.leonerd.org.uk/code/xseticon/) which is
developed by Paul Evans.

Download
--------
* [st-netwmicon-0.8.5-v2.diff](st-netwmicon-0.8.5-v2.diff)
* [st-netwmicon-0.8.4.diff](st-netwmicon-0.8.4.diff) (Deprecated)
* [netwmicon.sh](netwmicon.sh) (Deprecated. Used for 0.8.4-patch. Look at
  patch-description to understand how its supposed to work. It seems to distort
  the icon.)

Authors
-------
* Aleksandrs Stier - <aleks.stier@icloud.com>
