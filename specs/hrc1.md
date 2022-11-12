---
hrc: 1
author: tiannian <dtiannian@gmail.com>
type: Conception
status: Draft
created: 
replacement:
---

# HRC definition

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
## Basic Type

### Integer

Define integers using attribute plus length:

``` shell
# standard unsigned integers
u8, u16, u32, u64, u128

# standard signed integers
i8, i16, i32, i64, i128

# any width integers
u24, u5, u7, i10
```

`i` means signed, `u` means unsigned, `number` means witdh.

