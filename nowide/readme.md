nowide
======

Description
-----------
This patch adds a new terminal mode, /NOWIDE/. If it's enabled, wide characters
will be replaced with a faint question mark. This mode can be enabled or
disabled by default with the `renderwide` variable in `config.def.h`, and can be
toggled with a keybind (`Ctrl+Shift+W` by default).

This mode is specially useful if your font doesn't support wide characters,
since rendering them usually makes the terminal really, really slow, specially
when scrolling.

This patch is intended for ST 0.8.2, but it should be easy to port it to newer
versions.

Download
--------
* [st-nowide-20241013-0.8.2.diff](st-nowide-20241013-0.8.2.diff)

Authors
-------
* [8dcc](https://github.com/8dcc) - <8dcc.git@gmail.com>
