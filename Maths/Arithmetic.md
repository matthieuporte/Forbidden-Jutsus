
### Notation
---

$a | b$ means a divides b

$b \in a\mathbb{Z}$ means b is a multiple of a

### Euclidean division and gcd
---

Euclidean division: $a = b*q + r$

- Euclidean Lemma: $pgcd(a,b) = pgcd(b,r)$
    
    $pgcd(a,b) = pgcd(b, a - qb)$
    

### Congruences
---

$a \equiv b \pmod n \implies \exists k \in\mathbb{N} , a= b + kn$

also $a \equiv b [n]$

$a \equiv b [n] \text { and } c \equiv d [n] \implies a+c \equiv b + d [n]$

$a \equiv b [n] \text { and } c \equiv d [n] \implies ac \equiv bd [n]$

$a \equiv b [n], \forall m \in \mathbb{N}, a^m \equiv b^m [n]$

>[!info] Careful !
>We denote $D(a)$ the set of divisors of $a$ and $a\mathbb{Z}$ the set of multiples of $a$


### Bezout
---

Bezout Theorem :

let (a,b) be two integers, then $\exists (u_1,u_2) \in \mathbb{Z}^2$ so that

$au_1 + b u_2 = gcd (a,b)$

Bezout Corollary :

$\text {if }d|a \text { and } d|b \text { then } d|gcd(a,b)$

Gauss Lemma :

$\text {if }a|bc \text { and } gcd(a,b) = 1 \implies a|c$

_to solve ax + by = d equations you need to do the Euclid algorithm and “go back up”_


### Little Fermat Theorem
---

Let p be a prime number,

$$ p | {p \choose k} \text { and } {p \choose k} \equiv 0 [n] $$

$$ n^p \equiv n[p] $$

if $p \nmid n$ then

$$ n^{p-1} \equiv 1[p] $$