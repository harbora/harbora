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

Each user is 2-n threshold signature. `n` is a all control device.

### BLS

If use BLS, owner have:

- SecretKey
- Code
- PublicKey
- AggrPublicKey
- User Address

Same as schnorr, generate BLS using the following rule:

1. Same as schnorr's 1 ~ 4
2. Compute threshold public key.

## User ID

## Permission

## Auth


