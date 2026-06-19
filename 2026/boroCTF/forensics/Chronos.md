---
solver: Arajtav
points: 200
---

# Description

> Would you rather posess the powers of Chronos, the God of Time or posess the powers of a bilingual?

[chronos.pcap](../_assets/chronos.pcap)

# Solution

Opening the pcap in Wireshark you can see all the packets are exactly the same, the only thing that differs is the `time` field.
You can use `tshark` to dump the time deltas:

```bash
tshark -r chronos.pcap -T fields -e frame.time_delta
```

Looking at these you can see they are always either `0.25` or `0.75`.
Since there are only these 2 states, you can convert them to `0` and `1` respectively with `| cut -c 3 | tr '27' '01'`.
Then again with `tr` you can remove the newlines to get one long binary string, `| tr -d '\n'`.
The result should be:

```
11000100110111101110010011011110100001101010100010001100111101101100011001100000110110101100010011011110110001001110101011011000110000101110100001100110101111101110011011100000100000001100111011010000011001101110100011101000110100101011111011011100110010101110000001100000111010000110001001001000110110101111101
```

The first byte of the flag should be `b` (from the flag format) which is `01100010` in binary.
The binary string we have is really close to that, the only thing that's missing is the leading zero.
Adding it and converting the string from binary to ascii you get the flag — `boroCTF{c0mbobulat3_sp@gh3tti_nep0t1$m}`.
