
### Definitions
>[!abstract]- Transpose
>>The transpose $A^T$ of a matrix $A$ can be obtained by reflecting the elements along its main diagonal. Repeating the process on the transposed matrix returns the elements to their original position.
>>
>> ![[200px-Matrix_transpose.gif]]


>[!abstract]- Inverse
>>The inverse of a matrix is another matrix that, when multiplied by the given matrix, yields the multiplicative identity. For a matrix $A$, its inverse is $A^{-1}$. And 
>>$A \cdot A^{-1} = I$

>[!abstract]- Trace
>>The trace of a square matrix $A$, denoted $tr(A)$, is defined to be **the sum of elements on the main diagonal** (from the upper left to the lower right) of $A$. The trace is only defined for a square matrix $(n \times n)$.

>[!abstract]- Determinant
>> The **determinant** is a scalar value that is a function of the entries of a square matrix. It is nonzero if and only if the matrix is invertible and the linear map represented by the matrix is an isomorphism.
>> 
>> It is denoted $det(A)$

>[!abstract]- Rank
>> The rank of a matrix $A$ is the dimension of the vector space generated (or spanned) by its columns. This corresponds to the maximal number of linearly independent columns of A.
>>
>>It is denoted $rank(A)$


<br>

---

### Product of matrices

>[!danger] 
>L**[CL]**C number of **column** on the **left** must **equal** the number of **row** on the **right**



- Matrix multiplication #WIP 

---

### Notations


$\mathcal{M}_n(\mathbb{K})$ is the vector space of square matrix of order n with coefficients in $\mathbb{K}$

$0_{\mathcal{M}_n(\mathbb{K})}$ is the null matrix

$I_n$ is the identity matrix of dimension $(n \times n)$

---

### Inverse of a matrix


[Youtube video that explains kramer's method](https://youtu.be/Fg7_mv3izR0?si=TzhiXIz_DMDNlLKN)

>[!abstract] Definition
>Let $A \in \mathcal{M}_n(\mathbb{K})$. $A$ is invertible if there exists a matrix $A \in \mathcal{M}_n(\mathbb{K})$ such that :
>
>$$AB = BA = I_n$$

>[!info] proposition
>Let $A \in \mathcal{M}_n(\mathbb{K})$. A is invertible iff $det(A) \neq 0$. Furthermore : 
>
>$$det(A^{-1}) = \frac{1}{det(A)}$$

⚠ Only square matrices are invertible !

---

### Transition Matrix


The transition matrix allows us to change the basis.

- If all the **columns** of the transition matrix are **linearly independent**, then $f$ is **injective**
- If all the **columns** of the transition matrix make out a **spanning family**, then $f$ is **surjective**
- If all the **columns** of the transition matrix make out a **basis**, then $f$ is **bijective**

#### Rank of a Matrix

$$\text{Rank a} = \text{rank f} = dim(Im f)$$

---

### Change of basis

#wip

---

### Determinant of a square matrix


The determinant is a scalar associated with a matrix

The determinant of the matrix $A = \begin{pmatrix} a_{1,1} & a_{1,2} \\ a_{2,1} & a_{2,2} \end{pmatrix} \in \mathcal{M}_2(\mathbb{K})$, denoted $det(A)$ is the scalar defined by :

$$ det(A) = \begin{vmatrix}  
a_{11} & a_{12} \\ a_{21} & a_{22} \\ \end{vmatrix} = a_{11}a_{22} - a_{21}a_{12} $$

The determinant of the matrix $A = \begin{pmatrix} a_{1,1} & a_{1,2} & a_{1,3} \\ a_{2,1} & a_{2,2} & a_{2,3} \\ a_{3,1} & a_{3,2} & a_{3,3}  \end{pmatrix} \in \mathcal{M}_3(\mathbb{K})$, denoted $det(A)$ is the scalar defined by :

$$ det(A) = \begin{vmatrix}

a_{1,1} & a_{1,2} & a_{1,3} \\

a_{2,1} & a_{2,2} & a_{2,3} \\ a_{3,1} & a_{3,2} & a_{3,3} \end{vmatrix} = a_{11} \begin{vmatrix}  
a_{22} & a_{23} \\ a_{32} & a_{33} \\ \end{vmatrix}

- a_{21} \begin{vmatrix}  
    a_{12} & a_{13} \\ a_{32} & a_{33} \\ \end{vmatrix}
- a_{31} \begin{vmatrix}  
    a_{12} & a_{13} \\ a_{22} & a_{23} \\ \end{vmatrix} $$


>[!info] Properties on the determinant
> $\text{Let } A,B \in \mathcal{M}_n \text{ and } \lambda \in \mathbb{K}. \text{Then :}$
> >$det(\lambda A) = \lambda^ndet(A)$
> >$det(AB) = det(A)det(B)$
> >$det(A) = det(A^T)$
>
> $A^T$  is the transpose of the matrix $A$

#### Tips
The determinant of a diagonal matrix is the <u>product</u> of the terms of the diagonal.
$$A = \begin{pmatrix} 2 & 0 & 0 \\ 0 & 2 & 0 \\ 0 & 0 & 3  \end{pmatrix}, det(A) = 12$$


The determinant of a upper/lower triangular matrix is the <u>product</u> of the terms of the diagonal.
$$A = \begin{pmatrix} 2 & 4 & 2 \\ 0 & 2 & 3 \\ 0 & 0 & 3  \end{pmatrix}, det(A) = 12$$

[Vandermonde matrix](https://en.wikipedia.org/wiki/Vandermonde_matrix)

1) Two row/column equal $\implies$ det is null
2) Two row/column linearly dep. $\implies$ det is null
3) One row/column is made out of $0 \implies$ det is null
4) Adding a linear combination of other column in one colum doesn't change the det
5) Swaping 2 cols/row multiplies the det by $-1$
6) Multipliying a row/col by $\lambda$ multiplies the det by $\lambda$ 




