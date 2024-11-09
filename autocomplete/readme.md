autocomplete
============
urxvt's [autocomplete-ALL-the-things](https://github.com/Vifon/autocomplete-ALL-the-things) extension's port for st

Description
-----------

Completes the currently typed word using the other words visible in the st window.

For example the terminal looks like this:

![Preview](usage.gif)

It was strongly inspired by `dabbrev` feature in GNU Emacs and later by
[skeleton-complete](https://github.com/baohaojun/skeleton-complete) by Bao
Haojun.

Basic usage
-----------

Just press the key bound (in the example above: Alt-Ctrl-slash) to
complete the word at point. Subsequent uses cycle through other
possible completions.

Advanced usage
--------------

For more advanced completions use `ACMPL_FUZZY_WORD` and `ACMPL_FUZZY`. It's
behavior is inspired by [skeleton-complete](https://github.com/baohaojun/skeleton-complete), please see [its readme](http://baohaojun.github.io/skeleton-complete.html) for a more detailed explanation.

Available commands
-------------------

* `ACMPL_WORD` -- classical prefix-based completion for words
* `ACMPL_WWORD` -- completion for WORDS (in the Vim meaning)
* `ACMPL_FUZZY_WORD` -- fuzzy completion for words
* `ACMPL_FUZZY_WWORD` -- fuzzy completion for WORDS
* `ACMPL_FUZZY` -- fuzzy completion for arbitrary strings
* `ACMPL_SUFFIX` -- fuzzy completion for suffixes, disrespecting
  prefixes of both completion and given strings
* `ACMPL_SURROUND` -- fuzzy completion for surrounded by quotes or
  braces strings, excluding surrounding
* `ACMPL_UNDO` -- undo the completion (must be used right after a completion)
* `ACMPL_DEACTIVATE` -- exit the autocompletion mode

Acknowledgments
---------------

Thanks to Stanislav Seletskiy for various contributions.

Thanks to Bao Haojun for the great idea of [skeleton-complete](https://github.com/baohaojun/skeleton-complete).

Copyright
---------

Copyright (C) 2012-2021  Wojciech Siewierski, Gaspar Vardanyan

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.

Download
--------
* [st-0.8.5-autocomplete-20220327-230120.diff](st-0.8.5-autocomplete-20220327-230120.diff)

The use of `tmpnam' is dangerous, better use `mkstemp'
* [st-autocomplete-20240703-6508693.diff](st-autocomplete-20240703-6508693.diff)

Contribution
------------
You can create issues and do pull requests on [this gitlab repo](https://gitlab.com/GasparVardanyan/st-autocomplete).

Authors
-------
* [Wojciech Siewierski](https://github.com/vifon)
* [Gaspar Vardanyan](https://gitlab.com/GasparVardanyan)
* [El Bachir](https://github.com/elbachir-one)
