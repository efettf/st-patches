anysize
=========

Description
-----------
By default, st's window size always snaps to the nearest multiple of the
character size plus a fixed inner border (set with borderpx in config.h). When
the size of st does not perfectly match the space allocated to it (when using a
tiling WM, for example), unsightly gaps will appear between st and other apps,
or between instances of st.

This patch allows st to resize to any pixel size, makes the inner border size
dynamic, and centers the content of the terminal so that the left/right and
top/bottom borders are balanced. With this patch, st on a tiling WM will always
fill the entire space allocated to it.

Download
--------
* [st-anysize-0.8.1.diff](st-anysize-0.8.1.diff)
* [st-anysize-20201003-407a3d0.diff](st-anysize-20201003-407a3d0.diff)
* [st-anysize-0.8.4.diff](st-anysize-0.8.4.diff)
* [st-anysize-20220718-baa9357.diff](st-anysize-20220718-baa9357.diff)

Authors
-------
* Augusto Born de Oliveira - <augustoborn@gmail.com>

Expected anysize
================

As said above, the anysize patch will automatically balance the left/right and
top/bottom borders, with the terminals contents centered and the borders dynamic.
This behavior may be unexpected, such as terminal content placement, and the
terminal contents 'swimming'; constantly moving/shaking while the terminal is
being resized, which isn't very good to look at.

This variant will only add the border paddings to the bottom and the right of the
window, which is usually expected as english is left to right and the terminal
output comes from the top.

The change is very small, and only requires 2 lines to be changed in `x.c`.

The outcome of this behavior is what should be expected from an 'anysize' patch.

Download
--------
* [st-expected-anysize-0.9.diff](st-expected-anysize-0.9.diff)
