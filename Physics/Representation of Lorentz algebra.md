---
banner: "![[../pics/578352d4226c4fedd5721e6e5f0a1c311670647902276.jpeg]]"
banner_y: 0.42
---

>[!abstract]- Pre-knowledge
>- Lie algebra
>- [[../Mathematics/Abstract group theory|Abstract group theory]]
>- [[Dirac algebra]]

# Representation of Lorentz algebra
## 1 Poincare group
### 1.1 Poincare group
The *Poincare group* is the group of transformations that preserve the Minkowski matrix $\eta_{\mu\nu}$. An element of Poincare group is in the form of
$$
x^\mu\to\Lambda^\mu{}_\nu x^\nu+a^\nu,
$$
where $\Lambda^\mu{}_\nu$ is the Lorentz transformation matrix and $a^\mu$ is a displacement. One can denote such an element as $T(\Lambda,a)$.

### 1.2 Lorentz group
The subgroup of Poincare group with $a^\mu=0$ is called *Lorentz group*, denoted as $O(1,3)$. It has four disconnected branches.

The branch with $\det\Lambda=1$ and $\Lambda^0{}_0\geqslant1$ is a subgroup called the *restricted Lorentz group*, denoted as $SO(1,3)$. It's group elements are Lorentz transformations that preserve the time direction and space orientation. Sometimes one simply refer to $SO(1,3)$ as Lorentz group.

### 1.3 Lorentz Lie algebra
An infinitesimal Poincare transformation $T(\Lambda,a)$ can be written as
$$
T(\Lambda,a)=\exp\left(\frac{i}{2}\omega_{\mu\nu}J^{\mu\nu}-ia_\mu P^\mu\right)=1+\frac{i}{2}\omega_{\mu\nu}J^{\mu\nu}-ia^\mu P^\mu.
$$
Therefore, the generators of Pincare transformation are $J^{\mu\nu}$ and $P^\mu$. They form the *Poincare Lie algebra*. Through multiplication rules of Poincare group, one can work out the structure constant of Poincare Lie algebra
$$
\begin{aligned}[]
[J^{\mu\nu},J^{\rho\sigma}]&=i(\eta^{\nu\rho}J^{\mu\sigma}-\eta^{\mu\rho}J^{\nu\sigma}-\eta^{\nu\sigma}J^{\mu\rho}+\eta^{\mu\sigma}J^{\nu\rho}),\\
[P^\mu,J^{\rho\sigma}]&=i(\eta^{\mu\rho}P^\sigma-\eta^{\mu\sigma}P^\rho),\\
[P^\mu,P^\nu]&=0.
\end{aligned}
$$

When considering only generators of Lorentz transformation $J^{\mu\nu}$, the result is called the *Lorentz Lie algebra*, denoted as $\mathfrak{so}(1,3)$.

---
## 2 Representation of $\mathfrak{so}(1,3)$
### 2.1 Structure of $\mathfrak{so}(1,3)$
Since the indices of $J^{\mu\nu}$ are anticommutating, one can define
$$
J_i\doteq\frac{1}{2}\epsilon_{ijk}J^{jk},\quad K_i\doteq J^{0i}.
$$
Then the commutation relation becomes
$$
[J_i,J_j]=i\epsilon_{ijk}J_k,\quad[J_i,K_j]=i\epsilon_{ijk}K_k,\quad[K_i,K_j]=-i\epsilon_{ijk}J_k.
$$
If one further define
$$
M_i\doteq\frac{1}{2}(J_i+iK_i),\quad N_i\doteq\frac{1}{2}(J_i-iK_i),
$$
then the commutation relations become
$$
[M_i,M_j]=i\epsilon_{ijk}M_k,\quad[N_i,N_j]=i\epsilon_{ijk}N_k,\quad[M_i,N_j]=0.
$$
This implies that $M_i$ and $N_i$ generates an $\mathfrak{su}(2)$ subalgebra respectively. Therefore one can write
$$
\mathfrak{so}(1,3)=\mathfrak{su}(2)\oplus\mathfrak{su}(2).
$$
Note that there are actually some ambiguity about complexation of $\mathfrak{so}(1,3)$ here.

### 2.2 Irreducible representations of $\mathfrak{su}(2)$
An irreducible representation of $\mathfrak{su}(2)$ is a representation on the vector space spanned by $\ket{j,m}$. The Casimir operator $J^2$ acting on $\ket{j,m}$ gives
$$
J^2\ket{j,m}=j(j+1)\ket{j,m}.
$$
The dimension of such a representation is $2j+1$.

The number $j$ here is used to lable different representations here
$$
(j_1,j_2)\doteq(j_1)_{\mathfrak{su}(2)}\otimes(j_2)_{\mathfrak{su}(2)}.
$$

>[!warning]
>This section requires perfection.

### 2.3 Scalar representation
The trivial representation $(0,0)$ is also called the *scalar representation* of $\mathfrak{so}(1,3)$. It corresponds to the Lorentz scalar which is invarient under Lorentz transformation.

### 2.4 Spinor representation
The representation $(1/2,0)$ and $(0,1/2)$ are also called *spinor representation*. The corresponding vectors are called *left/right handed Weyl spinor* respectively. The generator of Lorentz transformation under this two representations are
$$
S^{ij}\doteq\frac{1}{2}\epsilon^{ijk}\sigma^k,\quad S^{0i}_L\doteq-\frac{i}{2}\sigma^i,\quad S^{0i}_R\doteq\frac{i}{2}\sigma^i.
$$

The direct sum of these two representations is also a commenly used representation