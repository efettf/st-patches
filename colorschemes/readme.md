colorschemes
============

Description
-----------
This patch adds multiple color schemes and lets you change them without having
to restart st.

Predefined color schemes:

- the default (dark) st color scheme
- the default (dark) alacritty color scheme
- One Half (dark & light)
- Solarized (dark & light)
- Gruvbox (dark & light)

It's similar to the [palettes](../palettes/) patch but it has additional
features:

- Support for the colors 17 to 256 (_palettes_ returns random colors here).
- Allow different background and foreground color indices for different
  color schemes.
- Add a key binding for switching through color schemes.

Key bindings
------------

- Select the first..eighth color scheme with Alt+1..8.
- Select the next color scheme with Alt+0.
- Select the previous one with Ctrl+Alt+0.

Download
--------
* [st-colorschemes-0.8.5.diff](st-colorschemes-0.8.5.diff)

Authors
-------
* Max Schillinger - <maxschillinger@web.de>
