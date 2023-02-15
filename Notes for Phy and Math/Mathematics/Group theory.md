---
banner: "![[f7d4736291c346278d477c9b5c21d8fa1662047112613.jpeg]]"
banner_y: 0.28
---
# Group theory
## 1 Abstract group theory
---
### 1.1 Basic concepts
#### 1.1.1 Equivalence relation
For any set $X$, an *equivalence relation* is a binary relation $\sim$ that satisfies
$$\begin{aligned}\forall a,b,c\in X,\quad&a\sim a;\\
&a\sim b\Rightarrow b\sim a;\\
&(a\sim b)\land(b\sim c)\Rightarrow a\sim c.\end{aligned}$$
Notice that equivalence relation is not always equality.

With an equivalence relation $\sim$ on a set $X$, one can define *equivalence class* $[a]$
$$[a]\doteq\{x:x\in X,x\sim a\}.$$
It can be proved that equivalence classes divide a set into disjoint subsets. And with a given disjoint decomposition of the set one can naturally construct an equivalence relation.

#### 1.1.2 Group
A *group* is a set $G$ equipped with a *multiplication map* $\ast:G\times G\to G$, an *inverse map* $(\cdot)^{-1}:G\to G$ and an *identity element* $1_G\in G$. They sadisfy that $\forall g_1,g_2,g_3\in G$,
$$\begin{aligned}&g_1\ast g_1^{-1}=g_1^{-1}\ast g_1=1_G;\\
&1_G\ast g_1=g_1\ast 1_G=g_1;\\
&g_1\ast(g_2\ast g_3)=(g_1\ast g_2)\ast g_3.\end{aligned}$$
A set with only an associative multiplication map is called a *monoid*. If it also has an identity element then it is called *unital monoid*.

A *subgroup* of $G$ is a subset $H$ that multiplication and inverse map preserve it.

The *direct product* of two groups $G(\cdot)$ and $H(\ast)$ is also a group $G\times H$ with multiplication map $\star$
$$(g_1,h_1)\star(g_2,h_2)\doteq(g_1\cdot g_2,h_1\ast h_2).$$

#### 1.1.3 Order of a group
The *order* of a group $G$ is the cardinality of $G$ as a set, denoted as $|G|$. That is roughly the number of elements in it. A group with its order $|G|<\infty$ is called a *finite group*, otherwise it is called an *infinite group*.

The *order* of a group element $g$ is defined as the smallest natural number $n$ that makes $g^n=1_G$. Note that for a finite group $g^{|G|}=1_G$, so $|G|/n\in\mathbb{N}$. An element with order $2$ is called an *involution*.

#### 1.1.4 Abelian group
Two group elements $a$ and $b$ are *commute* if they satisfy
$$a\cdot b=b\cdot a.$$
A group with every element commute with each other is called an *Abelian group*.

The *center* of a group is the set of elements that commute with all elements in the group, denoted as $Z(G)$
$$Z(G)\doteq\{z\in G:\forall g\in G,z\cdot g=g\cdot z\}.$$
The center of a group is an abelian subgroup of it.

#### 1.1.5 General linear group
*General linear group* is an important example of non-abelian group. It is defined as the group of all invertible linear transformation of a given vector space $V$, denoted as $\mathrm{GL}(V)$.

For a finite dimensional $V$, there's an equivalent definition. Since $V$ is isomorphic to $\mathbb{F}^n$ where $\mathbb{F}$ is a field, one can define the general linear group as the group of all invertible $n\times n$ matrix on field $\mathbb{F}$. Under this definition, $\mathrm{GL}(V)$ is also denoted as $\mathrm{GL}(n,\mathbb{F})$.

Here are some important subgroups of $\mathrm{GL}(n,\mathbb{F})$,
- special linear group
$$\mathrm{SL}(n,\mathbb{F})\doteq\{A\in\mathrm{GL}(n,\mathbb{F}):\det A=1\};$$
- (special) orthorgonal group
$$\begin{aligned}&\mathrm{O}(n,\mathbb{F})\doteq\{A\in\mathrm{GL}(n,\mathbb{F}):AA^T=\mathbb{1}\},\\&\mathrm{SO}(n,\mathbb{F})\doteq\{A\in\mathrm{O}(n,\mathbb{F}):\det A=1\};\end{aligned}$$
- (special) unitary group
$$\begin{aligned}&\mathrm{U}(n)\doteq\{A\in\mathrm{GL}(n,\mathbb{C}):AA^H=\mathbb{1}\},\\&\mathrm{SU}(n)\doteq\{A\in\mathrm{U}(n):\det A=1\};\end{aligned}$$
- symplectic group
$$\mathrm{Sp}(2n,\mathbb{F})\doteq\{A\in\mathrm{GL}(2n,\mathbb{F}):A^TJA=\mathbb{1}\},$$
where $J$ is *standard symplectic form* on $\mathbb{R}^{2n}$, defined as
$$J\doteq\begin{pmatrix}0 & \mathbb{1}_n\\-\mathbb{1}_n & 0\end{pmatrix}.$$

