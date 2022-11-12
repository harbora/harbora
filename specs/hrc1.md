---
hrc: 1
author: tiannian <dtiannian@gmail.com>
type: Conception
status: Draft
created: 
requires:
---

# Uniform Resource Descriptor For Harbora

## Binary Expression in HRC

All binary in harbora's HRC document can express in `hex`.

```
0123456789abcdefABCDEF
```

Some separators may be used to split hex strings. Since two hexadecimal characters represent a byte, 
each segment must be an even number of hexadecimal characters.

Separators can be space (` `), comma (`,`), colon (`:`). But mixing is not allowed.

``` shell
# space
ab cD7c 6c

# comma
ab.cD7c.6c

# colon
ab:cD7c:6c
```

### Comment

> Only used in HRC document, not text form.

In some cases, you need to add some comments in hex. You can add parentheses after the segment:

```shell
ab:cD7c(comment 1):6c
```

### Variable Length Bytes

There are two cases of variable bytes, abbreviation arrays and indefinite length bytes.

Abbreviation arrays can use on too long bytes. Write length in `....`, length can use comment.

``` shell
XX..[length]..XX
```

Indefinite length bytes basic form is:

```
XX..XX
```

Also, we can alse define length range

```
XX..[1 .. 5]..XX
```

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
b08a(mgc)  XX(ver) XX(cat)
XX(usl)    XX..[usl]..XX(usr)
XX(idl)    XX..[idl]..XX(id)
XXXX(ptl)  XX..[ptl]..XX(pth)
XXXX(dtl)  XX..[dtl]..XX(dta)
```
- mgc: Magic number, always `b08a`
- ver: Version of HURD
- cat: Category of protocol
- usl: Length of user.
    - usr: User id.
- idl: Length of id
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

## Basic Type

