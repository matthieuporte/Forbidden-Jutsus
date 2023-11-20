

Let $E$ and $F$ be two $\mathbb{K}$-vector spaces

---

### DEFINITION

A map $f$ from $E$ to $F$ is a _**linear map**_ if :


$$
\begin{flalign}
& \text{1. } f(0_E) = 0_F \\ &
\text{2. } f(u + v) = f(u) + f(v), \forall u,v \in E \\ &
\text{3. } f(\lambda\cdot u) = \lambda \cdot f(u), \forall (u,\lambda) \in E*\mathbb{K} &
\end{flalign}
$$

>[!info] 
>The set of all linear maps from $E$ to $F$ is denoted $\mathcal{L}(E,F)$

---

### VOCABULARY 

**morphism** : Any linear map.

**endomorphism** : Linear map from $E$ to $E$. (denoted $\mathcal{L}(E)$) )

**isomorphism** : Linear map from $E$ to $F$ that is bijective.

**automorphism** : both an endomorphism and an isomorphism


>[!abstract]- Identity Linear Map
>> The Identity Linear Map, often simply called the identity map, is a linear transformation from a vector space to itself that leaves vectors unchanged. In other words, it is a linear operator that maps each vector to itself.
>> 
>> Let $V$ be a vector space. The identity linear map on $V$, denoted by $I_V$ or simply $I$, is defined as follows:
>>
>>For any vector $v$ in $V$, the image of $v$ under the identity linear map is itself:
>>
>>$I(v) = v$
>>
>>The identity linear map preserves vector addition and scalar multiplication, which are the defining properties of a linear transformation. Mathematically, this means that for any vectors $u$ and $v$ in $V$ and any scalar $c$:
>>
>>$I(u + v) = I(u) + I(v)$
>>
>>$I(cu) = cI(u)$
>>
>>This property makes the identity linear map an example of a linear transformation that doesn't alter the structure of the vector space—it acts as a kind of "do-nothing" transformation.

---

### Properties

#### Proposition 1
Let $E$ and $F$ two $\mathbb{K}$-vector spaces. if $f$ is a linear map from $E$ to $F$ then :

$$
f(0_E) = 0_F \text{ and } \forall u \in E, f(-u) = -f(u).
$$

#### Proposition 2
Let $E$ and $F$ two $\mathbb{K}$-vector spaces and $f$ a linear map from $E$ to $F$. $f$ is linear if and only if,

$$
\forall(u,v) \in E^2 \text{ and } \forall(\alpha,\beta) \in \mathbb{K}^2,
f(\alpha u + \beta v) = \alpha f(u) + \beta f(v).
$$

---

### Linear independence

A family (or set) of vectors is said to be linearly independent if no vector in the family can be written as a linear combination of the others. 

Let $E$ be a vector space and consider a family of vectors $\{\mathbf{e}_1, \mathbf{e}_2, \ldots, \mathbf{e}_n\}$ in $E$. This family is linearly independent if and only if:

$$ \begin{aligned}
& \forall (\lambda_1, \lambda_2, \ldots, \lambda_n) \in \mathbb{R}^n, \\
& \lambda_1 \mathbf{e}_1 + \lambda_2 \mathbf{e}_2 + \ldots + \lambda_n \mathbf{e}_n = \mathbf{0} \\ 
& \qquad \implies \lambda_1 = \lambda_2 = \ldots = \lambda_n = 0
\end{aligned}$$

Otherwise, they are linearly dependent. 

---

### Spanning family

A spanning family refers to a family (or set) of vectors that collectively span a vector space, meaning that any vector in the space can be expressed as a linear combination of vectors from this family. 

More formally, let $E$ be a vector space, and consider a family of vectors $\{\mathbf{e}_1, \mathbf{e}_2, \ldots, \mathbf{e}_n\}$ in $E$. This family is said to be a spanning family for $E$ if, for every vector $\mathbf{e}$ in $E$, there exist scalars $\lambda_1, \lambda_2, \ldots, \lambda_n$ such that:

$$
\lambda_1 \mathbf{e}_1 + \lambda_2 \mathbf{e}_2 + \ldots + \lambda_n \mathbf{e}_n = \mathbf{e}$$

In other words, any vector in $E$ can be represented as a linear combination of the vectors in the spanning family. The set of all possible linear combinations of vectors from the spanning family forms the entire vector space $E$. Then :

$$ 
\text{span}(\{\mathbf{e}_1, \mathbf{e}_2, \ldots, \mathbf{e}_n\}) = E $$

>[!tip]- Tips for verifying if a family is spanning
> 1) If the dimension of the space is $n$ over some field $F$.
>	Then, the set contains at least $n$ linearly independent vectors from $F^n$ must be a spanning set of that space.
> <br>
> 2) Solve the system. If you find a value for every $\lambda$ then it is spanning

---

### Image and Kernel of a Linear map


$Im(f) = {f(x); x ∈ E}$ 

$Im(f) = y ∈ F, ∃x ∈ E$ such that $y = f(x).$

$Ker(f) = {x ∈ E : f(x) = 0F }.$

**KERNEL JUTSU**

Let $f ∈ L(E, F).$ Then $f$ is injective if and only if

$$ Ker(f) = {0E}. $$

---

### Operations on linear maps


Let $L(E,F)$ be a $\mathbb{K}$-vector space

Let $E, F$ and $G$ three $\mathbb{K}$-vector spaces.

Let $f ∈ L(E, F)$ and $g ∈ L(F, G)$.

Then $g\circ f$ is a linear map from $E$ to $G$

---

### Rank nullity theorem

Let $f: E \to F$ be a linear map, then :

$$ \text{dim}(E) = \text{dim}(ker(f)) + \text{dim}(Im(f))  
$$