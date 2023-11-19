

### Product of matrices

---

>[!tip] 
>L**[CL]**C; number of **column** on the **left** must **equal** the number of **row** on the **right**


- Matrix transition #WIP 
- Matrix multiplication #WIP 

### Notations

---

$\mathcal{M}_n(\mathbb{K})$ is the vector space of square matrix of order n with coefficients in $\mathbb{K}$

$0_{\mathcal{M}_n(\mathbb{K})}$ is the null matrix

$I_n$ is the identity matrix

### Inverse of a 3\*3 matrix

---

[Youtube video that explains kramer's method](https://youtu.be/Fg7_mv3izR0?si=TzhiXIz_DMDNlLKN)

>[!tip] 
>It works for any square matrix


### Transition Matrix

---

The transition matrix allows us to change the basis.

- If all the **columns** of the transition matrix are **linearly independent**, then $f$ is **injective**
- If all the **columns** of the transition matrix make out a **spanning family**, then $f$ is **surjective**
- If all the **columns** of the transition matrix make out a **basis**, then $f$ is **bijective**

#### Rank of a Matrix

$$\text{Rank a} = \text{rank f} = dim(Im f)$$

### Determinant of a square matrix

---

The determinant is a scalar associated with a matrix

The determinant of the matrix $A = \begin{pmatrix} a_{1,1} & a_{1,2} \\ a_{2,1} & a_{2,2} \end{pmatrix} \in \mathcal{M}_2(\mathbb{K})$, denoted $det(A)$ is the scalar defined by :

$$ det(A) = \begin{vmatrix}  
a_{11} & a_{12} \\ a_{21} & a_{22} \\ \end{vmatrix} = a_{11}a_{22} - a_{21}a_{12} $$

The determinant of the matrix $$A = \begin{pmatrix} a_{1,1} & a_{1,2} & a_{1,3} \\

a_{2,1} & a_{2,2} & a_{2,3} \\ a_{3,1} & a_{3,2} & a_{3,3}  
\end{pmatrix} \in \mathcal{M}_3(\mathbb{K})$$
, denoted $det(A)$ is the scalar defined by :

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

### Inverse of a Matrix
---
A matrix is invertible (or non-singular) if and only if it is a square matrix and its determinant is non-zero.

#WIP 