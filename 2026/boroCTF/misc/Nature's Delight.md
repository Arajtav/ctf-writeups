---
solver: Arajtav
points: 200
---

# Description

> I found this tag stuck on the back of my shirt! My friend must have put it... but who even makes these?
> 
> flag format: boroCTF{tag_maker}

[weirdtag.jpg](../_assets/weirdtag.jpg)

# Solution

The image contains an [UPC](https://en.wikipedia.org/wiki/Universal_Product_Code).
Querying it in a barcode database like https://www.barcodelookup.com returns the producer is Poland Spring.
The flag is `boroCTF{poland_spring}`.
