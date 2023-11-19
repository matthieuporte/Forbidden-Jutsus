

## Sequences 

### Limit of a sequence

---

we say that $(U_n)$ converges to $l \in \mathbb{R}$ if

$$ \forall \epsilon > 0, \exists n_\epsilon \in \mathbb{N} : \forall n \in \mathbb{N} (n \geq n_\epsilon \implies |U_n - l| < \epsilon ) $$

indeterminate limits

$+ \infty - \infty;0\times\infty;\frac{\infty}{\infty};\frac{0}{0}$

### **Big _O_ notation**

---

we study the limit of $\frac {U_n} {V_n}$

$\theta$ → $\infty$ (the limit of $U_n$ is greater)

o → 0 (the limit of $V_n$ is greater)

O → anything else

~ → 1 (the limits of both are equivalent)

### Sequences Proofs

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

#### Sandwich/squeeze theorem
Let $(U_n)$ , $(V_n)$ and $(W_n)$ three real sequences such that :

$$ \begin{aligned} 
& \forall n \in \mathbb{N}, (U_n) \leq (V_n) \leq (W_n) \\ 
& \text {If }(U_n) \text{ and } (W_n)\text { converges to the same limit } \textit {l} \\ 
& \qquad \implies (V_n) \text{ converges to } \textit {l} 
\end{aligned} $$

> [!tip] 
> $|U_n - l| < \epsilon \iff -\epsilon < U_n - l < \epsilon \iff -\epsilon + l< U_n < \epsilon + l$