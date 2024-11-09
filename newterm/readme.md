New terminal in current directory
=================================

This patch allows you to spawn a new st terminal using Ctrl-Shift-Return. It
will have the same CWD (current working directory) as the original st instance.

The `getcwd_by_pid` function is inspired on [the function with the same name of
dvtm](https://github.com/martanne/dvtm/blob/master/dvtm.c#L1036).

By default the current st terminal will be the parent process of the new terminal.
This can conflict with the swallow patch for dwm and can result in the wrong st
terminal window being swallowd. The orphan variant of this patch works around this
issue by spawning the new terminal window as an orphan instead (meaning that it
will have no parent process).

To have newterm working with tabbed, apply the st-newterm-0.8.2-tabbed.diff patch
on top of st-newterm-0.8.2.diff.

To have tmux support, apply the st-newterm-0.9-tmux.diff patch on top of
st-newterm-0.9.diff.

With the tmux patch, newterm won't launch a new terminal with the CWD of the tmux
client itself, but it will use the CWD of the current process in the tmux session
running under st.

The tmux client must be a direct child of st in order to make newterm detect it
(you'll need to use `exec tmux` or similar). If the child of st isn't a tmux
client, newterm will fallback to the CWD of st's child (which is what newterm
does without the tmux patch).

The tmux patch only works on Linux.

Download
--------

* [st-newterm-0.8.2.diff](st-newterm-0.8.2.diff)
  * [st-newterm-0.8.2-tabbed.diff](st-newterm-0.8.2-tabbed.diff)
* [st-newterm-orphan-20210712-4536f46.diff](st-newterm-orphan-20210712-4536f46.diff)
* [st-newterm-20220221-0.8.5.diff](st-newterm-20220221-0.8.5.diff)
* [st-newterm-0.9.diff](st-newterm-0.9.diff)
  * [st-newterm-0.9-tabbed.diff](st-newterm-0.9-tabbed.diff)
  * [st-newterm-0.9-tmux.diff](st-newterm-0.9-tmux.diff)

Authors
-------
* Matías Lang
* Stein Bakkeby (orphan version)
* Gaspar Vardanyan (tabbed support)
* [Meator](https://github.com/meator) - <meator.dev@gmail.com> (all of the st-newterm-0.9* patches)
