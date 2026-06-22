---
solver: Arajtav
points: 100
---

# Description

> You have yours and I have mine. Together we have something larger than ourselves.

[chal](../_assets/chal)

# Solution

Decompiling `chal` the logic looks something like

```c
fgets(&str, 12, stdin);
uint32_t value = atoi(&str);

if ((int32_t)value > 10000) {
    value = 1;
}

if ((int32_t)value < 0) {
    value = -value;
}

int32_t value2 = value + 2;
if (value2 < -1) {
    flag();
}
```

The vulnerability obviously has to be in the way the program handles the number, casting it sometimes but not always.

The range for a `uint32_t` is `0` to `4294967295`. `(int32_t)value > 10000` needs to fail since `value = 1` will not pass the final check.
Due to the signedness change the passing values are `10001` to `2147483647`.
The range that is interesting to use then remains `0` to `10000` and `2147483648` to `4294967295`.

The range for the final check is `2147483646` to `4294967292`.
The values above `2147483647` are impossible from the second check, hence the only possible value passing all checks is `2147483647`.

The flag was `boroCTF{tw0s_c0mpl3men+_M3}`.
