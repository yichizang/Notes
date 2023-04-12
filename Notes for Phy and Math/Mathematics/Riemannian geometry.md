---
banner: "![[../pics/102875535_p6.jpg]]"
banner_y: 0.492
---

>[!abstract]- Pre-knowledge
>- [[Differential geometry]]

# Riemannian geometry
## 1 Riemannian metrics
### 1.1 Definition of Riemannian metrics
The *Riemannian metrics* $g$ on a manifold $M$ is a bilinear form $g:T_pM\times T_pM\to\mathbb{R}$ for any $p\in M$ that satisfies the following.
- Symmetric, that is for all $X_p,Y_p\in T_pM$, there is $g(X_p,Y_p)=g(Y_p,X_p)$;
- Positive-definite, that is for all $X_p\in T_pM$, there is $g(X_p,X_p)\geqslant0$;
- Non-degenerate, that is for any $X_p\ne0$, there is a $Y_p\in T_pM$ that $g(X_p,Y_p)\ne0$.

If for any smooth $X,Y\in\mathfrak{X}(M)$, the map $p\mapsto g(X_p,Y_p)$ is also smooth, then $g$ is called *smooth*.

>[!note]+ Physicists' notation:
>The metrics map is $g_{ij}X^iY^j$.

>[!note]
>Note that in physics, a metrics isn't necessarily positive-definite. The number of negative eigenvalues of a metrics is called its *signature*.
>- In the case of positive-definite metrics, the manifold is called *Riemannian*.
>- When the signature is $1$, it is called *Lorentzian*.

### 1.2 Line element
The metrics can also be written in the form of *line element*
$$
\mathrm{d}s^2\doteq g_{ij}\mathrm{d}x^i\otimes\mathrm{d}x^j,
$$
where
$$
g_{ij}\doteq g\left(\frac{\partial}{\partial x^i},\frac{\partial}{\partial x^j}\right).
$$

Consider $g_{ij}$ as a matrix, then its inverse is denoted as $g^{ij}$. It satisfies
$$
g_{ij}g^{jk}=\delta^k_i.
$$

### 1.3 Isomorphism between cotangent and tangent vector
The metrics naturally induces an isomorphism between vector field and one-form
$$
\hat{g}:\mathfrak{X}(M)\cong\Omega^1(M)
$$
such that
$$
\hat{g}(X):Y\mapsto g(X,Y).
$$
This provides an isomorphism $T_pM\cong T_p^\ast M$. Under a local chart, this map can be written as
$$
X^i\frac{\partial}{\partial x^i}\mapsto g_{ij}X^i\mathrm{d}x^j.
$$
Its inverse map can also be written as
$$
\omega_i\mathrm{d}x^i\mapsto g^{ij}\omega_i\frac{\partial}{\partial x^j}.
$$

>[!note]+ Physicists' notation:
>The metrics can be used to lower/raise indices.
>- $g_{ij}X^j=X_i$;
>- $g^{ij}W_j=W^i$.

#### 1.3.1 Gradient vector field
For $f\in C^\infty(M)$, the *gradient vector field* of $f$ is the vector field mapped to $\mathrm{d}f$ by $\hat{g}$. That is to say
$$
\forall X\in\mathfrak{X}(M),\quad g(\mathrm{grad}\ f,X)=\mathrm{d}f(X)=X(f).
$$
It can be written under a local chart as
$$
\mathrm{grad}\ f=g^{ij}\frac{\partial f}{\partial x^i}\frac{\partial}{\partial x^j}.
$$

>[!note]+ Physicists' notation:
>$(\mathrm{grad}\ f)^i=g^{ij}\partial_jf$, sometimes also denoted simply as $\partial^if$.

