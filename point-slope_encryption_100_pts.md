# Point-Slope Encryption (100 pts)



---

## Problem
We uncovered these [weird numbers](./files/points.txt) from Dr. Miles’ secret folder, but we don’t know what to do with it! Can you help us? We also found [this script](./files/encrypt.py) and [this data](./files/handout.txt) in the same place, if it helps.

## Hint
That ‘s’ function seems like it does something familiar…


---

## Solution
The 's' function in encrypt.py approximates the derivative at a point of a function. This should be clear to anyone who has taken an introductory calculus course, as it is  computing the limit definition of the derivative: $$ f'(x) = \lim \limits_{\Delta x\to\infty} \frac{f(x+\Delta x)-f(x)}{\Delta x}$$

We see that the function 'f' is the secret_func, which we don't have. However, looking in the handout.txt file, we have ```df/dx = 1651/(12pi * cosx + 5pi * sinx)```. We can integrate this function to recover secret_func! Using wolframalpha, we get:

```
def secret_func(x):
    return (-127* (math.log(   abs(  3*math.cos(x/2) - 2*math.sin(x/2)     )     ) - math.log(  abs(      2* math.cos(x/2) + 3* math.sin(x/2)   )      )))/math.pi
```
(abs functions are added to make sure the function doesn't error when taking logs of negative values)

We probably could have reversed the encryption function if we spent some more time on it, but didn't bother since we thought of an easier way to do it. (at first glance, it seems to be linearizing the function and returning the x,y of the linearized mapping)

In order to decrypt the message, we can simply encrypt every possible character (a-z,A-Z, 0-9, {}). To decrypt, we iterate through every point in points.txt, and find the character whose encrypted point most closely matches it!

```
validchars = 'abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ{}0123456789_!@#$%^&*()'
print "generating..."
arr = []
for c in validchars:
    arr.append(encrypt(secret_func, a, ord(c)))


print "decrypting...."
f = open('points.c4344870fa17.txt').readlines()

flag = ""
for ln in f:
    #parse the line
    sp = ln.replace('(',"").replace(")","").split(", ")
    x = float(sp[0])
    y = float(sp[1])

    tuples = [] # list of closest matching points
    for i in range(len(arr)):
        pt = arr[i]
        dist = math.hypot(x - pt[0], y - pt[1])
        tuples.append((dist, i))
    tuples.sort(key=lambda x: x[0]) # sort it
    print x,y 
    print map(lambda x: validchars[x[1]], tuples)
    print " "
    flag+= validchars[tuples[0][1]]
print repr(flag)
```

Running this code gives us the flag as ```fl{gucslI_1z_fuN}```, which is close but obviously wrong. We then looked at the next closest matching characters for each point (printed out by the above program), and managed to correct it to ```flag{c4lC_Iz_fuN}```

## Flag
```flag{c4lC_Iz_fuN}```