---
banner: "![[../pics/mmexport1663523939450.jpg]]"
banner_y: 0
---

>[!abstract]- Pre-knowledge
>- [[Abstract group theory]]
>- [[Linear algebra]]
>- [[Abstract group theory]]

# Topology
## 1 Topological space
### 1.1 Topological space
For a set $X$, a collection of subsets of $X$ denoted as $\mathcal{T}$ is called a *topology* if it satisfies the following
- $\varnothing\in\mathcal{T}$ and $X\in\mathcal{T}$;
- for a subcollection $\{U_i\}\subset\mathcal{T}$, $\bigcup\{U_i\}\in\mathcal{T}$;
- for any $U_1$ and $U_2$ in $\mathcal{T}$, $U_1\cap U_2\in\mathcal{T}$.
The pair $(X,\mathcal{T})$ is called a *topological space*. It is also denoted simply as $X$. An element of $\mathcal{T}$ is called an *open set*.

For a topological space $(X,\mathcal{T})$ and a point $x\in X$, $N\subset X$ is called a *neighborhood* of $x$ if $N$ contains at least one open set $U\ni x$.

### 1.2 Open covering
A subset $\{U_i\}\subset\mathcal{T}$ is called an *open covering* of $X$ if $\bigcup\{U_i\}=X$. Another open covering $\{V_j\}_J$ is called a *refinement* of $\{U_i\}_I$ if for any $j\in J$, there is an $i\in I$ such that $V_j\subset U_i$.

An open covering $\{U_i\}$ is called *locally finite* if for any $x\in X$, there is a neighborhood $U\ni x$ such that there only exists finite number of $i$ that $U_i\cap U\ne\varnothing$.

It can be proved that for any open covering $\{U_i\}$, there is a refinement that is locally finite.

### 1.3 Continuous map and homeomorphism
For two topological spaces $(X_1,\mathcal{T}_1)$ and $(X_2,\mathcal{T}_2)$, a map $f:X_1\to X_2$ is called a *continuous map* if $f^{-1}(V)\in\mathcal{T}_1$ for any $V\in\mathcal{T}_2$. If $f$ is bijective and both $f$ and $f^{-1}$ are continuous, then $f$ is called a *homeomorphism*.

### 1.4 Compactness
For a topological space $(X,\mathcal{T})$, a subset $V\subset X$ is called *closed* if its complement in $X$ is an open set. That is to say $X-V\in\mathcal{T}$.

For a collection of closed sets $\{V_i\}_I$, $\bigcup\{V_i\}$ is also a closed set. For two closed sets $V_1$ and $V_2$, $V_1\cap V_2$ is also closed.

A topological space $X$ is called *compact* if every open covering $X=\bigcup\{U_i\}_I$ has a finite subcovering $X=\bigcup\{U_i\}_1^n$.

### 1.5 Connectivity
For a topological space $X$, it is called *connected* if it can't be written as $X=X_1\cup X_2$ with $X_1\cap X_2=\varnothing$. Otherwise it is called *disconnected*.

For two points $x_1,x_2\in X$, a *path* from $x_1$ to $x_2$ is a continuous map $p:[0,1]\to X$ that $p(0)=x_1$ and $p(1)=x_2$. If for any two points in $X$ there is a path connecting them, then $X$ is called *path-connected*.

Every path-connected topological space is connected.

