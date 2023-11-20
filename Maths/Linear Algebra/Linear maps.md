

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


### Image and Kernel of a Linear map

Let $f : E \rightarrow F$ 

$$\begin{aligned}
& ker(f) = \{ x \in E : f(x) = 0\} \\ \\
& Im(f) = \{w \in F : w = f(x), x \in E\}
\end{aligned}$$


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