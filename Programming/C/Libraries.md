In C, you can include a library with the include directive like so.

```c
#include <library.h>
```

When you use the include directive in your C program, the compiler will look into the **include directory**. This folder is by default "/usr/local/include" in a Linux or MacOs environment.

That means that if you include, for example, the SDL library like so:

```c
#include <SDL2/SDL.h>
```

The compiler will look for the file located at "usr/local/include/SDL2/SDL.h".

Those files are header files, and their role is to declare the function that you will be using later in your program. The declaration contains the arguments of the function, their type and what the function is returning. But the header files only *declare* and do not *define* the function. That is where the **lib directory** comes in. This directory contains the actual compiled implementations of the functions declared in the header file. This folder is by default "/usr/local/lib" in a Linux or MacOs environment.

To specify which library you are using, you typically want to add this line in your Makefile:

```c
cLDLIBS = -lSDL2 -lSDL2_image -lm
```

During the compilation process, the compiler will link the compiled library files specified by the "-l" command (just above) to your program. This will allow you to use every functions that are in the header files that you included !

In summary, when you include a library in your source code, you typically include header files that declare the functions provided by the library. The actual implementations of those functions are found in the compiled library files, which are linked during the compilation process.