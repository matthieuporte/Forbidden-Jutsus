
pwndbg 
format string

```c
printf("%5$i")
```

%n in c

```shell
python -c 'print("%x."*10)' | ./challenge
```

GOT : global offset table

### Challenge

compile with
```shell
gcc -m32 -no-pie -Wl,-z,norelro challenge.c -o challenge
```

```c
#include <stdio.h>
#include <stdlib.h>

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