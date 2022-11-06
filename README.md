# Tmux binder mode

An adhoc proof of concept for a binder mode in tmux similar to i3's stack mode.

No automated installation yet. To install, add the binaries to your PATH and add the following to your .tmux.conf:

```
unbind -n M-s
bind -n M-s run "toggle_marked '#{pane_id}'"
set-hook -g pane-focus-in "run 'is_marked #{pane_id} && open_marked #{pane_id}'"
set-hook -g after-split-window "run 'clone_mark #{pane_id}'"
```