### 1.4 Length
With the metrics defined, one can define the *length* of a tangent vector $X_p\in T_pM$ as
$$
|X_p|\doteq\sqrt{g(X_p,X_p)}.
$$
Therefore, for a curve $\gamma:(-1,1)\to M$, the length of the curve can be defined as
$$
L(\gamma)=\int_{-1}^1\mathrm{d}t\ |\dot{\gamma}(t)|=\int_{-1}^1\mathrm{d}t\sqrt{g_{ij}\frac{\mathrm{d}x^i}{\mathrm{d}t}\frac{\mathrm{d}x^j}{\mathrm{d}t}}.
$$

### 1.5 Vielbeins
Consider a set of basis $\{e_a\}$ of $T_pM$. If they satisfy
$$
g(e_a,e_b)=\delta_{ab},
$$
then this set of basis is called an *vielbein*. One can also define the corresponding set of basis $\{e^a\}$ of $T_p^\ast M$ as $e^a\doteq\hat{g}(e_a)$.

Write the vielbein under local chart $e_a=e_a^\mu\partial_\mu$ and $e^a=e^a_\mu\mathrm{d}x^\mu$. It satisfies
$$
e^\mu_ae^a_\nu=\delta^\mu_\nu,\quad e^\mu_ae^b_\mu=\delta^b_a.
$$

### 1.6 Killing vector field
For two Riemannian manifolds $(M,g)$ and $(N,h)$, a map $f:M\to N$ is called an *isometry* if it is a diffeomorphism and that $f^\ast h=g$, which means
$$
h(f_\ast X_p,f_\ast Y_p)=g(X_p,Y_p).
$$
For two isometries $f_1,f_2$, their composition $f_1\circ f_2$ is also an isometry. Therefore, the set of isometries forms an *isometry group*.

A vector field $X\in\mathfrak{X}(M)$ is called a *Killing vector field* if its flow is an isometry $\varphi_t^\ast g=g$, which means
$$
\mathcal{L}_Xg=0.
$$
This equation is called the *Killing equation*. When considering a local chart, it can be written as
$$
X^k\partial_kg_{ij}+g_{kj}\partial_iX^k+g_{ik}\partial_jX^k=0.
$$

## 2 Hodge theorem
### 2.1 Hodge $\ast$-operator
Define the *Hodge $\ast$-operator* as the map
$$
\begin{aligned}
\ast:&&\Omega^k(M)&\to\Omega^{n-k}(M)\\
&&e^1\wedge\cdots\wedge e^k&\mapsto e^{k+1}\wedge\cdots\wedge e^n.
\end{aligned}
$$
Apparently $\ast(\ast\omega)=-\omega$.

For a general $k$-form
$$
\omega=\sum_I\omega_I\ e^{i_1}\wedge\cdots\wedge e^{i_k},
$$
its Hodge $\ast$-operator is given as
$$
\ast\omega=\sum_I\mathrm{Sgn}(I,J)\ \omega_I\ e^{j_1}\wedge\cdots\wedge e^{j_{n-k}},
$$
where $J$ is the complement set of index of $I$. Another way is to write
$$
\omega=\sum_I\omega_I\ \mathrm{d}x^{i_1}\wedge\cdots\wedge\mathrm{d}x^{i_k}.
$$
Then the Hodge $\ast$ is given as
$$
(\ast\omega)_{I_2}=\frac{1}{k!\sqrt{\det g}}\epsilon^{J_1,J_2}\omega_{J_1}g_{J_2,I_2}.
$$

### 2.2 Volume form
One can define the *volume form*
$$
\mathrm{vol}\doteq\ast1=e^1\wedge\cdots\wedge e^n.
$$
On a local chart, this can be written as
$$
\mathrm{vol}=\sqrt{\det g_{ij}}\ \mathrm{d}x^1\wedge\cdots\wedge\mathrm{d}x^n.
$$

### 2.3 Laplace-Beltrami operator
Define the map $\delta:\Omega^k(M)\to\Omega^{k-1}(M)$ as
$$
\delta:\omega\mapsto(-1)^{nk+k+1}\ast\mathrm{d}\ \ast.
$$
Such a map satisfies
- $\delta^2=0$;
- $\ast\ \delta\ \mathrm{d}=\mathrm{d}\ \delta\ \ast$;
- $\delta\ast\mathrm{d}=\mathrm{d}\ast\delta=0$.

