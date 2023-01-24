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
protocol://user@id:path?data
```

- protocol: Protocol can compact web2 world.
- id: An ID or address, node address, group address or others.
- user: Resources access user.
- path: Path to resource.
- data: Any data pass to resource.

### Binary

`HURD` also have binary format. This format can parse in stream.

```
b08a(mgc)
XX(ver)
XX(cat)
XX(usl)
XXXX(ptl)
XXXX(dtl)
XX..[usl]..XX(usr)
XX..[idl]..XX(id)
XX..[ptl]..XX(pth)
XX..[dtl]..XX(dta)
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
hrb 1 g
```

- `hrb` is magic, means hrb protocol.
- `1` is version, means version number
- `g` is category.


