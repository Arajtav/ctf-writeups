---
solver: Arajtav
points: 100
---

# Description

> Need higher WPM? Try monkeytype.

# Solution

When connecting to the socket the message `Please enter {N} characters!` was displayed. All you needed to do was to enter N characters, fast.

The flag was `boroCTF{Hum@n1y_im7o5s!ble}`.

# Script

```python
HOST = "..."
PORT = ...

s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
s.connect((HOST, PORT))

socket_file = s.makefile('rw', encoding='utf-8')
question = socket_file.readline().strip()

number = int(question.split(" ")[2], 16)

socket_file.write("A" * number + "\n")
socket_file.flush()

while True:
  chunk = s.recv(4096)
  if not chunk:
    break
  print(chunk.decode('utf-8', errors='ignore'), end="")
```
