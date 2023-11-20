

## Sequences 

---

### Limit of a sequence


we say that $(U_n)$ converges to $l \in \mathbb{R}$ if

$$
\forall \epsilon > 0, \exists n_\epsilon \in \mathbb{N} : \forall n \in \mathbb{N} (n \geq n_\epsilon \implies |U_n - l| < \epsilon ) $$

indeterminate limits

$+ \infty - \infty;0\times\infty;\frac{\infty}{\infty};\frac{0}{0}$


---

### Big _O_ notation


we study the limit of $\frac {U_n} {V_n}$

$\theta$ → $\infty$ (the limit of $U_n$ is greater)

o → 0 (the limit of $V_n$ is greater)

O → anything else

~ → 1 (the limits of both are equivalent)

---



## Series
  
A numerical series is the sum of the terms of a sequence.

--- 

### Nature of a Series (CVG/DVG)

Definition 1 : Let $(U_n)_{n \in \mathbb{N}}$ a sequence of real numbers, we call series of general term $U_k$ and denote $\sum{U_k}$ the sequence of partial sums $(S_n)_{n\in\mathbb{N}}$ where for any integer $n \in \mathbb{N}$,

$S_n = \sum_{k=0}^{n} U_k$

### Geometric series

Let $q \in \R^*$ and let us consider the series $\sum q^k$ we have $\forall n \in \N$ :

$S_n = \sum q^k$. $\frac{1-q^{n+1}}{1-q}$ if q ≠ 0

$-1 < q < 1 \iff S_n$ CVG, otherwise $S_n$ DVG.

We say that $\sum U_k$ CVG (converges) iff $(S_n)_{n\in\N}$ CVG

Proposition 1 : Let $\sum U_k$ and $\sum V_k$ two series and let $\lambda \in \R$, we have :

1. if $\sum U_k$ CVG and $\sum V_k$ CVG, then $\sum (U_k + V_k)$ CVG
    
2. if $\sum U_k$ CVG, then $\sum \lambda U_k$ CVG
    
3. if $\sum U_k$ CVG and $\sum V_k$ DVG, then $\sum (U_k + V_k)$ DVG

### Convergence necessary condition

Let $(U_k)_{k\in\N}$ a seq. We have :

$$ \sum {U_k} \text{ CVG} \implies (\lim_{k \to +\infty} U_k = 0) $$

### Positive Term series

$\sum U_k$ is a PTS if $\forall k \in \N, U_k \ge 0$

Proposition : Let $\sum U_k$ and $\sum V_k$ two series such that : $\forall k \in \N, 0 \le U_k \le V_k$, Then :

1. if $\sum V_k$ CVG, then $\sum U_k$ CVG
    
2. if $\sum U_k$ DVG, then $\sum V_k$ DVG
    

### Riemann series

We call Riemann series any series of general term $\frac{1}{n^\alpha}$ where $\alpha \in \R$

### Riemann theorem

Let $\alpha \in \R$, then :

$$ \sum {\frac{1}{n^\alpha}} \text{ CVG} \iff \alpha > 1 $$

### Comparaison criteria

>[!abstract]- Reminder on landau comparators
>$$ 
> f(x) = o(g(x)) \implies \lim_{x\to x_0}\frac {f(x)}{g(x)} = 0 $$
>
> $$ 
> f(x) = O(g(x)) \implies \frac {f(x)}{g(x)} \text{ is bounded} $$
>
> $$ 
> f(x) \sim g(x) \implies \lim_{x\to x_0}\frac {f(x)}{g(x)} = 1 $$

Proposition : Let $\sum U_n$ and $\sum V_n$ two PTS

1. If $U_n \sim_{+\infty} V_n$ then $\sum U_n$ and $\sum V_n$ are of same nature
    
2. if $U_n = o(V_n)$ then if $\sum V_n$ CVG then $\sum U_n$ CVG
    

### Riemann’s rule

Let $(U_n)$ a positive numerical sequence

$$ \exists \alpha > 1, \lim_{n \to +\infty} n^\alpha \times U_n = 0 \implies \sum U_n \text{ CVG} $$

### D’alembert’s rule

Let $(U_n)$ a strictly positive sequence such that :

$$ \lim_{n \to +\infty}\frac{U_{n+1}}{U_n} = l,\space l \in \R_+ \cup \{+\infty\} $$

Then :

$l < 1 \implies \sum U_n$ CVG

$l > 1 \implies \sum U_n$ DVG

$l = 1 \implies$?

### Cauchy’s rule

Let $(U_n)$ a strictly positive sequence such that :

