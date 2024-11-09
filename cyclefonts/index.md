cyclefonts
==========

Description
-----------
This patch adds a keybinding that lets you cycle between multiple different
fonts. Define `fonts` in your `config.def.h` as an array instead of `font`.

Notes
-----
* `currentfont` controls which font is loaded at the start, and must not exceed
  the size of the fonts array.
* Font size doesn't change while cycling fonts, use `zoomreset` to change the
  font size to default one for the current font.

Download
--------
* [st-cyclefonts-0.8.4.diff](st-cyclefonts-0.8.4.diff)
* [st-cyclefonts-20210604-4536f46.diff](st-cyclefonts-20210604-4536f46.diff)
* [st-cyclefonts-20220731-baa9357.diff](st-cyclefonts-20220731-baa9357.diff)

Author
------
* Miles Alan - m@milesalan.com (0.8.4)
* Justinas Grigas - <jstn_as@protonmail.com> (Updated versions)
