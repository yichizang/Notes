---
banner: "![[../pics/371054ab98143e770df64f1b57e11fcb1662130033085.jpeg]]"
banner_y: 0.236
---

>[!abstract]- Pre-knowledge
>- [[../Mathematics/Lie algebra and Lie group|Lie algebra and Lie group]]
>- [[../Mathematics/Representation theory|Representation theory]]
>- [[Representation of Lorentz algebra]]

# Supersymmetry algebra
## 1 Lie superalgebra
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

>[!note]
>The prefix "super-" is also called $\mathbb{Z}_2$-graded.

### 1.3 Lie superalgebra
In analogue to Lie algebra, one can define a *Lie superbracket* $\{\cdot,\cdot]$ to be an algebra multiplication that satisfies the following.
- Superanticommutating
$$
\{x,y]=-(-1)^{\eta(x)\eta(y)}\{y,x];
$$
- Super Jacobi identity
$$
\{x,\{y,z]](-1)^{\eta(x)\eta(z)}+\{y,\{z,x]](-1)^{\eta(y)\eta(x)}+\{z,\{x,y]](-1)^{\eta(z)\eta(y)}=0,
$$
where the sign before each term is defined according to the number of fermonic interchanges required to turn the first term into the concerning term.

Denote the Lie superalgebra as $\mathfrak{g}=\mathfrak{g}_0\oplus\mathfrak{g}_1$, one can prove that $\mathfrak{g}_0$ is an ordinary Lie algebra and $\mathfrak{g}_1$ is an adjoint representation of $\mathfrak{g}_0$.

