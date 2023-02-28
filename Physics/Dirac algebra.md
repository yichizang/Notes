---
banner: "![[../pics/90177237_p15.jpg]]"
banner_y: 0.304
---

>[!abstract]- Pre-knowledge
>- [[../Mathematics/Linear algebra|Linear algebra]]
>- [[../Mathematics/Matrix theory|Matrix theory]]

# Dirac algebra
## 1 Introduction
*Dirac algebra* is a subalgebra of Clifford algebra $\mathrm{Cl}_{1,3}(\mathbb{C})$. The basis of Dirac algebra is listed as follow.

| Type          | Element(s)                                                         |
| ------------- | ------------------------------------------------------------------ |
| Scalar        | $1_\gamma$                                                       |
| Vectors       | $\gamma^\mu:\{\gamma^\mu,\gamma^\nu\}=2\eta^{\mu\nu}\times1_\gamma$ |
| Pseudoscalar  | $\gamma^5\doteq i\gamma^0\gamma^1\gamma^2\gamma^3$                 |
| Pseudovectors | $\gamma^\mu\gamma^5$                                               |
| Tensors       | $\sigma^{\mu\nu}\doteq\dfrac{i}{2}[\gamma^\mu,\gamma^\nu]$         |

These $\gamma^\mu$ and $\gamma^5$ are also called *Dirac matrix*.

## 2 Properties
The multiplication of Dirac matrix satisfies
$$
(\gamma^\mu)^2=\eta^{\mu\mu}\times1_\gamma,\quad(\gamma^5)^2=1_\gamma.
$$

The (anti)commutators satisfy
$$
\{\gamma^5,\gamma^\mu\}=0,\quad[\gamma^5,\sigma^{\mu\nu}]=0.
$$

## 3 Trace
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

## 4 Contraction
The contraction of Dirac matrix satisfies
$$
\begin{aligned}
\gamma^\mu\gamma_\mu&=4\times1_\gamma,\\
\gamma^\mu\gamma^\nu\gamma_\mu&=-2\gamma^\nu,\\
\gamma^\mu\gamma^\rho\gamma^\sigma\gamma_\mu&=4g^{\rho\sigma}\times1_\gamma,\\
\gamma^\mu\gamma^\nu\gamma^\rho\gamma^\sigma\gamma_\mu&=-2\gamma^\sigma\gamma^\rho\gamma^\nu.
\end{aligned}
$$

## 5 Instance
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
\sigma^\mu&\doteq(\mathbb{1}_2,\pmb{\sigma}),\\
\bar{\sigma}^\mu&\doteq(\mathbb{1}_2,-\pmb{\sigma}).
\end{aligned}
$$
Here the $\pmb{\sigma}$ is the Pauli matrix, defined as
$$
\sigma^1\doteq\begin{pmatrix}
0 & 1\\
1 & 0
\end{pmatrix},\quad\sigma^2\doteq\begin{pmatrix}
i & 0\\
0 & -i
\end{pmatrix},\quad\sigma^3\doteq\begin{pmatrix}
1 & 0\\
0 & -1
\end{pmatrix}.
$$

In this way, the pseudoscalar $\gamma^5$ is
$$
\gamma^5\mapsto\begin{pmatrix}
-\mathbb{1}_2 & 0\\
0 & \mathbb{1}_2
\end{pmatrix}.
$$
