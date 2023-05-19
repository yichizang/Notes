---
banner: "![[../pics/32ecdacb7c612e32e61ecf96f9ab6b9a1662395440249.jpeg]]"
banner_y: 0.244
---

>[!abstract]- Pre-knowledge
>- [[Topology]]
>- [[Differential geometry]]

# Algebraic topology
## 1 Homotopy
### 1.1 Homotopy
For two topological space $M$ and $N$ and two maps $f_0,f_1:M\to N$, a *homotopy* is a map
$$
\begin{aligned}
F:&&[0,1]\times M&\to N\\
&&(0,x)&\mapsto f_0(x)\\
&&(1,x)&\mapsto f_1(x).
\end{aligned}
$$
$f_0$ is *homotopic* to $f_1$ in this case, denoted as $f_0\simeq f_1$.

Such homotopy $\simeq$ defines an equivalence relation on the set of maps from $M$ to $N$.

### 1.2 Homotopy equivalence
A map $f:M\to N$ between two topological space is a *homotopy equivalence* if there exists another map $g:N\to M$ such that
$$
f\circ g\simeq1_N,\quad g\circ f\simeq1_M.
$$
Such $g$ is called the *homotopy inverse* of $f$.

The two topological spaces $M$ and $N$ are called *homotopy equivalent*, denoted as $M\simeq N$.

A topological space that is homotopy equivalent to a point is called *contractible*. An example is $\mathbb{R}^n$.

### 1.3 Deformation retraction
A *retraction* of a topological space $M$ onto its subspace $N\subset M$ is a map
$$
f:M\to N
$$
that $f|_N=1_N$.

A *deformation retraction* is the homotopy from the identity map on $M$ to a retraction from $M$ to $N$
$$
F:[0,1]\times M\to M.
$$
Then $F(t,\cdot)$ is a homotopy equivalence. The inverse is the inclusion of $N$ into $M$.

>[!example]
>An example would be
>$$
>\begin{aligned}
>F:&&[0,1]\times(\mathbb{R}^{n+1}-\{0\})&\to(\mathbb{R}^{n+1}-\{0\})\\
>&&(t,x)&\mapsto(1-t)x+t\frac{x}{|x|},
>\end{aligned}
>$$
>which is a deformation retraction from $(\mathbb{R}^{n+1}-\{0\})$ to $S^n$.