### 1.6 Quotient topology
For a topological space $(X,\mathcal{T})$ and an equivalence relation $\sim$, one can define a topology on $X/\sim$ as
$$
\mathcal{T}'=\{U':U'\subset X/\sim,p^{-1}(U')\in\mathcal{T}\},
$$
where $p:X\to X/\sim$. $(X/\sim,\mathcal{T}')$ is called the *quotient space* of $(X,\mathcal{T})$.

### 1.7 Hausdorff space
A topological space $X$ is called a *Hausdorff space* if for all $x_1\ne x_2\in X$ there exists disjoint neighborhoods $U_1$ and $U_2$ of $x_1$ and $x_2$ respectively.

## 2 Homology and cohomology
### 2.1 Simplical homology
#### 2.1.1 $q$-simplex
A *$q$-simplex* is a convex hull of $q+1$ affinely independent points $a_i\in\mathbb{R}^m$. That is the set
$$
\sigma=\braket{a_0,\cdots,a_q}\doteq\left\{\sum t_ia_i:\sum t_i=1,t_i\geqslant0\right\}.
$$
The points $a_i$ are called *vertices*. They are said to *span* $\sigma$.

The turple $(t_0,\cdots,t_q)$ is called the *barycentric coordinates* of point $\sum t_ia_i$.

A *face* of $\sigma$ is a subset spanned by a subset of points. The *boundary* $\partial\sigma$ is the union of proper faces and the *interior* is the complement of boundaries.

#### 2.1.2 Simplical complex
A *simplical complex* is a set $K$ of simplices on $\mathbb{R}^m$ that satisfies
- if $\sigma\in K$ and $\tau$ is a face of $\sigma$, then $\tau\in K$;
- for two $\sigma,\tau\in K$, the intersection $\sigma\cap\tau$ is either $\varnothing$ or a face of both $\tau$ and $\sigma$.

The *dimension* of $K$ is the maximal dimension of the simplices in $K$.

The *polyhedron* of $K$ is the union of all simplices in $K$, denoted as $[K]$. The *$d$-skeleton* of $K$ is the union of all $n$-simplices in $K$ for $n\leqslant d$, denoted as $K^{(d)}$.

The *triangulation* of $M$ is a [[Differential geometry#1.1.3 Smooth map|diffeomorphism]] $[K]\to M$.

#### 2.1.3 Chain group
For a simplical complex $K$, if $K^{(q)}$ is spanned by $\{\sigma_i\}$, then its *chain group* $C_q(K)$ is the [[Abstract group theory#5.2 Free group|free]] [[Abstract group theory#1.3 Abelian group|Abelian group]] [[Abstract group theory#5.1 Generator|generated]] by $\{\sigma_i\}$
$$
C_q(K)\doteq\mathbb{Z}\sigma_1\oplus\cdots\oplus\mathbb{Z}\sigma_l.
$$

Define the *boundary homomorphism* $\partial_q$ as
$$
\begin{aligned}
\partial_q:&&C_q(K)&\to C_{q-1}(K)\\
&&\braket{a_1,\cdots,a_l}&\mapsto\sum_i(-1)^i\braket{a_i,\cdots,a_{i-1},a_{i+1},\cdots,a_l}.
\end{aligned}
$$
One can prove that $\partial_{q-1}\circ\partial_q=0$, which is similar to [[Differential geometry#2.1.3 Exterior derivative|exterior derivative]].

#### 2.1.4 Chain complex
For an $n$ dimensional simplical complex $K$, a *chain complex* $(C_\bullet,\partial)$ is the sequence of groups $C_i(K)$ with maps $\partial_q:C_q\to C_{q-1}$ that satisfies $\partial_{q-1}\circ\partial_q=0$
$$
0\stackrel{\partial_n}{\to}C_n\stackrel{\partial_{n-1}}{\to}C_{n-1}\to\cdots\to C_1\stackrel{\partial_1}{\to}C_0\stackrel{\partial_0}{\to}0.
$$
One can define
$$
Z_q(K)\doteq\mathrm{Ker}\ \partial_q,\quad B_q(K)\doteq\mathrm{Im}\ \partial_{q+1}.
$$
Then the $q$-th *homology group* of $C_\bullet(K)$ is defined as
$$
H_q(K;\mathbb{Z})\doteq Z_q(K)/B_q(K).
$$

#### 2.1.5 Eular characteristic
One can prove that for any $M$ with two different triangulations $[K_1]\to M$ and $[K_2]\to M$, their homology group
$$
\forall q,\quad H_q(K_1;\mathbb{Z})\cong H_q(K_2;\mathbb{Z}).
$$
Therefore, one can define $H_q(M;\mathbb{Z})$.

In the similar way as $C_q(K;\mathbb{Z})$, one can define $C_q(K;\mathbb{R})$ and therefore $H_q(K;\mathbb{R})$. The dimension of $H_q(M;\mathbb{R})$ is called the $q$-th *Betti number*. Its alternative sum is the *Eular characteristic* of $M$
$$
\chi(M)\doteq\sum_q(-1)^q\dim H_q(M;\mathbb{R}).
$$

### 2.2 Mayer-Vietoris exact sequence
#### 2.2.1 Exact sequence
For a sequence of homomorphism
$$
\cdots\stackrel{f_{q+2}}{\to}M_{q+1}\stackrel{f_{q+1}}{\to}M_q\stackrel{f_q}{\to}M_{q-1}\stackrel{f_{q-1}}{\to}\cdots,
$$
if it satisfies
$$
\forall q,\quad\mathrm{Ker}\ f_q=\mathrm{Im}\ f_{q+1},
$$
then it is called an *exact sequence*.

#### 2.2.2 Mayer-Vietoris theorem
Consider two simplical complexes $K_1,K_2$ that $K\doteq K_1\cup K_2$ and $K'\doteq K_1\cap K_2$ are both simplical complexes. One can use the inclusion maps to define the following two maps naturally
$$
\begin{aligned}
\varphi:&&H_q(K')&\to H_q(K_1)\oplus H_q(K_2);\\
\psi:&&H_q(K_1)\oplus H_q(K_2)&\to H_q(K).
\end{aligned}
$$

For an element $[z]\in H_q(K)$, one can write the decomposition $z=c_1+c_2$ with $c_i\in C_q(K_i)$. Then one can define the map (independent of the choice of $z$ and decomposition)
$$
\begin{aligned}
\Delta:&&H_q(K)&\to H_{q-1}(K')\\
&&[z]&\mapsto[\partial c_1]=-[\partial c_2].
\end{aligned}
$$

With the 3 maps above, one can prove that the following is an exact sequence
$$
\begin{aligned}
&\cdots&&\stackrel{\Delta}{\to}&&H_q(K')&&\stackrel{\varphi}{\to}&H_q(K_1)&\oplus H_q(K_2)&&\stackrel{\psi}{\to}&&H_q(K)&&\\
&&&\stackrel{\Delta}{\to}&&H_{q-1}(K')&&\stackrel{\varphi}{\to}&H_{q-1}(K_1)&\oplus H_{q-1}(K_2)&&\stackrel{\psi}{\to}&&H_{q-1}(K)&&\cdots
\end{aligned}
$$
This is called the *Mayer-Vietoris exact sequence*.
