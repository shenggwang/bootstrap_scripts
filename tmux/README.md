# Tmux

Two .tmux-conf files. Only visually differ.
* tmux_dark.conf
* tmux_light.conf

## toggle between modes
Download the above two files to `~/.tmux` and adds the following alias to shell run commands (zshrc, bashrc, etc).
``` shell
alias od='tmux source-file ~/.tmux/tmux_dark.conf'
alias ld='tmux source-file ~/.tmux/tmux_light.conf'

# to remove dark_blue
LS_COLORS=$LS_COLORS:'di=0;36' ; export LS_COLORS
PS1='[\033[1;36m]\u[\033[1;31m]@[\033[1;32m]\h:[\033[1;35m]\w[\033[1;31m]$[\033[0m] '
```
Remove dark blue in vim, create .vimrc and add following line
```
:color desert
```
Reload the rc file. Now you should be able to switch between two modes by executing `od` or `ol`

## shotcuts

* Prefix = ctrl + a
* Every shorcut start with Prefix

| panes    |  |
| -------- | ----------- |
| -        | Create pane horizontally      |
| \|       | Create pane vertically        |
| z        | Make/unmake pane full screen  |
| o        | Change pane                   |
| h j k l  | left, down, up, right         |
| H J K L  | resize current pane           |
| !        | convert current pane in new window |
| q        | display pane number |
| (space)  | change pane places  |
| x        | close pane          |

| windows  |  |
| -------- | ----------- |
| w        | list window |
| c        | create new window |
| h l      | move forward and backward through windows |
| 0..9     | select window
| n p      | move to next and previous windows |
| f        | search window by text |
| ,        | rename window         |
| C        | close window          |


| Sessions |  |
| -------- | ----------- |
| s        | list all sessions        |
| (        | move to next session     |
| )        | move to previous session |
| .        | move a window from a session to another |
| $        | rename session           |
| d        | detach session           |

| buffer   |  |
| -------- | ----------- |
| [        | copy mode   |
| ]        | paste current buffer content |
| =        | list all paste buffer and paste selected butter contents |

| in copy mode | (vi mode) |
| ------------ | --------- |
| h j k l      | left, down, up, right |
| w            | move cursor forward one word  |
| b            | move cursor backward one word |
| f (type char)| move to next occurence of the specific char |
| F (type char)| move to previous occurence of the specific char |
| ctrl + b     | scroll up one page   |
| ctrl + f     | scroll down one page |
| g            | jump top    |
| G            | jump bottom |
| ?            | search backward |
| /            | search forward  |

| others | |
| ------ | --------- |
| t      | display time |
| r      | reloads the file (TODO: make switchable light and dark modes) |
| :      | enter command mode |


## commands

| command | description |
| ------- | ----------- |
| tmux new -s <session>             | create session with name |
| tmux new -s <session> -n <window> | create session with name and first window with name |
| tmux attach -t <session>          | attach detached session |

