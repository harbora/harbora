---
hrc: 4
author: tiannian <dtiannian@gmail.com>
type: Conception
status: Draft
created: 
replacement:
---

# User

Each user is a digital signature public key. It means user use signature to verify itself.

## User ID

User ID is not a public key, is a hash of public key.

$UserId=H_1(H_2(PublicKey))$.

> $H_2$ is standard SHA3-512.
>
> $H_1$ is standard SHAKE-256 with 160 bits outputs.

User ID is a hash of public key, so we can use User ID to verify Public Key.

### Public Key

Public key is a point, must create by multiply of point and scalar number.

$P=sG$

$P$ is public key, a point on a curve.

$s$ is private key, a scalar number on finate field. It also can be a shared key.

$G$ is a generate point.

## Domain Name of user

When user change public key, the User ID also changed. But sometimes we need
a static name of user id. We can use Domain Name or ENS like service to do this.

## Basic and Advanced Usage

It should be noted that the user only requires one public key. How to construct this public key depends on different schemes.

### Single private key

The most basic way is to directly use a private key to construct a public key.

The disadvantage of this scheme is that the user must be responsible for the management of the private key.

### Threshold signature for multi-device

Users can configure multiple devices as management devices.
In this case a threshold signature of 1/n is used.

It is also possible to co-manage with the device using a managed server.
In this case a threshold signature of t+1/n is used. t is number of server.




