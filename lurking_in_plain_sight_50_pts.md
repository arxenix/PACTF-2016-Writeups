# Lurking in Plain Sight (50 pts)



---

## Problem
The flag is lurking in [plain sight](http://104.236.130.98/plain_sight/).



---

## Solution
At first, we tried looking at the site's HTML, and visiting the links on the site to see if there was any comments with the flag on the linked youtube videos and articles. We also checked cookies & session variables, but nothing was found. We then checked the HTTP response, and found the header ```flag```, with the value ```i_found_a_header!```

## Flag
```i_found_a_header!```