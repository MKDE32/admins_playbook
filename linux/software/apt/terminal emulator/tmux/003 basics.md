# start / stop
```
tmux
tmux kill-server
```





# bg sessions
```
tmux attach
tmux ls
tmux detach-client 
```
- start
- show
- go in bg (`ctrl + b d`)





# all you need
```
sudo apt install xclip
sudo apt install wl-clipboard
```
- install clipboard x11
- install clipboard wayland



```
tmux set -g mouse on
set -g set-clipboard on
```
- save at least this in `~/.tmux.conf`



