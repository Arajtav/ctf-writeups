---
solver: Arajtav
points: 200
---

# Description

> What is the name of the nearest restaurant??? I'm hungry!
>
> flag format: boroCTF{foreverflames_pizzeria}
> (Replace any space with an underscore)

[geosint2.jpg](../_assets/geosint2.jpg)

# Solution

That one was a little bit harder.

1. On the right you can see a sign saying "DORIXONA", using [Wiktionary](https://en.wiktionary.org/wiki/dorixona) you can see it is an Uzbek word.
2. Knowing that you can use Google Images searching only for the building part and adding `uzbekistan` to the query.
3. One of the top results for me is [this yandex.com maps page](https://yandex.com/maps/org/999/141484067242/?ll=64.453563%2C39.768485&z=19.6).
4. Here you can directly see the closest restaurant is `Orzu Burger`

The flag was `boroCTF{Orzu_Burger}`.

# Alt Solution (worse)

This is what I actually did at the CTF but I cannot reproduce now.
At the second step it either did not show me that result or I missed it.
Instead I found some Russian I think page with an offer for an apartment in one of those buildings.
The address was either wrong or google maps just couldn't find it, but I got the city and the street and then manually found those 3 buildings on Street View.
