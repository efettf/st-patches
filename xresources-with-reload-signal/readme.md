xresources with signal reloading
================================

Description
-----------
This patch adds the ability to configure st via Xresources and signal reloading.
This patch is not based on [xresources patch](https://st.suckless.org/patches/xresources) and is extended from [xst's commit on github](https://github.com/gnotclub/xst/commit/c0ffcfbaf8af25468103dd92e0c7e83555e08c7a).

You can basically pass a `USR1` signal to all st processes after updating your Xresources to reload the settings:
```
pidof st | xargs kill -s USR1
```

Download
--------
* [st-xresources-signal-reloading-20220309-1bb14b1.diff](st-xresources-signal-reloading-20220309-1bb14b1.diff)
* [st-xresources-signal-reloading-20220407-ef05519.diff](st-xresources-signal-reloading-20220407-ef05519.diff)

Authors
-------
* Mahdi Mirzadeh - <https://mirzadeh.pro>
* wael - 40663@protonmail.com fix variables + arg.h st.h removal
