# Lost Keys (50 pts)


---

## Problem
Hey, I’m Cameron Wong. I had a flag ready for you, but it seems that it’s locked away somewhere, and I’ve lost my keys… What I do have, though, is a door, maybe you can try getting into that?

door.txt: ```2a1308041e03173f0e1a0231040e0a1c1f1c380d02022e12```
## Hint
If your first instinct was to google my name and/or my username, you’re barking up the wrong tree! I’m way more narcissistic than that! Also, I hate typing spaces in keys, that’s just annoying.



---

## Solution
The message is encrypted using a repeated XOR cipher, with the key being ```CameronWong```, since he is narcissistic and doesn't use spaces in his keys.

We can use the site http://xor.pw/ to decrypt this. Set the input #1 type to hex, and the value to ```2a1308041e03173f0e1a0231040e0a1c1f1c380d02022e12```, then input #2 type to ASCII and the value to ```CameronWongCameronWongCa``` (half the length of the hex, since each ascii character is two hexadecimal digits). Set the output type to ascii, and XOR it to get the flag.

## Flag
```ireallyhatereconproblems```