# tmux

Server manages sessions. Sessions contain windows. Windows contain panes. Prefix key (`C-b`) then command.

Core value: persistent sessions that survive disconnection.

## Essential keybindings

```
C-b d       detach
C-b c       new window
C-b n/p     next/prev window
C-b 0-9     jump to window

C-b %       split right
C-b "       split down
C-b o       cycle panes
C-b arrow   move between panes
C-b x       kill pane

C-b [       copy mode (scroll) - q to exit
C-b ?       list all bindings
```

## Shell commands

```
tmux              start new session
tmux ls           list sessions
tmux attach -t X  attach to session X
tmux kill-server  nuclear option
```

.


Change tmux working directory while in session

If you'd like the working directory of tmux to change while you are working in that tmux session, you can use the attach_session command at the tmux command promt.

To get to the tmux command prompt use <leader>: and then use attach-session with the -c flag.

# at the tmux command prompt
:attach-session -t . -c new_working_dir

Sh

This build's on Jake's last post.



Looks like you need this:

    move-window [-rdk] [-s src-window] [-t dst-window]
                  (alias: movew)
            This is similar to link-window, except the window at src-window
            is moved to dst-window.  With -r, all windows in the session are
            renumbered in sequential order, respecting the base-index option.

Calling movew without parameters moves current window to first free position. movew -r will renumber all the windows at once.
