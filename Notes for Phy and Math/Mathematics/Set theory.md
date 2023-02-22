---
banner: "![[../pics/92583070_p0.jpg]]"
banner_y: 0.476
---

>[!abstract]- Pre-knowledge
>- [[Mathematical logic]]

# Set theory
## 1 Axioms and basic concepts
### 1.1 ZFC axioms
#### 1.1.1 Axiom of existence
The axiom of existence states that *there exists a set*
$$
\exists x(x=x).
$$

It provides an ontological support on the theory.

#### 1.1.2 Axiom of extensionality
The axiom of extensionality states that *two sets with equal elements are equal*
$$
\forall X\forall Y(\forall u(u\in X\Leftrightarrow u\in Y)\Rightarrow X=Y).
$$

This axiom shows that a set is determined by its elements.

#### 1.1.3 Axiom schema of separation
The axiom schema of separation states that *for a fomula $\varphi(u)$ and for any set $X$, the set $Y\doteq\{u\in X:\varphi(u)\}$ exists*
$$
\forall X\exists Y\forall u(u\in Y\Leftrightarrow(u\in X\land\varphi(u))).
$$
It is called an axiom schema because it actually represents infinite many axioms for every $\varphi(u)$.

This axiom puts a restriction on the comprehension statement that for any fomula $\varphi(u)$, the set $\{u:\varphi(u)\}$ exists. This unrestricted statement would lead to consiquences like Russell's paradox which is about sets like $\{x:x\notin x\}$. Also, from this axiom one can define the [[Set theory#2.1 Empty set|empty set]] $\varnothing$.

#### 1.1.4 Axiom of pairing
The axiom of pairing states that *for any two $x$ and $y$, exists a set that contains only $x$ and $y$*
$$
\forall x\forall y\exists X\forall z(z\in X\Leftrightarrow(x=z\lor y=z)).
$$
According to axiom of extensionality, the set with only one element $\{x\}=\{x,x\}$ is a set.