With $\delta$ and $\mathrm{d}$ defined, one can define the *Laplace-Beltrami operator* as
$$
\Delta\doteq\delta\mathrm{d}+\mathrm{d}\delta:\Omega^k(M)\to\Omega^k(M).
$$
A form $\omega$ that satisfies $\Delta\omega=0$ is called a *harmonic form*. In particular, $f\in C^\infty(M)$ that $\Delta f=0$ is called a *harmonic function*. One can prove that
$$
\Delta\omega=0\quad\Leftrightarrow\quad(\delta\omega=0)\lor(\mathrm{d}\omega=0).
$$

### 2.4 Inner product
Since Hodge $\ast$ maps a $k$-form to an $(n-k)$-form, $\omega\wedge\ast\omega$ is an $n$-form. Therefore, one can define a positive-defined inner product on $\Omega^k(M)$ as
$$
(\omega,\eta)\doteq\int_M\omega\wedge\ast\eta=\int_M\eta\wedge\ast\omega.
$$

Then the $\delta$ and $\mathrm{d}$ are adjoint operators under this inner product
$$
(\mathrm{d}\omega,\eta)=(\omega,\delta\eta).
$$
And the Laplace-Beltrami operator $\Delta$ is the self-adjoint operator
$$
(\Delta\omega,\eta)=(\omega,\Delta\eta).
$$

### 2.5 Hodge decomposition
Define the set of harmonic $k$-form as
$$
\mathbb{H}^k(M)\doteq\{\omega:\omega\in\Omega^k(M),\Delta\omega=0\}.
$$
The *Hodge decomposition* states that any

>[!warning]
>Not finished yet.

## 3 Connection and derivative
### 3.1 Connection
For two vector fields $X,Y\in\mathfrak{X}(M)$, one can define the *covariant derivative* of $Y$ on the flow of $X$ as the map
$$
\begin{aligned}
\nabla:&&\mathfrak{X}(M)\times\mathfrak{X}(M)&\to\mathfrak{X}(M)\\
&&(X,Y)&\mapsto\nabla_XY.
\end{aligned}
$$
It needs to satisfy the following.
- Linearity $\nabla_{fX+gY}Z=f\nabla_XZ+h\nabla_YZ$;
- Additivity $\nabla_X(Y+Z)=\nabla_XY+\nabla_XZ$;
- Leibnitz rule $\nabla_X(fY)=X(f)Y+f\nabla_XY$.

Such $\nabla$ is called a *connection*.

Under a local chart, it can be written as
$$
\nabla_{\partial_j}\partial_k=\Gamma^i{}_{jk}\partial_i,
$$
where the coefficient $\Gamma^i{}_{jk}$ is called the *Christoffel symbol*. Then for a general vector field, there is
$$
\nabla_XY=X^i\left(\frac{\partial Y^k}{\partial x^i}+\Gamma^k{}_{ij}Y^j\right)\frac{\partial}{\partial x^k}.
$$

>[!note]+ Physicists' notation:
>The covariant derivative is often simply written as $\nabla_iY^j=\dfrac{\partial Y^j}{\partial x^i}+\Gamma^j{}_{ik}Y^k$. In this way, the properties are acturally:
>- Linearity: $(fX^i+gY^i)\nabla_iZ^j=fX^i\nabla_iZ^j+gY^i\nabla_iZ^j$;
>- Additivity: -
>- Leibnitz rule: $X^i\nabla_i(fY^j)=X^i(\partial_if)Y^i+X^if(\nabla_iY^j)$.
>This can be viewed as a result of $\nabla_if=\partial_if$.

### 3.2 Derivative along the curve
For a curve $\gamma$, define the set of vector fields along the curve as $J(\gamma)$, then the *covariant derivative along $\gamma$* is defined as
$$
\frac{\mathrm{D}}{\mathrm{d}t}:J(\gamma)\to J(\gamma)
$$
that is linear and satisfies the Leibnitz rule.

