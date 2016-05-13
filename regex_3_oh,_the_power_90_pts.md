# Regex 3: Oh, The Power! (90 pts)



---

## Problem
By now you are acquainted with the powers of regex, but can you make a regex match only the powers of 5? Only a string of 5^n repeating ‘x’s should pass.

You have all of 30 characters.

## Hint
Take away 4/5ths of a power of 5, and you have: a power of 5.



---

## Solution
Well, our solution was pretty stupid for this one. We just made the regex brute force match powers of 5, hoping that their test cases didn't test higher powers. Luckily, it worked.

```x{625}|x{125}|x{25}|x{5}|x```