---
solver: Arajtav
points: 100
---

# Description

> Challenge: So is this not the flag? If its not not, then what else?
>
> `9d 90 8d 90 bc ab b9 84 8b 97 ce db a0 96 8c a0 91 cf 8b a0 91 90 8b a0 8b 97 cc a0 99 93 bf 98 82`

# Solution

The XOR cipher is one of the most basic digital ciphers.
It works by applying XOR operation with some key on every value of the plaintext.
Since part of the plaintext is known (`boroCTF{...` from the flag format) all you need to do to get the key is
to XOR for example the first byte of the plaintext (`b`) with the first byte of the ciphertext (`0x9d`).

```python
BYTES = "9d 90 8d 90 bc ab b9 84 8b 97 ce db a0 96 8c a0 91 cf 8b a0 91 90 8b a0 8b 97 cc a0 99 93 bf 98 82"
values = [int(b, 16) for b in BYTES.split(" ")]
KEY = values[0] ^ b'b'[0]
result = [chr(v ^ KEY) for v in values]
print("".join(result))
```

The flag is `boroCTF{th1$_is_n0t_not_th3_fl@g}`.

# Alt Solution

Since they key is `0xff`, that is all bytes set to 1, you can also think it as inverting every byte of the text.
It does not change anything, it's just a different way to think about it.
