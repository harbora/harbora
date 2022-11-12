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

## HURD

HURD is Harbora Uniform Resources Descriptor.

All resource in harbora have two form, `text` form and `binary` form

### Text

`HURD` text form is the subset of [URL (RFC1738)](https://www.rfc-editor.org/rfc/rfc1738).

Text form of `HURD` following these rule.

```shell
protocol://user@id:path?key1=value1&key2=value2#hash
```

- protocol: Protocol can compact web2 world.
- id: An ID or address, node address, group address or others.
- user: Resources access user.
- path: Path to resource. [URL (RFC1738)](https://www.rfc-editor.org/rfc/rfc1738)
- key=value: KV map. same as [URL (RFC1738)](https://www.rfc-editor.org/rfc/rfc1738).
- hash: Can be any value

### Binary

## Type

