glyph wide support
================================

Description
-----------
This patch fixes wide glyphs truncation.
This patch is based from [Lukesmithxyz/st's commit on github](https://github.com/LukeSmithxyz/st/commit/e3b821dcb3511d60341dec35ee05a4a0abfef7f2)

Download
--------
* [st-glyph-wide-support-20220411-ef05519.diff](st-glyph-wide-support-20220411-ef05519.diff)

Use this patch if wide glyph characters are still being chopped during editing.
For all informations about how this looks, why it might and might not happen, look [here](https://github.com/LukeSmithxyz/st/pull/349).
* [st-glyph-wide-support-20230701-5770f2f.diff](st-glyph-wide-support-20230701-5770f2f.diff)

Use this patch if you are using boxdraw.
* [st-glyph-wide-support-boxdraw-20220411-ef05519.diff](st-glyph-wide-support-boxdraw-20220411-ef05519.diff)

Authors
-------
* Dreomite - Creating the original commit
* wael - 40663@protonmail.com
* Iskustvo - Fixing the solution for chopping during editing
