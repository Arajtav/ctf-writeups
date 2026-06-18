---
solver: Arajtav
points: 300
---

# Description

> You may be pretty good at geosint. But are ya good enough?
>
> Find the country in every image, image 1 to image 10. And in the order that they are numbered, order it like that in the flag. Also seperate EVERY space with an underscore,
>
> Seperate each and every space with an **underscore** (so United States of America, would be United_States_of_America) and each COUNTRY gets seperated with a **comma**.
>
> Example flag: boroCTF{forever_flames,shiny,satoshi,this_is_not_the_flag}
>
> **(NOTE: ONLY 50 MAX ATTEMPTS)**

[panorama.zip](../_assets/panorama.zip)

# Solution

1. Using Google Images to reverse image search reveals it is an airport in Argentina.
2. Again Google Images shows it is Alexandria, Egypt.
3. Devanagari script on the wall + flat landscape means it's India.
4. Looks like Australia, could be New Zealand too I cannot tell them apart.
5. Burmese alphabet (though at first I though it is one of Georgian scripts).
6. After an hour of looking at road signs articles in wikipedia, the only country with that no overtaking sign is Ecuador.
7. The only country with those speed limit zone signs is Iceland.
8. Those mountains look like Kyrgyzstan, I also thought it may be Tajikistan but it felt a little bit off.
9. Google Images searching the church showed it is in Ghana.
10. I guessed Russia based on the `Евросеть` sign and the red rectangular road sign with 2 white stripes, but it doesn't seem to be unique to Russia.

To sum up I did have to guess a few times and it actually took me 11 tries.
The flag was `boroCTF{Argentina,Egypt,India,Australia,Myanmar,Ecuador,Iceland,Kyrgyzstan,Ghana,Russia}`
