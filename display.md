# `display`
Automatically shows the value every time GDB stops (breakpoint, step, etc).

### Syntax:
```bash
display [/format] expression
```

### Examples:
```bash
display /5i $rip    # Shows 5 consecutive assembly instructions pointing by %rip register
display i           # Shows value of 'i' every stop
display /x i        # Shows value of 'i' in hexadecimal
display $eax        # Register tracking
```

### Common uses and information
 * Use `undisplay <n>` or `disable display <n>` to turn off
 * Use `info display` to list all active displays
 * Very useful for **debugging** ***loops*** or ***watching*** variabls change over time.

