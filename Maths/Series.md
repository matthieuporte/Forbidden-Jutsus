

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

- $$(U_n) \textit { is bounded } \iff \exists M \in \mathbb{R} : \forall n \in \mathbb{N} (|(U_n)| \leq M )$$
    
    $$ [\impliedby] \space\space\space (|(U_n)| \leq M ) \\\implies (-M \leq (U_n) \leq M ) \implies (U_n) \textit { is bounded } $$
    
    $$ [\implies] \space\space\space (U_n) \textit { is bounded } \\\implies \forall n \in \mathbb{N}, \exists (m,K) \in \mathbb{R}^2 : m \leq (U_n) \leq K $$$$ K \leq |K| \textit { and } -|m| \leq m \implies -|m| \leq (U_n) \leq |K| $$$$M = max(|m|,|K|) \implies |K| \leq M \textit { and } -M \leq -|m| $$ $$implies -M \leq (U_n) \leq M \implies (|(U_n)| \leq M ) $$
    
- $(U_n) \textit { converges} \implies (U_n) \textit { is bounded}$
    
    $(U_n)$ converges means that
    
    $$\forall \epsilon > 0, \exists n_\epsilon \in \mathbb{N} : \forall n \in \mathbb{N} (n \geq n_\epsilon \implies |(U_n) - l| < \epsilon )$$
    
    The property is true for all $\epsilon > 0$ so it is true for 1 for instance.
    
    This means that there is a rank _n_ where $|(U_n) - l| < 1$
    
    $$\implies |(U_n)| = |(U_n) - l + l| \leq |(U_n) - l| + |l| < 1 + |l|$$
    
    This means that $(U_n)$ is bounded after the rank _n_
    
    Let $M = max(u_0,u_1,...,(U_{n-1}),1+|l|)$
    
    Then for $n \in \mathbb{N}, |(U_n)| \leq M$. The sequence is hence bounded.
    
- $\textit {Sandwich or squeeze theorem}$
    
    $$\text {Let }(U_n)\text {,} (V_n)\text { and } (W_n)\text { three real sequences such that :}$$
    
    $\forall n \in \mathbb{N}, (U_n) \leq (V_n) \leq (W_n)$
    
    $$\text {If }(U_n) \text{ and } (W_n)\text { converges to the same limit } \textit {l} \implies (V_n) \text{ converges to } \textit {l}$$
    
	
> [!tip] 
> $|U_n - l| < \epsilon \iff -\epsilon < U_n - l < \epsilon \iff -\epsilon + l< U_n < \epsilon + l$