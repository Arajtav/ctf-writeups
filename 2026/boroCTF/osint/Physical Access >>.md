---
solver: Arajtav
points: 100
---

# Description

> Help!! I forgot my password and got locked out of my Windows PC!
>
> I need to get back in, what can I do?!
>
> What is one of the two files I can exploit in order to get back into my PC?
>
> Flag format: boroCTF{explorer.exe}

# Solution

The flag was `boroCTF{utilman.exe}`.
It's an executable you can launch from windows login screen. Replacing it with for example `cmd.exe` makes it so you can get a shell and reset your password.