#### 1.1.6 Examples of groups
Some common groups are listed here.
- The *cyclic group* of order $N$, denoted as $\mathbb{Z}_N$, is a group defined on $\{0,1,\cdots,N-1\}$, with the group multiplication defined as
$$a\cdot b\doteq(a+b)\mod N;$$
- The *permutation group* on a set $X$ is denoted as $S_X$. It is the group of all invertible maps from $X$ to itself. Invertible here implies that the maps are one-one maps. Group multiplication is simply composition of two maps;
- The *quaternion group* is a group of order $8$, denoted as $Q\doteq\{\pm1,\pm i,\pm j,\pm k\}$. They satisfy the multiplication rule as follow$$i\cdot j=k,\quad i\cdot i=j\cdot j=k\cdot k=-1,$$where the first rule is valid under rotation.
- A function space as a group. The set of all maps from $X$ to a group $G$ forms a group, denoted as $\mathcal{F}[X\to G]$. The group multiplication is simply the multiplication of $G$
$$(f_1\ast f_2)(x)\doteq f_1(x)\times_G f_2(x);$$
- The power set $\mathcal{P}(X)$ of a set $X$ also forms a group. The group multiplication is the symmetric difference of two subsets
$$Y_1\cdot Y_2\doteq(Y_1-Y_2)\cup(Y_2-Y_1).$$

---
### 1.2 Homomorphism and isomorphism
#### 1.2.1 Definition
For two groups $G(\times)$ and $H(\ast)$, a *homomorphism* is a map $\phi:G\to H$ that preserves the group structure
$$\phi(g_1\times g_2)=\phi(g_1)\ast\phi(g_2).$$
If the map is one-one and onto, then it is called an *isomorphism*. If $\phi$ is a homomorphism and $G=H$ then it is called an *endomorphism*. If $\phi$ is also an isomorphism, then it is called an *automorphism*.

The set of all homomorphisms from $G$ to $H$ is denoted as $\mathrm{Hom}(G,H)$. In the same way is $\mathrm{Iso}\ (G,H)$, $\mathrm{End}(G)$ and $\mathrm{Aut}(G)$ defined.

#### 1.2.2 The great $\mathbb{R}^2$ isomorphic theorem
This is an significant achievement of myself. I came up with it one night returning to my dorm with my roommate. This theorem defines the boundary of mathematics human could reach. *The great $\mathbb{R}^2$ isomorphic theorem* states that any math or physics theorem or statement is isomorphic to $\mathbb{R}^2$.

The proof is trivial. Since any math or physics theorem and statement human could study is written on scratch paper, and the surface of a paper is isomorphic to $\mathbb{R}^2$, the proof is therefore finished.

In recent years, this theorem faces challenge due to the wide use of computer technology.

#### 1.2.3 Representation
A (linear) *representation* of a group $G$ is a homomorphism from $G$ to a general linear group
$$\rho:G\to\mathrm{GL}(V),$$
where $V$ is called the *representation space*. For instance, the homomorphism
$$\pi:\mathrm{SU}(2)\to\mathrm{SO}(3)$$
offers a representation of $\mathrm{SU}(2)$ on $\mathbb{R}^3$.

More detailed discussion on representation theory can refer to [[Representation theory]].

#### 1.2.4 Fiber product
For two groups $G_1$ and $G_2$ that are homomorphic to a same group $H$
$$\begin{aligned}&\phi_1:G_1\to H\\&\phi_2:G_2\to H,\end{aligned}$$
a subgroup of $G_1\times G_2$ can be constructed as
$$G_1\times_{\phi_1,\phi_2}G_2\doteq\{(g_1,g_2)|\phi_1(g_1)=\phi_2(g_2)\}.$$
This is called their *fiber product*.

