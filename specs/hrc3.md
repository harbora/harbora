---
hrc: 3
author: tiannian <dtiannian@gmail.com>
type: Conception
status: Draft
created: 
replacement:
---

# Cryptography Infrastructure

Harbora have some core cryptography infrastructure.

## ECC, Cryptography abstraction and Schemes

The cryptographic infrastructure described here is done based on cryptographic abstractions.

Abstraction based on ECC and finite fields, separating algorithms into schemes and curves.

ECC includes two levels, basic and pair friendly:

- Basic: include basic point operation. Like Secp256k1, Curve25519 etc.
- Pairing friendly: support pairing operation. Like bn254, bls12-381

## Digital Signature

harbora needs to use a digital signature algorithm that supports aggregation,
which means that the algorithm of ECDSA cannot be used.

To satisfy this requirement, the following schemes are supports:

- Schnorr: require basic level.
- BLS: require pairing friendly.

Due to the performance consumption of digital signatures, the number of digital signature
verifications is minimized in harbora's protocol.
Use DH+HMAC as much as possible.

## DH Key Exchange

In order to reduce the number of digital signature verifications,
it is necessary to use DH for key exchange and convert to symmetric encryption as soon as possible

## Symmetric encryption

Use symmetric encryption to transmit traffic, encrypted storage and other operations in harbora.

### Encryption with MAC

For security, symmetric encryption needs to be used in conjunction with MAC.

These scheme can be used:

- Stream Encryption + MAC: Strobe

## ECC Key Derive

In order to reduce the number of times the private key has to be recorded, a derivation algorithm like EIP44 can be used.

## Types

### PublicKey and SecretKey

In order to store different types of public and private keys, it is necessary to use enumerations to express them.

``` rust
enum PublicKey {
    Curve25519(..),
    Secp256k1(..),
    Bls12_381(..),
    Bn265(..),
}
```
#### Encode

``` shell
XX(ty) XX..XX
```

First byte is type.
