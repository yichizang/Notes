---
banner: "![[../pics/db4c51d13f2e0bf97d85f466913918c21660752419469.jpeg]]"
banner_y: 0.268
---

>[!abstract]- Pre-knowledge
>- [[Abstract group theory]]
>- [[Topology]]

# Differential geometry
## 1 Introduction
### 1.1 Euler characteristic
For a topological object $P$, the Euler characteristic $\chi$ is
$$
\chi(P)\doteq V-E+F,
$$
where $V,E,F$ are numbers of vertices, edges and faces respectively. This Euler characteristic is a topological invarient. For a sphere $S^2$ and a torus $T^2$, its value is
$$
\chi(S^2)=2,\quad\chi(T^2)=0.
$$

### 1.2 Index of vector field
Consider a smooth vector field on a sphere $S^2$ that flows from the north pole to the south pole.

### 1.3 A fancy example by Witten
Consider the integral
$$
Z=\int^{+\infty}_{-\infty}\frac{\mathrm{d}x}{\sqrt{2\pi}}\exp\left[-\frac{1}{2}s^2(x)\right]\frac{\mathrm{d}s}{\mathrm{d}x}.
$$
After doing a change of variable, one can see that the value of $Z$ only depends on the behavior of $s(x)$ at $x\to\pm\infty$. For instance, when $s(x)\to+\infty$ at both $x\to\pm\infty$, the integral vanishes as
$$
Z=\int^{+\infty}_{+\infty}\frac{\mathrm{d}s}{\sqrt{2\pi}}\exp\left[-\frac{1}{2}s^2\right]=0.
$$
On the other hand, when $s(x)\to\pm\infty$ as $x\to\pm\infty$, the integral becomes
$$
Z=\int^{+\infty}_{-\infty}\frac{\mathrm{d}s}{\sqrt{2\pi}}\exp\left[-\frac{1}{2}s^2\right]=1.
$$
Etc.

Since the value of $Z$ only depend on the asymptotic behavior of $s(x)$, multiplying a constant $t$ onto $s(x)$ won't change $Z$. Then by putting $t\to\infty$ one gets
$$
Z=\int^{+\infty}_{-\infty}\frac{\mathrm{d}x}{\sqrt{2\pi}}\exp\left[-\frac{1}{2}t^2s^2(x)\right]t\frac{\mathrm{d}s}{\mathrm{d}x}.
$$
The value of the exponential vanishes everywhere except for $s(x)=0$. Actually the kernal forms a $\delta$ function. Thus the value of the integration becomes
$$
Z=\sum_{x_0:s(x_0)=0}\mathrm{sign}\left.\frac{\mathrm{d}s}{\mathrm{d}x}\right|_{x_0}.
$$
This result is localized to the zero points of $s(x)$. This is a similar behavior as a topological invarient.

---
## 2 Manifold
### 2.1 Manifold
For a [[Topology#1.6 Hausdorff space|Hausdorff space]] $M$, it is called an $n$-dimensional *smooth manifold* if it satisfies
- $M=\bigcup_iU_i$ being an [[Topology#1.1 Topological space|open covering]];
- there being a [[Topology#1.2 Continuous map and homeomorphism|continuous]] and invertible map $\varphi_i:U_i\to\mathbb{R}^n$ that maps each $U_i$ to an open subset of $\mathbb{R}^n$;
- for all $i,j$, $\varphi_i(U_i\cap U_j)$ is also open in $\mathbb{R}^n$ and the map $\varphi_i\circ\varphi_j^{-1}$ is smooth.

Here $(U_i,\varphi_i)$ is called a *coordinate chart* and the set $\{(U_i,\varphi_i)\}$ is called an *atlas*. One can write $\varphi_i$ as
$$
\varphi_i=(x^1,x^2,\cdots,x^n),
$$
where each $x^j:U_i\to\mathbb{R}$ is called *local coordinate*.

### 2.2 Submanifold
For an $n$-dimensional manifold $M$, a subset $N\subset M$ is called a *submanifold* if it satisfies that for any $p\in N$, there is a coordinate chart $(U,\varphi)$ that $p\in U$ and
$$
N\cap U=\{q\in U:x^{m+1}(q)=\cdots=x^n(q)=0\}.
$$
$N$ itself is an $m$-dimensional manifold. Sometimes $N$ is called a submanifold of *codimension* $n-m$ in $M$.