For a vector field $X'\in J(\gamma)$ induced by a vector field $X\in\mathfrak{X}(M)$, there is
$$
\left.\frac{\mathrm{D}}{\mathrm{d}t}X'\right|_{t=0}=\left.\nabla_{\dot{\gamma}}X\right|_{\gamma(0)}.
$$
Under a local chart, one can write
$$
\frac{\mathrm{D}}{\mathrm{d}t}X=\left(\frac{\mathrm{d}X^k}{\mathrm{d}t}+\frac{\mathrm{d}x^i}{\mathrm{d}t}X^j\Gamma^k{}_{ij}\right)\frac{\partial}{\partial x^k}.
$$

>[!note]+ Physicists' notation:
>$(\mathrm{D}_\gamma X)^i=\dfrac{\mathrm{d}x^j}{\mathrm{d}t}\nabla_jX^i$.

### 3.3 Parallel transport
For a curve $\gamma$, a vector field $X\in\mathfrak{X}(M)$ is called a *parallel vector field* along $\gamma$ if it safisfies
$$
\frac{\mathrm{D}}{\mathrm{d}t}X=0.
$$
This can be written under a local chart as
$$
\frac{\mathrm{d}X^k}{\mathrm{d}t}+\frac{\mathrm{d}x^i}{\mathrm{d}t}X^j\Gamma^k{}_{ij}=0,
$$
which is a set of $n$ differential equations with $n$ unknowns. Then, given the initial condition $X(0)\in T_{\gamma(0)}M$, there is a unique solution $X\in J(\gamma)$. Such $X(t)$ is said to be obtained from $X(0)$ by *parallel transport* along curve $\gamma$.

### 3.4 Levi-Civita connection
For a Riemannian manifold $(M,g)$, there is a natural choice of connection that satisfies
- compatibility with metrics $Z(g(X,Y))=g(\nabla_ZX,Y)+g(X,\nabla_ZY)$;
- torsion free $\nabla_XY-\nabla_YX=[X,Y]$.

Such a connection is called the *Levi-Civita connection*.

>[!note]+ Physicists' notation:
>- Compatibility: $Z^k\partial_k(g_{ij}X^iY^j)=Z^kg_{ij}(\nabla_kX^i)Y^j+Z^kg_{ij}X^i(\nabla_kY^j)$
>or $\partial_kg_{ij}=g_{\ell j}\Gamma^\ell{}_{ki}+g_{i\ell}\Gamma^\ell{}_{kj}$;
>- Torsion free: $X^i\nabla_iY^j-Y^i\nabla_iX^j=X^i\partial_iY^j-Y^i\partial_iX^j$.

The Christoffel symbol of Levi-Civita connection is
$$
\Gamma^k{}_{ij}=\frac{1}{2}g^{k\ell}\left(\frac{\partial g_{j\ell}}{\partial x^i}+\frac{\partial g_{i\ell}}{\partial x^j}-\frac{\partial g_{ij}}{\partial x^\ell}\right).
$$

### 3.5 Geodesic
A curve $\gamma$ is called a *geodesic* if its tangent vector is parallel transported to itself with respect to Levi-Civita connection
$$
\frac{\mathrm{D}}{\mathrm{d}t}\dot{\gamma}=0.
$$

Under a local chart, this can be written as
$$
\frac{\mathrm{d}^2x^i}{\mathrm{d}t^2}+\Gamma^i{}_{jk}\frac{\mathrm{d}x^j}{\mathrm{d}t}\frac{\mathrm{d}x^k}{\mathrm{d}t}=0.
$$
This is the Eular-Lagrangian equation of the following action
$$
S=\int\mathrm{d}t\sqrt{g_{ij}\frac{\mathrm{d}x^i}{\mathrm{d}t}\frac{\mathrm{d}x^j}{\mathrm{d}t}},
$$
which is just the length of the curve.

