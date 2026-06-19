---
solver: Arajtav
points: 100
---

# Description

> Psst...I've been hearing some rumors about this special command called nc. I don't know what it is so I have to assume it means Next Challenge ... right??
> Maybe that MAN has more answers.

# Solution

Upon connecting to the server with netcat you could see

```
======================
WELCOME TO VULNBOT!!!
======================

You will need to figure out how to exploit my expert design.

help - list commands
```

After sending `help` command you could see

```
1. cheese
2. flag
```

Sending `flag` you got

```
Are you SURE you don't want to see what the Cheese option does? (y/n)
```

The last step was to answer `y`.

The flag was `boroCTF{0nLinE_C@ts*}`.
