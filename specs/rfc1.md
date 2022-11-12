---
rfc: 1
author: tiannian <dtiannian@gmail.com>
type: Cencept
status: Draft
created: 
requires:
---

# Uniform Resource Descriptor For Harbora

## Binary Expression in Harbora RFC

All binary in harbora's RFC document can express in `hex`.

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

> Only used in RFC document, not text form.

In some cases, you need to add some comments in hex. You can add parentheses after the segment:

```shell
ab:cD7c(comment 1):6c
```

## Node Address

Node address is a `Bytes32`. It generate follow `RFC2`.

Node address 

## Form

All resource in harbora have two form, `text` form and `binary` form

### Text

URD text form is the subset of [URL (IETF-RFC1738)](https://www.rfc-editor.org/rfc/rfc1738).

### Binary

