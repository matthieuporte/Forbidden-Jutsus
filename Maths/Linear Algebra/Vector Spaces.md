

Studying Vector spaces will allow us to notice general theorems that can be applied to many mathematical structures.

> _a vector space is a set whose elements, often called vectors, may be added together and multiplied ("scaled") by numbers called scalars._

---
### Definition

A $\mathbb{K}$-vector space is a non-empty set $E$ with:
- An internal law
$$
\begin{array}{rcl} 
& E \times E & \rightarrow & E \\
& (u,v) & \mapsto & u + v
\end{array}
$$
- An external law
$$
\begin{array}{rcl} 
& \mathbb{K} \times E & \rightarrow & E \\
& (\lambda,v) & \mapsto & \lambda \cdot v
\end{array}
$$

$\mathbb{K}$ is a set (often $\mathbb{C}$ or $\mathbb{R}$)


A vector space follows 8 laws :


1. $$\begin{flalign}
& u + v = v + u \quad(\forall (u,v) \in E) &
\end{flalign}$$
2. $$\begin{flalign}
& u + (v + w) = (u + v) + w \quad(\forall (u,v,w) \in E) &
\end{flalign}$$

3. $$\begin{flalign}
& 1 \cdot u = u \quad(\forall u\in E) &
\end{flalign}$$
4. $$\begin{flalign}
& \lambda \cdot (\mu \cdot u) = (\lambda \mu) \cdot u \quad(\forall \space\lambda,\mu \in \mathbb{K} ,u \in E) &
\end{flalign}$$
5. There exists a neutral element $0_E \in E$ so that $u + 0_E = u \space\space\space(\forall u \in E)$ <br><br>
6. All elements admit a symmetric $u'$ so that $u + u' = 0_E$. This element $u'$ is denoted $-u$
7. $$\begin{flalign}
& \lambda \cdot (v + u) = (\lambda \cdot v) + (\lambda \cdot u) \quad(\forall \space\lambda \in \mathbb{K} ,v,u \in E) &
\end{flalign}$$
8. $$\begin{flalign}
& (\lambda + \mu) \cdot u = (\lambda \cdot u) + (\mu \cdot u) \quad(\forall \space\lambda,\mu \in \mathbb{K} ,u \in E) &
\end{flalign}$$

The elements of $E$ are called <u>vectors</u>
The elements of $\mathbb{K}$ are called <u>scalars</u>
The neutral element $0_E$ is also called <u>the null vector</u>
The symmetrical $-u$ is also called <u>the opposite</u>
the internal composition law on $E$, denoted $+$, is the addition
the external composition law on $E$ is the multiplication by a scalar

>[!info] Note that :
>> $0_E$ is unique
> $-u$ is unique

>[!abstract]- In summary
>To make sure an object is a vector space you need to check:
>1. the internal law
2. the external law
3. the neutral element
4. it’s symmetrical
5. both laws together

---
### Vector Sub-Space

A sub space is very useful to prove that a set is a Vector space.

We will see that a vector sub-space is vector space.

**Definition :**

Let $E$ be a vector space, $F$ is a subspace if and only if

1. $0_E \in F$
2. $u + v \in F \space\space\space \forall (u,v) \in F²$
3. $\lambda \cdot u \in F \space\space\space \forall \lambda \in \mathbb{K},v \in F$

 >📌 check those three conditions to see if $F$ is in fact a vector subspace


---
### Linear combination

Let's consider a set of vectors \(v_1, v_2, \ldots, v_n\) in a vector space \(V\) and corresponding scalars \(c_1, c_2, \ldots, c_n\). The linear combination of these vectors with the given scalars is expressed as:

\[c_1v_1 + c_2v_2 + \ldots + c_nv_n\]

For example, in \(\mathbb{R}^2\), if we have vectors \(v_1 = \begin{bmatrix} 1 \\ 2 \end{bmatrix}\) and \(v_2 = \begin{bmatrix} 3 \\ 4 \end{bmatrix}\), and scalars \(c_1 = 2\) and \(c_2 = -1\), the linear combination would be:

\[2 \begin{bmatrix} 1 \\ 2 \end{bmatrix} - 1 \begin{bmatrix} 3 \\ 4 \end{bmatrix} = \begin{bmatrix} 2 \\ 4 \end{bmatrix} - \begin{bmatrix} 3 \\ 4 \end{bmatrix} = \begin{bmatrix} -1 \\ 0 \end{bmatrix}\]

Let $E$ be a vector space. Then $F$ is a vector sub space if and only if all linear combination of two element of $F$ also belongs to $F$.

>[!success] Intersection
>the intersection $\cap$ of two vector sub spaces is also a sub space

>[!failure] Union
> the union $\cup$ of two vector sub spaces is NOT a sub space

</aside>

---

### Sum of a Vector Sub-Space

Let $F$ and $G$ be two vectorial sub spaces of $E$

The sum of two vectorial sub spaces is also a vss, in fact, it is the smallest vss including both $F$ and $G$

$F$ and $G$ are in direct sum in $E$ if

- $F \cap G = \{0_E\}$
- $F + G = E$

We then denote $F \oplus G = E$

$F$ and $G$ are called additional sub-spaces


>[!tip] 
>$F$ and $G$ are additional sub-spaces in $E$ if and only if any element of $E$ is uniquely written as the sum of an element of $F$ and an element of $G$


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

### Basis

---

### Dimentions 