$$ \lim_{n \to +\infty}\sqrt[n]{U_n} = l,\space l \in \R_+ \cup \{+\infty\} $$

Then :

$l < 1 \implies \sum U_n$ CVG

$l > 1 \implies \sum U_n$ DVG

$l = 1 \implies$?

### Alternating Series

$\sum U_n$ is an alternating series if there exists a positive sequence $(a_n)$ such that :

$\forall n \in \N, U_n = (-1)^n a_n$

#### Alternating series special criteria (ASSC)/ Leibniz thm

Theorem : Let $(U_n)$ be an alternating sequence such that :

1. $\lim_{n \to +\infty} U_n = 0$
    
2. $(|U_n|)_{n \in \N}$ is $\searrow$
    

Then : $\sum U_n$ CVG

Proposition : Let $\alpha \in \R, \sum{\frac{(-1)^n}{n^\alpha}}$ CVG $\implies \alpha > 0$

#### Absolute convergence

$\sum U_n$ is converging absolutely if the series $\sum |U_n|$ CVG

if only $\sum U_n$ CVG then it is called a semi-converging series

Theorem : if a series is absolutely converging then it is CVG

### Power Series

---

Let $x \in \R$, we call power series any series of general term $U_n(x) = a_n \times x^n$

Remarks : if $x = 0$, any power series if CVG.

#### Convergence radius

Let $(a_n) \in \R^{\N}$, $\sum a_n x$

#WIP 

$$
\sum^{+ \infty}_{n = 0} x^n = \frac{1}{1-x}
$$

$$
\sum^{+ \infty}_{n = 0} \frac{x^n}{n!} = e^x
$$


## Sequences Proofs

--- 

#### $$(U_n) \textit { is bounded } \iff \exists M \in \mathbb{R} : \forall n \in \mathbb{N} (|(U_n)| \leq M )$$


$$ \begin{flalign} 
& [\impliedby] \space\space\space (|(U_n)| \leq M ) \\&
\qquad \implies (-M \leq (U_n) \leq M ) \\&
\qquad \qquad \implies (U_n) \textit { is bounded } &
\end{flalign} $$

$$ \begin{flalign} 
& [\implies] \space\space\space (U_n) \textit { is bounded } \\ &
\qquad \implies \forall n \in \mathbb{N}, \exists (m,K) \in \mathbb{R}^2 : m \leq (U_n) \leq K &
\end{flalign} $$

$$ \begin{flalign} 
& K \leq |K| \textit { and } -|m| \leq m \\ &
\qquad \implies -|m| \leq (U_n) \leq |K| &
\end{flalign} $$

$$ \begin{flalign} 
& M = max(|m|,|K|) \\ &
\qquad \implies |K| \leq M \textit { and } -M \leq -|m| \\ &
\qquad \implies  -M \leq (U_n) \leq M \\ &
\qquad \implies (|(U_n)| \leq M ) &
\end{flalign} $$

---

#### $(U_n)$ converges $\implies (U_n)$ is bounded

$(U_n)$ converges means that

$$ \begin{aligned}
& \forall \epsilon > 0, \exists n_\epsilon \in \mathbb{N} : \forall n \in \mathbb{N} (n \geq n_\epsilon \\
& \qquad \implies |(U_n) - l| < \epsilon )
\end{aligned}$$

The property is true for all $\epsilon > 0$ so it is true for 1 for instance.

This means that there is a rank _n_ where 
$$ \begin{aligned}
& |(U_n) - l| < 1 \\
& \qquad \implies |(U_n)| = |(U_n) - l + l| \leq |(U_n) - l| + |l| < 1 + |l|
\end{aligned}$$

This means that $(U_n)$ is bounded after the rank _n_

$$\begin{flalign}
& \text{Let } M = max(u_0,u_1,...,(U_{n-1}),1+|l|) &
\end{flalign}$$

Then for $n \in \mathbb{N}, |(U_n)| \leq M$. The sequence is hence bounded.   

---

#### Sandwich/squeeze theorem
Let $(U_n)$ , $(V_n)$ and $(W_n)$ three real sequences such that :

$$ \begin{aligned} 
& \forall n \in \mathbb{N}, (U_n) \leq (V_n) \leq (W_n) \\ 
& \text {If }(U_n) \text{ and } (W_n)\text { converges to the same limit } \textit {l} \\ 
& \qquad \implies (V_n) \text{ converges to } \textit {l} 
\end{aligned} $$

> [!tip] 
> $|U_n - l| < \epsilon \iff -\epsilon < U_n - l < \epsilon \iff -\epsilon + l< U_n < \epsilon + l$

---