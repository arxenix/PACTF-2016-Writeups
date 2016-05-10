# A Fierce Attacker (80 pts)


---


## Problem
Intelligence states that the flag is located on a server with the domain ‘pactf2.tk’ on a secret sub-domain. Can you find the correct sub-domain?


## Hint
Take a guess. Or find someone fierce instead.


---


## Solution
The problem name, statement, and hint immediately led us to think of using the subdomain scanning tool "fierce", which is available by default in kali linux. If you did not know of this tool, it is on the first page of the search results for "fierce sub domain".

We simply run the command ```fierce -dns pactf2.tk``` and wait for the results, to find the hidden subdomain ```vpn.pactf2.tk```. Visiting this page gets us the flag

## Flag
```CJY0n9d1cZHkuEkEsF2U5sf1Aqh0TQ```