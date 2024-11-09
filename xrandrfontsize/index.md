xrandrfontsize
==============

Description
-----------
Solves the frustrating necessity of adjusting the font size when constantly
moving terminal window between monitors (i.e. by tiling WM).

Primary usecases:

* monitors have very different DPI (e.g. HiDPI laptop + FullHD monitor);
* one monitor is near you (laptop) and another is far (UHD TV on the wall);
* one monitor is for coding (large font) and another for logs (small font);
* single ultrawide monitor is split into two (for main working area to be always in the center -- instead of bottom left corner).

Example for monitor splitting (first associated area is treated as primary):
```bash
xrandr --listmonitors | grep -wo "HDMI-0~[0-9]" | sed 's/^/--delmonitor /' | xargs -r xrandr
xrandr --setmonitor HDMI-0~1 2845/648x1600/366+995+0 HDMI-0 --setmonitor HDMI-0~2 995/226x1600/366+0+0 none
```

Configure
---------

Associative map value meaning:

* `commented-out` : fixed relative points size (monitor dpi)
* `=0` : use fixed absolute pixel size (default screen dpi)
* `>0` : use auto absolute pixel size (monitor dpi)
* `<0` : use auto relative points size (monitor dpi)

```c
MonitorConfig monitors_config[] = {
	// {"eDP-1", ...},   // commented-out, uses default font size as usual
	{"DP-1", 0},         // auto-scales font size based on global Xorg DPI
	{"HDMI-0~1", -20},   // applies relative font size (e.g. "monospace-20")
	{"HDMI-0~2", -14},   // uses smaller font for ultrawide side-screen
	{"HDMI-1", 18},      // fixed font size for TV (i.e. "monospace:pixelsize=18")
};
```

NOTE: font size is assigned separately per each output name, because there is
not much sense to scale font size strictly and **solely** by DPI.
And you may need *intentionally* different font sizes (like usecases above).

Download
--------
* [xrandrfontsize-0.8.4-20211224-2f6e597.diff](xrandrfontsize-0.8.4-20211224-2f6e597.diff)

INFO: it clearly applies over at least 15 other patches.

Authors
-------
* Dmytro Kolomoiets - <amerlyq+code@gmail.com>
