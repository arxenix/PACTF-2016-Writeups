# Point-Slope Encryption (100 pts)



---

## Problem
We uncovered these [weird numbers](./files/points.txt) from Dr. Miles’ secret folder, but we don’t know what to do with it! Can you help us? We also found [this script](./files/encrypt.py) and [this data](./files/points.txt) in the same place, if it helps.

## Hint
That ‘s’ function seems like it does something familiar…


---

## Solution
The 's' function in encrypt.py approximates the derivative at a point of a function. This should be obvious to anyone who has taken an introductory calculus course, as it is simply computing the limit definition of the derivative: $$ f'(x) = \lim_{\Delta x\to\infty} \frac{f(x+\Delta x)-f(x)}{\Delta x}$$

The 'secret' variable is 