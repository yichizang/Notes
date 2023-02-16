---
banner: "![[../pics/99277165_p0.jpg]]"
banner_y: 0.172
---

>[!abstract]- Pre knowledge
>- [[Abstract group theory]]
>- [[Linear algebra]]

# Matrix theory
---
## 1 Basic concepts
### 1.1 Definition of matrix
An *$m\times n$ matrix* is an array of numbers in $\mathbb{F}$ with $m$ rows and $n$ columns that looks like
$$A=\begin{pmatrix}A_{11} & \cdots & A_{1n}\\\vdots & \ddots & \vdots\\A_{m1} & \cdots & A_{mn}\end{pmatrix}.$$
An $n\times n$ matrix is called a square matrix of order $n$.

An identity matrix is a square matrix of order $n$ with $1$ on the diagnoal and $0$ elsewhere
$$
\mathbb{1}_n\doteq\begin{pmatrix}
1 & 0 & \cdots & 0\\
0 & 1 &  & \vdots\\
\vdots &  & \ddots & 0\\
0 & \cdots & 0 & 1
\end{pmatrix}.
$$
It's sometimes denoted simply as $\mathbb{1}$.

### 1.2 Matrix of linear map and operator
For a [[Linear algebra#2.1 Linear map|linear map]] $T\in\mathcal{L}(V,W)$ and selected [[Linear algebra#^b3f615|basis]] of $V$ and $W$, one can write a matrix $A$ to represent the map, where
$$T\ket{e_V^j}=\sum_iA_{ij}\ket{e_W^i}.$$
This is called the *matrix of linear map* $T$ under these bases, denoted as $\mathcal{M}(T,\{e_V\},\{e_W\})$ or $\mathcal{M}(T)$. Here the matrix is $\dim W\times\dim V$.

For a [[Linear algebra#2.4 Linear operator|linear operator]] $T\in\mathcal{L}(V)$, one only need to select a basis of $V$ to write the matrix of $T$. The matrix of a linear operator is a square matrix.

The matrix of identity map $1_V$ is the identity matrix $\mathbb{1}$.

### 1.3 Matrix of vector
For a vector $\ket{v}$ and selected basis of $V$, one can also write a matrix $v$ to represent the vector
$$\ket{v}=\sum_iv_{1i}\ket{e_i}.$$
This is called the *matrix of vector* $\ket{v}$ under this basis, denoted as $\mathcal{M}(\ket{v})$. This matrix is $\dim V\times 1$, so the index $1$ is usually omitted $v_i\doteq v_{1i}$.

### 1.4 Matrix operation
The addition and scalar multiplication of matrix is simply adding or multiplying on each number individually. *Matrix multiplication* is defined between an $m\times n$ matrix $A$ and an $n\times p$ matrix $B$ as
$$(AB)_{ij}=\sum_{k=1}^nA_{ik}B_{kj}.$$
The outcome is an $m\times p$ matrix.

The *inverse* of an $n\times n$ square matrix $A$ is another $n\times n$ square matrix $A^{-1}$ that
$$
AA^{-1}=A^{-1}A=\mathbb{1}_n.
$$

These matrix operations satisfy
$$
\begin{aligned}
\mathcal{M}(T+S)&=\mathcal{M}(T)+\mathcal{M}(S);\\
\mathcal{M}(\lambda T)&=\lambda\mathcal{M}(T);\\
\mathcal{M}(T^{-1})&=\mathcal{M}^{-1}(T);\\
\mathcal{M}(T\ket{v})&=\mathcal{M}(T)\mathcal{M}(\ket{v});\\
\mathcal{M}(S\circ T)&=\mathcal{M}(S)\mathcal{M}(T).
\end{aligned}
$$

### 1.5 Change of basis
For two sets of basis $\{\ket{v_i}\}$ and $\{\ket{w_i}\}$ of $V$ and an operator $T\in\mathcal{L}(V)$, the *transition matrix* from $\{\ket{v_i}\}$ to $\{\ket{w_i}\}$ is defined as
$$
A\doteq\mathcal{M}(1_V,\{w_i\},\{v_i\}).
$$
Using this transition matrix, one can change the basis of $\mathcal{M}(T)$
$$
\mathcal{M}(T,\{w_i\})=A^{-1}\mathcal{M}(T,\{v_i\})A.
$$

### 1.6 Rank
For a matrix $A\in\mathbb{F}^{m,n}$, its *row rank* is the [[Linear algebra#1.5 Dimensionality|dimension]] of the subspace [[Linear algebra#1.3 Span|spanned]] by rows of $A$ in $\mathbb{F}^n$, and its *column rank* is the dimension of the subspace spanned by columns of $A$ in $\mathbb{F}^m$.

It can be proved that the row rank and the column rank are equal. Its value is called the *rank* of $A$.

The dimension of $\mathrm{Im}\ T$ is equal to the rank of $\mathcal{M}(T)$.