## 2 Fundamental group
### 2.1 Path
#### 2.1.1 Path
For a [[Topology#1.1 Topological space|topological space]] $X$, a *path* is a [[Topology#1.3 Continuous map and homeomorphism|continuous map]] $f:[0,1]\to X$. A *homotopy* of a path is another continuous map (or family of maps)
$$
\begin{aligned}[]
[0,1]\times[0,1]&\to X\\
(s,t)&\mapsto f_t(s)
\end{aligned}
$$
that satisfies $\forall t\in[0,1]$, the end points are fixed $f_t(0)=x_0,f_t(1)=x_1$. This is actually the concept of smoothly changing the path with both ends fixed.

If two paths are related with a homotopy, then they are called *homotopic*, denoted as $f_1\simeq f_2$. One can prove that this forms an [[Set theory#1.3.4 Equivalence relation|equivalence relation]].

#### 2.1.2 Product path
For two paths $f,g$ that satisfy $f(1)=g(0)$, which is to say that the tail of $f$ is the head of $g$, their *product path* is defined as
$$
f\cdot g:s\mapsto\left\{\begin{aligned}
&f(2s),&&s<1/2\\
&g(2s-1),&&s\geqslant1/2.
\end{aligned}\right.
$$

If there is a homotopy for both $f$ and $g$, then one can define the homotopy $f_t\cdot g_t$. It also relates the two producted path $(f_0\cdot g_0)\simeq(f_1\cdot g_1)$.

#### 2.1.3 Loops
A path with both ends at the same point $f(0)=f(1)=x_0$ is called a *loop*. Such point $x_0$ is called the *basepoint*.

### 2.2 Fundamental group
#### 2.2.1 Fundamental group
The set of all homotopy classes $[f]$ of loops $f:[0,1]\to X$ at point $x_0$ is denoted as $\pi_1(X,x_0)$. One can prove that this forms a group under multiplication
$$
[f][g]\doteq[f\cdot g].
$$
- The identity of the group is $1_\pi:s\mapsto x_0$;
- The inverse is $[f]^{-1}=[\bar{f}]$, where $\bar{f}(s)=f(1-s)$.

This group is called the *fundamental group* at basepoint $x_0$.

For two fundamental groups $\pi_1(X,x_0)$ and $\pi_1(X,x_1)$, there is an isomorphism
$$
\begin{aligned}
\beta_h:&&\pi_1(X,x_0)&\cong\pi_1(X,x_1)\\
&&[f]&\mapsto[h\cdot f\cdot\bar{h}],
\end{aligned}
$$
where $h(0)=x_0$ and $h(1)=x_1$. Therefore, one can simply denote as $\pi_1(X)$.

For two [[Topology#1.5 Connectivity|path connected]] topological spaces $X$ and $Y$, $\pi_1(X\times Y)$ is isomorphic to $\pi_1(X)\times\pi_1(Y)$.

>[!example]
>The fundamental group of $S^1$ is $\pi_1(S^1)\cong\mathbb{Z}$. For $n>1$, $\pi_1(S^n)=0$.
>
>This can be used to prove several interesting theorems. (LEFT FOR LATER)

>[!note]
>As a general case, the set of homotopic equivalence classes of $S^n$ on a topological space is the $n$-th homotopic group $\pi_n(X)$.

#### 2.2.2 Simply connected
A topological space $X$ is called *simply connected* if it is path connected and its fundamental group is trivial.

It can be understood as there is no "hole" in the space so that a loop can continuously sweep over the entire space.

#### 2.2.3 Induced homomorphism
Consider a map $\varphi:X\to Y$ that maps $x_0\in X$ to $y_0\in Y$. It induces a homomorphism
$$
\begin{aligned}
\varphi_\ast:&&\pi_1(X,x_0)&\to\pi_1(Y,y_0)\\
&&[f]&\mapsto[\varphi\circ f].
\end{aligned}
$$

For a topological space $X$ and its subspace $A\subset X$, the inclusion map $i:A\hookrightarrow X$ induces a homomorphism $i_\ast:\pi_1(A)\to\pi_1(X)$.
- If $X$ retracts onto $A$, then $i_\ast$ is injective;
- If $X$ deformation retracts onto $A$ then $i_\ast$ is isomorphism.

Generally, a homotopy equivalence induces an isomorphism.

### 2.3 Van Kampen's theorem
Let $\{A_i\}$ be a set of path connected open set that all contains $x_0$ and $X\doteq\bigcup\{A_i\}$. Each intersection $A_i\cap A_j$ and $A_i\cap A_j\cap A_k$ is also path connected. One can prove that
$$
N\doteq\{i_{i\ast}(f)i_{j\ast}(f)^{-1}:f\in\pi_1(A_i\cap A_j)\}
$$
is a [[Abstract group theory#6.5 Normal subgroups and quotient group|normal subgroup]] of $(\pi_1(A_1)\ast\pi_1(A_2)\cdots)$. The *van Kampen's theorem* states that there is an isomorphism
$$
\pi_1(X)\cong(\pi_1(A_1)\ast\pi_1(A_2)\cdots)/N.
$$

A simpler version states that if $X=A_1\cup A_2$ with $A_i$ path connected and $A_1\cap A_2$ simply connected, then
$$
\pi_1(X)\cong\pi_1(A_1)\ast\pi_1(A_2).
$$

>[!note]
>The normal subgroup $N$ is here to define how to "identity" elements in $\pi_1(A_i)$.

### 2.4 Covering space
#### 2.4.1 Covering space
A *covering space* of a space $X$ is another space $\tilde{X}$ with a map $p:\tilde{X}\to X$ that satisfies


## 3 Simplical homology
### 3.1 $q$-simplex
A *$q$-simplex* is a convex hull of $q+1$ linearly independent points $a_i\in\mathbb{R}^m$. That is the set
$$
\sigma=\braket{a_0,\cdots,a_q}\doteq\left\{\sum t_ia_i:\sum t_i=1,t_i\geqslant0\right\}.
$$
The points $a_i$ are called *vertices*. They are said to *span* $\sigma$. The equivalence class of the order of vertices under even permutation is called the *orientation* of the simplex. A simplex with given orientation is called *oriented* simplex.

The turple $(t_0,\cdots,t_q)$ is called the *barycentric coordinates* of point $\sum t_ia_i$.

A *face* of $\sigma$ is a subset spanned by a subset of points. The *boundary* $\partial\sigma$ is the union of proper faces and the *interior* is the complement of boundaries.

### 3.2 Simplical complex
A *simplical complex* is a set $K$ of simplices on $\mathbb{R}^m$ that satisfies
- if $\sigma\in K$ and $\tau$ is a face of $\sigma$, then $\tau\in K$;
- for two $\sigma,\tau\in K$, the intersection $\sigma\cap\tau$ is either $\varnothing$ or a face of both $\tau$ and $\sigma$.

The *dimension* of $K$ is the maximal dimension of the simplices in $K$.

The *polyhedron* of $K$ is the union of all simplices in $K$, denoted as $|K|$. The *$d$-skeleton* of $K$ is the union of all $n$-simplices in $K$ for $n\leqslant d$, denoted as $K^{(d)}$.

The *triangulation* of a [[Topology#1.1 Topological space|topological space]] $M$ is a [[Topology#1.3 Continuous map and homeomorphism|homeomorphism]] $|K|\to M$.

### 3.3 Chain group
For a simplical complex $K$, assign an orientation to each $q$-simplex $\sigma_i\in K$. Then its *chain group* $C_q(K)$ is the [[Abstract group theory#5.2 Free group|free]] [[Abstract group theory#1.3 Abelian group|Abelian group]] [[Abstract group theory#5.1 Generator|generated]] by $\{\sigma_i\}$
$$
C_q(K)\doteq\mathbb{Z}\sigma_1\oplus\cdots\oplus\mathbb{Z}\sigma_l.
$$
Here $\mathbb{Z}$ is called the background ring of $C_q(K)$. It can be replaced by any other rings like $\mathbb{Z}_2$ or $\mathbb{R}$. The $q$-simplex with opposite orientation is denoted as $-\sigma_i$.

Define the *boundary homomorphism* $\partial$ as
$$
\begin{aligned}
\partial:&&C_q(K)&\to C_{q-1}(K)\\
&&\braket{a_1,\cdots,a_l}&\mapsto\sum_i(-1)^i\braket{a_1,\cdots,a_{i-1},a_{i+1},\cdots,a_l}.
\end{aligned}
$$
One can prove that $\partial\circ\partial=0$, which is similar to [[Differential geometry#2.1.3 Exterior derivative|exterior derivative]].

### 3.4 Homology group
For an $n$ dimensional simplical complex $K$, a *chain complex* $(C_\bullet,\partial)$ is the sequence of groups $C_i(K)$ with maps $\partial:C_q\to C_{q-1}$
$$
0\stackrel{\partial_{n+1}}{\to}C_n\stackrel{\partial_n}{\to}C_{n-1}\to\cdots\to C_1\stackrel{\partial_1}{\to}C_0\stackrel{\partial_0}{\to}0.
$$
One can define
$$
Z_q(K)\doteq\mathrm{Ker}\ \partial_q,\quad B_q(K)\doteq\mathrm{Im}\ \partial_{q+1}.
$$
Then the $q$-th *homology group* of $C_\bullet(K)$ is defined as
$$
H_q(K;\mathbb{Z})\doteq Z_q(K)/B_q(K).
$$

One can prove that for any $M$ with two different triangulations $|K_1|\to M$ and $|K_2|\to M$, their homology group
$$
\forall q,\quad H_q(K_1;\mathbb{Z})\cong H_q(K_2;\mathbb{Z}).
$$
Therefore, one can define $H_q(M;\mathbb{Z})$ as a topological invariant of $M$.

### 3.5 Eular characteristic
Consider the background ring $\mathbb{R}$. The dimension of $H_q(M;\mathbb{R})$ is called the $q$-th *Betti number*. Its alternative sum is the *Eular characteristic* of $M$
$$
\chi(M)\doteq\sum_q(-1)^q\dim H_q(M;\mathbb{R}).
$$
One can prove that this is equivalent to
$$
\chi(M)=\sum_q(-1)^q\dim C_q(K;\mathbb{R}),
$$
which is a generalization of the 2-dimensional case $\chi=\mathrm{V}-\mathrm{E}+\mathrm{F}$.

### 3.6 Simplicial map
For two simplicial complex $K_1$ and $K_2$, a *simplicial map* is a map $f:K_1\to K_2$ that if $\braket{a_1,\cdots,a_l}$ is a simplex in $K_1$, then $\braket{f(a_1),\cdots,f(a_l)}$ is a simplex in $K_2$.

A simplicial map induces a homomorphism between chain groups
$$
\begin{aligned}
f_\ast:&&C_\bullet(K_1)&\to C_\bullet(K_2)\\
&&\braket{a_1,\cdots,a_l}&\mapsto\left\{\begin{aligned}
&\braket{f(a_1),\cdots,f(a_l)},&&f(a_i)\ne f(a_j)\\
&0&&\exists f(a_i)=f(a_j).
\end{aligned}\right.
\end{aligned}
$$
Such homomorphism commutes with the boundary homomorphism
$$
f_\ast\circ\partial=\partial\circ f_\ast.
$$

## 4 Cohomology
### 4.1 Cochain group
For a chain group $C_q(K)$, one can define the *cochain group* as
$$
C^q(K)\doteq\mathrm{Hom}(C_q(K),\mathbb{Z}).
$$
In the case of $\mathbb{R}$, the cochain group $C^q(K)$ is just the dual vector space of chain group $C_q(K)$.

One can also define the *coboundary map* $\delta:C^q\to C^{q+1}$ that
$$
\forall f\in C^q,\quad\delta f:c\mapsto f(\partial c),
$$
where $c\in C_{q+1}$. It satisfies $\delta\circ\delta=0$.

### 4.2 Cochain complex
Similar to the chain complex, the coboundary map gives a cochain complex
$$
0\stackrel{\delta^0}{\to}C^0\stackrel{\delta^1}{\to}C^1\to\cdots\to C^{n-1}\stackrel{\delta^{n-1}}{\to}C^n\stackrel{\delta^n}{\to}0.
$$
Then one can define
$$
Z^q\doteq\mathrm{Ker}\ \delta^q,\quad B^q\doteq\mathrm{Im}\ \delta^{q-1}.
$$
The *cohomology group* is then defined as
$$
H^q(K;\mathbb{Z})\doteq K^q/B^q.
$$

There exists a bilinear map
$$
H_q(K;\mathbb{Z})\otimes H^q(K;\mathbb{Z})\to\mathbb{Z}.
$$
When considering $\mathbb{R}$, $H^q(K;\mathbb{R})$ is the dual vector space of $H_q(K;\mathbb{R})$.

### 4.3 de Rham theorem
For a smooth manifold $M$ and a triangulation $|K|\to M$, the *de Rham theorem* states that there is an isomorphism
$$
H^\bullet_{\text{dR}}(M)\cong H^\bullet(K;\mathbb{R}).
$$
As the wedge product in $H^\bullet_{\text{dR}}$, there is a *cup product* in $H^\bullet$
$$
\cup:C^k(K)\times C^l(K)\to C^{k+l}(K)
$$
that for $\sigma=\braket{a_1,\cdots,a_{k+l}}$, there is
$$
(\varphi\cup\psi)(\sigma)=\varphi(\braket{a_1,\cdots,a_k})\psi(\braket{a_k,\cdots,a_{k+l}}).
$$

The structure $(H^\bullet,\cup)$ forms a structure of *cohomology ring*.

### 4.4 Poincare duality
For an $n$-dimensional oriented connected closed manifold $M$, a $k$-dimensional submanifold $N\subset M$ can be viewed as a (representitive) element $[N]\in H_k(M)$. It can be proved that there exists $\eta\in H^{n-k}(M)$ such that
$$
\forall\omega\in H^k(M),\quad\int_N\omega=\int_M\omega\wedge\eta.
$$
This isomorphism is called the *Poincare duality*
$$
\begin{aligned}
\vartheta:&&H_k(M)&\cong H^{n-k}(M)\\
&&[N]&\mapsto\eta.
\end{aligned}
$$

For two submanifolds $[N_1]\in H_k(M)$ and $[N_2]\in H_{n-k}(M)$, their *intersection number* is defined as
$$
[N_1]\cdot[N_2]\doteq\int_M\vartheta(N_1)\wedge\vartheta(N_2).
$$

## 5 Mapping degree
### 5.1 Mapping degree
For two $n$ dimensional smooth oriented connected closed manifolds $M$ and $N$, a smooth map $f:M\to N$ induces a homomorphism $f_\ast:H_\bullet(M;\mathbb{Z})\to H_\bullet(N;\mathbb{Z})$. The *mapping degree* of $f$ is defined as
$$
\deg f\doteq\frac{\displaystyle\int_Mf^\ast\mathrm{vol}_N}{\displaystyle\int_N\mathrm{vol}_N}.
$$

### 5.2 Linking number
For two knots $K_i:S^1\to\mathbb{R}^3$, one can define a map
$$
\begin{aligned}
F:&&S^1\times S^1&\to S^2\\
&&(x_1,x_2)&\mapsto\frac{x_1-x_2}{|x_1-x_2|}.
\end{aligned}
$$
The mapping degree of the map $F$ is the *linking number* of the two knots
$$
\mathrm{Lk}(K_1,K_2)\doteq\deg F=\frac{1}{4\pi}\int_{S^1}\mathrm{d}x_1^i\int_{S^1}\mathrm{d}x_2^j\frac{(x_1-x_2)^k}{|x_1-x_2|^3}\epsilon_{ijk},
$$
where $\mathrm{vol}_{S^2}=\dfrac{1}{2}\epsilon_{ijk}x^i\mathrm{d}x^j\wedge\mathrm{d}x^k$.

## 6 Mayer-Vietoris exact sequence
### 6.1 Exact sequence
For a sequence of homomorphism
$$
\cdots\stackrel{f_{q+2}}{\to}M_{q+1}\stackrel{f_{q+1}}{\to}M_q\stackrel{f_q}{\to}M_{q-1}\stackrel{f_{q-1}}{\to}\cdots,
$$
if it satisfies
$$
\forall q,\quad\mathrm{Ker}\ f_q=\mathrm{Im}\ f_{q+1},
$$
then it is called an *exact sequence*.

### 6.2 Mayer-Vietoris theorem
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

### 6.3 Poincare lemma
For two homotopy equivalent simplicial complex $K_1$ and $K_2$, their homology groups are isomorphic
$$
H_\bullet(K_1;\mathbb{Z})\cong H_\bullet(K_2;\mathbb{Z}).
$$
As a special case, any contractible space has the homology group isomorphic to that of a point
$$
H_q(\mathbb{R}^n;\mathbb{R})=\left\{\begin{aligned}
&\mathbb{R},&&q=0\\
&0,&&q\ne0.
\end{aligned}\right.
$$
This is called the *Poincare lemma*.