---
title: "Tmux cho người lười."
date: 2023-10-08
description: "Để trở thành master terminal"
tags: [tips]
---

### tmux architech
![My imageg](/images/tmux-architech.png)

## Attach and detach

|Keybind |Description|
|-----|--------|
|tmux|Start new tmux session       |
|tmux attach  |Attach to tmux session running in the background      |
|Ctrl+B d | Detach from tmux session, leaving it running in the background |
|Ctrl+B & |Exit and quit tmux|
|Ctrl+B ? |List all key bindings (press `q` or `esc` to exit help screen)|

## Split window into panes

|Keybind |Description|
|-----|--------|
|Ctrl+B % | Vertical split (panes side by side)|
|Ctrl+B " |Horizontal split (one pane below the other)|
|Ctrl+B o |Move to other pane|
|Ctrl+B ! |Remove all panes but the current one from the window|
|Ctrl+B q |Display window index numbers|
|Ctrl+B Ctrl-Up/Down| Resize current pane (due north/south)|
|Ctrl+B Ctrl-Left/Right| Resize current pane (due west/east)|


## Change the status bar background color
`Ctrl+B :`
+ Change the status bar background color: `set -g status-bg cyan`  
+ Change inactive window color: `set -g window-status-style bg=yellow`  
+ Change active window color: `set -g window-status-current-style bg=red,fg=white`

## References
https://github.com/tmux-plugins/list