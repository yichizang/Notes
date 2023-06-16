---
banner: "![[../pics/97631195_p0.png]]"
banner_y: 0.272
---

>[!abstract]- Pre-knowledge
>- [[Linear algebra]]
>- [[Differential geometry]]
>- [[Riemannian geometry]]

# Fiber bundle
## 1 Vector bundle
### 1.1 Vector bundle
Two [[Differential geometry#1.1.1 Manifold|smooth manifold]] $E$ and $M$, a [[Linear algebra#1.1 Definition|vector space]] $\mathbb{R}^n$ and a projection map $\pi:E\to M$ form a rank $n$ *vector bundle* if they satisfy
- for each $p\in M$, the preimage $E_p\doteq\pi^{-1}(p)\subset E$ is $\mathbb{R}^n$;
- for any $p\in M$, there is an [[Topology#1.2 Open covering|open covering]] $\{U\}$ and a [[Differential geometry#1.1.3 Smooth map|diffeomorphism]]
$$
t:E_U\doteq\pi^{-1}(U)\to U\times\mathbb{R}^n
$$
such that $t\circ\pi'=\pi$ where $\pi':U\times\mathbb{R}^n\to U$ and the induced map $E_p\to\{p\}\times\mathbb{R}^n$ is a linear isomorphism.

The map $t$ is called a *local trivialization* of the bundle. $E$ is called the *total space*. $M$ is called the *base space*. The vector space $E_p$ is called a *fiber*.

In the case of $n=1$, the vector bundle is called a *line bundle*.

>[!example]
>One can construct a line bundle $L$ on $\mathbb{R}\mathrm{P}^n$ as
>$$
>L\doteq\{([x],y):[x]\in\mathbb{R}\mathrm{P}^n;y=\lambda x,\lambda\in\mathbb{R}\}.
>$$
>For an open subset $U_i\doteq\{[(x^0,x^1,\cdots,x^l)]:x^i\ne0\}$, the local trivialization is
>$$
>\begin{aligned}
>t_i:&&\pi^{-1}(U_i)&\to U_i\times\mathbb{R}\\
>&&([x],y)&\mapsto([x],y^i).
>\end{aligned}
>$$
>This bundle is called the *Hopf line bundle* or *tautological line bundle*.

### 1.2 Transition function
For two local trivializations $t_\alpha:\pi^{-1}(U_\alpha)\to U_\alpha\times\mathbb{R}^n$ and $t_\beta:\pi^{-1}(U_\beta)\to U_\beta\times\mathbb{R}^n$, the composition satisfies
$$
\begin{aligned}
t_\alpha\circ t_\beta^{-1}:&&(U_\alpha\cap U_\beta)\times\mathbb{R}^n&\to(U_\alpha\cap U_\beta)\times\mathbb{R}^n\\
&&(p,v)&\mapsto(p,g_{\alpha\beta}(p)v),
\end{aligned}
$$
where $g_{\alpha\beta}(p)\in\mathrm{GL}(n,\mathbb{R})$. Generally, the map $g_{\alpha\beta}:(U_\alpha\cap U_\beta)\to\mathrm{GL}(n,\mathbb{R})$ is called the *transition map* from $\alpha$ to $\beta$.

The transition functions satisfy
- $g_{\alpha\alpha}=1_n$;
- $g_{\alpha\beta}=g_{\beta\alpha}^{-1}$;
- $g_{\alpha\beta}g_{\beta\gamma}g_{\gamma\alpha}=1_n$.

The third condition is called *cocycle condition*.

>[!note]
>The transition map shows how the trivializations $U_\alpha\times\mathbb{R}^n$ are "glued" together to construct the vector bundle.

### 1.3 Subbundle
For a vector bundle $(E,\pi,M)$, a vector bundle $(F,\pi,M)$ is called its *subbundle* if
- $F$ is a [[Differential geometry#1.1.2 Submanifold|submanifold]] of $E$;
- for each $p\in M$, the fiber $F_p$ is a [[Linear algebra#1.2 Subspace and sum of subspace|subspace]] of $E_p$.

### 1.4 Section
The *section* of a vector bundle $(E,\pi,M)$ is a map
$$
s:M\to E
$$
such that $\pi\circ s=1_M$. That is to say, $s(p)\in E_p$ for any $p\in M$.

The set of all sections is denoted as $\Gamma(E,M)$.

### 1.5 Bundle map
For two vector bundles $(E_1,\pi_1,M_1)$ and $(E_2,\pi_2,M_2)$, a *bundle map* between them is a pair of smooth maps
$$
\begin{aligned}
F&:E_1\to E_2\\
f&:M_1\to M_2
\end{aligned}
$$
that satisfies $\pi_2\circ F=f\circ\pi_1$ and that $F_p:E_{1p}\to E_{2f(p)}$ is a linear map.

Two vector bundles $E_1$ and $E_2$ that share a common base space $M$ are called *isomorphic* if there is a bundle map $E_1\to E_2$ over the identity map on $M$.

### 1.6 Metrics on vector bundle
For a vector bundle $(E,\pi,M)$, one can define a *metrics* on the fiber as a map
$$
g_p:E_p\times E_p\to\mathbb{R}
$$
that is symmetric, positive-definite and non-degenerate. The metrics is smooth under the change of $p$.

In the case of the [[Differential geometry#1.2.3 Tangent bundle|tangent bundle]] $TM$, the metrics is just [[Riemannian geometry#1.1 Definition of Riemannian metrics|Riemannian metrics]].

>[!note]
>The metrics is independent of the local trivialization. Therefore, a transition function will "preserve the inner product" of the metrics. So one can write $g_{\alpha\beta}(p)\in O(n)$.

## 2 Operation on vector bundle
### 2.1 Whitney sum
For two vector bundles $(E_1,\pi_1,M)$ and $(E_2,\pi_2,M)$, the *Whitney sum* of them is defined as
$$
E_1\oplus E_2\doteq\{(x_1,x_2)\in E_1\times E_2:\pi_1(x_1)=\pi_2(x_2)\}.
$$
This naturally induces a map
$$
\begin{aligned}
\pi_1\oplus\pi_2:&&E_1\oplus E_2&\to M\\
&&(x_1,x_2)&\mapsto\pi_1(x_1)=\pi_2(x_2)
\end{aligned}
$$
and a fiber structure $(E_1\oplus E_2)_p\doteq E_{1p}\oplus E_{2p}$.

The Whitney sum naturally forms a vector bundle $(E_1\oplus E_2,\pi_1\oplus\pi_2,M)$ with natural local trivialization.

### 2.2 Tensor product
For two vector bundles $(E_1,\pi_1,M)$ and $(E_2,\pi_2,M)$, the *tensor product* of them is defined as
$$
E_1\otimes E_2\doteq\bigcup_{p\in M}(E_{1p}\otimes E_{2p}).
$$

It is also a vector bundle over $M$ with fiber given by $(E_1\otimes E_2)_p\doteq E_{1p}\otimes E_{2p}$. The local trivialization is naturally given.

### 2.3 Dual vector bundle
For a vector bundle $(E,\pi,M)$, the *dual vector bundle* is defined as
$$
E^\ast\doteq\bigcup_{p\in M}(E_p)^\ast.
$$

Given the local trivialization of $E$
$$
t:E_U\cong U\times\mathbb{R}^n,
$$
one can take the [[Linear algebra#5.3 Dual map|dual map]], use the relation $(\mathbb{R}^n)^\ast\cong\mathbb{R}^n$ and take the inverse to get
$$
t^\ast:E_U^\ast\cong U\times\mathbb{R}^n.
$$

### 2.4 Pullback
For a vector bundle $(E,\pi,M)$ and a map $f:N\to M$, the *pullback* of the vector bundle is
$$
f^\ast E\doteq\{(p,x)\in N\times E:f(p)=\pi(x)\}.
$$
The projection map is
$$
\begin{aligned}
f^\ast\pi:&&f^\ast E&\to N\\
&&(p,x)&\mapsto p,
\end{aligned}
$$
and the fiber is simply given by $(f^\ast E)_p=E_{f(p)}$.

### 2.5 Quotient bundle
For a vector bundle $(E,\pi,M)$ and its subbundle $(F,\pi,M)$, one can define a natural *quotient bundle* as the bundle with [[Linear algebra#4.3 Quotient space|quotient space]] as fiber
$$
E/F\doteq\bigcup_{p\in M}E_p/F_p.
$$
The projection is the natural map $\pi:E/F\to M$.

>[!example]
>Consider an [[Differential geometry#1.4.3 Immersion and embedding|embedding]] $f:M\to N$. The [[Differential geometry#1.2.3 Tangent bundle|tangent bundle]] $(TM,\pi,M)$ is a subbundle of the pullback bundle $(f^\ast TN,f^\ast\pi,M)$. Then, the quotient bundle $f^\ast TN/TM$ is called the *normal bundle* of $M$.

## 3 Principal $G$-bundle
### 3.1 $G$-bundle
For a [[Lie algebra and Lie group#1.1 Lie group|Lie group]] $G$ with a [[Representation theory#1.1.1 Definition of representation|representation]] $\rho:G\to\mathrm{GL}(n)$, a *$G$-bundle* $\pi:E\to M$ satisfies
- for each $p\in M$, the fiber is $\pi^{-1}(p)\cong V$;
- there is local trivialization;
- the transition function $g_{\alpha\beta}:(U_\alpha\cap U_\beta)\to\mathrm{GL}(n)$ can be constructed by
$$
g_{\alpha\beta}=\rho\circ f_{\alpha\beta}:(U_\alpha\cap U_\beta)\to G\to\mathrm{GL}(n)
$$
where $f_{\alpha\beta}$ satisfies the cocycle condition.

$G$ is called the *structure group* of the bundle.

### 3.2 Principal $G$-bundle
For a Lie group $G$ and a manifold $M$, a *principal $G$-bundle* is a manifold $P$ with a projection map $\pi:P\to M$ that satisfies
- for each point $p\in M$, the preimage $\pi^{-1}(p)\cong G$;
- there is local trivialization $t_\alpha:\pi^{-1}(U_\alpha)\to U_\alpha\times G$;
- there is transition function
$$
\begin{aligned}
t_\alpha\circ t_\beta^{-1}:&&(U_\alpha\cap U_\beta)\times G&\to(U_\alpha\cap U_\beta)\times G\\
&&(p,h)&\mapsto(p,g_{\alpha\beta}(p)\cdot h),
\end{aligned}
$$
where $g_{\alpha\beta}:(U_\alpha\cap U_\beta)\to G$ satisfies the conditions.

### 3.3 Right action on principal $G$-bundle
Similar to the [[Lie algebra and Lie group#4.1 $G$-action|right action]] of Lie group, one can define a *right action* $R_g$ on the total space $P$ for each group element $g\in G$
$$
\begin{aligned}
R_g:&&P&\to P\\
&&u&\mapsto u\cdot g
\end{aligned}
$$
such that $\pi(u)=\pi(R_gu)$ and $t_\alpha(R_gu)=t_\alpha(u)\cdot g$. One can prove that this is independent of the choice of trivialization.

The [[Lie algebra and Lie group#4.2 Homogenous space|orbit]] of $G$ action is the fiber $\pi^{-1}(p)\cong G$.

>[!note]
>A principal $G$-bundle is trivial if and only if it admits a section. With a section $s:M\to P$ one can choose the trivialization
>$$
>\begin{aligned}
>t:&&M\times G&\cong P\\
>&&(p,g)&\mapsto R_g(s(p)).
>\end{aligned}
>$$

### 3.4 Associated vector bundle
For a principal $G$-bundle $(P,\pi,M,G)$ and a representation $\rho:G\to\mathrm{GL}(n)$, one can define the *right $G$-action* on $P\times\mathbb{R}^n$ as
$$
R_g:(u,\ket{v})\mapsto\left(R_gu,\rho^{-1}(g)\ket{v}\right).
$$
Then the quotient $E=P\times_\rho\mathbb{R}^n\doteq(P\times\mathbb{R}^n)/R_g$ forms a $G$-bundle with fiber $\mathbb{R}^n$ and base space $M$. This is the *associated vector bundle* of the principal $G$-bundle.

Conversely, one can construct a principal $G$-bundle with a $G$-bundle.

## 4 Connection and curvature
### 4.1 Connection
For a vector bundle $(E,\pi,M)$, a *connection* is a bilinear map
$$
\begin{aligned}
\nabla:&&\mathfrak{X}(M)\times\Gamma(E)&\to\Gamma(E)\\
&&(X,s)&\mapsto\nabla_Xs
\end{aligned}
$$
that satisfies
- $\nabla_{fX}s=f\nabla_Xs$;
- the Leibnitz rule $\nabla_X(fs)=(Xf)s+f\nabla_Xs$,

where $f\in C^\infty(M)$ and $s\in\Gamma(E)$.

If the connection $\nabla$ and the metrics $g$ satisfies
$$
Xg(s_1,s_2)=g(\nabla_Xs_1,s_2)+g(s_1,\nabla_Xs_2),
$$
for $s_i\in\Gamma(E)$ and $X\in\mathfrak{X}(M)$, then the connection is called *compatible* with the metrics, which is similar to the [[Riemannian geometry#3.4 Levi-Civita connection|Levi-Civita connection]].

### 4.2 Curvature
For a vector bundle $(E,\pi,M)$, a *curvature* is a trilinear map
$$
\begin{aligned}
F:&&\mathfrak{X}(M)\times\mathfrak{X}(M)\times\Gamma(E)&\to\Gamma(E)\\
&&(X,Y,s)&\mapsto F(X,Y)s
\end{aligned}
$$
that satisfies 
- $F(X,Y)s=-F(Y,X)s$;
- $F(fX,gY)(hs)=fghF(X,Y)s$,

where $f,g,h\in C^\infty(M)$.

The map is given by
$$
F(X,Y)=\left(\nabla_X\nabla_Y-\nabla_Y\nabla_X-\nabla_{[X,Y]}\right).
$$

### 4.3 Connection and curvature form
For an open covering $U_\alpha$, one can take a frame $s_i\in\Gamma(\pi^{-1}(U_\alpha))$ and write an arbitrary section as
$$
s=\sum_ia^is_i,
$$
where $a^i\in C^\infty(M)$.

Then the connection and the curvature can be written as
$$
\nabla_Xs_i=\sum_js_jA^j{}_i(X)
$$
and
$$
F(X,Y)s_i=\sum_js_jF^j{}_i(X,Y).
$$
Here $A^i{}_j\in\Omega^1(M)$ and $F^i{}_j\in\Omega^2(M)$ are [[Differential geometry#2.1 Differential form|1-forms and 2-forms]].

One can also see the two matrics as two differential forms with matrics values $A\in\Omega^1(M;\mathfrak{gl}(n))$ and $F\in\Omega^2(M;\mathfrak{gl}(n))$. They are called the *connection form* and the *curvature form* respectively.

The connection form and the curvature form satisfies the following relations
$$
\begin{aligned}
F-\mathrm{d}A-A\wedge A&=0\\
\mathrm{d}F-F\wedge A+A\wedge F&=0.
\end{aligned}
$$

### 4.4 Local coordinate
Using a local coordinate and a frame $s_i$, one can write a section as
$$
s=\sum_ia^i(x)s_i.
$$
Then the connection of base vector is given by
$$
\nabla_{\partial_\mu}s=\sum_is_i\left[\frac{\partial a^i}{\partial x^\mu}+(A_\mu)^i{}_ja^j\right].
$$
The curvature is given by
$$
F(\partial_\mu,\partial_\nu)=\frac{\partial A_\nu}{\partial x^\mu}-\frac{\partial A_\mu}{\partial x^\nu}+\left[A_\mu,A_\nu\right].
$$

### 4.5 Change of local trivialization
Given a transition function $g_{\alpha\beta}:(U_\alpha\cap U_\beta)\to\mathrm{GL}(n)$, one can write the change of connection form and curvature form pointwisely
$$
A_\beta=(g_{\alpha\beta})^{-1}A_\alpha g_{\alpha\beta}+(g_{\alpha\beta})^{-1}\mathrm{d}(g_{\alpha\beta})
$$
and
$$
F_\beta=(g_{\alpha\beta})^{-1}F_\alpha g_{\alpha\beta}.
$$

>[!example]
>In Maxwell's theory, the gauge transformation (transition function) is given by
>$$
>g_{\alpha\beta}=e^{i\lambda_{\alpha\beta}(x)}.
>$$
>Therefore, the gauge field (connection) transforms as
>$$
>A_\beta=A_\alpha+i\mathrm{d}(\lambda_{\alpha\beta}),
>$$
>and the field strength (curvature) is invarient.

### 4.6 Parallel transport
For a path $\gamma:[0,1]\to M$ on the manifold, a section $s\in\Gamma(E)$ is called *parallel* along the path if
$$
\nabla_{\dot{\gamma}}s=0.
$$
Given the value of section at one end $s|_{t=0}=s_0\in E_{\gamma(0)}$, one can do *parallel transport* to obtain the value of the section at the other end
$$
\begin{aligned}
E_{\gamma(0)}&\to E_{\gamma(1)}\\
s_0&\mapsto s_1.
\end{aligned}
$$

### 4.7 Holonomy group
For a closed loop $\gamma(0)=\gamma(1)=p$, the parallel transport gives a map
$$
\tau_\gamma:E_p\to E_p.
$$

For two loops $\gamma_1$ and $\gamma_2$ that share common end $p$, one can define the multiplication as
$$
\tau_{\gamma_1}\circ\tau_{\gamma_2}=\tau_{\gamma_1\cdot\gamma_2},
$$
and the inverse as
$$
(\tau_\gamma)^{-1}=\tau_{\gamma^{-1}}.
$$
These $\tau_\gamma$ forms a group called *holonomy group*.

### 4.8 Ehresmann connection
For a principal $G$-bundle $(P,\pi,M,G)$, one can also define a connection called *Ehresmann connection* $A\in\Omega^1(P;\mathfrak{g})$. It satisfies
- for a $X\in\mathfrak{g}$, define a vector field $\bar{X}\in\mathfrak{X}(P)$
$$
\bar{X}(u)\doteq\left.\frac{\mathrm{d}}{\mathrm{d}t}(u\cdot\exp tX)\right|_u,
$$
then $A(\bar{X})=X$;
- for any $g\in G$, the right action acts as the [[Lie algebra and Lie group#3.4 Adjoint action|adjoint action]]
$$
A\circ R_g=(R_g)^\ast A=(\mathrm{ad}~g^{-1})A.
$$
