---
solver: Arajtav
points: 100
---

# Description

> Mark (from Meta) called me the other day and attached this photo. He told me he needed to remember what model camera he took his picture with.
> Could you help me?

[Mark-Zuckerberg.png](../_assets/Mark-Zuckerberg.png)

# Solution

You can use ExifTool to dump the EXIF metadata of the image.

```bash
exiftool Mark-Zuckerberg.png | grep boroCTF
```

This returns the flag under `Camera Model Name`, the flag is `boroCTF{M3+a_d@ta_1s_M7_Fa40rite}`.
