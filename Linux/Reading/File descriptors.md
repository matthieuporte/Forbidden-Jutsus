
A file descriptor is a non-negative integer that uniquely identifies an open file within a process. 

File descriptors are used to represent input and output resources, such as files, pipes, sockets, and other types of communication channels.

There are three standard file descriptors that are automatically opened for each new process:

1. **Standard Input (stdin):** (int value is `0`) 
It is the default input stream, typically connected to the keyboard.

3. **Standard Output (stdout):** (int value is `1`) 
It is the default output stream, where the program writes its regular output.

4. **Standard Error (stderr):**(int value is `2`) 
It is used for error messages or diagnostics, separate from regular output.

When a process starts, these file descriptors are already open, and they can be used to read input and write output without explicitly opening files.

Beyond the standard file descriptors, when a program opens a file or a communication channel, the operating system assigns a unique file descriptor to that resource. These file descriptors can be manipulated, duplicated, and redirected within a program using various system calls, such as `open`, `read`, `write`, `close`, `dup`, and `dup2`.


### Why is it an int ??

The decision to represent file descriptors as integers offered simplicity, efficiency, and compatibility with existing programming languages and hardware architectures.

REMEMBER : The file in itself is a real file, the int is just a pointer to it that's it !