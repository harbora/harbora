---
hrc: 4
author: tiannian <dtiannian@gmail.com>
type: Conception
status: Draft
created: 
replacement:
---

# User and Owner

## Owner

Every node in the network has an owner determined by a public-private keypair.

The owner is the absolute controller of the node, has all the capabilities of the node,
and can interact with the outside world instead of the node

Owner is a plain user.

## User

Each user is a digital signature public key. It means user use signature to verify itself.

### User ID

User ID is not a public key, is a hash of public key.

$UserId=H_1(H_2(PublicKey))$.

> $H_2$ is standard SHA3-512.
>
> $H_1$ is standard SHAKE-256 with 160 bits outputs.

User ID is a hash of public key, so we can use User ID to verify Public Ksy.

### Domain Name of user

When user change public key, the User ID also changed. But sometimes we need
a static name of user id. We can use Domain Name or ENS like service to do this..

### User number

## Permission

## Auth


