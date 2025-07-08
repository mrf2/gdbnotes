# Examine Memory

## Syntax: `x/[N][FU][F] 0xADDRESS`
|Field|Meaning|
|---|---|
|`N`|Number of units to display|
|`F`|Size of each unit (bytes, words)|
|`U`|Display format (hex, char, dec)|

## Full Table of Modifers
### 1. Unit size Specifiers (F)
|Code|Size|Description|
|---|---|---|
|`b`|1 bytes| "byte"|
|`h`|2 bytes| "halfword" *(short)*|
|`w`|4 bytes| "word" *(int on 32-bit systems)*|
|`g`|8 bytes| "giant word" *(64-bit integer)*|

### 2. Display Format Specifiers (U)
|Code|Format|Meaning|
|---|---|---|
|`x`|hexadecimal|Most commonly sed for raw memory|
|`d`|signed decimal|Shows signed numbers|
|`u`|unsigned decimal|Useful for positive-only integers|
|`o`|octal|Display octal numbers|
|`t`|binary|Display binary numbers|
|`c`|character or ASCII|Interprets as ASCII printable char|
|`f`|floating point|Shows as float/double *(based on size)*|
|`a`|address|Shows as memory address *(useful for pointers)*|
|`i`|instruction|Disassembles as machine instructions|

### 3. Count Prefix (N)
|Example|Meaning|
|---|---|
|`x/1bx`|Examine 1 byte in hexadecimal|
|`x/3dc`|Examine 3 characters as signed decimals|
|`x/5i $rip`|Examine 5 assembly instruction|


 * First get the address of the varaible `x`:
```bash
(gdb) print &x
$1 = (uint32_t *) 0x555555555234
```
Suppose we get the memory address: `0x555555555234`
 * Now examine the 4 bytes at that address:
```bash
(gdb) x/4bx 0x555555555234
```


