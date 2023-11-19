
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


- Matrix transition #WIP 
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
>Let $A \in \mathcal{M}_n(\mathbb{K})$. A is invertible iff $det(Q) \neq 0$. Furthermore : 
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

>[!tip] 
>1 : we remove the first column and the first line
>2 : we remove the first column and the second line
>3 : we remove the first column and the third line

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


---
