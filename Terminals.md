# Terminals

## tmux shortcuts
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
- open .tmux.conf `nano ~/.tmux.conf`
- add these lines and save the file
```bash
bind '"' split-window -c "#{pane_current_path}"
bind '%' split-window -h -c "#{pane_current_path}"
set-option -g mouse on
```

#### tmux session management
- detach from a session: `ctrl+b, d`
- create new session `tmux new-session -s mysession`
- list of all sessions `tmux ls`
- attach to a session `tmux attach-session -t mysession`
- kill a session `tmux kill-session -t mysession`

#### Adding tmux plugin manager

- clone it `git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm`
- open .tmux.conf `nano ~/.tmux.conf`
- add these lines at the end and save the file
  ```bash
  set -g @plugin 'tmux-plugins/tpm'
  set -g @plugin 'tmux-plugins/tmux-sensible'
  # this line below should be added at the bottom
  run '~/.tmux/plugins/tpm/tpm'
  ```
- reload tmux `tmux source ~/.tmux.conf`

#### Adding tmux yank
- clone it `git clone https://github.com/tmux-plugins/tmux-yank ~/.tmux/plugins/tmux-yank`
- open .tmux.conf and add these line at the bottom `run-shell ~/.tmux/plugins/tmux-yank/yank.tmux` and save it
- reload tmux `tmux source ~/.tmux.conf`

