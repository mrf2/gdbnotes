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

### Common uses and information
 * Use `set print pretty on` for nice structs/arrays
 * `p *ptr@10` $\rightarrow$ print 10 elements starting from `ptr` *(array-style)* * Works wee with symbolic expressions, structs, arrays * Can be formatted *(hex, decimal, char, etc.)* * Temporary, not shown on next stop unless re-typed
