# recognize monitors
```
xrandr --auto
```

# shows connected monitors
```
xrandr --verbose | grep connected
```








# SET MODE
```
xrandr
xrandr --output <DISPLAY> --mode 1024x768
```

# ADD MODE (IF NEEDED)
```
xrandr --query
cvt 1024 768
xrandr --newmode "1024x768"  65.00  1024 1072 1168 1312  768 771 775 798 -hsync +vsync
xrandr --addmode Virtual-1 1024x768
```
