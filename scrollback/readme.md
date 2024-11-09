scrollback
==========

Description
-----------
Scroll back through terminal output using Shift+{PageUp, PageDown}.

Download
--------
* [st-scrollback-0.8.4.diff](st-scrollback-0.8.4.diff)
* [st-scrollback-20201205-4ef0cbd.diff](st-scrollback-20201205-4ef0cbd.diff)
* [st-scrollback-20210507-4536f46.diff](st-scrollback-20210507-4536f46.diff)
* [st-scrollback-0.8.5.diff](st-scrollback-0.8.5.diff)
* [st-scrollback-0.9.2.diff](st-scrollback-0.9.2.diff)

Alternative implementation that uses a ring buffer for more
efficient scrolling:

* [st-scrollback-ringbuffer-0.8.5.diff](st-scrollback-ringbuffer-0.8.5.diff)
* [st-scrollback-ringbuffer-0.9.2.diff](st-scrollback-ringbuffer-0.9.2.diff)

Apply the following patch on top of the previous to use float argument in
kscrollup/kscrolldown.

* [st-scrollback-float-0.9.2.diff](st-scrollback-float-0.9.2.diff)

Apply the following patch on top of the previous to allow column and row reflow.

* [st-scrollback-reflow-0.8.5.diff](st-scrollback-reflow-0.8.5.diff)
* [st-scrollback-reflow-0.9.diff](st-scrollback-reflow-0.9.diff)
* [st-scrollback-reflow-20230607-211964d.diff](st-scrollback-reflow-20230607-211964d.diff)
* [st-scrollback-reflow-0.9.2.diff](st-scrollback-reflow-0.9.2.diff)

Apply the following patch on top of the previous to allow scrolling
using `Shift+MouseWheel`.

* [st-scrollback-mouse-20170427-5a10aca.diff](st-scrollback-mouse-20170427-5a10aca.diff)
* [st-scrollback-mouse-0.8.diff](st-scrollback-mouse-0.8.diff)
* [st-scrollback-mouse-0.8.2.diff](st-scrollback-mouse-0.8.2.diff)
* [st-scrollback-mouse-20191024-a2c479c.diff](st-scrollback-mouse-20191024-a2c479c.diff)
* [st-scrollback-mouse-20220127-2c5edf2.diff](st-scrollback-mouse-20220127-2c5edf2.diff)
* [st-scrollback-mouse-0.9.2.diff](st-scrollback-mouse-0.9.2.diff)

Apply the following patch on top of the previous two to allow scrollback using
mouse wheel only when not in `MODE_ALTSCREEN`. For example the content is being
scrolled instead of the scrollback buffer in `less`. Consequently the Shift
modifier for scrolling is not needed anymore. **Note: patches before
`20191024-a2c479c` might break mkeys other than scrolling functions.**

* [st-scrollback-mouse-altscreen-20170427-5a10aca.diff](st-scrollback-mouse-altscreen-20170427-5a10aca.diff)
* [st-scrollback-mouse-altscreen-0.8.diff](st-scrollback-mouse-altscreen-0.8.diff)
* [st-scrollback-mouse-altscreen-20190131-e23acb9.diff](st-scrollback-mouse-altscreen-20190131-e23acb9.diff)
* [st-scrollback-mouse-altscreen-20200416-5703aa0.diff](st-scrollback-mouse-altscreen-20200416-5703aa0.diff)
* [st-scrollback-mouse-altscreen-20220127-2c5edf2.diff](st-scrollback-mouse-altscreen-20220127-2c5edf2.diff)

Apply the following patch on top of the first two to allow changing how fast the mouse scrolls.

* [st-scrollback-mouse-increment-0.8.2.diff](st-scrollback-mouse-increment-0.8.2.diff)
* [st-scrollback-mouse-increment-0.9.2.diff](st-scrollback-mouse-increment-0.9.2.diff)

Apply the following patch on top of the first two to allow a `\e[ m` escape,
marking the line to quickly scroll to with Control+{PageUp, PageDown}.
* [st-scrollback-mark-0.9.2.diff](st-scrollback-mark-0.9.2.diff)

Notes
-----
* Patches modify config.def.h, you need to add mkeys to your own config.h
* With patches before `20191024-a2c479c`: you can not have a mshortcut for the
  same mkey so remove Button4 and Button5 from mshortcuts in config.h
* The mouse and altscreen patches `20191024-a2c479c` (and later) are simpler and
  more robust because st gained better support for customized mouse shortcuts.
  As a result, the altscreen patch doesn't really need the mouse patch. However
  to keep it simple the instructions stay the same: the alrscreen patch still
  applies on top of the (now very minimal) mouse patch.

Authors
-------
* Jochen Sprickerhof - <st@jochen.sprickerhof.de>
* M Farkas-Dyck - <strake888@gmail.com>
* Ivan Tham - <pickfire@riseup.net> (mouse scrolling)
* Ori Bernstein - <ori@eigenstate.org> (fix memory bug)
* Matthias Schoth - <mschoth@gmail.com> (auto altscreen scrolling)
* Laslo Hunhold - <dev@frign.de> (unscrambling, git port)
* Paride Legovini - <pl@ninthfloor.org> (don't require the Shift modifier
  when using the auto altscreen scrolling)
* Lorenzo Bracco - <devtry@riseup.net> (update base patch, use static
  variable for config)
* Kamil Kleban - <funmaker95@gmail.com> (fix altscreen detection)
* Avi Halachmi - <avihpit@yahoo.com> (mouse + altscreen rewrite after `a2c479c`)
* Jacob Prosser - <geriatricjacob@cumallover.me>
* Timo Röhling - <timo@gaussglocke.de> (ring buffer implementation)
* [Alexander Arkhipov](gopher://mineeyes.cyou/) - <scm_2022@mineeyes.cyou> (0.8.5 update)
* Ashish Kumar Yadav - <ashishkumar.yadav@students.iiserpune.ac.in> (reflow implementation)
