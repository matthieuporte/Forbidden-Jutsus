
> [!tip] 
0 = false, anything else is true

### Printf

| size_t | %zu |
| --- | --- |
| char | %c |
| string | %s |
| unsigned long | %lu |
| long | %l |
| int | %d |
| unsigned int | %u |
| hexa | %x (%X for caps) |
| floating point (double) | %f |
| double floating point | %lf |
| scientific notation | %e |
| shorter between scientific and floating point | %g |
| pointer | %p |
| 5 0 before number | %05i |



## How to Debug

*see proper errors (memory leaks and lines)*
```c
//Makefile 
CFLAGS = -g -fsanitize=address 
LDFLAGS = -fsanitize=address
```

### GDB
---
`gdb ./execfile` : launch gdb
`ctrl + x` then `a` / `tab` : get in visual mode
`start` : start the program
`n` : go to the next line
`s` : next step of the program
`display variable` : will show the variable at every step
`print varible` : will show the variable once
`b(line number)` : sets a breakpoint
`run` : go to the next breakpoint / the end of the program
`ctrl + l` : fix the interface if it is buggy
`q` : leave gdb