---
banner: "![[../pics/90177237_p15.jpg]]"
banner_y: 0.304
---

>[!abstract]- Pre-knowledge
>- [[../Mathematics/Linear algebra|Linear algebra]]
>- [[../Mathematics/Matrix theory|Matrix theory]]
>- [[Representation of Lorentz algebra]]

# Dirac algebra
## 1 Introduction
*Dirac algebra* is a subalgebra of Clifford algebra $\mathrm{Cl}_{1,3}(\mathbb{C})$. The basis of Dirac algebra is listed as follow.

| Type          | Element(s)                                                           | Total number |
| ------------- | -------------------------------------------------------------------- | ------------ |
| Scalar        | $1_\gamma$                                                           | $1$          |
| Vectors       | $\gamma^\mu:\{\gamma^\mu,\gamma^\nu\}=-2\eta^{\mu\nu}\times1_\gamma$ | $4$          | 
| Pseudo-scalar  | $\gamma^5\doteq i\gamma^0\gamma^1\gamma^2\gamma^3$                   | $1$          |
| Pseudo-vectors | $\gamma^\mu\gamma^5$                                                 | $4$          |
| Tensors       | $\sigma^{\mu\nu}\doteq\dfrac{i}{2}[\gamma^\mu,\gamma^\nu]$           | $6$          |

The $\gamma^\mu$ and $\gamma^5$ are also called *Dirac matrix*.

