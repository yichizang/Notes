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
### 1.1 Basic concept
#### 1.1.1 Vector bundle
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

#### 1.1.2 Transition function
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

#### 1.1.3 Section
The *section* of a vector bundle $(E,\pi,M)$ is a map
$$
s:M\to E
$$
such that $\pi\circ s=1_M$. That is to say, $s(p)\in E_p$ for any $p\in M$.

The set of all sections is denoted as $\Gamma(E,M)$.

#### 1.1.4 Bundle map
For two vector bundles $(E_1,\pi_1,M_1)$ and $(E_2,\pi_2,M_2)$, a *bundle map* between them is a pair of smooth maps
$$
\begin{aligned}
F&:E_1\to E_2\\
f&:M_1\to M_2
\end{aligned}
$$
that satisfies $\pi_2\circ F=f\circ\pi_1$ and that $F_p:E_{1p}\to E_{2f(p)}$ is a linear map.

Two vector bundles $E_1$ and $E_2$ that share a common base space $M$ are called *isomorphic* if there is a bundle map $E_1\to E_2$ over the identity map on $M$.

#### 1.1.5 Metric on vector bundle

### 1.2 Operation on vector bundle
#### 1.2.1 Whitney sum
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

#### 1.2.2 Tensor product
For two vector bundles $(E_1,\pi_1,M)$ and $(E_2,\pi_2,M)$, the *tensor product* of them is defined as
$$
E_1\otimes E_2\doteq\bigcup_{p\in M}(E_{1p}\otimes E_{2p}).
$$

It is also a vector bundle over $M$ with fiber given by $(E_1\otimes E_2)_p\doteq E_{1p}\otimes E_{2p}$. The local trivialization is naturally given.

#### 1.2.3 Dual vector bundle
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

#### 1.2.4 Pullback
