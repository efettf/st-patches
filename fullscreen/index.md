fullscreen
==========

Description
-----------
Add the ability to toggle st into fullscreen mode. This is only useful if running st outside of a tiling window manager. With KDE or Gnome, the only option given is to maximize the window, which can still leave many graphical elements visible. For a pure terminal exeprience, fullscreen is the way to go.

Two key bindings are defined: F11 which is typical with other applications and ALT+ENTER which matches default xterm behavior.

Notes
-----
This patch is inspired by the go_fullscreen() patch included in this build: [https://github.com/mcaimi/st](https://github.com/mcaimi/st/commit/e7c66e955a336a0a2de1b4b1dc5c1574934da549)
However, by using the NET_WM_STATE_TOGGLE flag, as opposed to ADD and REMOVE, this implementation is simpler.

Download
--------
* [st-fullscreen-0.8.5.diff](st-fullscreen-0.8.5.diff)

Authors
-------
* cdarkly - <cdarkly@protonmail.com>
