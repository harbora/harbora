---
hrc: 4
author: tiannian <dtiannian@gmail.com>
type: Conception
status: Draft
created: 
replacement:
---

# User and Owner

## User Address and Owner

Every node in the network has an owner determined by a public-private keypair.

The owner is the absolute controller of the node, has all the capabilities of the node,
and can interact with the outside world instead of the node

This a threshold signature.

### Schnorr

If use Schnorr, have:

- SecretKey
- Code
- PublicKey
- Merkle
- User Address

When a user generate this, follow this flow:

1. Generate a random seed $s$.
2. Compute $l = Hash(s)$
3. Split $l$ to $c, a$
4. Compute public key $pk = aG$
5. Build merkle, use $pk$ as leaf.
6. Compute merkle root as user address.

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


