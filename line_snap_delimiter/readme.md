line\_snap\_delimiter
=====================

Description
-----------
The primary use-case would be snap selecting a line in a terminal
multiplexer like tmux. Such selection would typically select across
all panes, whereas the user most likely wanted to select only the line
within a pane.

This patch adds following new variable into `config.def.h`:
* `snap_line_delimiters`: this is the array of (multi-byte) characters which
                          will terminate a line snap selection. By default it
                          contains the `tmux` window pane separator `│`.

Notes
-----
* When snap selecting a line and dragging it, the selection can span multiple
  panes. It's probably possible to address this in follow-up patches.

* The new delimiter variable does *not* affect word snap selection. If you want
  to ignore certain characters when double tapping a word for seleciton, add that
  character to `worddelimiters` in `config.def.h`. However, if a word snap selection
  does select the line snap delimiter, a subsequent line snap selection will de-select
  that character again anyway.

Download
--------
* [st-line\_snap\_delimiter-3bd7e43.diff](st-line_snap_delimiter-3bd7e43.diff)

Authors
-------
* Michael Buch - <michaelbuch12@gmail.com>