---
### 1.3 Group action
#### 1.3.1 Left group action
A *left group action* of a group $G$ on a set $X$ is a map $\cdot:G\times X\to X$ that satisfies
$$
\begin{aligned}
&g_1\cdot(g_2\cdot x)=(g_1\cdot g_2)\cdot x, \\
&1_G\cdot x=x.
\end{aligned}
$$
An alternative way is to define a map $\Phi:G\to S_X$ so that
$$
\begin{aligned}
\Phi(g):X&\to X \\
x&\mapsto g\cdot x.
\end{aligned}
$$
In this way, the restrictions become $\Phi(g_1)\circ\Phi(g_2)=\Phi(g_1\ast g_2)$ and $\Phi(1_G)(x)=x$.

If $G$ can act on $X$, then $X$ is called a *$G$-set*.

#### 1.3.2 Orbit
If $X$ is a $G$-set, then one can define an equivalence relation $\sim$ on $X$
$$a\sim b\quad\Leftrightarrow\quad\exists g\in G,g\cdot a=b.$$
The equivalence class of this relation $[x]$ is called the *orbit* of $G$ through point $x$. The set of orbits is denoted as $X/G$.

#### 1.3.3 Group action on associated function space
If $X$ is a $G$-set and $Y$ is any set, then there is naturally a left group action on the function space $\mathcal{F}[X\to Y]$, defined as
$$(g\cdot F)(x)\doteq F(g^{-1}\cdot x).$$
The inverse here is to ensure the group action is associative for non-abelian group
$$(g\cdot(h\cdot F))(x)=(h\cdot F)(g^{-1}\cdot x)=F(h^{-1}\cdot g^{-1}\cdot x)=((g\cdot h)\cdot F)(x).$$

---
### 1.4 Permutation group
#### 1.4.1 Symmetric group
Recall that a permutation group $S_X$ on a set $X$ is the group of invertible maps from $X$ to itself. If $X=\{1,2,\cdots,n\}$, then $S_X$ is called a *symmetric group*, denoted as $S_n$. Its element can be denoted as
$$\phi=\begin{pmatrix}1 & 2 & \cdots & n\\\phi_1 & \phi_2 & \cdots & \phi_n\end{pmatrix},$$
which maps $i$ to $\phi_i$. Here different $\phi_i$ have different values. Its inverse is then
$$\phi^{-1}=\begin{pmatrix}\phi_1 & \phi_2 & \cdots & \phi_n\\1 & 2 & \cdots & n\end{pmatrix}.$$

#### 1.4.2 Cayley's theorem
*Cayley's theorem* states that a finite group $G$ is isomorphic to a subgroup of $S_G$.

To prove this note that multiplying a group element $g$ on the entire group
$$g\cdot G\doteq\{g\cdot g_1,g\cdot g_2,\cdots\}$$
is equivalent to applying a permutation since $g\cdot g_1\ne g\cdot g_2$ if $g_1=g_2$. This is called the *rearrangement lemma*. Thus an element of $G$ can be mapped to an element of $S_G$. ^4e9ddd

#### 1.4.3 Cyclic permutation
For $m$ elements $\{a_1,a_2,\cdots,a_m\}$, consider the permutation
$$a_1\to a_2\to\cdots\to a_m\to a_1$$
that leaves the other $n-m$ elements unchanged. This is called the *cyclic permutation* of length $m$, denoted as $(a_1a_2\cdots a_m)$. Note that
$$(a_1a_2\cdots a_m)=(a_2\cdots a_ma_1)=\cdots.$$

The multiplication of cyclic permutations satisfies
$$(a_1\cdots a_k)\cdot(a_k\cdots a_m)=(a_1\cdots a_m),$$
where $a_i\ne a_j$ for $i\ne j$. Disjoint permutations commute with each other.

It can be proved that any permutation can be written as product of disjoint cyclic permutations, which is called the *cycle decomposition*.

#### 1.4.4 Transposition
A *transposition* is a permutation of the form $(ij)$. It satisfies
$$\begin{aligned}&(ij)\cdot(jk)\cdot(ij)=(ik),\\&(ij)^2=1_S.\end{aligned}$$
Any cyclic permutation can be written as product of transpositions, and thus any permutation can.

#### 1.4.5 Odd and even
A permutation can be decomposed into transpositions in different ways, but the numbers of transpositions have the same parity. A permutation consists of even (odd) number of transpositions is called a *even (odd) permutation*.

