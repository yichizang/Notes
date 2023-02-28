---
banner: "![[../pics/371054ab98143e770df64f1b57e11fcb1662130033085.jpeg]]"
banner_y: 0.236
---

>[!abstract]- Pre-knowledge
>- Lie algebra
>- Representation theory

>[!note]+
>The prefix super is sometimes called $\mathbb{Z}_2$-graded.

# Lie superalgebra
## 1 Basic concept
### 1.1 Supervectorspace
A *supervectorspace* is a vector space $V$ that can be decomposed as
$$
V=V_0\oplus V_1,
$$
where the indices $0$ and $1$ are called the *grade* of the vector space. One can naturally define a *grading function*
$$
\eta(x)=i,\quad\text{if}\ x\in V_i.
$$
This grading function is only defined on the subspace $V_0$ and $V_1$.

If $\eta(x)=0$ then $x$ is called *even* or *bosonic*, otherwise it is called *odd* or *fermonic*.

### 1.2 Superalgebra
Define an algebra multiplication $\ast$ on $V$ such that
$$
\begin{aligned}
&V_1\ast V_1,V_0\ast V_0\subset V_0;\\
&V_1\ast V_0,V_0\ast V_1\subset V_1.
\end{aligned}
$$
Also the grading function satisfies
$$
\eta(x\ast y)=(\eta(x)+\eta(y))\mod2.
$$

### 1.3 Lie superalgebra
In analogue to Lie algebra, one can define a *Lie superbracket* $\{,]$ to be an algebra multiplication that satisfies the following.
- Superanticommutating
$$
\{x,y]=-(-1)^{\eta(x)\eta(y)}\{y,x];
$$
- Super Jacobi identity$$
\{x,\{y,z]]\pm\{x,\{y,z]]\pm\{x,\{y,z]]=0,
$$where the sign before each term is defined according to the number of fermonic interchanges required to turn the first term into the concerning term.

Denote the Lie superalgebra as $\mathfrak{g}=\mathfrak{g}_0\oplus\mathfrak{g}_1$, one can prove that $\mathfrak{g}_0$ is an ordinary Lie algebra and $\mathfrak{g}_1$ is a representation of $\mathfrak{g}_0$.

