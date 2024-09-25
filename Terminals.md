# Terminals

## tmux
```
ctrl+b % = vertical split
ctrl+b " = horizontal split
ctrl+b o = switch panes
ctrl+b ! = convert pane to window
ctrl+b <arrow> = resize pane
ctrl+b : kill-pane = close pane
ctrl+b : set mouse on = avail mouse buttons and scrolling
ctrl+b & = close window
```

#### change tmux config file (.tmux.conf) to make panes in same dir and making the mouse usable.
```bash
bind '"' split-window -c "#{pane_current_path}"
bind '%' split-window -h -c "#{pane_current_path}"
set-option -g mouse on
```

#### tmux session management
_to detach from a session hit_: ctrl+b, d
```bash
tmux new-session -s mysession
tmux ls
tmux attach-session -t mysession
tmux kill-session -t mysession
```