## 4 Curvature
### 4.1 Curvature
The *curvature* of a connection $\nabla$ on $M$ is the map
$$
\begin{aligned}
R:&&\mathfrak{X}(M)\times\mathfrak{X}(M)\times\mathfrak{X}(M)&\to\mathfrak{X}(M)\\
&&(X,Y,Z)&\mapsto R(X,Y)Z
\end{aligned}
$$
such that
$$
R(X,Y)Z\doteq\nabla_X\nabla_YZ-\nabla_Y\nabla_XZ-\nabla_{[X,Y]}Z.
$$
This satisfies
- $R(X,Y)Z=-R(Y,X)Z$;
- $R(fX,gY)(hZ)=fgh\ R(X,Y)Z$.

Under a local chart, it can be written as
$$
R\left(\frac{\partial}{\partial x^i},\frac{\partial}{\partial x^j}\right)\frac{\partial}{\partial x^k}=R^l{}_{kij}\frac{\partial}{\partial x^l},
$$
where
$$
R^\ell{}_{kij}=\Gamma^s{}_{jk}\Gamma^\ell{}_{is}-\Gamma^s{}_{ik}\Gamma^\ell{}_{js}+\frac{\partial\Gamma^\ell{}_{jk}}{\partial x^i}-\frac{\partial\Gamma^\ell{}_{ik}}{\partial x^j}.
$$

The curvature comes from the fact that parallel transporting a vector along a closed curve does not necessarily comes back to itself.

### 4.2 Riemann curvature
The *Riemann curvature* is the curvature with respect to Levi-Civita connection. One can denote
$$
R(X,Y,Z,W)\doteq g(R(X,Y)Z,W).
$$
Under a local chart, this can be written as
$$
R(\partial_i,\partial_j,\partial_k,\partial_\ell)=R_{\ell kij}=R^s{}_{kij}g_{s\ell}.
$$

The Riemann curvature satisfies the following
- $R(X,Y,Z,W)=-R(Y,X,Z,W)$;
- $R(X,Y,Z,W)=-R(X,Y,W,Z)$;
- $R(X,Y,Z,W)=R(Z,W,X,Y)$;
- the first Bianchi identity $R(X,Y)Z+R(Y,Z)X+R(Z,X)Y=0$;
- the second Bianchi identity $\nabla_WR(X,Y)Z+\nabla_XR(Y,W)Z+\nabla_YR(W,X)Z=0$.

Under local chart, this is written as
- $R_{ijk\ell}=-R_{jik\ell}=-R_{ij\ell k}=R_{k\ell ij}$;
- $R^\ell{}_{ijk}+R^\ell{}_{jki}+R^\ell{}_{kij}=0$;
- $R^\ell{}_{kij;s}+R^\ell{}_{kjs;i}+R^\ell{}_{ksi;j}=0$.

### 4.3 Ricci and scalar curvature
The *Ricci curvature* is defined by contracting the first and the last index of Riemann curvature
$$
R_{ij}\doteq R^k{}_{ijk}=R_{\ell ijk}g^{\ell k}.
$$
If there is a constant $\Lambda$ that $R_{ij}=\Lambda g_{ij}$, then the manifold is called an *Einstein manifold*. An example of Einstein manifold is $S^2$.

The *scalar curvature* is defined by further contracting the index of Ricci curvature
$$
R\doteq R_{ij}g^{ij}.
$$

### 4.4 Gauss-Bonnet theorem
For a 2-dim oriented closed Riemannian manifold $(M,g)$, the *Gauss curvature* is defined as
$$
\kappa\doteq\frac{R_{1212}}{\det g}=\frac{1}{2}R.
$$
The *Gauss-Bonnet theorem* states that the integral of Gauss curvature is related to the Eular characteristics
$$
\frac{1}{2\pi}\int_M\mathrm{vol}\ \kappa=\chi(M).
$$
This is a great example of obtaining information of the global feature of the object (Eular characteristics) from local informations (curvature).