## 2 Calculation rules
### 2.1 Fierz identity
Denote the 16 elements as $\Gamma^i$. They form a complete basis of $4\times 4$ matrix with two [[Representation of Lorentz algebra#2.2.1 Dirac spinor|Dirac spinor]] indices. That is
$$
\Gamma=\sum_iA_i\Gamma^i.
$$
There is also the orthogonality relation
$$
\mathrm{Tr}(\Gamma^i\Gamma^j)=4\delta^{ij}.
$$
Therefore, one have
$$
\Gamma=\sum_i\mathrm{Tr}(\Gamma\Gamma^i)\Gamma^i,
$$
which is called the *Fierz identity*.

### 2.2 Multiplication
The multiplication of Dirac matrix satisfies
$$
(\gamma^\mu)^2=-\eta^{\mu\mu}\times1_\gamma,\quad(\gamma^5)^2=1_\gamma.
$$
Therefore, when considering Dirac matrics as linear operators, the eigenvalue of $\gamma^0$ is $\pm1$ and that of $\gamma^i$ is $\pm i$. Then one can require
$$
(\gamma^0)^\dagger=\gamma^0,\quad(\gamma^i)^\dagger=-\gamma^i,\quad(\gamma^5)^\dagger=\gamma^5.
$$

The (anti)commutators satisfy
$$
\{\gamma^5,\gamma^\mu\}=0,\quad[\gamma^5,\sigma^{\mu\nu}]=0.
$$

### 2.3 Trace
The trace of Dirac matrix satisfies
$$
\mathrm{Tr}(1_\gamma)=4,\quad\mathrm{Tr}(\gamma^\mu)=\mathrm{Tr}(\gamma^5)=0.
$$

Using the above trace rule and the multiplication relations, one can have the following trace rules
$$
\begin{aligned}
\mathrm{Tr}(\gamma^\mu\gamma^\nu)&=4\eta^{\mu\nu},\\
\mathrm{Tr}(\gamma^\mu\gamma^\nu\gamma^\rho\gamma^\sigma)&=4(\eta^{\mu\nu}\eta^{\rho\sigma}-\eta^{\mu\rho}\eta^{\nu\sigma}+\eta^{\mu\sigma}\eta^{\nu\rho}),\\
\mathrm{Tr}(\text{even num of }\gamma)&=0,\\
\mathrm{Tr}(\gamma^\mu\gamma^\nu\gamma^5)&=0,\\
\mathrm{Tr}(\gamma^\mu\gamma^\nu\gamma^\rho\gamma^\sigma\gamma^5)&=-4i\epsilon^{\mu\nu\rho\sigma},\\
\mathrm{Tr}(\gamma^\mu\gamma^\nu\gamma^\rho\gamma^\sigma\cdots)&=\mathrm{Tr}(\cdots\gamma^\sigma\gamma^\rho\gamma^\nu\gamma^\mu).
\end{aligned}
$$

### 2.4 Contraction
The contraction of Dirac matrix satisfies
$$
\begin{aligned}
\gamma^\mu\gamma_\mu&=4\times1_\gamma,\\
\gamma^\mu\gamma^\nu\gamma_\mu&=-2\gamma^\nu,\\
\gamma^\mu\gamma^\rho\gamma^\sigma\gamma_\mu&=4g^{\rho\sigma}\times1_\gamma,\\
\gamma^\mu\gamma^\nu\gamma^\rho\gamma^\sigma\gamma_\mu&=-2\gamma^\sigma\gamma^\rho\gamma^\nu.
\end{aligned}
$$

### 2.5 Similarity transformation
There is the following similarity trandformation relation
$$
\begin{aligned}
\mathcal{B}\gamma_\mu\mathcal{B}^{-1}&=(\gamma_\mu)^\dagger\\
\gamma^5\gamma_\mu(\gamma^5)^{-1}&=-\gamma_\mu\\
\mathcal{C}\gamma_\mu\mathcal{C}^{-1}&=-(\gamma_\mu)^T\\
\mathcal{BC}\gamma_\mu(\mathcal{BC})^{-1}&=-(\gamma_\mu)^\ast,
\end{aligned}
$$
where $\mathcal{B}=\gamma^0$ and $\mathcal{C}$ satisfies $\mathcal{CC}^\dagger=1_\gamma$ and $\mathcal{C}=-\mathcal{C}^T$. $\mathcal{C}$ is called *charge conjugation matrix*. In 4 dimensional case, $\mathcal{BC}=i\gamma^2$.

## 3 Lorentz transformation
There is an important identity for the Lorentz transformation of Dirac matrix
$$
(\Lambda_{\frac{1}{2}}^{-1})^a{}_b(\gamma^\mu)^b{}_c(\Lambda_{\frac{1}{2}})^c{}_d=\Lambda^\mu{}_\nu(\gamma^\nu)^a{}_d.
$$
This shows that the Dirac matrix has one vector index and two (inverse) spinor indices, which means that the Dirac matrix as a whole is invarient under Lorentz transformation.

## 4 Instance
An instance of Dirac matrix is
$$
\gamma^\mu\mapsto\begin{pmatrix}
0 & \sigma^\mu\\
\bar{\sigma}^\mu & 0
\end{pmatrix},
$$
where the $\sigma^\mu$ and $\bar{\sigma}^\mu$ are defined as
$$
\begin{aligned}
\sigma^\mu&\doteq(-\mathbb{1}_2,\pmb{\sigma}),\\
\bar{\sigma}^\mu&\doteq(-\mathbb{1}_2,-\pmb{\sigma}).
\end{aligned}
$$
Here the $\pmb{\sigma}$ is the Pauli matrix, defined as
$$
\sigma^1\doteq\begin{pmatrix}
0 & 1\\
1 & 0
\end{pmatrix},\quad\sigma^2\doteq\begin{pmatrix}
0 & -i\\
i & 0
\end{pmatrix},\quad\sigma^3\doteq\begin{pmatrix}
1 & 0\\
0 & -1
\end{pmatrix}.
$$

In this way, the pseudo-scalar $\gamma^5$ is
$$
\gamma^5\mapsto\begin{pmatrix}
\mathbb{1}_2 & 0\\
0 & -\mathbb{1}_2
\end{pmatrix}.
$$
The charge conjugation matrix is
$$
\mathcal{C}\mapsto\begin{pmatrix}
0 & 1 & 0 & 0\\
-1 & 0 & 0 & 0\\
0 & 0 & 0 & -1\\
0 & 0 & 1 & 0
\end{pmatrix}.
$$