---

## Diagonalization of a square matrix

As we've just seen, life is easy with triangular of diagonal matrices. Our goal in this section is gonna be to reduce a matrix aka make it triangular or diagonal.

### Introduction

#### Eigen values and eigen vectors

>[!abstract] Definition
> Let $A \in \mathcal{M}_n(\mathbb{K})$ and $\lambda \in \mathbb{K}$.
> 1. We denote $\lambda$ as an <u>**eigen value**</u> of $A$ if there exists a vector $v \in \mathbb{K}^n$ not null such that $Av = \lambda v$ 
> 2. The vector $v$ is called <u>**eigen vector**</u> associated with $A$.
> 3. The set of eigen values of $A$ in $\mathbb{K}$ is called <u>**spectrum**</u> of $A$ in $\mathbb{K}$, denoted $Sp_{\mathbb{K}}(A)$.

⚠ The vector $v$ (eigen vector) is non-null by definition, but the eigen value can be null !

#### Eigen sub-spaces

Let $\lambda$ an eigen value of a square matrix $A$. Then :

$$
E_{\lambda} = \{v \in \mathbb{K}^n | Av = \lambda v\} = Ker(A -\lambda I_n)
$$

$E_{\lambda}$ is a vector sub-space of $\mathbb{K}^n$, called <u>**eigen sub-space**</u> of $A$ associated with the eigen value $\lambda$.

>[!abstract] Definition
> A vector sub space $F$ of $\mathbb{K}^n$ is $A$-stable if $\forall v \in F, Av \in F$. We say $AF \subset F$.
> >[!info] Proposition
> >An eigen space of a matrix $A$ is $A$-stable 

#### Direct sum of eigen sub-spaces

see [[1 - Vector Spaces]] for a revision on direct sums

>[!danger] theorem
> Let $\lambda_1,...,\lambda_k$ distinct eigen values of a square matrix $A$. Then the eigen sub-spaces $E_{\lambda_1},...,E_{\lambda_k}$ are in direct sum.


#### Cancelling polynomials

>[!abstract] Definition
>The polynomial $P \in \mathbb{K}[X]$ is a cancelling polynomial of $A$ if $P(A) = 0_{\mathcal{M}_n(\mathbb{K})}$

By misuse, we write: $P(A) = 0$

>[!info] Lemma
>Let $P \in \mathbb{K}_p[X]$ a cancelling polynomial of a matrix $A \in \mathcal{M}_n(\mathbb{K})$.
>> $$
>> \text{Si }P(0) \neq 0, \text{ then }A\text{ is invertible}
>> $$

The cancelling polynomial can be a great tool to find the inverse of a square matrix :

>[!example]-
> The polynomial $P(X) = X^2 - 5X + 4$ is the cancelling polynomial of 
> $$
> A = \begin{pmatrix} 3 & -1 & -1 \\ -1 & 3 & -1 \\ -1 & -1 & 3  \end{pmatrix}
> $$
> We have $P(0) = 4 \neq 0$, therefore $A$ is invertible. 
> $$
> \begin{aligned}
> & \space\space\qquad A^2-5A = -4I_3 \\
> & \implies A(-\frac{1}{4}A + \frac{5}{4}I_3) = I_3 \\
> & \implies A^{-1} = -\frac{1}{4}A + \frac{5}{4}I_3 \\
> & \implies A^{-1} = 
> \begin{pmatrix} 
> 0.5 & 0.25 & 0.25 \\
> 0.25 & 0.5 & 0.25 \\
> 0.25 & 0.25 & 0.5  
> \end{pmatrix}
> \end{aligned}
> $$

#wip how to find a cancelling polynomial

### Characteristic polynomial 

### Diagonalizable matrices

### Applications

#### Computation of the power of a square matrix

#### Solving a system of recurrent sequences

#### Solving a linear differential system with constant coefficients.

