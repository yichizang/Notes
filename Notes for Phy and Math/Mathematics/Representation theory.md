---
banner: "![[mmexport1673758945790.jpg]]"
banner_y: 0.184
---

>[!abstract]- Pre-knowledge
>- [[Abstract group theory]]
>- [[Linear algebra]]

# Representation theory
## 1 Finite group
In this chapter, groups are finite by default.

---
### 1.1 Representation of finite group
#### 1.1.1 Definition of representation
A *representation* of a group $G$ on a finite dimensional complex vector space $V$ is defined as a [[Abstract group theory#2.1 Definition|homomorphism]] $\rho$
$$\rho:G\to\mathrm{GL}(V).$$
We say that $\rho$ gives $V$ a *$G$-module* structure.

Sometimes we call $V$ itself the representation of $G$, in which case we denote $\rho(g)(\ket{v})$ as $g\cdot\ket{v}$ or $g\ket{v}$. The [[Linear algebra#1.5 Dimensionality|dimension]] of $V$ is sometimes called the *degree* of the representation.

For two representations $V$ and $W$, a map $\varphi:V\to W$ is called a *$G$-linear map* if it [[Abstract group theory#1.4 Abelian group|commutes]] with all $g\in G$.

A *subrepresentation* of $V$ is the representation on $V$'s $G$-invariant subspace $W$. If $V$ has no proper non-zero subrepresentation, then it is an *irreducible* representation.

#### 1.1.2 Operations of representation
For two representations $V$ and $W$, their [[Linear algebra#^fd1ad8|direct sum]] and [[Linear algebra#0.1.1 Tensor product|tensor product]] are also representations of the group, the latter defined as
$$g(\ket{v}\otimes\ket{w})\doteq g\ket{v}\otimes g\ket{w}.$$

The [[Linear algebra#5.1 Dual space|dual vector space]] $V^*\doteq\mathrm{Hom}(V,\mathbb{C})$ is also a representation, defined in the way that the natural pairing $\braket{u|v}$ between $V^*$ and $V$ is preserved. So the dual homomorphism $\rho^*$ satisfies
$$\braket{u|g^*g|v}=\braket{u|v},$$
where $\bra{u}g^*=\rho^*(g)(\bra{u})$. To satisfy that, $\rho^*$ has to be defined as
$$\rho^*(g)\doteq{}^t\rho(g^{-1}),$$
where the upper ${}^t$ refers to the [[Linear algebra#0.1.2 Adjoint map|adjoint map]].

More generally, $\mathrm{Hom}(V,W)$ is also a representation, noticing $\mathrm{Hom}(V,W)=V^*\otimes W$. For any $\varphi\in\mathrm{Hom}(V,W)$, by writing it in the form of
$$\varphi=\sum_i\ket{w_i}\bra{v_i},$$
it's easy to show that
$$(g\varphi)\ket{v}=\sum_ig\ket{w_i}\bra{v_i}g^{-1}\ket{v}=g\ \varphi\ g^{-1}\ket{v}.$$

#### 1.1.3 Regular representation
The [[Abstract group theory#3.1 Left group action|left group action]] of $G$ on a set $X$ naturally generates a representation called the *permutation representation*. The representation space is the vector space [[Linear algebra#1.3 Span|spanned]] from a set of [[Linear algebra#^b3f615|basis]] $\{\ket{e_x}\}$ marked by elements in $X$. The representation is defined as
$$g\ket{v}=g\sum_xv_x\ket{e_x}\doteq\sum_xv_x\ket{e_{gx}}.$$

When the set $X$ is $G$ itself, this representation is called the *regular representation*, denoted as $R$ or $R_G$.

#### 1.1.4 Complete reducibility
For any subrepresentation $W\subset V$ of group $G$, there is a complementary $G$-[[Linear algebra#6.1 Invarient subspace|invarient subspace]] $U\subset V$ that makes $V=U\oplus W$. This can be proved by constructing a $G$-invarient inner product and then taking the orthogonal subspace of $W$ as $U$.

Any representation can be written as a direct sum of irreducible representations. This property is called *complete reducibility* or *semisimplicity*. Complete reducibility can be generalized to representation of compact groups.

#### 1.1.5 Schur's lemma
*Schur's lemma* is an important lemma in representation theory. It states that for two irreducible representations $V$ and $W$ of $G$ and a homomorphism $\varphi:V\to W$, the following statements hold:
- Either $\varphi$ is an isomorphism or $\varphi=0$.
- If $V=W$ then $\varphi=\lambda\cdot 1_V$, where $\lambda\in\mathbb{C}$ and $1_V$ is the identity map.

Using Schur's lemma, one can prove that for any representation $V$ of $G$, there is a unique way to deecomposite it into direct sum of irreducible representations
$$V=\bigoplus_iV_i^{\oplus a_i}.$$
Note that the decomposition of the $n$th term into $a_n$ copies of $V_n$ is not unique if $a_n>1$.

---
### 1.2 Character
#### 1.2.1 Definition of character
For a representation $V$ of $G$, its *character* $\chi_V$ is defined as a function on $G$
$$\chi_V(g)\doteq\mathrm{Tr}\ \rho(g).$$
Character is a [[Abstract group theory#^e1a076|class function]], and $\chi_V(1_G)=\dim V$.

For two representations $V$ and $W$ of $G$, their characters satisfy
$$
\begin{aligned}&\chi_{V\oplus W}=\chi_V+\chi_W, \\
&\chi_{V\otimes W}=\chi_V\cdot\chi_W, \\
&\chi_{V^*}=\chi^*_V, \\
&\chi_{\wedge^2V}(g)=\frac{1}{2}\left[\chi_V(g)^2-\chi_V(g^2)\right], \\
&\chi_{\mathrm{Sym}^2V}(g)=\frac{1}{2}\left[\chi_V(g)^2+\chi_V(g^2)\right].\end{aligned}
$$
^e0aad1

#### 1.2.2 Character table
A *character table* is a table with information about different representations of a group.

Take the [[Abstract group theory#4.1 Symmetric group|symmetric group]] $S_3$ as an example. It has three irreducible representations, namely,
- the *trivial representation* $U$;
- the *alternating representation* $U'$, which maps like the [[Abstract group theory#^3aa69c|sign homomorphism]];
- the *standard representation* $V$, which is a two dimensional representation decomposed from the permutation representation. It maps according to the permutation of $\{\ket{e_1},\ket{e_2},-(\ket{e_1}+\ket{e_2})\}$.

The character table of $S_3$ looks like

|            $S_3$ | $1_S$ | $(12)$ | $(123)$ |
| ----------------:| -----:| ------:| -------:|
|                  |     1 |      3 |       2 |
|      trivial $U$ |     1 |      1 |       1 |
| alternating $U'$ |     1 |     -1 |       1 |
|     standard $V$ |     2 |      0 |      -1 |

The first two rows have the group name and list the representitive element and size of all the conjugacy classes. Below are different irreducible representations and their characters.

Character table can be used to work out the decomposition of an arbitary representation basing on the fact that
$$
V=\bigoplus_iV_i^{\oplus a_i}\quad\Rightarrow\quad \chi_V=\sum_ia_i\chi_{i}.
$$

#### 1.2.3 Projection to trivial representations
For a representation $V$ of group $G$, define
$$
V^G\doteq\{\ket{v}:\forall g\in G,g\ket{v}=\ket{v}\}.
$$
This is the direct sum of all trivial subrepresentations of $V$. To find $V^G$, consider the map $\varphi$
$$
\mathrm{End}(V)\ni\varphi\doteq\frac{1}{|G|}\sum_{g\in G}g.
$$
It is a $G$-linear map that projects $V$ to $V^G$. To prove this note that according to [[Abstract group theory#^4e9ddd|rearrangement lemma]], one have
$$
h\sum g=\sum g.
$$
Also $\varphi\circ\varphi=\varphi$.

The number $n$ of trivial representations in the decomposition of $V^G$ is the dimension of $V^G$ since a trivial representation has the dimension of $1$. So
$$
n=\dim V^G=\mathrm{Tr}\ \varphi=\frac{1}{\left|G\right|}\sum_g\chi_V(g).
$$

#### 1.2.4 Orthogonality of character
For two irreducible representations $V$ and $W$, consider the representation $\mathrm{Hom}(V,W)^G$. This is the set of all $G$-linear maps from $V$ to $W$. According to Schur's lemma, one have
$$
\dim\mathrm{Hom}(V,W)^G=\left\{\begin{aligned}
&1 && V\cong W,\\
&0 && V\not\cong W.
\end{aligned}\right.
$$
On the other hand, since $\mathrm{Hom}(V,W)=V^*\otimes W$, its character is
$$
\chi_{\mathrm{Hom}(V,W)}(g)=\chi^*_V(g)\cdot\chi_W(g).
$$
This means that
$$
\frac{1}{|G|}\sum_g\chi^*_V(g)\chi_W(g)=\left\{\begin{aligned}
&1 &&V\cong W, \\
&0 &&V\not\cong W.
\end{aligned}\right.
$$

To interpret it, consider the vector space of all class functions on $G$, denoted as $\mathbb{C}_{\text{class}}(G)\cong\mathbb{C}^c$ where $c$ is the number of conjugacy classes in $G$. Define an inner product on $\mathbb{C}_{\text{class}}(G)$ as
$$
\braket{\alpha,\beta}\doteq\frac{1}{|G|}\sum_g\alpha^*(g)\beta(g).
$$
Then characters of different irreducible representations of $G$ are orthonormal under this inner product. 

#### 1.2.5 Completeness of character
In general, for a group function $\alpha:G\to\mathbb{C}$, the following map
$$
\varphi\doteq\sum_g\alpha(g)g
$$
is a $G$-linear map for all $V$ if and only if $\alpha$ is a class function.

Suppose that $\braket{\alpha,\chi_V}=0$ for any irreducible $V$. According to Schur's lemma, $\varphi=\lambda\cdot 1_V$. Then
$$
\begin{aligned}
\lambda=&\frac{1}{\dim V}\mathrm{Tr}\ \varphi
=\frac{1}{\dim V}\sum_g\alpha(g)\chi_V(g) \\
=&\frac{|G|}{\dim V}\braket{\alpha,\chi_{V^*}}^*=0,
\end{aligned}
$$
which means that $\varphi=0_V$. Using the linear independence of $g$, one can prove that $\alpha(g)=0$ for all $g$. This means that charaters of irreducible representations are also complete on $\mathbb{C}_{\text{class}}$.

Completeness means that the number of different irreducible representations of $G$ is equal to the number of conjugacy classes in $G$.

On the other direction of the character table, the orthogonal relation also holds. Namely
$$
\frac{1}{|G|}\sum_i\chi^*_i(g)\chi_i(h)=\left\{\begin{aligned}
&\frac{1}{c(g)} &&g\sim h, \\
&0 &&g\not\sim h,
\end{aligned}\right.
$$
where $c(g)$ is the number of elements in the conjugacy class of $g$, and the sum is over all irreducible representations.

#### 1.2.6 A general projection
For two irreducible representations $V$ and $W$, consider the map
$$
\mathrm{End}(V)\ni\psi\doteq\frac{\dim W}{|G|}\sum_g\chi_W^\ast(g)\cdot g.
$$
According to the Schur's lemma, $\psi=\lambda\cdot 1_V$. So
$$
\begin{aligned}
\lambda=&\frac{\mathrm{Tr}\ \psi}{\dim W} \\
=&\frac{1}{|G|}\sum_g\chi_W^\ast(g)\cdot\chi_V(g) \\
=&\left\{\begin{aligned}
&1 &&V=W \\
&0 &&V\ne W.
\end{aligned}\right.
\end{aligned}
$$

Therefore, for a representation $V=\bigoplus_iV_i^{\oplus a_i}$ where $V_i$ are irreducible representations, the map
$$
\pi_i\doteq\frac{\dim W}{|G|}\sum_g\chi_i^\ast(g)\cdot g
$$
is the projection of $V$ onto $V_i$.

#### 1.2.7 Decomposition of representations
For a representation $V$ that can be decomposed into irreducible representations as
$$
V=\bigoplus_iV_i^{\oplus a_i},
$$
one can work out each $a_i$ using the orthonormality of characters of irreducible representations
$$
a_i=\braket{\chi_V,\chi_i}.
$$
Also, since
$$
\braket{\chi_V,\chi_V}=\sum_ia_i^2,
$$
the representation $V$ is irreducible if and only if $\braket{\chi_V,\chi_V}=1$.

When applying above to the regular representation $R_G$, noticing that
$$
\chi_R(g)=\left\{\begin{aligned}
&0 &&g\ne1_G, \\
&|G| &&g=1_G,
\end{aligned}\right.
$$
the number of $V_i$ in $R_G$ is given by
$$
a_i=\braket{\chi_R,\chi_i}=\frac{1}{|G|}\chi_i(1_G)\cdot|G|=\dim V_i.
$$

#### 1.2.8 Representation ring
The *representation ring* $R(G)$ of group $G$ is a ring structure generated by representations of $G$. The addition structure of $R(G)$ is a [[Abstract group theory#5.2 Free group|free]] abelian group generated by irreducible representations $V_i$ of $G$. Namely the elements of $R(G)$ can be written in the form of
$$
\sum_ia_iV_i,\quad a_i\in\mathbb{Z}.
$$
The multiplication is tensor product on the generators. Elements of $R(G)$ are called *virtual representations*.

With representation ring, character can be defined as a ring homomorphism
$$
\chi:R(G)\to\mathbb{C}_{\text{class}}(G)
$$
according to the [[Representation theory#^e0aad1|properties of character]]. This map is an injective, and elements in $\mathrm{Im}\ \chi$ are called *virtual characters*.

Notice that $\chi$ induces an isomorphism
$$
\begin{aligned}
\chi_{\mathbb{C}}:R(G)\otimes\mathbb{C}&\to\mathbb{C}_{\text{class}} \\
\sum_ic_iV_i&\mapsto\sum_ic_i\chi_i.
\end{aligned}
$$

The virtual representations (characters) of $G$ form a lattice $\Lambda\cong\mathbb{Z}^c$ in $\mathbb{C}_{\text{class}}$, and the actual representations (characters) form a cone $\Lambda_0\cong\mathbb{N}^c\subset\mathbb{Z}^c$.

---
### 1.3 Induction and restriction
#### 1.3.1 Restricted and induced representations
For a subgroup $H\subset G$, a representation $V$ of $G$ can be restricted to a representation of $H$, denoted as $\mathrm{Res}^G_HV$ or $\mathrm{Res}\ V$.

On the opposite, for a representation $V$ of $G$ and an $H$-invarient subspace $W\subset V$, the subspace
$$
g\cdot W\doteq\{g\ket{w}\}
$$
only depends on the [[Abstract group theory#6.1 Coset|left coset]] $gH$. One can denote the subspace as $\sigma\cdot W$ with a coset $\sigma\in G/H$. Then $V$ is called *induced* by $W$ if it can be written as
$$
V=\bigoplus_{\sigma_i\in G/H}\sigma_i\cdot W.
$$
It is denoted as $\mathrm{Ind}_H^GW$ or $\mathrm{Ind}\ W$. Such an induced representation exists and is unique up to isomorphism.

To construct $V=\mathrm{Ind}\ W$ from $W$, first write
$$
\ket{v}=\sum_ig_i\ket{w_i},
$$
where representitive $g_i\in\sigma_i\in G/H$ and $\ket{w_i}\in W$. Group action on $V$ is then defined as
$$
g\cdot g_i\ket{w_i}\doteq(g_j\cdot h)\ket{w_i}=g_jh\ket{w_i}.
$$

#### 1.3.2 Properties of restriction and induction
For an induced representation $V=\mathrm{Ind}_H^GW$ and another representation $U$ of $G$, an $H$-linear map $\varphi:W\to U$ uniquely corresponds to a $G$-linear map $\tilde{\varphi}:V\to U$, which means
$$
\mathrm{Hom}(W,\mathrm{Res}\ U)^H=\mathrm{Hom}(\mathrm{Ind}\ W,U)^G.
$$
With $V=\bigoplus_i\sigma_i\cdot W$, the $\tilde{\varphi}$ is defined as
$$
\tilde{\varphi}(g_i\ket{w})\doteq g_i\varphi g_i^{-1}g_i\ket{w}=g_i\varphi\ket{w},
$$
where $g_i\in\sigma_i\in G/H$. Here the map $\tilde{\varphi}$ is independent of the specific choice of $g_i$ since $\varphi$ is an $H$-linear map.

For $W=\bigoplus_iW_i$, its induction is $\mathrm{Ind}\ W=\bigoplus_i\mathrm{Ind}\ W_i$.

For a representation $V$ of $G$ and a representation $W$ of $H\subset G$, the tensor product gives
$$
U\otimes\mathrm{Ind}\ W=\mathrm{Ind}(\mathrm{Res}\ U\otimes W).
$$
As a specital case, $\mathrm{Ind}(\mathrm{Res}\ U)=U\otimes P$ where $P$ is the [[Representation theory#1.1.3 Regular representation|permutation representation]] of $G$ on $G/H$.

Restriction and induction are both *transitive*. That is for subgroups $H\subset K\subset G$, a representation $W$ of $H$ and a representation $V$ of $G$,
$$
\begin{aligned}
\mathrm{Ind}_H^GW&=\mathrm{Ind}^G_K(\mathrm{Ind}^K_HW),\\
\mathrm{Res}^G_HV&=\mathrm{Res}^K_H(\mathrm{Res}^G_KV).
\end{aligned}
$$
