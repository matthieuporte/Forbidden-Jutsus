
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

---

## How to Debug

*see proper errors (memory leaks and lines)*
```c
//Makefile 
CFLAGS = -g -fsanitize=address 
LDFLAGS = -fsanitize=address
```

---

### GDB

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

---

### Change struct not in place and update pointer

sometimes I want to change some struct so much that I'd rather create a new one, free the old one and change the pointer. The problem is that if you free the old pointer you can't update it anymore. The solution is to use **double pointers** like this :
```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

struct MyStruct {
    int data;
};

void updateStruct(struct MyStruct** oldStructPtr) {
    // Allocate memory for the new struct
    struct MyStruct* newStruct = malloc(sizeof(struct MyStruct));
    
    // Set values in the new struct
    newStruct->data = 42;
    
    // Free the memory allocated for the old struct
    free(*oldStructPtr);
    
    // Update the pointer to point to the new struct
    *oldStructPtr = newStruct;
}

int main() {
    // Allocate memory for the old struct
    struct MyStruct* oldStruct = malloc(sizeof(struct MyStruct));
    
    // Set values in the old struct
    oldStruct->data = 0;  
    
    // Call the function to update the struct
    updateStruct(&oldStruct);
    
    // Now 'oldStruct' points to the newly allocated memory
    // You can access and modify the members of the struct through 'oldStruct'
    printf("Data in the updated struct: %d\n", oldStruct->data);
    free(oldStruct);
    return 0;
}
```

In this example, the `updateStruct` function takes a pointer to a pointer (`struct MyStruct** oldStructPtr`) as an argument. This allows it to modify the original pointer, and the changes are reflected in the `main` function.

The important point to remember is that you must update the value, not the pointer.
```c
*oldStructPtr = newStruct; // updates the value pointed by the pointer
oldStructPtr = &newStruct; // change the pointer /!\ only in this scope
```

---

### How to use ```.``` vs ```->```

- Use **`.`** when you have an instance of the struct.
- Use `->` when you have a pointer to the struct.

the `->` dereferences while the `.` only access the value

---

### Are malloc checks worth it ?

In real code yes, but it's very rarely useful. anyway here's how to do it :
```c
int *arr = malloc(10 * sizeof(int)); 

if (arr == NULL) { 
	printf("Memory allocation failed!\n");
	return 1; 
}
```

