
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

>[!abstract]- Matrix similarity
>>In linear algebra, two $n \times n$ matrices $A$ and $B$ are called similar if there exists an invertible $n \times n$ matrix $P$ such that :
>>$$
>>B = P^{-1}AP
>>$$



<br>

---

### Matrix multiplication

>[!danger] 
><span class="leftimg desktop">![[Matrix_multiplication_qtl1.svg.png]]</span><span class ="mobile">![[Matrix_multiplication_qtl1.svg.png]]</span>
>The number of **columns in the first matrix** must be **equal** to the number of **rows in the second matrix**. The **result matrix has** the number of **rows of the first** and the number of **columns of the second** matrix.





>[!info]- Illustration
><span class="leftimg desktop">![[Matrix_multiplication_diagram_2.svg.png]]</span><span class ="mobile">![[Matrix_multiplication_diagram_2.svg.png]]</span>
>The figure to the left illustrates diagrammatically the product of two matrices **A** and **B**, showing how each intersection in the product matrix corresponds to a row of **A** and a column of **B**.

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

$$
\text{Rank a} = \text{rank f} = \text{dim}(\text{Im} (f))$$

>[!warning]- Transition Matrix vs Matrix of a linear map
> - A transition matrix changes the basis of a vector space. It must be invertible since it is a bijective function.
>  - A matrix of a linear map chages the vector space itself. If the dimension vary then it will not be invertible.
>
>In summary a transition matrix if a matrix of a linear map that is an endomorphism too $\mathcal{L}(E)$

>[!example]- Compute the rank of a matrix
>Find the number of linearly independent column vector that makes a matrix to find $\text{dim}(\text{Im} (f))$

#### Find a transition matrix

Let $E$ be a n-dimentional vector-space and $\mathcal{B}_1 = \{v_1,...,v_n\}$, $\mathcal{B}_2 = \{w_1,...,w_n\}$ two of its basis.

The _transition matrix_ $P$ from $\mathcal{B}_1$ to $\mathcal{B}_2$ is the $n \times n$ matrix whose columns are coordinates of $v_j$ in basis $\mathcal{B}_2$ :

$$
P = \begin{bmatrix} [v_1]_{\mathcal{B}_2} & ... & [v_n]_{\mathcal{B}_2} \end{bmatrix}
$$

>[!example]-
>
>Let $V = \mathbb{R}^2$, $\mathcal{B}_1$ be the standard basis and $\mathcal{B}_2 = \{[ 1 \space 1 ],[0 \space 1]\}$ . Then:
>
>$$
>P = \begin{bmatrix} 1 & 0 \\ 1 & 1   \end{bmatrix}
>$$

---

### Change of basis

>[!info]- Graphical interpretation
>A vector represented by two different bases (green and blue arrows).
>
>![[122px-3d_two_bases_same_vector.svg.png]]

Let $E$ and $F$ two vector spaces.
Let $\mathcal{B}_1$ and $\mathcal{B}_1'$ two basis of $E$ with $P$ the transition matrix.
Let $\mathcal{B}_2$ and $\mathcal{B}_2'$ two basis of $F$ with $Q$ the transition matrix.
For $f \in \mathcal{L}(E,F)$, $A = \text{Mat}_{ \mathcal{B}_1, \mathcal{B}_1'}(f)$ and $A' = \text{Mat}_{ \mathcal{B}_2, \mathcal{B}_2'}(f)$. Then: 

>[!info]- Demonstration
> $$
> \begin{flalign}
> & \space\space\qquad PX = X' \\ &
> \space\space\qquad QY = Y' \\ &
> \space\space\qquad AX = Y \\ &
> \space\space\qquad A'X' = Y' \\ &
> \implies Y = Q^{-1}Y' \\ &
> \implies AX = Q^{-1}Y' \\ &
> \implies QAX = Y' \\ &
> \implies QAX = A'X' \\ &
> \implies QAP^{-1}X' = A'X' \\ &
> \implies QAP^{-1} = A' &
> \end{flalign}
> $$

$$
A' = QAP^{-1}$$

<br>

>[!example]- Exercise
>Let  $\mathcal{B}_1$ and $\mathcal{B}_2$ be the standard input and output basis of $f$
>$$
>\begin{array}{l|rcl}\text{Let } f : & \mathbb{R_2[X]} & \longrightarrow & \mathbb{R^2} \\ & P & \longmapsto & (P(2),P'(2))) \end{array}
>$$
>
>Find the matrix of $f$  in bases $\mathcal{B}_1' = (1,(1+X),(1+X)^2)$ as input basis and $\mathcal{B}_2' = ((1,2),(2,3))$ as output basis
>
> 1) #### Find the matrix of f form $\mathcal{B}_1$ to $\mathcal{B}_2$
> >Compute the values of each vector in the input basis through $f$.
>>
> $f(1) = (1,0)$
> $f(X) = (2,1)$
> $f(X^2) = (4,4)$
> >
> >Deduce the matrix of $f$ from $\mathcal{B}_1$ to $\mathcal{B}_2$
> >
> >$A = \begin{pmatrix} 1 & 2 & 4 \\ 0 & 1 & 4   \end{pmatrix}$
> 2) #### Find both transition matrices
> >Let $P$ be the transition matrix from $\mathcal{B}_1$ to $\mathcal{B}_1'$.
> >Let $Q$ be the transition matrix from $\mathcal{B}_2$ to $\mathcal{B}_2'$.
> >
> >$P = \begin{pmatrix} 1 & 0 & 0 \\ -2 & 1 & 0 \\ 1 & -1 & 1   \end{pmatrix}$
> >
> >$Q = \begin{pmatrix} -3 & 2 \\ 2 & -1 \end{pmatrix}$
> >
> >(see previous section)
> 3) #### Deduce the matrix of f from $\mathcal{B}_1'$ to $\mathcal{B}_2'$
> > Compute the inverse of P with kramer's method which gives:
> > 
> >$P = \begin{pmatrix} 1 & 0 & 0 \\ 2 & 1 & 0 \\ 1 & 1 & 1   \end{pmatrix}$
> >
> >Compute the formula $A' = QAP^{-1}$ which gives :
> >
> >$A' = \begin{pmatrix} -15 & -8 & -4 \\ 12 & 7 & 4 \end{pmatrix}$


