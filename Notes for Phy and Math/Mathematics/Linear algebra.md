---
banner: "![[mmexport1663524017232.jpg]]"
banner_y: 0.312
---

>[!abstract]- Pre-knowledge
>- [[Abstract group theory]]
>- [[Matrix theory]]

### 0.1 Tensor product
The *tensor product* of two vector spaces $U$ and $V$ is a vector space equipped with a bilinear map from $U\times V$ to it. It can be viewed as the vector spaces spanned from $\ket{e_u^i}\otimes\ket{e_v^j}$, where $\{\ket{e_u^i}\}$ and $\{\ket{e_v^j}\}$ are basis of $U$ and $V$ respectively.

### 0.2 Adjoint map
The *adjoint map* of $\varphi$ is defined as the map $^t\varphi$ that satisfies
$$\braket{^t\varphi(u)|v}=\braket{u|\varphi(v)}.$$

If map $\varphi$ is its own adjoint map, then it is called a *self-adjoint map*.

# Linear algebra
## 1 Vector space
### 1.1 Definition
A *vector space* is a set $V$ equipped with an *addition* $+:V\times V\to V$ and a *scalar multiplication* $\cdot:\mathbb{F}\times V\to V$ on a field $\mathbb{F}$. It's an [[ Abstract group theory#1.4 Abelian group|Abelian]] [[ Abstract group theory#1.2 Group|group]] under addition operation. It also satisfies that $\forall \lambda,\xi\in\mathbb{F},\forall\ket{u},\ket{v}\in V$
$$\begin{aligned}\lambda(\xi\ket{v})&=(\lambda\xi)\ket{v}\\(\lambda+\xi)\ket{v}&=\lambda\ket{v}+\xi\ket{v}\\\lambda(\ket{u}+\ket{v})&=\lambda\ket{u}+\lambda\ket{v}\end{aligned}$$
For a set $S$, one can varify that the set of all maps from $S$ to $\mathbb{F}$ forms a vector space on $\mathbb{F}$, denoted as $\mathbb{F}^S$.

### 1.2 Subspace and sum of subspace
A *subspace* of $V$ is a subset $U$ that is also a vector space under the same addition and scalar multiplication. To varify whether $U$ is a subspace of $V$, one only need to check if
- $U$ has additive identity or $U\ne\varnothing$;
- $U$ is close under addition;
- $U$ is close under scalar multiplication.

The *sum* of two subspaces $U$ and $W$ is defined as the set of all possible sums of elements in $U$ and $W$
$$U+W\doteq\{\ket{v}:\ket{v}=\ket{u}+\ket{w}\}.$$
The sum of subspaces $\{U_i\}$ is the smallest subspace that contains all the $U_i$.

For two subspaces $U$ and $W$ of $V$, if every element $\ket{v}$ in $U+W$ can be uniquely decomposed into $\ket{v}=\ket{u}+\ket{w}$, then $U+W$ is called the *direct sum* of $U$ and $W$, denoted as $U\oplus W$. It can be proved that $U+W$ is a direct sum if and only if $U\cap V=\{\ket{0}\}$. ^fd1ad8

