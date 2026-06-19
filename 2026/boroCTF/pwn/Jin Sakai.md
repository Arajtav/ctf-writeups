---
solver: Arajtav
points: 100
---

# Description

> The Eagle's curse has completely made him go mad...
> 
> Once a hero of Tshushima, now a bloodthirsty warrior.
> 
> Please put an end to this madness.

[JinSakai.zip](../_assets/JinSakai.zip)

# Solution

The python code is not important, the vulnerability is in the `boss.c` file.

## Phase 1

The first phase to run is `fight_phase1()`, one of the first things you see is c `gets()` function.
It's a function intended to load a string from standard input into a preallocated buffer, however it does not size checks.
With this function you can overwrite `state.samurai_hp` which is located directly after the 32-byte long buffer.

They payload needs to be:

1. Any 32 characters (the buffer).
2. Any 3 characters (the lower bytes of the int).
3. A byte starting with a high bit (for example `0x80`) to make the int negative due to two's complement.
4. A newline (`0x0a`) to continue.

## Phase 2

The second phase is `fight_phase2()`, it is simpler as it only involves overflowing an int.
You can see `samurai_hp` is initialized to `INT_MAX` and the flag condition is `samurai_hp == INT_MIN`.
In order to reach it you need to increment `samurai_hp` by `1` with conveniently placed `samurai_hp += amount` a line earlier.
To get there you need to in order answer:

1. `3` (the choice).
2. `1` (the item).
3. `2` (the target).
4. `1` (the amount to add).

## The final payload

The final payload should look like that

```
41 41 41 41 41 41 41 41  41 41 41 41 41 41 41 41
41 41 41 41 41 41 41 41  41 41 41 41 41 41 41 41
42 42 42 80 0a 33 0a 31  0a 32 0a 31 0a
```

You can echo and pipe it into `xxd -p -r` to convert it into binary.

The flag was `boroCTF{gh0st_0f_3xpl01t4t10n}`.