---

### Determinant of a square matrix


The determinant is a scalar associated with a matrix

>[!abstract]- Formal definition
>Let
>> $A = (a_{i,j})1≤i,j≤n \in \mathcal{M}_n$
>
>The determinant of matrix $A$ is :
>
>>det($A$) $= \sum^n_{i=1}(-1)^{i+j}a_{i,j}\lambda_{i,j}$
>
if we develop in regard to the jth column; and 
>
>>det($A$) $= \sum^n_{j=1}(-1)^{i+j}a_{i,j}\lambda_{i,j}$
>
>if we develop in regard to the ith column

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


>[!info]- Graphical interpretation
>
![[220px-Area_parallellogram_as_determinant.svg.png]]
>The area of the parallelogram is the absolute value of the determinant of the matrix formed by the vectors representing the parallelogram's sides.
>
>![[Determinant_parallelepiped.svg.png]]
>The volume of this parallelepiped is the absolute value of the determinant of the matrix formed by the columns constructed from the vectors r1, r2, and r3.

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
>The polynomial $P \in \mathbb{K}_p[X]$ is a cancelling polynomial of $A$ if $P(A) = 0_{\mathcal{M}_n(\mathbb{K})}$

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

### Characteristic polynomial 

>[!abstract] Definition
> Let $A \in \mathcal{M}_n(\mathbb{K})$. The characteristic polynomial of $A$, denoted $P_A$, is the polynomial from $\mathbb{K}[X]$ defined by $P_A(X) = \text{det}(A - XI_n)$

>[!example]-
>The characteristic polynomial of $A = \begin{pmatrix} 0 & 1 \\ 3 & -2 \end{pmatrix}$  is
>$$
>P_A(X) = \begin{vmatrix} -X & 1 \\ 3 & -2-X \end{vmatrix} = X(2+X) -3
>$$
>Hence :
>$$
>P_A(X) = X^2 + 2X -3 = (X - 1)(X + 3)
>$$


Proposition :

- $P_A(0) = \det{A}$
- $P_A = P_{A^T}$


>[!danger] theorem
>Let $A \in \mathcal{M}_n(\mathbb{K})$. A scalar $\lambda \in \mathbb{K}$ is an eigen value of A if and only if $P_A(\lambda) = 0$

⬆ This means that the roots of the characteristic polynomial are eigen values of $A$.

>[!danger] Cayley-Hamilton Theorem
>Let $A \in \mathcal{M}_n(\mathbb{K})$ and $P_A \in \mathbb{K}_p[X]$ the characteristic polynomial of $A$.
>Then $P_A(A) = 0_{\mathcal{M}_n(\mathbb{K})}$

⬆ This means a characteristic polynomial is a cancelling polynomial too $A$.

### Diagonalizable matrices

>[!abstract] Definition
>Let $A \in \mathcal{M}_n(\mathbb{K})$. We say that $A$ is diagonalizable if there exists an invertible matrix $P$ in $GL_n(\mathbb{K})$ and a diagonal matrix $D$  in $\mathcal{M}_n(\mathbb{K})$ such that :
>$$
>A = P^{-1}DP
>$$
>In other words $A$ has to be similar to a diagonal matrix.

In fact the column vectors of the matrix $P$ are eigen vectors of $A$.

#todo mimos diagonalizable 

### Applications

#### Computation of the power of a square matrix

#### Solving a system of recurrent sequences

#### Solving a linear differential system with constant coefficients.

