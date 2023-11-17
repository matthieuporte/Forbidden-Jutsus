
### Techniques to code golf in C

---

Declare **```void```** functions if no **```return```** is expected

---

Certain compilers, such as GCC, allow you to omit basic `#include`

---
you can use operator precedence to save parenthesis.  For example, 
```c
(x+y)*2
```

can become 

```c 
x+y<<1
```

---
Define parameters instead of variables. 

  ```c
  f(x){int y=x+1;...}
  ```
   instead of 
   ```c
   f(x,y){y=x+1;...}
   ```
---
If you can, try to replace 

  ```c
  for(int i=0;i<n;i++){...}
  ```
   with 
   ```c
   for(int i=n;i--;){...}
   ```
---
Any `while` can be changed into a `for` of the same length:

```c
while(*p++)
for(;*p++;)
```
---

`i[array]` desugars into `*(i+array)`, and since `+` is commutative for `pointer+integer` too, it is equivalent to `*(array+i)` and therefore `array[i]`.

---

 Use `*a` instead of `a[0]` for accessing the first element of an array.

---
printing something by a condition can be done with `?:`, `&&` or `||`:

```c
cond&&printf("%d\n",n);
cond||printf("%d\n",n);
cond?:printf("%d\n",n);
```
---
The comma operator can be used to execute multiple expressions in a single block while avoiding braces:

```c
main(){
int i = 0;
int j = 1;
if(1)
	i=j,j+=1,printf("%d %d\n",i,j); // multiple statements are all executed
else
	printf("failed\n");
}
```
---
 Instead of >= and <= you can simply use integer division (/) when the compared values are above zero, which saves one character. For example:

```c
putchar(c/32&&126/c?c:46); //Prints the character, but if it is unprintable print "."
```

Which is of course still shrinkable, using for example just > and ^ (a smart way to avoid writing && or || in some cases).

```c
putchar(c>31^c>126?c:46);
```

The integer division trick is for example useful to decide whether a number is less than 100, as this saves a character:

```c
a<100 vs 99/a
```

This is also good in cases when higher precedence is needed.