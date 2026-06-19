---
solver: Arajtav
points: 200
---

# Description

> The hexagonal colors are simply beautiful.

[dance.png](../_assets/dance.png)

# Solution

The image contains 10 squares of different colors.
All you need to do is to get the color codes for all of those,

```
#626F72
#6F4354
#467B6E
#457633
#725F6C
#302465
#5F596F
#55345F
#426540
#747D00
```

remove the `#`s and convert the remaining hexadecimal digits into ascii to get `boroCTF{nEv3r_l0$e_YoU4_Be@t}`.

# A Script

```zsh
while color=$(hyprpicker | tail -c 7 | xxd -r -p) && [ -n "$color" ]; do printf "%s" "$color"; done; echo ""
```

I use `hyprpicker` since I am on Hyprland, but it can be any color picker.
Using that command you can just click on all the colors in order and get the flag, it should be a little bit faster.