#### 1.1.5 Axiom of union
The axiom of union states that *for any set $X$, there is a $Y$ that $u\in Y$ if and only if there is a $z\in X$ that $u\in z$*
$$
\forall X\exists Y\forall u(u\in Y\Leftrightarrow\exists z(z\in X\land u\in z)).
$$
Such a $Y$ is unique and is called the *union* of $X$, denoted as $\bigcup X$. From this axiom one can define the [[Set theory#2.3 Intersection and union|union]] of sets $X\cup Y$.

#### 1.1.6 Axiom of power set
With [[Set theory#2.5 Subset|subset]] defined, the axiom of power set states that *for any set $X$, there exists a set $Y$ that $u\in Y$ if and only if $u\subset X$*
$$
\forall X\exists Y\forall u(u\in Y\Leftrightarrow u\subset X).
$$
Such a set $Y$ is unique and is called the *power set* of $X$, denoted as $\mathcal{P}(X)$.

#### 1.1.7 Axiom of infinity
Define the *successor* of $X$ as $S(X)\doteq X\cup\{X\}$. The axiom of infinity states that *there exists a set $X$ that $\varnothing\in X$ and for any $x\in X$, $S(x)\in X$*
$$
\exists X(\varnothing\in X\land\forall x(x\in X\Rightarrow S(x)\in X)).
$$

#### 1.1.8 Axiom of fundation
The axiom of fundation states that *for any set $X\ne\varnothing$, there exists a $Y\in X$ that $X\cap Y=\varnothing$*
$$
\forall X(X\ne\varnothing\Rightarrow\exists Y(Y\in X\land X\cap Y=\varnothing)).
$$

This axiom shows that for any set $X$, $X\notin X$. It also shows that ordinal rank of sets can be well-defined.

#### 1.1.9 Axiom schema of replacement
The axiom schema of replacement states that *for a given formula $\psi(x,y)$ that for any $x$ there is a unique $y$ that satisfies $\psi(x,y)$, then for any $A$, the following $B$ exists*
$$
B\doteq\{y:\exists x(x\in A\land\psi(x,y))\}.
$$
That is to say
$$
\forall A(\forall x\in A\exists!y\psi(x,y)\Rightarrow\exists B\forall x\in A\exists y\in B\psi(x,y)).
$$
Here $\exists!$ means that uniquely exists.

This is also an axiom schema. The property of $\psi(x,y)$ actually suggests that its a function. Thus the axiom suggests that the image of a set is also a set.

#### 1.1.10 Axiom of choice
The axiom of choice states that *for any set $X\ne\varnothing$, if $\varnothing\notin X$ and elements in $X$ are disjoint, then exists a set $S$ that for any $x\in X$, $S\cap x$ has only one element*
$$
\forall X((\varnothing\notin X\land\forall x\in X\forall y\in X(x\cap y\ne\varnothing\Leftrightarrow x=y))\Rightarrow\exists S\forall x\in X\exists!y(S\cap x=\{y\})).
$$

There are many equivalent axioms for the axiom of choice, for example the well-ordering axiom. This axiom is independent of the rest axioms. The axiom system that does not accept AC is is called *ZF axiom system*.

---
### 1.2 Basic concept
#### 1.2.1 Empty set
For a fomula $\varphi(u)$, if there is a set $X$ that $\forall u(\varphi(u)\Rightarrow u\in X)$, then define
$$
\{u:\varphi(u)\}\doteq\{u\in X:\varphi(u)\}.
$$
One can prove that this set does not depend on the specific choice of $X$. Thus the $X$ here is an arbitrary set that satisfies $\forall u(\varphi(u)\Rightarrow u\in X)$.

Since $x\ne x\Rightarrow x\in X$, one can define the *empty set* as
$$
\varnothing\doteq\{x:x\ne x\}.
$$

#### 1.2.2 Class
For a fomula $\varphi(u)$, the concept $\{u:\varphi(u)\}$ is called a *class*. Note that a class is not necessarily a set. A class that is not a set is called a *proper class*.

The mathematical approach to deal with proper classes is called *virtual class*.

#### 1.2.3 Set operation
The *union* of a set $X$ is defined as the set mensioned in [[Set theory#1.5 Axiom of union|axiom of union]]. The *union of two sets* $X$ and $Y$ is defined as
$$
X\cup Y\doteq\bigcup\{X,Y\}.
$$

The *intersection of two sets* $X$ and $Y$ is defined as
$$
X\cap Y\doteq\{u:u\in X\land u\in Y\}.
$$
One can also define the *intersection* of a set $X$ as
$$
\bigcap X\doteq\{u:\forall Y(Y\in X\Rightarrow u\in Y)\}.
$$

The *difference* of two sets $X$ and $Y$ is defined as
$$
X-Y\doteq\{u\in X:u\notin Y\}.
$$
One can also define the *symmetric difference* of two sets as
$$
X\bigtriangleup Y\doteq(X-Y)\cup(Y-X).
$$

The result of the above operations are also sets.

#### 1.2.4 Operation rule
The above operations obey following rules.

Commutative law
$$
\begin{aligned}
&X\cup Y=Y\cup X,\\
&X\cap Y=Y\cap X,\\
&X\bigtriangleup Y=Y\bigtriangleup X;
\end{aligned}
$$
Associative law
$$
\begin{aligned}
&(X\cup Y)\cup Z=X\cup(Y\cup Z),\\
&(X\cap Y)\cap Z=X\cap(Y\cap Z),\\
&(X\bigtriangleup Y)\bigtriangleup Z=X\bigtriangleup(Y\bigtriangleup Z);
\end{aligned}
$$
Distributive law
$$
\begin{aligned}
&(X\cup Y)\cap Z=(X\cap Z)\cup(Y\cap Z),\\
&(X\cap Y)\cup Z=(X\cup Z)\cap(Y\cup Z);
\end{aligned}
$$
De Morgan's law
$$
\begin{aligned}
&X-(Y\cup Z)=(X-Y)\cap(X-Z),\\
&X-(Y\cap Z)=(X-Y)\cup(X-Z).
\end{aligned}
$$

#### 1.2.5 Subset
For two sets $X$ and $Y$, if every element of $X$ is an element of $Y$, then $X$ is a *subset* of $Y$, denoted as $X\subset Y$. If $X\subset Y$ and $X\ne Y$, then $X$ is called a *proper subset* of $Y$, denoted as $X\subsetneqq Y$.

For any set $X$, $\varnothing\subset X$.

Subset satisfies the following for arbitrary $X,Y,Z$.
$$
\begin{aligned}
&\varnothing\subset X,\\
&X\subset X,\\
&(X\subset Y\land Y\subset X)\Rightarrow X=Y,\\
&(X\subset Y\land Y\subset Z)\Rightarrow X\subset Z.
\end{aligned}
$$
Also one have
$$
(X\subset Y)\Leftrightarrow(X\cap Y=X)\Leftrightarrow(X\cup Y=Y)\Leftrightarrow(X-Y=\varnothing).
$$

---
### 1.3 Relations and functions
#### 1.3.1 Cartesian product
For two sets $a$ and $b$, their *ordered pair* is defined as the set
$$
(a,b)\doteq\{\{a\},\{a,b\}\}.
$$
It can be proved that $(a_1,b_1)=(a_2,b_2)$ if and only if $a_1=a_2$ and $b_1=b_2$.

The *Cartesian product* of two sets $X$ and $Y$ is defined as
$$
X\times Y\doteq\{(x,y):x\in X\land y\in Y\}.
$$
This is also a set. When $X=Y$, this is also denoted as $X^2$.

#### 1.3.2 Binary relation
A set $R$ is called a *binary relation* if there are sets $X$ and $Y$ that $R\subset X\times Y$. Generally, one have the notation $R(x,y)$ for $(x,y)\in R$, called $x$ and $y$ has the relation $R$. It is sometimes denoted as $xRy$.

If $R\subset X^2$ then $R$ is called a binary relation on $X$.

For a binary relation $R$, its *domain* is defined as
$$
\mathrm{dom}(R)\doteq\{x:\exists yR(x,y)\}.
$$
Its *range* is defined as
$$
\mathrm{ran}(R)\doteq\{y:\exists xR(x,y)\}.
$$

The *image* of set $X_1$ under relation $R$ is defined as
$$
R[X_1]\doteq\{y\in\mathrm{ran}(R):\exists x\in X_1(R(x,y))\}.
$$
The *inverse image* of $Y_1$ under the relation $R$ is defined as
$$
R^{-1}[Y_1]\doteq\{x\in\mathrm{dom}(R):\exists y\in Y_1(R(x,y))\}.
$$

The *inverse* of a binary relation is defined as
$$
R^{-1}\doteq\{(y,x):(x,y)\in R\}.
$$
The *composition* of two binary relations $R$ and $S$ is defined as
$$
S\circ R\doteq\{(x,z):\exists y((x,y)\in R\land(y,z)\in S)\}.
$$

#### 1.3.3 Map
If a binary relation $f$ satisfies
$$
((x,y)\in f\land(x,z)\in f)\Rightarrow y=z,
$$
then it is called *univalent* or *right-unique*. If $f$ satisfies
$$
\forall x\in X\exists y\in Y((x,y)\in f),
$$
then it is called *total*.

An univalent binary relation is called a *partial function*. A binary relation that is both univalent and total is called a *map* or *function*. Here $y$ is called the *value* of $f$ at $x$. One usually denote $(x,y)\in f$ as $f(x)=y$.

If $\mathrm{dom}(f)=X$ and $\mathrm{ran}(f)\subset Y$ and one have $f(x)=y$, then it is also denoted as
$$
\begin{aligned}
f:&&X&\to Y\\
&&x&\mapsto y.
\end{aligned}
$$

For any set $X$, one can define an *identity map* $1_X$ as
$$
\begin{aligned}
1_X:&&X&\to X\\
&&x&\mapsto x.
\end{aligned}
$$

For a map $f:X\to Y$, if for any two $x_1,x_2\in X$, $x_1\ne x_2\Rightarrow f(x_1)\ne f(x_2)$, then $f$ is called an *injective*. If $\mathrm{ran}(f)=Y$, then $f$ is called a *surjective*. If $f$ is both an injective and a surjective, then it is called a *bijective*.

If the inverse of a map is also a map, then this map is called *invertible*. A map is invertible if and only if it is injective.

#### 1.3.4 Restriction and expansion
For a map $f$ and a set $A$, define the *restriction* of $f$ on $A$ as
$$
f\restriction A\doteq\{(x,y)\in f:x\in A\}.
$$
If $g=f\restriction A$, then $f$ is called the *extension* of $g$.

For two maps $f$ and $g$, they are called *compatible* if for all $x\in(\mathrm{dom}(f)\cap\mathrm{dom}(g))$ one have $f(x)=g(x)$. The intersection of two maps is also a map. The union of two compatible maps is also a map. It is a extension of both maps.

#### 1.3.5 Index system
A map $i\mapsto X_i$ with $X_i$ being a set and $i\in I$ is called an *index system* of sets. $I$ is called an *index set*. Such an index system is usually written as $X\doteq\{X_i\}_{i\in I}$ or $\{X_i\}_I$.

For an index system $X=\{X_i\}_I$, its *general Cartesian product* is defined as
$$
\prod_{i\in I}X_i\doteq\{f:(f\text{ being a map on }I)\land\forall i\in I(f(i)\in X_i)\}.
$$
One can also define the *projection function* for all $i\in I$
$$
\begin{aligned}
p_i:&&\prod_{j\in I}X_j&\to X_i\\
&&f&\mapsto f(i).
\end{aligned}
$$