### 1.4 Induced Lie superalgebra
For a superalgebra $(V,\ast)$, one can naturally define a Lie superalgebra that
$$
\{x,y]\doteq x\ast y-(-1)^{\eta(x)\eta(y)}y\ast x=\left\{
\begin{aligned}
&\{x,y\},&&x,y\in V_0,\\
&[x,y],&&\text{otherwise}.
\end{aligned}
\right.
$$

### 1.5 Supersymmetry algebra
To associate elements in $\mathfrak{g}$ with actual physical symmetries, one consider $\mathfrak{g}=\mathfrak{g}_0+\mathfrak{g}_1$.

According to Coleman Mandula theorem, $\mathfrak{g}_0$ can only represent [[Representation of Lorentz algebra#1.3 Lorentz Lie algebra|Poincare symmetry]] $P^\mu$ and $J^{\mu\nu}$ and internal symmetry $B_l$.

Since $\mathfrak{g}_1$ is a representation of $\mathfrak{g}_0$, it has to be a representation of Lorentz Lie algebra $(N,M)$. According to the requirement of supersymmetry, its generators must be
$$
\{Q_a{}^A\},\ \{\bar{Q}_{aA}\}
$$
where the bar means Hermitian conjugate. They are called *supercharge*. Actually, one can prove that $\mathfrak{g}_1$ must be the spinner representation of Lorentz group.

>[!note]- Proof
>To work out the exact representation, one write down the indices explicitly as
>$$
>\{Q_{nm}^{(N,M)}\},\ \{\bar{Q}_{nm}^{(M,N)}\}.
>$$
>The Lie superbracket of two generators is
>$$
>\{Q_{nm},\bar{Q}_{\tilde{n}\tilde{m}}]=Q_{nm}\bar{Q}_{\tilde{n}\tilde{m}}+\bar{Q}_{\tilde{n}\tilde{m}}Q_{nm}.
>$$
>Since the Lorentz Lie algebra satisfies
>$$
>(N,M)\otimes(M,N)=\bigoplus_{K,L=|N-M|}^{N+M}(K,L),
>$$
>one can write the decomposition
>$$
>\{Q_{nm},\bar{Q}_{\tilde{n}\tilde{m}}]=\pm\sum_{K,L;k,l}(\text{CG-coefficients})X^{(K,L)}_{kl}.
>$$
>Therefore
>$$
>X^{(K,L)}_{kl}=\pm\sum_{\tilde{m},\tilde{n};m,n}(\text{CG-coefficients})\{Q_{nm},\bar{Q}_{\tilde{n}\tilde{m}}].
>$$
>By taking $K=L=M+N$, only one term is left. That is
>$$
>X^{(N+M,N+M)}_{N+M,N+M}=\pm\{Q_{nm},\bar{Q}_{\tilde{n}\tilde{m}}].
>$$
>According to requirement of supersymmetry, the right-hand-side is nonzero. Therefore the highest indices for $X$, which is $(N+M,N+M)$.
>
>On the other hand, one have $\{Q_{nm},\bar{Q}_{\tilde{n}\tilde{m}}]\in\mathfrak{g}_0$. Therefore, the $X$ above is both an element in $\mathfrak{g}_0$ and a representation of it. Since $\mathfrak{g}_0$ can only represent Poincare or internal symmetry, which limits $(N+M,N+M)$ to the following.
>- Poincare: $(1/2,1/2)$ or $(1,0)\oplus(0,1)$;
>- Internal: $(0,0)$.
Since $(0,0)$ gives a trivial scalar result, one only consider the case $(1/2,1/2)$, which means $N+M=1/2$. Therefore $(N,M)=(1/2,0)\text{ or }(0,1/2)$, which means $\mathfrak{g}_1$ can only be the spinner representation.

### 1.6 Generator relation
Since $N+M=1/2$, the CG-expension only has one term remains
$$
\{Q_\alpha{}^A,\bar{Q}_{\tilde{\alpha}B}]=C^A{}_B\sigma_{\alpha\tilde{\alpha}}^\mu P_\mu.
$$
One can prove that the $C^A{}_B$ can be diagnolized into identity matrix, therefore one can rechoose $A$ and $B$ to write
$$
\{Q_\alpha{}^A,\bar{Q}_{\tilde{\alpha}B}]=2\delta^A{}_B\sigma_{\alpha\tilde{\alpha}}^\mu P_\mu.
$$

Another relation can be derived is
$$
\{Q_\alpha{}^A,Q_{\beta}{}^B]=\epsilon_{\alpha\beta}X^{(A,B)}.
$$
One can prove that $X^{AB}$ commutes with all elements in $\mathfrak{g}_0$. It is called the *central charge*.

Finally, there are some internal symmetry $B_l$ that don't commute with $Q_\alpha{}^A$, which are called *$R$-symmetry*.

| $G_1$ | $G_2$ | $\{G_1,G_2]$ |
| ----- | ----- | ------------ |
|       |       |              |

## 2 Representation of sypersymmetry algebra
### 2.1 Representation of supersymmetry algebra
To find a representation of supersymmetry algebra, one first find an irreducible representation of Poincare group, which is a single-particle state $\ket{\psi}$. Then by applying $Q_\alpha$ and $\bar{Q}_{\tilde{\alpha}}$ on $\ket{\psi}$, one get the full irreducible representation of supersymmetry algebra.

Denote a bosonic single-particle state as $\ket{B}$ and a fermonic one as $\ket{F}$. Define the *fermion number operator* $(-)^F$ that
$$
\begin{aligned}
&(-)^F\ket{B}=\ket{B},\\
&(-)^F\ket{F}=-\ket{F}.
\end{aligned}
$$
Its trace is then
$$
\mathrm{Tr}\ (-)^F\doteq\sum\braket{\psi|(-)^F|\psi}=\sum_i\braket{B_i|(-)^F|B_i}+\sum_j\braket{F_j|(-)^F|F_j}=n_B-n_F.
$$
Also, the multiplication rule of superalgebra gives that
$$
\begin{aligned}
Q_\alpha&\ket{B}\to\ket{F},\\
&\ket{F}\to\ket{B}.
\end{aligned}
$$

### 2.2 $N=1$ massless case
A general state of massless Poincare representation is $\ket{m,\lambda;\lambda}$ where $\lambda$ is the helicity. Under a frame where $p^\mu=(E,0,0,E)$, one can write
$$
\{Q_\alpha,\bar{Q}_{\tilde{\alpha}}\}=2\sigma_{\alpha\tilde{\alpha}}^\mu p_\mu=4E\begin{pmatrix}
1 & 0\\
0 & 0
\end{pmatrix}.
$$
Since $Q$ and $\bar{Q}$ are elements of $\mathfrak{g}_1$, $\{,]$ is simply $\{,\}$. Here the only nontrivial representation is $Q_1,\bar{Q}_1$, with
$$
\{Q_1,\bar{Q}_1\}=4E.
$$
Defining $a=Q_1/\sqrt{4E}$ and $a^\dagger=\bar{Q}_1/\sqrt{4E}$,