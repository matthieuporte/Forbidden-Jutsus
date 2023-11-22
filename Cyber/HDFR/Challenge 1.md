
pwndbg 
format string

```c
printf("%5$i")
```

GOT : global offset table

### Challenge

```c
#include <stdio.h>
#include <stdlib.h>

// gcc -m32 -no-pie -Wl,-z,norelro challenge.c -o challenge

void flag(){
    system("/bin/bash -p");
}

int main() {
    char buffer[512];
    fgets(buffer, 512, stdin);

    printf(buffer);
    printf("\n");

    exit(-1);
}
```