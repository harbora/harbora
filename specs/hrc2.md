---
hrc: 2
author: tiannian <dtiannian@gmail.com>
type: Conception
status: Draft
created: 
replacement:
---

# Harbora Uniform Resources Descriptor

## HURD

HURD is Harbora Uniform Resources Descriptor.

All resource in harbora have two form, `text` form and `binary` form

### Text

`HURD` text form is the subset of [URL (RFC1738)](https://www.rfc-editor.org/rfc/rfc1738).

Text form of `HURD` following these rule.

```shell
protocol://user:password@domain/path?data
```

- protocol: Protocol can compact web2 world.
- domain: An ID or address, node address, group address or others.
- user: Resources access user.
- password: Password for user
- path: Path to resource.
- data: Any data pass to resource.

### Binary

`HURD` also have binary format. This format can parse in stream.

```
struct HurdHeader {
  ver: u8,
  user_len: u8,
  pass_len: u8,
  domain_len: u8,
  path_seg: u8,
  args_seg: u8,
  hash_len: u8,
  cat: varint64,
}

struct HurdBody {
  user: Bytes,
  pass: Bytes,
  domain: Bytes,
  path: [Bytes; 0 .. 255],
  args: [(Bytes, Bytes), 0 .. 255]
  hash: Bytes,
}
```
- mgc: Magic number, always `b08a`
- ver: Version of HURD
- cat: Category of protocol
- idl: based on cat
- usl: Length of user.
    - usr: User id.
- id: ID or address
- ptl: Length of Path
    - pth: Path
- dtl: Length of data
    - dta: Data

### Mapping and Convert between Text and Binary

Protocol on binary form have three segment, `mgc`, `ver`, and `cat`.
And this on text form also have three part:

``` shell
hrp1g
```

- `hrp` is magic, means harbora resource protocol.
- `1` is version, means version number
- `g` is category.

## Category for Version 1

- Node
  - Text: hrp1n://
  - Binary: 0xb08a0101
- Group
  - Text: hrp1g://
  - Binary: 0xb08a0102