### 1.4 Induced Lie superalgebra
For a superalgebra $(V,\ast)$, one can naturally define a Lie superalgebra that
$$
\{x,y]\doteq x\ast y-(-1)^{\eta(x)\eta(y)}y\ast x=\left\{
\begin{aligned}
&\{x,y\},&&x,y\in V_1,\\
&[x,y],&&\text{otherwise}.
\end{aligned}
\right.
$$

## 2 Supersymmetry algebra
### 2.1 Supersymmetry algebra
To associate elements in $\mathfrak{g}$ with actual physical symmetries, one consider $\mathfrak{g}=\mathfrak{g}_0+\mathfrak{g}_1$.

According to Coleman Mandula theorem, $\mathfrak{g}_0$ can only contain [[Representation of Lorentz algebra#1.3 Lorentz Lie algebra|Poincare symmetry]] $P^\mu$ and $J^{\mu\nu}$ and internal symmetry $B_l$.

Since $\mathfrak{g}_1$ is a representation of $\mathfrak{g}_0$, it has to be a representation of Lorentz Lie algebra $(N,M)$. One can prove that $\mathfrak{g}_1$ must be the spinner representation of Lorentz group. Denote the generators of $\mathfrak{g}_1$ as
$$
\{Q_\alpha{}^A,\bar{Q}_{\dot{\alpha} A}\}
$$
where $\alpha$ is the spinor index and $A$ is internal index. These generators are called *supercharges*.

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
>
Since $(0,0)$ gives a trivial scalar result, one only consider the case $(1/2,1/2)$, which means $N+M=1/2$. Therefore $(N,M)=(1/2,0)\text{ or }(0,1/2)$, which means $\mathfrak{g}_1$ can only be the spinner representation.

### 2.2 Generator relation
Since $N+M=1/2$, the CG-expension only has one term remains
$$
\{Q_\alpha{}^A,\bar{Q}_{\dot{\beta}B}]=C^A{}_B(\sigma^\mu)_{\alpha\dot{\beta}}P_\mu.
$$
One can prove that the $C^A{}_B$ can be diagnolized into identity matrix, therefore one can rechoose $A$ and $B$ to write
$$
\{Q_\alpha{}^A,\bar{Q}_{\dot{\beta}B}]=\delta^A{}_B(\sigma^\mu)_{\alpha\dot\beta}P_\mu.
$$

Another relation can be derived is
$$
\{Q_\alpha{}^A,Q_{\beta}{}^B]=\epsilon_{\alpha\beta}X^{[AB]}=\epsilon_{\alpha\beta}a^{l,[AB]}B_l,
$$
where $a^{l,[AB]}$ are coefficients. One can prove that $X^{[AB]}$ commutes with all elements in $\mathfrak{g}_0$. It is called the *central charge*. Also, there is
$$
\{\bar{Q}_{\dot\alpha A},\bar{Q}_{\dot\beta B}]=\epsilon_{\dot\alpha\dot\beta}X^\dagger_{[AB]}=\epsilon_{\dot\alpha\dot\beta}a^\ast_{l,[AB]}B^l.
$$

### 2.3 Supersymmetry algebra
The most general supersymmetry algebra is given by

| $G_1$                    | $G_2$                                       | $\{G_1,G_2]$                                                                                      |
| ------------------------ | ------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| $P^\mu$                  | $Q_\alpha{}^A$ or $\bar{Q}_{\dot{\alpha}A}$ | $0$                                                                                               |
|                          | $B_l$ or $X^{[AB]}$                         | $0$                                                                                               |
| $J^{\mu\nu}$             | $Q_\alpha{}^A$                              | $(\sigma^{\mu\nu})_\alpha{}^\beta Q_\beta{}^A$                                                    |
|                          | $\bar{Q}_{\dot{\alpha}A}$                   | $-(\bar{\sigma}^{\mu\nu})_{\dot{\alpha}}{}^{\dot{\beta}}\bar{Q}_{\dot{\beta}A}$                   |
| $Q_\alpha{}^A$           | $\bar{Q}_{\dot\beta B}$                     | $2\delta^A{}_B(\sigma^\mu)_{\alpha\dot\beta}P_\mu$                                                |
|                          | $Q_\beta{}^B$                               | $\epsilon_{\alpha\beta}X^{[AB]}=\epsilon_{\alpha\beta}a^{l,[AB]}B_l$                              |
|                          | $B_l$                                       | $S_l{}^A{}_BQ_\alpha{}^B$                                                                         |
| $\bar{Q}_{\dot\alpha A}$ | $\bar{Q}_{\dot\beta B}$                     | $\epsilon_{\dot\alpha\dot\beta}X^\dagger_{[AB]}=\epsilon_{\dot\alpha\dot\beta}a^\ast_{l,[AB]}B^l$ |
|                          | $B_l$                                       | $-S^\ast_{lA}{}^B\bar{Q}_{\dot\alpha B}$                                                                                      |
| $X^{[AB]}$               | $Q$ or $\bar{Q}$                            | $0$                                                                                               |
|                          | $X^{[CD]}$ or $B_l$                         | $0$                                                                                               |
| $B_l$                    | $B_m$                                       | $ic_{lm}{}^kB_k$                                                                                  |

Through Bianchi identity, the coefficients satisfies
$$
S_l{}^A{}_Ba^{k,[BC]}=-a^{k,[AB]}S^\ast_{lB}{}^C.
$$

## 3 Representation of supersymmetry algebra
### 3.1 Representation of supersymmetry algebra
To find a representation of supersymmetry algebra, one first find an irreducible representation of Poincare group, which is a single-particle state $\ket{\psi}$. Then by applying $Q_\alpha$ and $\bar{Q}_{\tilde{\alpha}}$ on $\ket{\psi}$, one get the full irreducible representation of supersymmetry algebra.

### 3.2 Fermion number operator
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
Therefore, the commutation relation gives
$$
\{(-)^F,Q_\alpha\}=0.
$$
By calculating $\mathrm{Tr}\left[(-)^F\{Q_\alpha{}^A,\bar{Q}_{\dot\beta B}\}\right]$, one can prove that at fixed $P_\mu$, $\mathrm{Tr}(-)^F=0$.

### 3.3 Massive case
Consider the massive case $P^2=-M^2$ under rest frame $P_\mu=(-M,0,0,0)$. The commutation relation becomes
$$
\begin{aligned}
\{Q_\alpha{}^A,\bar{Q}_{\dot\beta B}\}&=2M\delta_{\alpha\dot\beta}\delta^A{}_B,\\
\{Q_\alpha{}^A,Q_\beta{}^B\}&=\{\bar{Q}_{\dot\alpha A},\bar{Q}_{\dot\beta B}\}=0.
\end{aligned}
$$
Define the *creation* and *annihilation* operator as
$$
\begin{aligned}
a_\alpha{}^A&\doteq\frac{1}{\sqrt{2M}}Q_\alpha{}^A,\\
(a_\alpha{}^A)^\dagger&\doteq\frac{1}{\sqrt{2M}}\bar{Q}_{\dot\alpha A}.
\end{aligned}
$$
From a Clifford "vacuum" state $\ket{\Omega}$ that satisfies
$$
P^2\ket{\Omega}=-M^2\ket{\Omega},\quad a_\alpha{}^A\ket{\Omega}=0,
$$
one can construct the representation by applying $a^\dagger$
$$
\ket{\alpha_1A_1,\cdots,\alpha_nA_n}\doteq\frac{1}{\sqrt{n!}}(a_{\alpha_1}{}^{A_1})^\dagger\cdots(a_{\alpha_n}{}^{A_n})^\dagger\ket{\Omega}.
$$
Due to commutation relation, $n\leqslant 2N$. Therefore, this is a $2^{2N}$ dimensional representation. The highest spin is spin-$\frac{1}{2}N$.

>[!note]
>It is possible that $\ket{\Omega}$ also has spin. In which case the spin will also be taken into account.

### 3.4 Massless case
In the massless case, one can boost to a frame where $P_\mu=(-E,0,0,-E)$. The commutation relation therefore becomes
$$
\begin{aligned}
\{Q_\alpha{}^A,\bar{Q}_{\dot\beta B}\}&=2M\begin{pmatrix}
2 & 0\\
0 & 0
\end{pmatrix}_{\alpha\dot\beta}\delta^A{}_B,\\
\{Q_\alpha{}^A,Q_\beta{}^B\}&=\{\bar{Q}_{\dot\alpha A},\bar{Q}_{\dot\beta B}\}=0.
\end{aligned}
$$
The only non-trivial part is then $Q_1{}^A$ and $\bar{Q}_{\dot1A}$. Define the *creation* and *annihilation* operator as
$$
\begin{aligned}
a^A&\doteq\frac{1}{\sqrt{4E}}Q_1{}^A,\\
a^\dagger_A&\doteq\frac{1}{\sqrt{4E}}\bar{Q}_{\dot1A}.
\end{aligned}
$$
For massless particle, helicity $\lambda$ is an intrinsic character as mass. $a^A$ and $a^\dagger_A$ then raises and lower the halicity by $1/2$. From a "vacuum" state
$$
a^A\ket{\Omega;\lambda_0}=0,
$$
one can construct the representation by applying creation
$$
\ket{A_1,A_2,\cdots,A_n;\lambda_0+\frac{1}{2}n}\doteq\frac{1}{\sqrt{n!}}a^\dagger_{A_1}a^\dagger_{A_2}\cdots a^\dagger_{A_n}\ket{\Omega;\lambda_0}.
$$
Here also $n\leqslant N$ and therefore it's a $2^{N}$ dimensional representation with highest helicity $\lambda_0+N/2$.
