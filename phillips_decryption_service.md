# Phillips Decryption Service

This problem was a fun one, and more of a math problem in disguise. The overview is as follows: We have a server that will decrypt any message we send it except for the flag. Luckily for us, the server doesn't implement any sort of padding schemes, meaning the server is vulnerable to a "blinding" attack. This is also called an attack on "textbook RSA."

Briefly, the equation for RSA, where C is the ciphertext and P is the plaintext:

$$C^d = M^{ed} \pmod{n} $$

The server can then be viewed as a function:

$$f(x) = x^d \pmod{n}$$, assuming x =/= M

Now here's the exploit: we "blind" the server by multiplying the ciphertext C by some arbitrary number R'. R is a member of the set Z_*n (GCD(modulus,R) = 1 ; R < n), and then we "encrypt" R to get R', so what we send to the server is C*R' = M^e * R^e



We send this to the server as the message to be decrypted:

$$f(C*R') = (C*R')^d = C^d * (R')^d = M^{ed} * R^{eD} = M*R$$

From here, by fact that R is a member of Z_*n, R has a modular multiplicative inverse, effectively allowing us to cancel the R term, giving us the decrypted message.

```flag{0opZ_i_g00fd}```