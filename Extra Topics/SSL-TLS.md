# SSL - TLS 

## TLS (Transport Layer Security):

**TLS** is a **security protocol** that **provides privacy and data integrity for Internet communications**. 

Implementing TLS is a standard practice for building secure web apps.

**TLS** evolved from a previous encryption protocol called **Secure Sockets Layer (SSL)**, which was developed by **Netscape**. **TLS version 1.0** actually began development as **SSL version 3.1**

## SSL (Secure Sockets Layer):

**SSL**, or Secure Sockets Layer, is an **encryption-based** internet security **protocol**. 

It was first developed by **Netscape** in 1995 for purpose of **ensuring privacy, authentication, and data integrity** in internet communications. 

SSL is predecessor to the modern TLS encryption used today. 

A website that implements **SSL/TLS** has **"HTTPS" in its URL** instead of **"HTTP"**.

**HTTPS** is an **implementation of TLS encryption on top of the HTTP protocol**, which is used by all websites as well as some other web services.


### What does TLS do ?

There are three main components to what the TLS protocol accomplishes: 

1. **Encryption**: hides the data being transferred from third parties

2. **Authentication**: ensures that the parties exchanging information are who they claim to be.

3. **Integrity**: verifies that the data has not been forged or tampered with.


## How does TLS Work ?

For a wesite or application to use **TLS**, it must have a **TLS Certificate installed** on its **origin server** (the certificate is also known as an **SSL Certificate**). 

A TLS certificate is **issued by** a **Certificate Authority** to the person or business that owns a domain.

The certificate contains important information about who owns the domain, along with the server's **Public Key**, both of which are important for validating the server's identity.


A TLS connection is initiated using a sequence known as the **TLS Handshake.**

When a user navigates to a website that uses TLS, the TLS handshake begins between the user's device (also known as the client device) and the web server

During the **TLS handshake**, the user's device and the web server:

1. Specify which version of TLS (TLS 1.0, 1.2, 1.3, etc.) they will use

2. Decide on which **Cipher Suites** (see below) they will use

3. Authenticate the identity of the server using the server's TLS certificate

4. Generate **Session Keys** **_for encrypting messages_** between them after the handshake is complete.

The TLS handshake establishes a **Cipher Suite** for each communication session.

The **Cipher Suite** is a **set of algorithms** that specifies details such as which shared **encryption keys**, or **session keys**, will be used for that particular session.


TLS is able to set the matching session keys over an unencrypted channel thanks to a technology known as **public key cryptography**.

The **handshake also handles authentication**, which usually consists of the **server proving its identity to the client**. 

This is done using **Public Keys**.

**Public Keys** are encryption keys that use **one-way encryption**, meaning that **anyone with the public key can unscramble the data encrypted with the server's private key to ensure its authenticity**, but **only the original sender can encrypt data with the private key**. 

The server's **public key is part of its TLS certificate**.

![ssl1](./tls-ssl-handshake.png)

**Once data is encrypted and authenticated**, it is then **signed with a message authentication code (MAC)**. 

The **recipient can then verify the MAC** to ensure the integrity of the data. 

_This is kind of like the tamper-proof foil found on a bottle of aspirin; the consumer knows no one has tampered with their medicine because the foil is intact when they purchase it._


Types of SSL Cetificates: **Single-Domain** and **Multi-Domain**. 

The latest versions of TLS hardly impact web application performance at all.

_This Should Be Enough_