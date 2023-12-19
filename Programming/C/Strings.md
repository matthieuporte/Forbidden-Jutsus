
### Print into string

Simple print
[sprintf(3)](https://manpages.debian.org/stretch/manpages-dev/sprintf.3.en.html)

```c
char buffer[50]; 
sprintf(buffer, "My custom string");
```


Malloc and print
[asprintf(3)](https://manpages.debian.org/stretch/manpages-dev/asprintf.3.en.html)

```c
char *result;
int res = asprintf(&result, "The value is %d", 42);
free(result); 
```

---

### Copy string

Malloc and copy 
[strdup(3)](https://manpages.debian.org/bookworm/manpages-dev/strdup.3.en.html)

```c
const char *original = "Hello, World!";
// Malloc and duplicates the original string
char *duplicate = strdup(original); 
free(duplicate);
```

---

### Compare strings

[strcmp(3)](https://manpages.debian.org/testing/manpages-dev/strcmp.3.en.html)

```c
// str1 < str2 -> result < 0
// str1 == str2 -> result = 0
// str1 > str2 -> result > 0
int result = strcmp(str1, str2);
```