The *sign homomorphism* is the homomorphism
$$\mathrm{sgn}:S_n\to\mathbb{Z}_2$$
that maps even permutations to $+1$ and odd permutations to $-1$. This is sometimes denoted as the Levi-Civita symbol $\epsilon_{a_1a_2\cdots a_n}$, which means the sign of
$$\begin{pmatrix}1 & 2 & \cdots & n\\a_1 & a_2 & \cdots & a_n\end{pmatrix}.$$ ^3aa69c

The *alternating group* $A_n$ is a subgroup of $S_n$ consisting of even permutations.

---
### 1.5 Generator
#### 1.5.1 Generator
The *generating set* is a subset $S\subset G$ that every element in $G$ can be written as a product of elements in $S$
$$g=s_{i_1}s_{i_2}\cdots s_{i_n}.$$
If the generating set of a group is finite, then the group is called *finitely generated*.

A finitely generated set can be denoted as
$$G=\braket{S}=\braket{s_1,s_2,\cdots|R_1,R_2,\cdots},$$
where $s_i$ are elements in $S$ and $R_i=1_G$ are *relations* which are products of $s_i$. All other identities in $G$ should be consequences of these relations.

#### 1.5.2 Free group
If a group is generated with no restrictions, that is with no relations attached to the generating set, then it is called a *free group*, denoted as $F(S)$. The subgroup of a free group is also a free group. This is called the *Nielsen-Shreier theorem*.

Two free groups of the same order are isomorphism.

#### 1.5.3 Tietze transformation
*Tietze transformations* are four transformations on the generating set and relation that transforms a group to an isomorphic one. The transformations are listed here.
- If $R_i$ can be derived from the basic relations, then add $R_i$ to the basic relations;
- If $R_i$ is a basic relation that can be derived from other basic relations, then remove $R_i$ from the basic relations;
- If $R_i\cdot s^{-1}$ can be derived from basic relations, then add it to the basic relations and add $s$ to the generating set;
- If $R_i\cdot s^{-1}$ is a basic relation and $s$ is a generator, then remove $s$ from the generating set, remove $R_i\cdot s^{-1}$ from the basic relations, and replace $s$ in other basic relations with $R_i$.

---
### 1.6 Coset and conjugacy
#### 1.6.1 Coset
For a subgroup $H$ of $G$, the *left-coset* of $H$ is defined as
$$gH\doteq\{gh:h\in H\}.$$
Two left-cosets are either identical or disjoint, and every group element is in one of the cosets.

The set of cosets of $H$ in $G$ is called a *homogeneous space*, denoted as $G/H$. This is the orbit under right $H$ action on $G$. The order of $G/H$ is called the *index of $H$ in $G$*, denoted as $[G:H]$.

#### 1.6.2 Order of a group, again
For a finite group $G$ and its subgroup $H$, their orders satisfy $|G|/|H|\in\mathbb{N}$. This is called the *Lagrange theorem*. As a corollary, a group with prime order p is isomorphic to Zp and has no non-trivial subgroup.

For a prime number $p$, if $|G|/p^k\in\mathbb{N}$, then $G$ has a subgroup $H$ of order $p^k$. This is called the *Sylow's (first) theorem*.

#### 1.6.3 Conjugacy
Two group elements $g_1$ and $g_2$ are called *conjugate* if there is an $h\in G$ that $g_1=hg_2h^{-1}$. Conjugacy defines an equivalence relation and the corresponding equivalence class is called *conjugacy class*. A function of conjugacy classes is called a *class function*. ^e1a076

Two subgroups $H$ and $K$ of $G$ are called *conjugate* if there is a $g\in G$ that
$$K=gHg^{-1}\doteq\{ghg^{-1}\}.$$
Two isomorphisms from $H$ to $G$ are called *conjugate* if there is a $g\in G$ that$$
\forall h\in H,\quad \phi(h)=g\cdot\varphi(h)\cdot g^{-1}.
$$^4b8273

#### Normal subgroups and quotient group
A *normal subgroup* or *invarient subgroup* is a subgroup $N$ that satisfies
$$\forall g\in G,\quad gNg^{-1}=N.$$
Sometimes this is denoted as $N\triangleleft G$.

If $N\triangleleft G$, then the set of left cosets $G/N$ naturally forms a group with group multiplication defined as
$$(gN)\ast(hN)\doteq(g\cdot h)N.$$
This is called a *quotient group*.

A group with no nontrivial normal subgroup is called a *simple group*.