# Unauthorized Access (70 pts)



---

## Problem
Get us [authorized](http://104.236.130.98/).

## Hint
Can you change who you are?


---

## Solution
The webpage tells us that our access is denied because we aren't from Google. It likely detects this by checking some HTTP Headers in the browser's GET request. We could try spoofing various HTTP headers to match Google, but there is an even easier way! Use Google Translate's site translation service to proxy the request through Google's servers with their HTTP headers. Visit https://translate.google.com/, enter the site address http://104.236.130.98/, to view the unblocked webpage.

## Flag
```flag{PiA2G1ujz1vgnI4aaESV}```