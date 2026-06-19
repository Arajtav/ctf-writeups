---
solver: Arajtav
points: 200
---

# Description

> My friend Jonas Wagner sent me a challenge but I can't be bothered to do it. He was always one to be working on his own sorts of projects and stuff. You do it.

[burn.png](../_assets/burn.png)

# Solution

You need to

1. Run threshold of 255 only on blue channel.
2. Run threshold of 255 only on green channel.
3. Make an image that's the difference between those 2.

You should end up with a kinda readable flag — `boroCTF{0W_^MY_E7ES!}`.

# Command

```bash
magick burn.png \
  \( -clone 0 -channel B -separate -threshold 99.99% \) \
  \( -clone 0 -channel G -separate -threshold 99.99% \) \
  -delete 0 \
  -compose Difference -composite output.jpg
```

Although you can just use gimp like I did on the CTF.
You would have to do that anyway since there is no way to see on which channels the flag was without applying these effects first.
