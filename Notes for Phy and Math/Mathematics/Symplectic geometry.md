---
banner: "![[../pics/90177237_p15.jpg]]"
banner_y: 0.332
---

>[!abstract]- Pre-knowledge
>- [[Differential geometry]]

# 1 Symplectic geometry
## 1 Symplectic manifold

>[!note]
>**Roughly speaking**, a [[Riemannian geometry#1 Riemannian metrics|Riemannian manifold]] $(M,g)$ is where *length* makes sense, and a Symplectic manifold $(M,\omega)$ is where *area* makes sense.

### 1.1 Symplectic form
For a smooth manifold $M$, a *symplectic form* is a non-degenerate closed 2-form $\omega\in\Omega^2(M)$. Here non-degenerate means that the map
$$
\begin{aligned}
\omega:&&\mathfrak{X}(M)&\to\Omega^1(M)\\
&&X&\mapsto i(X)\omega=2\omega(X,\cdot)
\end{aligned}
$$
is an isomorphism. Closed means that $\mathrm{d}\omega=0$. Such a manifold is even dimensional.

The couple $(M,\omega)$ is called a *symplectic manifold*. If $M$ is closed and $\dim M=2n$, then $\wedge^n\omega$ is the volume form of $M$.

### 1.2 Symplectic structure on $\mathbb{R}^{2n}$
Consider $\mathbb{R}^{2n}$ with standard coordinates $(x^1,\cdots,x^n,p_1,\cdots,p_n)$, then the 2-form
$$
\omega\doteq\sum_i\mathrm{d}p_i\wedge\mathrm{d}x^i
$$
is a symplectic form on $\mathbb{R}^{2n}$.

### 1.3 Darboux theorem
The *Darboux's theorem* states that for a $2n$-dimensional symplectic manifold $(M,\omega)$ and an arbitary point $p\in M$, there is always a local chart at $p$ $(x^1,\cdots,x^n,p_1,\cdots,p_n)$ that
$$
\omega=\sum_i\mathrm{d}p_i\wedge\mathrm{d}x^i.
$$
Such coordinate is called *Darboux coordinate*.

This theorem proves that the local behavior of symplectic manifold is trivial (same as $\mathbb{R}^{2n}$). Therefore, more interests lies in the global behavior.

### 1.4 Liouville 1-form
A symplectic manifold is called *exact* if there exists a 1-form $\theta$ such that $\omega=\mathrm{d}\theta$. This $\theta$ is called *Liouville 1-form*. The vector field $Z$ that satisfies
$$
i(Z)\omega=\theta
$$
is called the *Liouville vector field*.

>[!example]
>Consider a manifold $M$ with local coordinate $(x^1,\cdots,x^n)$ and its cotangent space with coordinates $(p_1,\cdots,p_n)$. A [[Differential geometry#1.3 Cotangent vector|cotangent bundle]] on $M$ is another manifold $T^\ast M$, with local coordinate $(x^1,\cdots,x^n,p_1,\cdots,p_n)$.
>Consider the Liouville 1-form 
>$$
>\theta=\sum_ip_i\mathrm{d}x^i.
>$$
>The corresponding
>$$
>\omega=\mathrm{d}\theta=\sum_i\mathrm{d}p_i\wedge\mathrm{d}x^i
>$$
>is a symplectic form on $T^\ast M$.

### 1.5 Symplectomorphism
A [[Differential geometry#1.1.3 Smooth map|diffeomorphism]] $\psi:M\to N$ between two symplectic manifold that satisfies
$$
\psi^\ast\omega_N=\omega_M
$$
is called a *symplectomorphism*.

For the symplectic manifold $(\mathbb{R}^{2n},\omega)$, define the *symplectic group* as a group consisting of symplectomorphisms
$$
\mathrm{Sp}(n,\mathbb{R})\doteq\{g\in\mathrm{GL}(2n,\mathbb{R}):g^TJg=J\},
$$
where
$$
J\doteq\begin{pmatrix}
0 & -\mathbb{1}_n\\
\mathbb{1}_n & 0
\end{pmatrix}.
$$

### 1.6 Moser stability theorem
The *Moser stability theorem* states that for a symplectic manifold $M$ with a 1-parameter family of symplectic forms $\omega_t$, there is a 1-parameter family of symplectomorphism $\psi_t:M\to M$ that
$$
\psi_t^\ast\omega_t=\omega_0,\quad\psi_0=1_M.
$$

This theorem means that one cannot change the symplectic form to certain degree.

### 1.7 Lagrangian submanifold
A *Lagrangian submanifold* is a submanifold $L\subset M$ of a symplectic manifold $(M,\omega)$ such that
$$
\omega|_L=0,\qquad\dim L=\frac{1}{2}\dim M.
$$
An example would be $\mathbb{R}^n=\{(x^1,\cdots,x^n)\}\subset\mathbb{R}^{2n}$.

The *Weinstein's tubular theorem* states that for any Lagrangian submanifold $L\subset M$, there is an open neighbourhood $U$ of $L$ such that $(U,\omega)$ is symplectomorphic to $(T^\ast L,\omega)$.

## 2 Hamiltonian system
### 2.1 Poisson bracket
For a scalar function $f\in C^\infty(M)$, one can define a vector field $X_f$ that satisfies
$$
-\mathrm{d}f=i(X_f)\omega=2\omega(X_f,\cdot).
$$
The *Poisson bracket* of two scalar fields $f,g\in C^\infty(M)$ is defined as
$$
\{f,g\}\doteq\omega(X_f,X_g)=-\frac{1}{2}X_g(f)=\frac{1}{2}X_f(g).
$$
Under the local chart where $\omega=\sum\mathrm{d}p_i\wedge\mathrm{d}x^i$, $X_f$ can be written as
$$
X_f=2\sum_i\left(\frac{\partial f}{\partial p_i}\mathrm{d}x^i-\frac{\partial f}{\partial x^i}\mathrm{d}p_i\right).
$$
Then the Poisson bracket is
$$
\{f,g\}=\frac{\partial f}{\partial p_i}\frac{\partial g}{\partial x^i}-\frac{\partial f}{\partial x^i}\frac{\partial g}{\partial p_i}.
$$

The Poisson bracket satisfies the following.
- $\{f,g\}=-\{g,f\}$;
- Jacobi identity: $\{f,\{g,h\}\}+\{g,\{h,f\}\}+\{h,\{f,g\}\}=0$;
- Leibniz rule: $\{fg,h\}=f\{g,h\}+g\{f,h\}$.

One can prove that
$$
[X_f,X_g]=X_{\{f,g\}}.
$$

### 2.2 Canonical equation
In classical mechanics, the Hamiltonian $H\in C^\infty(M)$ defines the *Hamiltonian vector field* $X_H$, which generates a flow $\varphi_t$. Then for a scalar function $f\in C^\infty(M)$, its derivative along the flow is given by
$$
\frac{\mathrm{d}f}{\mathrm{d}t}=\{H,f\}.
$$
As a special case, the local coordinate $(x^i,p_i)$ satisfies
$$
\begin{aligned}
&\frac{\mathrm{d}x^i}{\mathrm{d}t}=\frac{\partial H}{\partial p_i}\\
&\frac{\mathrm{d}p_i}{\mathrm{d}t}=-\frac{\partial H}{\partial x^i}.
\end{aligned}
$$
This is called the *canonical equation*.

Especially when $\{f,H\}=0$, the function $f$ is a constant along the flow
$$
\frac{\mathrm{d}f}{\mathrm{d}t}=\{H,f\}=0.
$$
This is called the *Noether theorem*.

### 2.3 Integrable system
A set of functions $\{H_i\}$ that satisfies
$$
\mathrm{d}H_1\wedge\cdots\wedge\mathrm{d}H_k\ne0
$$
is called *analytically independent*. For a $2n$-dimensional symplectic manifold, the maximum size of a set of analytically independent that are also Poisson commute $\{H_i,H_j\}=0$ is $n$. Such a manifold is called a *completely integrable system*.

For such a completely integrable system, the (compact connected component of) preimage of any non-singular point of map
$$
\pi\doteq(H_1,\cdots,H_n):M\to\mathbb{R}^n
$$
is a Lagrangian submanifold that is diffeomorphic to a torus $T^n$. This is the *Arnold-Liouville theorem*.

### 2.4 Angle-action coordinate
For the preimage $L\doteq\pi^{-1}(p)\cong T^n$ of point $p$, one can take the angle coordinate
$$
(\phi_1,\cdots,\phi_n):L\to T^n
$$
where each $\phi_i$ runs from $0$ to $2\pi$. This is a set of coordinate on the Lagrangian submanifold $L$. One can further take the local chart $(\phi_1,\cdots,\phi_n,I_1,\cdots,I_n)$ so that the symplectic form becomes
$$
\omega=\sum_i\mathrm{d}I_i\wedge\mathrm{d}\phi_i,
$$
where on each $L$ the $I_i$ are constants. Such coordinate is called *angle-action coordinate*.

The integral of the Liouville 1-form on $L$ satisfies
$$
\frac{1}{(2\pi)^n}\int_L\theta=\frac{1}{(2\pi)^n}\int_L\sum_iI_i\mathrm{d}\phi_i=\sum_iI_i.
$$
