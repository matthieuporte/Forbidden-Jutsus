

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

<br>

A vector space follows 8 laws :


1. $u + v = v + u \space\space\space(\forall (u,v) \in E)$
3. $u + (v + w) = (u + v) + w \space\space\space(\forall (u,v,w) \in E)$
4. $1 \cdot u = u \space\space\space(\forall u\in E)$
5. $\lambda \cdot (\mu \cdot u) = (\lambda \mu) \cdot u \space\space\space(\forall \space\lambda,\mu \in \mathbb{K} ,u \in E)$
6. There exists a neutral element $0_E \in E$ so that $u + 0_E = u \space\space\space(\forall u \in E)$
7. All elements admit a symmetric $u'$ so that $u + u' = 0_E$. This element $u'$ is denoted $-u$
8. $\lambda \cdot (v + u) = (\lambda \cdot v) + (\lambda \cdot u) \space\space\space(\forall \space\lambda \in \mathbb{K} ,v,u \in E)$
9. $(\lambda + \mu) \cdot u = (\lambda \cdot u) + (\mu \cdot u) \space\space\space(\forall \space\lambda,\mu \in \mathbb{K} ,u \in E)$

The elements of $E$ are called <u>vectors</u>
The elements of $\mathbb{K}$ are called <u>scalars</u>
The neutral element $0_E$ is also called <u>the null vector</u>
The symmetrical $-u$ is also called <u>the opposite</u>
the internal composition law on $E$, denoted $+$, is the addition
the external composition law on $E$ is the multiplication by a scalar

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