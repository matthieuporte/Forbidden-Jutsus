
### Print into string

Simple print
[sprintf(3)](https://manpages.debian.org/stretch/manpages-dev/sprintf.3.en.html)

Malloc and print
[asprintf(3)](https://manpages.debian.org/stretch/manpages-dev/asprintf.3.en.html)

```c
char *result;
int res = asprintf(&result, "The value is %d", 42);
```

---

### Copy string

Malloc and copy
[strdup(3)](https://manpages.debian.org/bookworm/manpages-dev/strdup.3.en.html)

```c
const char *original = "Hello, World!";
char *duplicate; // Malloc and duplicates the original string
```

---

### Compare strings

[strcmp(3)](https://manpages.debian.org/testing/manpages-dev/strcmp.3.en.html)

```c
// the int indicates which is greater
int result = strcmp(str1, str2);
```
