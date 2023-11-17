
> [!tip] 
0 = false, anything else is true

### type sizes

|Type Name|32–bit Size|64–bit Size|
|:--|:--|:--|
|char|1 byte|1 byte|
|short|2 bytes|2 bytes|
|int|4 bytes|4 bytes|
|long|4 bytes|8 bytes|
|long long|8 bytes|8 bytes|

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