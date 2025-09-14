# `print`
Evalues and prints a C-style expression or variable **once**.

### Syntax:
```bash
p [/format] expression
```

### Examples:
```bash
p i                 # Print value of variable 'i'
p/x i               # Print value of variable 'i' in hexadecimal
p *ptr              # Dereference and print value pointed to by ptr
p $eax              # Print register
```

### **`signed`**/**`unsigned`** with a specific fixed witdht **(8-bit, 16-bit, 32-bit, etc)**
 * By default, **`p/d 128`** just print the decimal interpretation of the constant `128` (a host **`int`**)
 * GDB does not automatically **wrap** values the way a fixed-width 8-bit or 16-bit integer would, unless the value is ***explicitly cast to a type of that width***.

#### Examples:
```bash
(gdb) p/d (signed char) 128
$1 = -128           # 8-bit signed


(gdb) p/u (unsigned char) 128
$2 = 128           # 8-bit unsigned


(gdb) p/d (short) 65535
$3 = -1            # 16-bit signed


(gdb) p/u (short) 65535
$4 = 65535         # 16-bit unsigned


(gdb) p/d (int) 0xffffffff
$5 = -1           # 32-bit signed
```

### Common uses and information
 * Use `set print pretty on` for nice structs/arrays
 * `p *ptr@10` $\rightarrow$ print 10 elements starting from `ptr` *(array-style)* * Works wee with symbolic expressions, structs, arrays * Can be formatted *(hex, decimal, char, etc.)* * Temporary, not shown on next stop unless re-typed
