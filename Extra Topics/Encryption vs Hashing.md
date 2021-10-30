# Encryption vs Hashing 

**Encryption** is a **two-way function** where data is passed as a **PlainText** and comes out as a **CipherText**, which is **unreadable**.

Since encryption is **two-way**, the data can be **Decrypted** back so it is **readable again**. 


**Hashing** is a **one-way**, meaning the **PlainText** is scrambled into a **unique digest**, through the use of a **salt**, that **cannot be decrypted**. 

_Technically hashing can be reversed, but the computational power needed to decrypt makes it infeasible._

The way hashing works is with a **hashing algorithm**. 

This algorithm is most effective when it **collision resistant**.

**Collision resistance** means that **all the digests are unique and do not overlap with each other**.


## Symmetric and Asymmetric Encryption: 

Encryption comes in two types: **Asymmetric** and **Symmetric**.

**Asymmetric encryption** uses **two different keys**, a **public** and **private key**, for **encryption** and **decryption**.

The **private key is used to encrypt data**, and is kept a secret from everyone but the person encrypting the data.

The **public key** is available for anyone, and **is used for decryption**. 

Using asymmetric encryption, **the authenticity of the data can be verified**, because **if the data was modified in transit, it would not be able to be re-encrypted with the private key**.


**Symmetric encryption** uses the **same key for both encryption and decryption**. 

This type of encryption uses **less processing power and is faster**, but is **less secure** as only one key is used.

### Symmetric Encryption Algorithms: 

1. **Advanced Encryption Standard (AES)**
2. **Blowfish**
3. **Twofish**
4. **Rivest Cipher (RC4)**
5. **Data Encryption Standard (DES)**


### Asymmetric Encryption Algorithms: 

1. **Elliptic Curve Digital Signature Algorithm (ECDSA)**
2. **Rivest-Shamir-Adleman (RSA)**
3. **Diffie-Hellman**
4. **Pretty Good Privacy (PGP)**


### Hashing Algorithms:

1. **Message Digest Algorithm (MD5)**
2. **Secure Hashing Algorithm (SHA-1, SHA-2, SHA-3)**
3. **WHIRLPOOL**
4. **TIGER**
5. **Cyclical Reduction Check (CRC32)**


**NOTE: Base64 is a _binary-to-text encoding scheme_ NOT a hashing algorith. Base62 is _62 character (a-zA-Z0-9) encoding scheme_**

_This should be enough_