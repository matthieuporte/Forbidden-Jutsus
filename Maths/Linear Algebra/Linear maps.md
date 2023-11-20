
#WIP

Let $E$ and $F$ be two $\mathbb{K}$-vector spaces

**DEFINITION**

A map $f$ from $E$ to $F$ is a _**linear map**_ if :

- $f(0_E) = 0_F$
- $f(u + v) = f(u) + f(v), \forall u,v \in E$
- $f(\lambda\cdot u) = \lambda \cdot f(u), \forall (u,\lambda) \in E*\mathbb{K}$

<aside> 📖 The set of all linear maps from $E$ to $F$ is denoted $\mathcal{L}(E,F)$

</aside>

**********VOCABULARY**********

**morphism** : Any linear map.

**endomorphism** : Linear map from $E$ to $E$$\mathcal{L}(E,E)$. (denoted $\mathcal{L}(E)$) )

**isomorphism** : Linear map from $E$ to $F$ that is bijective.

**automorphism** : both an endomorphism and an isomorphism


### Identity Linear Map


Dans le contexte que vous avez donné, "idE(u)" représente l'image de l'élément \(u\) par l'identité de l'espace vectoriel \(E\). L'identité d'un espace vectoriel est l'application linéaire qui envoie chaque vecteur sur lui-même.

Formellement, si \(E\) est un espace vectoriel sur un corps \(K\), alors l'identité de \(E\), notée \(id_E\), est définie comme suit :

\[id_E : E \rightarrow E\]

\[id_E(u) = u \quad \text{pour tout } u \in E\]

Ainsi, \(id_E(u)\) est simplement le vecteur \(u\) lui-même. Cela signifie que pour tout \(u \in E\), l'application \(f(-u) + f(u) + u\) est équivalente à l'application de l'identité sur \(u\).

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