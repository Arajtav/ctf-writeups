---
solver: Arajtav
points: 200
---

# Description

> Truth, broken into sixty-four.

[64.zip](../_assets/64.zip)

# Solution

The filenames look like base64 encoded strings.
Decoding these reveals these are numbers from 1 to 64.
The files itself either contain some characters or nothing, always ending in 40.
What you need to do now is to concatenate them in order, taking only what's before the `40`.

```bash
for i in {1..64}; do echo -n "$i" | base64; done | xargs head -q -c -2
```

This results is a base64 encoded string `Ym9yb0NURntzMXh0eV9mMHVyX2IzYXV0eX0=`. Decoding it reveals the flag is `boroCTF{s1xty_f0ur_b3auty}`.
