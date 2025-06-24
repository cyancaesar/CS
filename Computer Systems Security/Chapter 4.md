# Cryptography

- Cryptography system
- Symmetric-key cryptography
- Public-key cryptography

Data security techniques:
1. Cryptography
2. Steganography

Cryptography means secret writing and Steganography means covered writing.

## Model of a Cryptosystem

Security System:
- Two parties (principals)
- Channel

Three Components of the Security System:
- Security-related transformation
- Secret information
- A trusted third party

Four Basic Security Tasks:
- Design an algorithm
- Generate secret information
- Develop method for the distribution
- Specify a protocol

## Categories of Cryptography

- Conventional (symmetric) methods
	- Character-level
	- Bit-level
- Public-key (asymmetric) methods

---

Requirements for secure encryption:
- Need a strong encryption algorithm
- Send and receiver must have copies of the secret key

Kerckhoff's Principle:
- We do not need to keep the algorithm secret, only the key.
- The strength of the cipher to attack is based on the secrecy of the key
- Key domain should be large

Cryptanalysis:
- Art of breaking the ciphers
- The process of attempting to discover the plaintext or key

4 Cryptanalysis Methods:
- Ciphertext-only
	- Brute-force
	- Statistical
	- Pattern
- Known plaintext
- Chosen plaintext
- Chosen ciphertext

---

Character-level:
- Substitutional
	- Mono-alphabetic
	- Poly-alphabetic
- Transpositional

Bit-level:
- Encode/decode
- Permutation
- Substitution
- Exclusive OR
- Rotation

---

## Character-level

Substitutional:
- Monoalphabetic (1:1)
	- Additive cipher (Shift/Caesar cipher)
		- `the classic shift`
	- Multiplicative cipher
		- `multiply the numeric character with the key`
	- Affine cipher
		- `apply additive and multiplicative`
	- Mapping cipher
		- `mapping table`
- Polyalphabetic (1:N)
	- Keyless cipher
		- `the key is the position`
	- Autokey cipher
		- `k1 is predetermined, k2 = p1, k3 = p2 .. kn = pn-1`
	- Playfair cipher
		- `5x5 matrix with conditions, check it out`
	- Vigenere cipher
		- `the key is a repeated stream of keyword`

---

## Bit-level

> REVIEW

---

## Public-key Cryptography

Components of Public-key system:
- Plaintext
- Encryption algorithm
- Public and Private key
- Ciphertext
- Decryption algorithm

Applications:
- Encryption/decryption
- Digital Signature
- Key Exchange

### RSA

Key generation:
- Select two large prime numbers: `p` and `q`
- Calculate `n = p x q`
- Calculate `y = (p-1) x (q-1)`
- Select a number that is relatively prime to `y` and call it `e`
- Determine `d` such that `(d x e) mod y = 1`
- The public key for encryption: `KU = {e,n}`
- The private key for decryption: `KR = {d, n}`

