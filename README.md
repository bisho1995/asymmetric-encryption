<div align="center" style="text-align:center">
    <h1 align="center">🔐 Asymmetric Encryption 🔑</h1>
    <p align="center">Generate Public-Private keypair on your server for asymmetric encryption and decryption</p>
    <p align="center" style="text-align:center">
    <img alt="build passing" src="https://img.shields.io/badge/build-passing-brightgreen">
    <img alt="MIT" src="https://img.shields.io/badge/license-MIT-green">
    </p>
</div>
<p><br/></p>

1. Generate public key and private key in the server.
2. Forward the public key to your apps (website or app)
3. Have your app generate a random key for encryption.
4. Encrypt the message using the random key generated by your app.
5. Encrypt the random key using the public key supplied by the server.
6. Send to the server both the encrypted message and the encrypted random string.
7. On the server end decrypt the encrypted string sent by the client using private key.
8. Using the decrypted key decrypt the message.

This module aims at solving the public key, private key and passphase part of the process.

# Installation

```
npm i --save asymmetric-encryption
```

or

```
yarn add asymmetric-encryption
```

## Usage

```
const encrypt = require("asymmetric-encrypt")

const { publicKey, privateKey } = encrypt.generateKeyPairSync();
const message = "message";

const enc = encrypt.encrypt(publicKey, message);
const dec = encrypt.decrypt(privateKey, enc);

console.log(dec)
```

Output should be

```
message
```

## Tests

```
npm tests
```
