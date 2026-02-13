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