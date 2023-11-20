
Not all differential equations can be easily solved, but there is some cases where the solutions can be expressed with the usual functions. We are going to study those cases in this chapter.


---

## TL;DR;

First order:

$$ S_0 = \{ t \to ke^{-\int \frac {b(t)} {a(t)}} ,k \in \mathbb{R} \} $$

$$ y_p = \int {\frac {c} {ay_0}} *y_0

$$

$$ S = \{ t \to y_p(t) + ke^{-\int \frac {b(t)} {a(t)}} ,k \in \mathbb{R} \} $$


---

## First order equations

A first order linear differential equation has the form :

$$ (E):\space\space\space\space\space ay'(t) + by(t) = c $$

where a,b and c are all functions defined on the interval $J \in \mathbb{R}$

To solve this equation you need to find an interval $I \subset J$ as big as possible (if possible $J$ as a whole) and all the real functions defined on it so that, $\forall t \in \mathbb{R}$ , the equality $(E)$ is verified.

$S$ is the set of function solutions of $(E)$ on the interval $I \subset J$

>[!info]
>To solve $(E)$ you need to
>1. Find the set 
>2. Find a specific solution $y_p$
>3. $S = \{y_p + y_0, y_0 \in (S_0)\}$


---

### Steps of resolution

Let’s consider a new equation $(E_0)$ (called homogeneous equation) obtained by canceling $c(t)$ in the right part of the equation.

$$ (E_0):\space\space\space\space\space ay'(t) + by(t) = 0 $$

We denote $(S_0)$ the set of solutions of $(E_0)$ on $I$. It cannot be empty since the null function is always a solution.

### Theorem :

_Let $y_p \in S$ a specific solution of $(E_0)$ in $I \subset J$. Let $y$ be a differentiable function on $I$. Then_

$$ y \in S \iff y - y_p \in S_0 $$

Therefore all solutions of $S$ are of the form $y = y_p + y_0$ with $y_0$ being a specific solution of $(E_0)$

We can now express the set $S$ like this

$$ S = \{y_p + y_0, y_0 \in (S_0)\} $$

---

### Solving $(E_0)$

#### Theorem :

_If there exists an interval $I$ on which $a$ and $b$ are continuous and $a$ does not cancel out, then the set of solutions on $(E_0)$ on $I$ is given by the following :_

$$ S_0 = \{ t \to ke^{-\int \frac {b(t)} {a(t)}} ,k \in \mathbb{R} \} $$

Where $\int \frac {b(t)} {a(t)}$ is a primitive of $\frac {b} {a}$

Now that we’ve got the set of solutions for $y_0$ we need to find a specific solution $y_p$ and we do so by using the :

---

### Variation of the constant

1. Get a non null solution $y_0$
    
2. We are looking for $y_p$ in the form $y_p = k(t)y_0(t)$
    
3. This gives us $y^{'}_p = k'(t)y_0(t) + k(t)y^{'}_0(t)$, we can now put back the two equations in $(E)$
    
    $$ ay^{'}_p + by_p = c \\ \iff ak'y_0 + aky^{'}_0 + bky_0 = c \\ \iff ak'y_0 + k(ay^{'}_0 + by_0) = c \\ \iff ak'y_0 = c \\ \iff k' = \frac {c} {ay_0} $$
    
4. We now look for an anti-derivative $k$ and we can now write : $y_p = \{ t \to k(t)y_0(t) \}$ which gives us :
    

$$ S = \{ t \to y_p(t) + ke^{-\int \frac {b(t)} {a(t)}} ,k \in \mathbb{R} \} $$

---

## Second order equations

A second order linear differential equation has the form :

$$ (E):\space\space\space\space\space ay''(t) + by'(t) + cy(t) = d $$

where a,b,c and d are all functions defined on the interval $J \in \mathbb{R}$

---

### Steps of resolution

Let’s consider a new equation $(E_0)$ (called homogeneous equation) obtained by canceling $c(t)$ in the right part of the equation.

$$ (E_0):\space\space\space\space\space ay''(t) + by'(t) + cy(t) = 0 $$

We denote $(S_0)$ the set of solutions of $(E_0)$ on $I$. It cannot be empty since the null function is always a solution.

>[!info]
> You will use the same steps as for the first order, but the steps in themselves will change a bit.

---

### Solving $(E_0)$

we associate to the homogeneous equation the characteristic equation :

$$ (C): \space\space\space\space ar^2 + br + c = 0 $$

We can now compute the discriminant $\Delta$

If $\Delta > 0$ then :

$$ S_0 = \{ t \to k1e^{{r_1}t} + k2e^{{r_2}t} ,(k1, k2) \in \mathbb{R}^2 \} $$

If $\Delta = 0$ then :

$$ S_0 = \{ t \to (k1 + k2t) e^{{r_1}t} ,(k1, k2) \in \mathbb{R}^2 \} $$

If $\Delta < 0$ then $(C)$ has got two conjugate roots : $r_1 = \alpha + i\beta$ and $r_2 = \alpha - i\beta$

$$ S_0 = \{ t \to (k1cos(\beta t) + k2sin(\beta t)) e^{\alpha t} ,(k1, k2) \in \mathbb{R} \} $$

First order in one line :

$$ S = \{ t \to \int {\frac {c} {ak_1e^{-\int \frac {b(t)} {a(t)}}}} *k_1e^{-\int \frac {b(t)} {a(t)}} + k_2e^{-\int \frac {b(t)} {a(t)}} ,(k_1,k_2) \in \mathbb{R}^2 \} $$