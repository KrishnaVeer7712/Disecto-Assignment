# Disecto-Assignment

For tackling the problem of Homomorphic Encryption (HE), I have used Paillier cryptosystem approach which supports homomorphic encryption, where two encrypted values can be added together, and the decryption of the result gives the addition. 

The output of following approach is shown below:

![Output](https://user-images.githubusercontent.com/41145993/174032711-04b2c6e4-fbee-4b86-ae95-9023065e9e17.PNG)

## Homomorphic Encryption uses three different stages:
### a) Key Generation:
1. We start with two large prime numbers (p and q) randomly and independently of each other such that gcd(pq, (p-1)(q-1))=1. This prperty assures if both primes are of equal length.
2. Then compute n=pq
3. Find λ as Lowest Common Multiplier for (p-1) and (q-1).
4. Select random integer number g.
5. Then calculate the value of the L function, and then gMu, which is the inverse of l mod n
6. The public key is then (n,g) and the private key is (gLamda,gMu).

### b) Encryption:
1. Let m be message to be encrypted where 0 ≤ m ≤ n.
2. Select random r where 0 ≤ r ≤ n.
3. Compute Ciphertext as c = g^m. r^n mod n^2

### c) Decryption:
1. Compute the plaintext message as: m= L(c^λ mod n^2).gMu mod n.
