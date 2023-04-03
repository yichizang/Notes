---
banner: "![[../pics/d5ac70a9eea9c232c577e30963ac163d1647968603962.jpeg]]"
banner_y: 0.648
---

>[!abstract]- Pre-knowledge
>- [[../Mathematics/Differential geometry|Differential geometry]]
>- [[../Mathematics/Riemannian geometry|Riemannian geometry]]

# Physicists' notation for Riemannian Geo
## 1 Tangent/cotangent vectors
The [[../Mathematics/Differential geometry#1.2.1 Tangent vector|tangent]] or *contravariant* vectors are denoted with upper indices
$$
V^i
$$
and [[../Mathematics/Differential geometry#1.3.1 Cotangent space|cotangent]] or *covariant* vectors are denoted with lower indices
$$
W_i.
$$
Especially, $\mathrm{d}f$ is denoted as
$$
\frac{\partial f}{\partial x^i}.
$$

The map of tangent vector $V:C^\infty(M)\to C^\infty(M)$ is
$$
f\mapsto V^i\partial_if.
$$
The map of cotangent vector $W:\mathfrak{X}(M)\to C^\infty(M)$ is
$$
V^i\mapsto V^iW_i.
$$
In the special case, the map of $\mathrm{d}f$ is
$$
V^i\mapsto V^i\frac{\partial f}{\partial x^i}.
$$

## 2 Metrics
The [[../Mathematics/Differential geometry#3.2.1 Definition of Riemannian metrics|metrics]] maps
$$
(V^i,W^i)\mapsto g_{ij}V^iW^i.
$$
Its inverse satisfies
$$
g^{ij}g_{jk}=\delta^i{}_k.
$$

The metrics can be used to lower/raise indices
$$
g_{ij}V^j=V_i,\quad g^{ij}W_j=W^i.
$$
For instance, the [[../Mathematics/Differential geometry#3.2.4 Isomorphism between cotangent and tangent vector|gradiant]] is $\mathrm{d}f$ with index raised.

## 3 Covariant derivative
The [[../Mathematics/Differential geometry#4.1.1 Connection|covariant derivative]] is denoted as
$$
\nabla_iY^j=\frac{\partial Y^j}{\partial x^i}+\Gamma^j{}_{ik}Y^k.
$$
It acting on cotangent vectors and scalars as
$$
\begin{aligned}
\nabla_i W_j&=\frac{\partial W_j}{\partial x^i}+\Gamma^k{}_{ij}W_k,\\
\nabla_if&=\frac{\partial f}{\partial x^i}.
\end{aligned}
$$
Also $\nabla_ig_{jk}=0$, which means
$$
\partial_ig_{jk}=
$$