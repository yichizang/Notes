---
banner: "![[../pics/db4c51d13f2e0bf97d85f466913918c21660752419469.jpeg]]"
banner_y: 0.268
---

>[!abstract]- Pre-knowledge
>- [[Abstract group theory]]
>- Lie group and Lie algebra
>- [[Topology]]

# Differential geometry
## 1 Manifold
### 1.1 Basic concepts
#### 1.1.1 Manifold
For a [[Topology#1.6 Hausdorff space|Hausdorff space]] $M$, it is called an $n$-dimensional *smooth manifold* if it satisfies
- $M=\bigcup_iU_i$ being an [[Topology#1.2 Open covering|open covering]];
- there being a set of [[Topology#1.2 Continuous map and homeomorphism|continuous]] and invertible map $\varphi_i:U_i\to\mathbb{R}^n$ that maps each $U_i$ to an open subset of $\mathbb{R}^n$;
- for all $i,j$, $\varphi_i(U_i\cap U_j)$ is also open in $\mathbb{R}^n$ and the map $\varphi_i\circ\varphi_j^{-1}$ is smooth.

Here $(U_i,\varphi_i)$ is called a *coordinate chart* and the set $\{(U_i,\varphi_i)\}$ is called an *atlas*. One can write $\varphi_i$ as
$$
\varphi_i=(x^1,x^2,\cdots,x^n),
$$
where each $x^j:U_i\to\mathbb{R}$ is called *local coordinate*.

#### 1.1.2 Submanifold
For an $n$-dimensional manifold $M$, a subset $N\subset M$ is called a *submanifold* if it satisfies that for any $p\in N$, there is a coordinate chart $(U,\varphi)$ that $p\in U$ and
$$
N\cap U=\{q\in U:x^{m+1}(q)=\cdots=x^n(q)=0\}.
$$
$N$ itself is an $m$-dimensional manifold. Sometimes $N$ is called a submanifold of *codimension* $n-m$ in $M$.

#### 1.1.3 Smooth map
For an $m$-dimensional manifold $M$ and an $n$-dimensional manifold $N$, a map $f:M\to N$ is *smooth* at point $p\in M$ if for any chart $(U,\varphi)$ that $p\in U$ and the chart $(V,\psi)$ at $f(p)\in V$, the map
$$
\psi\circ f\circ\varphi^{-1}:\varphi(U\cap f^{-1}(V))\to\psi(V)
$$
is smooth at $\varphi(p)$. A map is called a *smooth map* if it is smooth at any point $p\in M$.

If a smooth map between two manifolds with same dimensionality has a smooth inverse, then it is called a *diffeomorphism*.

For a smooth map $f:M\to N$, its *graph* is defined as the set
$$
\Gamma_f\doteq\{(x,f(x)):x\in M\}\subset M\times N.
$$
This is also a manifold with dimension $\dim M$.

#### 1.1.4 Boundary of manifold
Define the *upper half space* of $\mathbb{R}^n$ as
$$
\mathbb{H}^n\doteq\{(x^1,x^2,\cdots,x^n):x^n\geqslant0\}
$$
and its *boundary* is defined as
$$
\partial\mathbb{H}^n\doteq\{(x^1,\cdots,x^n):x^n=0\}.
$$

A *manifold with boundary* is a manifold $M$ with an open covering $\{U_i\}$ equipped with a set of continous invertible maps
$$
\varphi_i:U_i\to\mathbb{H}^n
$$
that maps each $U_i$ to an open subset of $\mathbb{H}^n$, and for all $i,j$, $\varphi_i(U_i\cap U_j)$ is also open in $\mathbb{H}^n$ and the map $\varphi_i\circ\varphi_j^{-1}$ is smooth. The *boundary* of $M$ is defined as the set of points mapped to $\partial\mathbb{H}^n$
$$
\partial M\doteq\{p\in M:\forall\varphi_i,\varphi_i(p)\in\partial\mathbb{H}^n\}.
$$
$\partial M$ is an $(n-1)$-dimensional submanifold of $M$.

>[!note]+
>The above definition is basically replacing $\mathbb{R}^n$ to $\mathbb{H}^n$ in the definition of manifold.

A [[Topology#1.3 Compactness|compact]] manifold $M$ is called *closed* if $\partial M=\varnothing$.

### 1.2 Vector
#### 1.2.1 Tangent vector
A *curve* in a manifold $M$ is a map
$$
\begin{aligned}
\gamma:&&(-1,1)&\to M\\
&&t&\mapsto\gamma(t).
\end{aligned}
$$

Denote the set of all smooth map $f:M\to\mathbb{R}$ as $C^\infty(M)$. A *tangent vector* at $p\in M$ is a map
$$
X_p:C^\infty\to\mathbb{R}
$$
that satisfies the following.
- For all $\alpha,\beta\in\mathbb{R}$ and $f,g\in C^\infty$, $X_p(\alpha f+\beta g)=\alpha X_p(f)+\beta X_p(g)$;
- Leibniz rule $X_p(f\circ g)=f(p)X_p(g)+g(p)X_p(f)$.

Considering a curve $\gamma$ that $\gamma(0)=p$, a corresponding tangent vector $X_p$ is
$$
X_p:f\mapsto\left.\frac{\mathrm{d}}{\mathrm{d}t}(f(\gamma(t)))\right|_{t=0}.
$$
Such a tangent vector is also denoted as $\dot{\gamma}(0)$.

>[!note]+ Physicists' notation:
>A vector $V$ acting on a scalar $f$ is $V^i\partial_if$.

#### 1.2.2 Tangent space
The set of tangent vectors at point $p$ forms a [[Linear algebra#1.1 Definition|vector space]], which is called the *tangent space* at $p$, denoted as $T_pM$. Considering a chart $(U,\varphi=(x^1,\cdots,x^n))$ at $p\in U$, one can define the following tangent vector
$$
\frac{\partial}{\partial x^i}:f\mapsto\left.\frac{\partial}{\partial\xi^i}\left(f(\varphi^{-1}(\xi))\right)\right|_{\xi=\varphi(p)}.
$$
It can be proved that this forms a [[Linear algebra#1.4 Linear dependence and basis|basis]] of $T_pM$ and therefore one can decomposite a tangent vector $X_p$ correponding to a curve $\gamma$ into
$$
X_p=\sum_iX_p^i\frac{\partial}{\partial x^i},\quad X_p^i=\left.\frac{\mathrm{d}}{\mathrm{d}t}\left(x^i(\gamma(t))\right)\right|_{t=0}.
$$
For another coordinate $\psi=(y^1,\cdots,y^n)$, the basis transforms as
$$
\frac{\partial}{\partial y^i}=\sum_j\frac{\partial x^j}{\partial y^j}\frac{\partial}{\partial x^j},
$$
where the matrix $\partial x^j/\partial y^i$ is called the *Jacobian* at $p$.

>[!note]+ Physicists' notation:
>A vector $V$ transforms as $V^i(y)=\dfrac{\partial y^i}{\partial x^j}V^j(x)$.

#### 1.2.3 Tangent bundle
The union of tangent spaces at each point of $M$ forms a *tangent bundle*
$$
TM\doteq\bigcup_{p\in M}\{T_pM\}=\{(p,X_p):p\in M,X_p\in T_pM\}.
$$
The tangent bundle is also a manifold, and there exists a natural map
$$
\begin{aligned}
\pi:&&TM&\to M\\
&&(p,X_p)&\mapsto p,
\end{aligned}
$$
which is a smooth map.

#### 1.2.4 Vector field
A smooth map
$$
\begin{aligned}
X:&&M&\to TM\\
&&p&\mapsto (p,X_p)
\end{aligned}
$$
is called a *(smooth) vector field* on $M$. It is also called the *section* of $TM$ since $\pi\circ X=1_M$. The set of all smooth vector fields is denoted as $\mathfrak{X}(M)$.

A formal definition of a smooth vector field would be a map
$$
X:C^\infty(M)\to C^\infty(M)
$$
that satisfies the following.
- For all $\alpha,\beta\in\mathbb{R}$ and $f,g\in C^\infty(M)$, $X(\alpha f+\beta g)=\alpha X(f)+\beta X(g)$;
- Leibniz rule $X(fg)=fX(g)+X(f)g$.

>[!note]+ Physicists' notation:
>Leibniz rule: $X^i\partial_i(fg)=X^i(\partial_if)g+X^if(\partial_ig)$.

To understand the second definition, note that the map can be written as
$$
X:f\mapsto X_{(\cdot)}(f).
$$

One can prove that $\mathfrak{X}(M)$ forms a Lie algebra with the Lie bracket
$$
[X,Y]\doteq X\circ Y-Y\circ X.
$$

>[!note]+ Physicists' notation:
>$[X,Y]^i=X^k(\partial_kY^i)-Y^k(\partial_kX^i)$.

#### 1.2.5 Flow
An *integral curve* of a vector field $X\in\mathfrak{X}(M)$ is a smooth curve $\gamma:(a,b)\to M$ that for any point on the curve $\gamma(t)$, there is
$$
\dot{\gamma}(t)=X_{\gamma(t)}.
$$
One can prove that there always exists a unique solution of an integral curve on a sufficiently small interval $(-\epsilon,\epsilon)$ with $\gamma(0)=p$. Denote the point $\gamma(t)$ on such curve as $\gamma_t(p)$.

If such a $\gamma$ is defined for any $t\in\mathbb{R}$, then $X$ is called *complete*. One can prove that any vector field on a compact smooth manifold is complete. In this case, the map
$$
\begin{aligned}
\gamma:&&\mathbb{R}\times M&\to M\\
&&(t,p)&\mapsto\gamma_t(p)
\end{aligned}
$$
which satisfies $\gamma_{t+s}(p)=\gamma_t(\gamma_s(p))$ is called a *flow* or *one-parameter group of diffeomorphisms*.

#### 1.2.6 Orientation
For two sets of basis $\{\partial/\partial x^i\}$ and $\{\partial/\partial y^i\}$ of a tangent space with fixed order, one can define an [[Set theory#1.3.4 Equivalence relation|equivalence relation]]
$$
\{\partial/\partial x^i\}\sim\{\partial/\partial y^i\}\Leftrightarrow\det\frac{\partial x^i}{\partial y^j}>0.
$$
Two sets of basis are of same *orientation* if they are in the same equicalence class.

For a manifold $M$, if there exists an atlas $\{U_i,\varphi_i\}$ such that for any $p\in U_i\cap U_j$, the basis of $T_pM$ satisfies
$$
\{\partial/\partial x^i\}_{\varphi_i}\sim\{\partial/\partial y^i\}_{\varphi_j},
$$
then $M$ is called *orientable*. An example of manifold that's not orientable is the Mobius strip.

### 1.3 Cotangent vector
#### 1.3.1 Cotangent space
For any map $f\in C^\infty$, there is a *cotangent vector* at $p\in M$ defined as
$$
\begin{aligned}
\mathrm{d}f_p:&&T_pM&\to\mathbb{R}\\
&&X_p&\mapsto X_p(f).
\end{aligned}
$$

>[!note]+ Physicists' notation:
>A covarient vector $W$ contracting with a (contravarient) vector $V$ gives $W_iV^i$. The covarient vector $\mathrm{d}f$ is just $\dfrac{\partial f}{\partial x^i}$.

The set of all cotangent vectors forms another vector space called *cotangent space*, denoted as $T_p^\ast M$, which is the [[Linear algebra#5.1 Dual space|dual vector space]] of $T_pM$. One can prove that $\{\mathrm{d}x^i_p\}$ forms a basis of $T_p^\ast M$. There is the orthogonal relation
$$
\mathrm{d}x^i\left(\frac{\partial}{\partial x^j}\right)=\delta^i{}_j.
$$
A cotangent vector can be decomposed as
$$
\mathrm{d}f_p=\sum_i\left.\frac{\partial f}{\partial x^i}\right|_p\mathrm{d}x^i
$$

#### 1.3.2 One-form
The union of cotangent spaces of all points of $M$ is the *cotangent bundle* of $M$
$$
T^\ast M\doteq\bigcup\{T_p^\ast M\}=\{(p,\mathrm{d}f_p):p\in M,\mathrm{d}f_p\in T_p^\ast M\}.
$$
The map
$$
\begin{aligned}
\omega:&&M&\to T^\ast M\\
&&p&\mapsto(p,\mathrm{d}f_p)
\end{aligned}
$$
is called a *one-form* on $M$. The set of all one-forms is denoted as $\Omega^1(M)$.

For a smooth map $f\in C^\infty(M)$, $\mathrm{d}f\in\Omega^1(M)$ has the natural paring
$$
\mathrm{d}f(X)=X(f)\in\mathbb{R}.
$$

### 1.4 Map between manifold
#### 1.4.1 Push-forward and pull-back
For a smooth map between two manifolds $f:M\to N$, there is a map from tangent space of $M$ to tangent space of $N$ called the *push-forward map*
$$
f_\ast:T_pM\to T_{f(p)}N
$$
such that
$$
f_\ast(X_p):g\mapsto X_p(g\circ f).
$$

There is also a map of cotangent space called *pull-back map*
$$
f^\ast:T_{f(p)}^\ast N\to T_p^\ast M
$$
such that
$$
f^\ast(\omega_{f(p)}):X_p\mapsto\omega_{f(p)}(f_\ast X_p).
$$

The push-forward and pull-back preserves the natural paring of tangent vector and cotangent vector.

#### 1.4.2 Regular map
If the push-forward map $f_\ast:T_pM\to T_{f(p)}N$ is surjective, then $f$ is called *regular* at point $p$. If $f$ is regular at every point $p\in M$, then $f$ is called a *submersion*.

If $f$ is not regular at point $p\in M$, then $p$ is called a *critical point* of $f$, and $f(p)$ is called the *critical value* of $f$. One can prove that the set of critical points in $N$ has [[Measure theory#1.3.3 Lebesgue-Stieltjes measure|Lebesgue measure]] zero.

#### 1.4.3 Immersion and embedding
For a smooth map $f:M\to N$, if $f_\ast$ is injective for all $p\in M$, then $f$ is called *immersion*. If an immersion $f$ is also a [[Topology#1.2 Continuous map and homeomorphism|homeomorphism]] onto
$$
f:M\to f(M)
$$
where $f(M)\subset N$, then $f$ is called an *embedding*.

## 2 Calculus on manifold
### 2.1 Differential form
#### 2.1.1 Exterior algebra
For $n$ cotangent vectors $\omega_i$ at point $p$, their *wedge product* is defined as the following map
$$
\begin{aligned}
\omega_p=\omega_1\wedge\cdots\wedge\omega_n:&&T_pM\times T_pM\times\cdots\times T_pM&\to\mathbb{R}\\
&&(X^1_p,X^2_p,\cdots,X^n_p)&\mapsto\frac{1}{n!}\det(\omega_i(X^j_p)).
\end{aligned}
$$
This is sometimes called an *$n$-form* at point $p$. The set of all such $\omega_p$ at $p$ forms an algebra called *exterior algebra*, denoted as $\wedge^nT_p^\ast M$, with its basis
$$
\mathrm{d}x^{i_1}\wedge\cdots\wedge\mathrm{d}x^{i_n}.
$$
The change of basis follows
$$
\mathrm{d}x^{i_1}\wedge\cdots\wedge\mathrm{d}x^{i_n}=\sum_{j_1\leqslant\cdots\leqslant j_n}\frac{D(x^{i_1},\cdots,x^{i_n})}{D(y^{j_1},\cdots,y^{j_n})}\mathrm{d}y^{j_1}\wedge\cdots\wedge\mathrm{d}y^{j_n}
$$
where $D(x)/D(y)$ is the Jacobian.

Note that $(\omega_1\wedge\cdots\wedge\omega_n)(X^1_p,\cdots,X^n_p)$ is anti-symmetric for both indices of $\omega_i$ and $X^i_p$.

For an $m$-form $\omega_p$ and an $n$-form $\eta_p$, their wedge is defined as
$$
(\omega_p\wedge\eta_p)(X^1_p,\cdots,X^{m+n}_p)=\frac{1}{(m+n)!}\sum_\sigma\mathrm{sign}(\sigma)\omega_p(X^{\sigma_1}_p,\cdots,X^{\sigma_m}_p)\eta_p(X^{\sigma_{m+1}}_p,\cdots,X_{\sigma^{m+n}_p}),
$$
where $\sigma\in S_{m+n}$ and $\mathrm{sign}(\sigma)$ is the [[Abstract group theory#4.5 Odd and even|sign map]].

#### 2.1.2 Differential $k$-forms
Define the union of all exterior algebras of $k$ order on the manifold $M$ as
$$
\wedge^kT^\ast M\doteq\bigcup_{p\in M}\{\wedge^kT^\ast_pM\}=\{(p,\omega_p):p\in M,\omega_p\in\wedge^kT^\ast_pM\}.
$$
This is also a manifold. A section of this manifold is called a *differential $k$-form*
$$
\begin{aligned}
\omega:&&M&\to\wedge^kT^\ast M\\
&&p&\mapsto(p,\omega_p).
\end{aligned}
$$
An alternative way to define such a differential $k$-form is a following $k$-linear map
$$
\omega:\mathfrak{X}(M)\times\cdots\mathfrak{X}(M)\to C^\infty(M).
$$
Denote the set of such differential $k$-forms as $\Omega^k(M)$, and especially define $\Omega^0(M)\doteq C^\infty(M)$.

#### 2.1.3 Exterior derivative
The *exterior derivative* is a linear map
$$
\mathrm{d}:\Omega^k(M)\to\Omega^{k+1}(M)
$$
that satisfies the following.
- For $k=0$, its defined as the cotangent vector $\mathrm{d}f(X)=X(f)$;
- The composition of two exterior derivative $\mathrm{d}\circ\mathrm{d}=0:\Omega^k(M)\to\Omega^{k+2}(M)$;
- The Leibniz rule $\mathrm{d}(\omega\wedge\eta)=(\mathrm{d}\omega)\wedge\eta+(-1)^k\omega\wedge(\mathrm{d}\eta)$.

The exterior derivative acting on a $k$-form is defined as
$$
\mathrm{d}\omega:(X^1,\cdots,X^{k+1})\mapsto\frac{1}{k+1}\left[\sum_{i=1}^{k+1}(-1)^{i+1}X^i(\omega(\cdots,X^{\ne i},\cdots))+\sum_{i<j}(-1)^{i+j}\omega([X^i,X^j],X^1,\cdots)\right].
$$
This can be expressed in the form of Lie derivative
$$
(\mathrm{d}\omega)(X^1,\cdots,X^{k+1})=\frac{1}{k+1}\sum_i(-1)^{i+1}\mathcal{L}_{i}(\omega)(\cdots,X^{\ne i},\cdots).
$$

It can be written under the basis expansion
$$
\omega=\sum_{i_1<\cdots<i_k} f_{i_1\cdots i_k}(x)\mathrm{d}x^{i_1}\wedge\cdots\wedge\mathrm{d}x^{i_k}
$$
as
$$
\mathrm{d}\omega=\sum\mathrm{d}f(x)\wedge\mathrm{d}x^{i_1}\wedge\cdots\wedge\mathrm{d}x^{i_k}.
$$

#### 2.1.4 Pull-back of differential form
For a smooth map $f:M\to N$, the pull-back map is
$$
f^\ast:\Omega^\bullet(N)\to\Omega^\bullet(M)
$$
that satisfies
$$
(f^\ast\omega)(X_1,\cdots,X_k)=f^\ast(\omega(f_\ast X_1,\cdots,f_\ast X_k)).
$$

This pull-back satisfies the following.
- $f^\ast:\Omega^k(N)\to\Omega^k(M)$ is a linear map;
- $f^\ast(\omega\wedge\eta)=f^\ast\omega\wedge f^\ast\eta$;
- For another smooth map $g:N\to L$, the composition satisfies $(g\circ f)^\ast=f^\ast\circ g^\ast$;
- It commutes with $\mathrm{d}$.

#### 2.1.5 Interior product
For a vector field $X\in\mathfrak{X}(M)$, one can define such linear map
$$
i(X):\Omega^k(M)\to\Omega^{k-1}(M)
$$
such that
$$
i(X)(\omega):(X_1,\cdots,X_{k-1})\mapsto k\omega(X,X_1,\cdots,X_{k-1}).
$$
This $i(X)(\omega)$ is called the *interior product* of $\omega$ by $X$.

#### 2.1.6 Lie derivative
Given a vector field $X\in\mathfrak{X}(M)$, the *Lie derivative* is a linear map
$$
\mathcal{L}_X:\Omega^k(M)\to\Omega^k(M)
$$
such that
$$
\mathcal{L}_X(\omega):(X_1,\cdots,X_k)\mapsto X(\omega(X_1,\cdots,X_k))-\sum_{i=1}^k\omega(X_1,\cdots,[X,X_i],\cdots,X_k).
$$

Consider a flow $\varphi_t:M\to M$ of $X\in\mathfrak{X}(M)$ which is a 1-parameter family of diffeomorphism, then the Lie derivative can be expressed as
$$
\mathcal{L}_X(\omega)=\lim_{t\to\infty}\frac{\varphi_t^\ast(\omega)-\omega}{t}.
$$
Note that such limit of push-forward for another $Y\in\mathfrak{X}(M)$ gives
$$
\lim_{t\to0}\frac{\varphi_{t\ast}(Y)-Y}{t}=-[X,Y],
$$
which can be defined as the Lie derivative of a vector field.

### 2.2 Integral on the manifold
#### 2.2.1 Integral on local chart
For a local chart $(U,\varphi)$, a $n$-form $\omega=f(x)\mathrm{d}x^1\wedge\cdots\wedge\mathrm{d}x^n$ can naturally introduce an integral
$$
\int_U\omega\doteq\int_{\varphi(U)}f(x)\mathrm{d}x^1\cdots\mathrm{d}x^n.
$$

#### 2.2.2 Partition of unity
For a [[Topology#1.2 Open covering|locally finite]] open covering $\{U_i\}$ of $M$, a *partition of unity* is a collection of $\chi_i\in C^\infty(M)$ that satisfies the following.
- $0\leqslant\chi_i(p)\leqslant1$ for any $\chi_i$ at any point $p$;
- $\chi_i(p)\ne0$ only when $p\in U_i$;
- $\sum_i\chi_i(p)=1$ for any point $p$.

#### 2.2.3 Integral on the manifold
With the partation of unity, one can define the integral on the entire manifold as
$$
\int_M\omega\doteq\sum_i\int_{\varphi_i(U_i)}\omega\ \chi_i(x).
$$
It can be proved that the value of this integral is independent of the choice of partation of unity and the choice of locally finite open covering.

For an oriented manifold $M$ with boundary and an $\omega\in\Omega^{n-1}(M)$, there is the *Stokes' theorem*
$$
\int_M\mathrm{d}\omega=\int_{\partial M}\omega.
$$

## 3 de Rham cohomology
### 3.1 de Rham cohomology
#### 3.1.1 Exact and closed form
Consider a manifold $M$ with an exterior derivative $\mathrm{d}$, a differential form $\omega\in\Omega^k(M)$ is called a *closed form* if $\mathrm{d}\omega=0$ and it is called an *exact form* if there exists an $\eta\in\Omega^{k-1}(M)$ such that $\omega=\mathrm{d}\eta$. The set of all closed $k$-form is denoted as $Z^k(M)$ and all exact $k$-form as $B^k(M)$
$$
Z^k(M)\doteq\mathrm{Ker}(\mathrm{d}:\Omega^k\to\Omega^{k+1}),\qquad B^k(M)\doteq\mathrm{Im}(\mathrm{d}:\Omega^{k-1}\to\Omega^k).
$$

#### 3.1.2 de Rham cohomology group
Since $\mathrm{d}^2=0$, all exact $k$-forms are closed, which means $B^k(M)\subset Z^k(M)$. The *de Rham cohomology group* of $M$ is defined as the [[Linear algebra#4.3 Quotient space|quotient space]]
$$
H_{\text{dR}}^k(M)\doteq Z^k(M)/B^k(M).
$$
Its dimension is called the *$k$-th Betti number* of $M$. This is a cohomology group of the following structure called *de Rham complex* $(\Omega^\bullet(M),\mathrm{d})$
$$
0\to\Omega^1(M)\stackrel{\mathrm{d}}{\to}\Omega^2(M)\stackrel{\mathrm{d}}{\to}\cdots\stackrel{\mathrm{d}}{\to}\Omega^n(M)\to 0.
$$

An element $\omega\in H^k_{\text{dR}}(M)$ is an equivalence class of $k$-form
$$
[\omega]=\sum[\omega_{i_1\cdots i_k}(x)]\mathrm{d}x^{i_1}\wedge\cdots\wedge\mathrm{d}x^{i_k}
$$
that $\mathrm{d}\omega=0$ and $[\omega]=[\eta]\Leftrightarrow\omega-\eta\in B^k(M)$.

#### 3.1.3 de Rham ring
For two elements $[\omega]\in H^k_{\text{dR}}$ and $[\eta]\in H^l_{\text{dR}}$, one can define their wedge product as
$$
[\omega]\wedge[\eta]\doteq[\omega\wedge\eta]\in H^{k+l}_{\text{dR}}.
$$
Apparently there is $[\omega]\wedge[\eta]=(-1)^{k+l}[\eta]\wedge[\omega]$. Such a structure $(H^\ast_{\text{dR}},\wedge)$ is called the *de Rham ring*.
