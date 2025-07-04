# list - listing source code

### Basic Syntax:
```bash
(gdb) list [location]
```

### Common `list` Usages:
|Command|Meaning|
|---|---|
|`list`|List 10 lines around current execution point (or line 1 if not started)|
|`list main`|List lines around function `main`|
|`list 20`|List lines around line 42 of the current source file|
|`list file.c:22`|List lines around line 22 in `file.c`|
|`list +`|List next 10 lines|
|`list -`|List previous 10 lines|
|`list func_name`|Show lines around a given function name|
|`list filename:function_name`|Show codes for a specific function in a specific file|
|`list .`|Show current line of execution|
 * Each `list` show **10 lines** by default.
 * To view more, repeat the `list` command or use `list +`

## `disas` - Disassemble 
### Basic Syntax:
```bash
(gdb) disassemble [location]
```

### Common `disassemble` Usage Patterns
|Command|Description|
|`disassemble`|Disassemble around current PC (program counter)|
|`disassemble main`|Disassemble the `main` function|
|`disassemble func_name`|Disassemble named function|
|`disassemble 0xaddress`|Disassemble starting at a specific address|
|`disassemble /m main`|Disassemble `main` with **interleaved source code**|
 * The `/m` modifier in `disassemble` means: **Disassemble with source code interleaved** - it shows both C source line and the corresponding assembly instructions.
