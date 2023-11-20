
## Derivatives

|Function|Derivative|
|---|---|
|$f * g$|$f’ * g + f * g’$|
|$f / g$|$(f'_g - f_g' )/g²$|
|$g ◦ f$|$f’ * g’ ◦ f$|
|$1 / u$|$- u’ / u²$|
|$u^{\alpha}$|$xu’u^{\alpha-1}$|
|$√u$|$u’/2√u$|
|$ln(u)$|$u’/u$|
|$e^u$|$u’e^u$|
|$cos(u)$|$-u’ sin(u)$|
|$sin(u)$|$u’ cos(u)$|

## Anti-Derivatives

|Function|Primitive|
|---|---|
|$1/x^n$|$-1/(n-1)x^{n-1}$|
|$u’u$|$u²/2$|
|$u’u^n$|$u^{n+1}/n+1$|
|$u’/√u$|$2√u$|
|$u’/u^n$|$-1/(n-1)u^{n-1}$|
|$u’/u$|$ln(|
|$u’e^u$|$e^u$|
|$u’ cos(u)$|$sin(u)$|
|$u’ sin(u)$|$-cos(u)$|

## Integration :

---

For a pair $(a,b) \in \mathbb{R}^2$ such that $a \le b$ and a continuous function $f : [a,b] \to \mathbb{R}$, we define the integral :

$$ I = \int_a^b f(t) \space dt $$

Furthermore, for any $x \in [a,b]$, we can define the function :

$$ F : x \to \int_a^x f(t)\space dt $$

Then f is differentiable and satisfies to $F' = f$, that is, $F$ is a primitive of the function $f$. For any other primitive $F_2$, we have :

$$ F_2(x) - F_2(a) = F(x) -\underbrace {F(a)}_{\text{= 0}} = F(x) $$

This leads to :

$$ \int_a^b f(t)\space dt = F(b) -F(a) = F_2(b) - F_2(a) $$

Thus the most common way of computing an integral, that you have seen before, is to find a primitive of $f$ and to compute $F(b) - F(a)$.

However, when no formal primitive is available, there are two other methods: the **integration by parts** and the **substitution.** These two methods enable one to transform the initial integral into another one, for which we can expect to find a primitive.

## Integration by parts

### Theorem :

$$ \int u'v + \int uv' = uv + c

$$

### Proof :

$(uv)' = u'v + uv'$

$\int (uv)' = \int u'v + \int uv'$

$\int u'v + \int uv' = uv + c$

## Integration by substitution

$tan (x)$ $= sin (x) / cos (x)$

$Sec (x) = 1 / cos(x)$

$Cosec (x) = 1 / sin(x)$

$$ Cot (x) = \frac 1 {tan (x)} = \frac {cos (x)}{sin(x)} $$

>[!tip] Theorems : 
>$Sec^2(x) = 1 + tan^2(x)$
>$(tan(x))' = sec^2(x) = 1 / cos^2(x)$