For any [[Linear algebra#^63b8c6|finite-dimensional]] vector space $V$ and its subspace $U$, one can always find a $W\subset V$ so that $V=U\oplus W$.

### 1.3 Span
The *span* of a set of vectors $\{\ket{v_i}\}$ is the set of all linear combinations of $\{\ket{v_i}\}$
$$\mathrm{span}(\ket{v_1},\cdots,\ket{v_n})\doteq\{\ket{v}=\sum_i\lambda_i\ket{v_i},\lambda_i\in\mathbb{F}\}.$$
The span of a set of vectors $\{\ket{v_i}\in V\}$ is the smallest subspace of $V$ that contains all the $\ket{v_i}$.

If a vector space can be spanned by a set of vectors in it, then it is called a *finite-dimensional vector space*. Otherwise it is an *infinite-dimensional vector space*. The subspace of a finite-dimensional vector space is also finite-dimensional. ^63b8c6

### 1.4 Linear dependence and basis
A set of vectors $\{\ket{v_i}\}$ is called *linear independent* if they satisfy
$$\sum_i\lambda_i\ket{v_i}=\ket{0}\quad\Rightarrow\quad\forall i,\lambda_i=0.$$
Otherwise it is called *linear dependent*.

In a finite-dimensional vector space $V$, the length of a linear independent set of vectors is no greater than the length of the set of vectors that spans $V$.

If a set of vectors $\{\ket{e_i}\}$ is both linear independent and spans the vector space, then it is called the *basis* of the vector space. Any vector in the vector space can be uniquely decomposed into a linear combination of $\{\ket{e_i}\}$
$$\ket{v}=\sum_iv_i\ket{e_i}$$
if and only if $\{\ket{e_i}\}$ is the basis of the vector space. ^b3f615

The set of vectors spans the vector space isn't necessarily a basis, but it must at least contain a set of basis. This leads to every finite-dimensional vector space has basis.

### 1.5 Dimensionality
Every basis of a finite-dimensional vector space $V$ has the same length, which is called the *dimension* of the vector space, denoted as $\dim V$. And every linear independent set of vectors in $V$ that has the length of $\dim V$ is its basis.

For any subspace $U\subset V$, its dimension is no greater than $V$
$$\dim U\leqslant \dim V.$$
And for two subspaces $U$ and $W$, their sum has the dimension
$$
\dim(U+W)=\dim U+\dim W-\dim(U\cap W).
$$
The sum is a direct sum if and only if the dimension of the summed space equals the sum of dimension of spaces.

---
## 2 Linear map
### 2.1 Linear map
A *linear map* from $V$ to $W$ is a map $T$ with *additivity* and *homogeneity*. That is a map that preserves addition and scalar multipliction
$$\begin{aligned}T(\ket{u}+\ket{v})&=T\ket{u}+T\ket{v};\\T(\lambda\ket{v})&=\lambda T\ket{v}.\end{aligned}$$
The set of all linear maps from $V$ to $W$ is denoted as $\mathcal{L}(V,W)$, which is also a linear space.

For two linear maps $S\in\mathcal{L}(U,V)$ and $T\in\mathcal{L}(V,W)$, one can define their product $ST\in\mathcal{L}(U,W)$ as
$$(ST)\ket{u}\doteq S(T\ket{u}).$$

### 2.2 Kernal and image
The *kernal* of a linear map $T\in\mathcal{L}(V,W)$ is the set of all vectors mapped to $\ket{0_W}$ by $T$
$$\mathrm{Ker}\ T\doteq\{\ket{v}:T\ket{v}=\ket{0_W}\}.$$
The *image* of a linear map $T\in\mathcal{L}(V,W)$ is the set of all vectors that can be mapped to by $T$
$$\mathrm{Im\ }T\doteq\{T\ket{v}\}.$$

The kernal is a subspace of $V$ and the image is a subspace of $W$. One can prove that
$$\dim V=\dim\mathrm{Ker}\ T+\dim\mathrm{Im\ } T.$$
This is called the *fundamental theorem of linear map*. Using this theorem one can prove that a linear map to a vector space of higher dimension can't be surjective and a linear map to a vector space of lower dimension can't be injecctive.

### 2.3 Invertibility
For a linear map $T\in\mathcal{L}(V,W)$, if there exists an $S\in\mathcal{L}(W,V)$ so that
$$S\circ T=1_W,\quad T\circ S=1_V,$$
then $T$ is called an *invertible* map and $S$ is the *inverse* of $T$, denoted as $T^{-1}$. Here $1_V$ is the identity map on $V$.

A linear map is invertible if and only if it is bijective.

When an invertible linear map connects two vector spaces $V$ and $W$, they are called *isomorphic* and the map is called an *isomorphism*. This is similar to [[ Abstract group theory#2.1 Definition|isomorphism]] in group theory. For finite-dimensional vector spaces on the same field $\mathbb{F}$, they are isomorphic if and only if they have the same dimension.

### 2.4 Linear operator
A *linear operator* is a linear map from $V$ to itself. The set of all linear operators on $V$ is denoted as $\mathcal{L}(V)\doteq\mathcal{L}(V,V)$.

For an operator $T$ on a finite-dimensional vector space $V$, the following statements are equivalent.
- $T$ is invertible;
- $T$ is injective (one-one);
- $T$ is surjective (onto).

---
## 3 Matrix
### 3.1 Definition of matrix
An *$m\times n$ matrix* is an array of numbers in $\mathbb{F}$ with $m$ rows and $n$ columns that looks like
$$A=\begin{pmatrix}A_{11} & \cdots & A_{1n}\\\vdots & \ddots & \vdots\\A_{m1} & \cdots & A_{mn}\end{pmatrix}.$$

For a linear map $T\in\mathcal{L}(V,W)$ and selected basis of $V$ and $W$, one can write a matrix $A$ to represent the map, where
$$T\ket{e_V^j}=\sum_iA_{ij}\ket{e_W^i}.$$
This is called the *matrix of linear map* $T$ under these bases, sometimes denoted as $\mathcal{M}(T)$. Here the matrix is $\dim W\times\dim V$. For a linear operator $T\in\mathcal{L}(V)$, one only need to select a basis of $V$ to write the matrix of $T$.

For a vector $\ket{v}$ and selected basis of $V$, one can also write a matrix $v$ to represent the vector
$$\ket{v}=\sum_iv_{1i}\ket{e_i}.$$
This is called the *matrix of vector* $\ket{v}$ under this basis, denoted as $\mathcal{M}(\ket{v})$. This matrix is $\dim V\times 1$, so the index $1$ is usually omitted $v_i\doteq v_{1i}$.

### 3.2 Matrix operation
The addition and scalar multiplication of matrix is simply adding or multiplying on each number individually. *Matrix multiplication* is defined between an $m\times n$ matrix $A$ and an $n\times p$ matrix $B$ as
$$(AB)_{ij}=\sum_{k=1}^nA_{ik}B_{kj}.$$
The outcome is an $m\times p$ matrix. These matrix operations satisfy
$$\begin{aligned}\mathcal{M}(T+S)&=\mathcal{M}(T)+\mathcal{M}(S);\\\mathcal{M}(\lambda T)&=\lambda\mathcal{M}(T);\\\mathcal{M}(T\ket{v})&=\mathcal{M}(T)\mathcal{M}(\ket{v});\\\mathcal{M}(S\circ T)&=\mathcal{M}(S)\mathcal{M}(T).\end{aligned}$$

### 3.3 Rank
For a matrix $A\in\mathbb{F}^{m,n}$, its *row rank* is the dimension of the subspace spanned by rows of $A$ in $\mathbb{F}^n$, and its *column rank* is the dimension of the subspace spanned by columns of $A$ in $\mathbb{F}^m$.

It can be proved that the row rank and the column rank are equal. Its value is called the *rank* of $A$.

The dimension of $\mathrm{Im}\ T$ is equal to the rank of $\mathcal{M}(T)$.

---
## 4 Product and quotient
### 4.1 Product of vector space
For two vector spaces $V$ and $W$ on $\mathbb{F}$, their *product* is a vector space $V\times W$ with addition and scalar multiplication defined as
$$\begin{aligned}(\ket{v_1},\ket{w_1})+(\ket{v_2},\ket{w_2})&\doteq(\ket{v_1}+\ket{v_2},\ket{w_1}+\ket{w_2}),\\\lambda(\ket{v},\ket{w})&\doteq(\lambda\ket{v},\lambda\ket{w}).\end{aligned}$$

The dimension of product space is
$$\dim V\times W=\dim V+\dim W.$$

### 4.2 Affine subset
An *affine subset* of $V$ is a subset of $V$ of the form
$$\ket{v}+U\doteq\{\ket{v}+\ket{u}\},$$
where $U$ is a subspace of $V$. Such $\ket{v}+U$ is *parallel* to $U$.

Any two affine subsets parallel to $U$ are either equal or disjoint, which means the following statements are equivalent.
- $\ket{v}-\ket{w}\in U$;
- $\ket{v}+U=\ket{w}+U$;
- $(\ket{v}+U)\cap(\ket{w}+U)\ne\varnothing$.

### 4.3 Quotient space
For a subspace $U$ of $V$, a *quotient space* $V/U$ is the set of all affine subsets parallel to $U$
$$V/U\doteq\{\ket{v}+U\}.$$
It is also a vector space with addition and scalar multiplication
$$\begin{aligned}(\ket{v}+U)+(\ket{w}+U)&\doteq(\ket{v}+\ket{w})+U,\\\lambda(\ket{v}+U)&\doteq\lambda\ket{v}+U.\end{aligned}$$

The dimension of a quotient space $V/U$ is
$$\dim V/U=\dim V-\dim U.$$
This can be proved with the help of *quotient map*, which is a linear map
$$
\begin{aligned}
\pi:V&\to V/U \\
\ket{v}&\mapsto\ket{v}+U.
\end{aligned}
$$

Any $T\in\mathcal{L}(V,W)$ naturally introduces a linear map
$$
\begin{aligned}
\tilde{T}:\quad V/\mathrm{Ker}\ T&\to W \\
\ket{v}+\mathrm{Ker}\ T&\mapsto T\ket{v}.
\end{aligned}
$$
$\tilde{T}$ is injective and $V/\mathrm{Ker}\ T$ is isomorphic to $\mathrm{Im}\ \tilde{T}=\mathrm{Im}\ T$.

---
## 5 Dual
### 5.1 Dual space
A *linear functional* of $V$ is a linear map from $V$ to $\mathbb{F}$. The set of all linear functionals of $V$ is called its *dual space*, denoted as $V^*\doteq\mathcal{L}(V,\mathbb{F})$. It is also a vector space.

We denote a dual vector in $V^*$ as $\bra{w}$ and it maps a vector $\ket{v}$ to $\braket{w|v}\in\mathbb{F}$.

The dimenstion of $V^*$ is equal to the dimension of $V$.

### 5.2 Dual basis
For a set of basis of $V$, denoted as $\{\ket{e_i}\}$, its *dual basis* is a set of dual vectors in $V^*$ of same amount $\{\bra{e^i}\}$ that maps
$$\braket{e^i|e_j}\doteq\delta_{ij},$$
where the $\delta_{ij}$ is the kronecker delta.

The dual basis is a set of basis of $V^*$.

### 5.3 Dual map
For a linear map $T\in\mathcal{L}(V,W)$, its *dual map* is $T^*\in\mathcal{L}(W^*,V^*)$ that maps $\bra{w}$ to $\bra{w}T$.

Dual map satisfies
- for any $S,T\in\mathcal{L}(V,W)$, $(S+T)^*=S^*+T^*$;
- for any $\lambda\in\mathbb{F}$ and $T\in\mathcal{L}(V,W)$, $(\lambda T)^*=\lambda T^*$;
- for any $S\in\mathcal{L}(U,V)$ and $T\in\mathcal{L}(V,W)$, $(ST)^*=T^*S^*$.

### 5.4 Kernal and image of dual map
For a subspace $U$ of $V$, its *annihilator* $U^0$ is defined as
$$U^0\doteq\{\bra{v}:\forall\ket{u}\in U,\braket{v|u}=0\}.$$
$U^0$ is a subspace of $V^*$. Its dimension satisfies
$$\dim U+\dim U^0=\dim V.$$

It can be proved that the kernal and image of a dual map $T^*$ are
$$\begin{aligned}\mathrm{Ker}\ T^*&=(\mathrm{Im}\ T)^0,\\\mathrm{Im}\ T^*&=(\mathrm{Ker}\ T)^0.\end{aligned}$$
$T^*$ is surjective (injective) if and only if $T$ is injective (surjective).

### 5.5 Matrix of dual map
The *transpose* of a matrix $A$ is defined by exchanging its rows and columns, denoted as $A^T$
$$\left(A^T\right)_{ij}=A_{ji}.$$
The transpose of an $m\times n$ matrix is an $n\times m$ matrix. The transpose of product is
$$(AB)^T=B^TA^T.$$

The matrix of $T^*$ under the dual basis is the transpose of the matrix of $T$
$$\mathcal{M}(T^*)=(\mathcal{M}(T))^T.$$

---
## 6 Eigenvalue and eigenvector
### 6.1 Invarient subspace
For an operator $T\in\mathcal{L}(V)$, a *$T$-invarient subspace* of $V$ is defined as a subspace $U$ that satisfies
$$\forall\ket{u}\in U,\quad T\ket{u}\in U.$$
This means that $T$ is an operator on $U$.

For an operator $T$, the following are $T$-invarient subspaces of $V$.
- $\{\ket{0}\}$;
- $V$;
- $\mathrm{Ker}\ T$;
- $\mathrm{Im}\ T$.

For an operator $T\in\mathcal{L}(V)$ with a $T$-invarient subspace $U\subset V$, one can naturally define a *restriction operator* $T|_U\in\mathcal{L}(U)$ as
$$
T|_U\ket{u}\doteq T\ket{u},
$$
and a *quotient operator* $T/U\in\mathcal{L}(V/U)$ as
$$
(T/U)(\ket{v}+U)\doteq T\ket{v}+U.
$$

### 6.2 Eigenvalue
An *eigenvalue* of operator $T\in\mathcal{L}(V)$ is a number $\lambda\in\mathbb{F}$ that
$$\exists\ket{v}\in V,\quad T\ket{v}=\lambda\ket{v}.$$

Any subset of $V$ of the form
$$U=\{\lambda\ket{v}\}=\mathrm{span}(\ket{v})$$
with $\ket{v}\ne\ket{0}$ is a one dimensional subspace of $V$, and clearly every one dimensional subspace of $V$ has a form of this. So $V$ has a one dimensional $T$-invarient subspace if and only if $T$ has an eigenvalue.

### 6.3 Eigenvector
For an operator $T$ with eigenvalue $\lambda$, its corresponding *eigenvector* is $\ket{v}\ne\ket{0}$ that
$$
T\ket{v}=\lambda\ket{v}.
$$
A nonzero $\ket{v}$ is an eigenvector of $T$ with eigenvalue $\lambda$ if and only if
$$
\ket{v}\in\mathrm{Ker}(T-\lambda\cdot 1_V).
$$

If $\{\lambda_i\}$ are different eigenvalue of $T$ and $\{\ket{v_i}\}$ are corresponding eigenvectors, then they are linear independent. Thus for any operator $T\in\mathcal{L}(V)$, the maximum number of different eigenvalues is $\dim V$.

