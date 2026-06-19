---
solver: Arajtav
points: 100
---

# Description

> Find the streetname. :D
> 
> flag format: boroCTF{street_name}

[Country.png](../_assets/Country.png)

# Solution

The first 2 things you can see on the image are
1. Arabic script
2. A 8 digits long phone number

There are only a few countries that have both — Tunisia, Chad, Lebanon, Kuwait, Bahrain, Qatar and Oman.

Looking at those in google maps you can eliminate1
- Kuwait, Bahrain and Qatar as they are too flat.
- Chad as it has no Street View coverage.
- Lebanon as it is not flat enough.

Now with only Tunisia and Oman left, Tunisia does not have enough Street View coverage and seemingly has more plants and different terrain in general.
The flag was `boroCTF{oman}`.
