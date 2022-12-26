# backstory

In my current setup I use [bspwm](https://github.com/baskerville/bspwm) as my window manager and [alacritty](https://github.com/alacritty/alacritty)
as my terminal emulator and I wanted a super simple terminal session manager to use with it.

After using [screen](https://www.gnu.org/software/screen/) and [tmux](https://github.com/tmux/tmux),
I realized that I didn't need all the bell and whistles provided by such tools.
In fact, the highly rich feature set of said tools would get in my way many times.

I decided to migrate to [tab-rs](https://github.com/austinjones/tab-rs), which is much more lean and heavily
inspired **terminalsession**. Although much more simpler than other tools, `tab-rs` has a few things that I dislike,
such as configurable sessions (not required, but once again a feature I don't need), use of websocket to connect to the server,
and a few annoying bugs.

# terminalsession

`terminalsession` is a bash _terminal session manager_ built on top
of [dtach](https://github.com/crigler/dtach) and [fzf](https://github.com/junegunn/fzf) (for interactive mode).

`terminalsession` doesn't requires any configuration and doesn't provide any window management capabilities. It allows
you to **list**, **create**, **attach** and **kill** _$SHELL_ sessions.
It also provides a interactive mode, that can be used as the initial program for your terminal emulator.
That's is the full feature set!

`terminalsession` stores the **dtach** sock files are stored in the _$XDG_RUNTIME_DIR_ dir (fallback to `/tmp`).
All sessions have an environment variable `$TERMINALSESSION` set with the name of the session - you can use it
to display the name of the current session in your prompt.

# usage

* `tsctl list` - list all existing sessions
* `tsctl attach <session_name>` - attach to an existing session or create & attach to a new one session
* `tsctl kill <session_name>` - kills an existing session (sends **SIGTERM** signal)
* `tsctl` - launch interactive mode

Once attached to a session, use **C-a** to detach from it.

In interactive mode:
- select an exising session from the list and press **enter** to attach to it
- type the name for a new session and press **enter** to create & attach to it
- select an existing session an press **C-k** to kill it
- press **C-r** to reload the session list
- press **C-h** for help
