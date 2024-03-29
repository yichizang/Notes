---
banner: "![[../pics/92583070_p0.jpg]]"
banner_y: 0.476
---

>[!abstract]- Pre-knowledge
>- Mathematical logic

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
Such a $Y$ is unique and is called the *union* of $X$, denoted as $\bigcup X$. From this axiom one can define the [[Set theory#1.2.3 Set operation|union]] of sets $X\cup Y$.

#### 1.1.6 Axiom of power set
With [[Set theory#1.2.5 Subset|subset]] defined, the axiom of power set states that *for any set $X$, there exists a set $Y$ that $u\in Y$ if and only if $u\subset X$*
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

### 1.3 Relation
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

#### 1.3.3 Possible properties of binary relation
For a set $X$ and a binary relation $R$ on $X$, the following are the possible properties of $R$. The precondition is $\forall x,y,z\in X$.

| Name                     | Expression                             |
| ------------------------ | -------------------------------------- |
| Reflexivity              | $R(x,x)$                               |
| Irreflexivity            | $\lnot R(x,x)$                         |
| Symmetry                 | $R(x,y)\Rightarrow R(y,x)$             |
| Asymmetry                | $\lnot (R(x,y)\land R(y,x))$           |
| Anti-symmetry            | $R(x,y)\land R(y,x)\Rightarrow x=y$    |
| Transitivity             | $R(x,y)\land R(y,z)\Rightarrow R(x,z)$ |
| Total                    | $R(x,y)\lor R(y,x)$                    |
| Connected                | $R(x,y)\lor R(y,x)\lor x=y$            | 
| Univalent (Right-unique) | $R(x,y)\land R(x,z)\Rightarrow y=z$    |

#### 1.3.4 Equivalence relation
For a set $X$, an *equivalence relation* is a binary relation $R\subset X^2$ that satisfies [[#1.3.3 Possible properties of binary relation|reflexivity, symmetry and transitivity]]. An equivalence relation is often denoted as $\sim$. Note that equivalence relation is not always equality.

>[!example]
>For a set $X$ and $\mathcal{I}\subset\mathcal{P}(X)$, if $\mathcal{I}$ satisfies
>$$
>\begin{aligned}
>&\varnothing\in\mathcal{I},\\
>&(A\subset B\land B\in\mathcal{I})\Rightarrow A\in\mathcal{I},\\
>&A,B\in\mathcal{I}\Rightarrow A\cup B\in\mathcal{I},
>\end{aligned}
>$$
>then it is called an *ideal* on $X$. If $X\notin\mathcal{I}$ then it is called a *proper ideal*. The following binary relation defined by an ideal is an equivalence relation
>$$
>R\doteq\{(A,B)\in\mathcal{P}(\mathcal{I})^2:A\bigtriangleup B\in\mathcal{I}\}.
>$$

#### 1.3.5 Equivalence class
With an equivalence relation $\sim$ on a set $X$, one can define *equivalence class* $[a]$
$$[a]\doteq\{x:x\in X,x\sim a\}.$$
Note that an equivalence class is a set instead of a proper class. The set of all equivalence classes of $R$ is called the *quotient set* of $X$ by $R$, denoted as
$$
X/R\doteq\{[x]:x\in X\}.
$$

For a set $X$, a family of nonempty disjoint subsets $X_i\subset X$ that satisfies
$$
\begin{aligned}
&\forall i,j\in I,i\ne j\Rightarrow X_i\cap X_j=\varnothing,\\
&\bigcup\{X_i\}_I=X,
\end{aligned}
$$
is called a *partition* of $X$. The equivalence classes on $X$ is a partition of $X$ and any partition of $X$ defines an equivalence relation.

### 1.4 Order
#### 1.4.1 Partial/total order
For a set $X$, a *partial order* is a binary relation $\le$ that satisfies [[#1.3.3 Possible properties of binary relation|reflexivity, anti-symmetry and transitivity]]. If its also [[#1.3.3 Possible properties of binary relation|total]], then it is called a *total order* or *line order*.

If $\le$ is a partial order (total order) on $X$, then it is denoted as $(X,\le)$. The set $X$ is called a *partial ordered set* (*total ordered set*).

#### 1.4.2 Strict order
For a set $X$, a *strict partial order* is a binary relation $<$ that satisfies [[#1.3.3 Possible properties of binary relation|irreflexivity, asymmetry and transitivity]]. If it is also [[#1.3.3 Possible properties of binary relation|connected]], then it is called a *strict total order*.

For any order $\le$, there is an *associated strict order* $<$ defined as
$$
(x\le y\land x\ne y)\Rightarrow x<y.
$$
And vise versa.

One also denote $<^{-1}$ as $>$ and $\le^{-1}$ as $\ge$.

#### 1.4.3 Extremal, extremum and bound
For $(X,\le)$, an element $x\in X$ is called a *minimal* if $\forall y\in X$ there is $\lnot(x>y)$, and it's called a *maximal* if $\lnot(x<y)$.

The element $x\in X$ is called a *minimum* if $\forall y\in X$ there is $x\le y$, and is called a *maximum* if $x\ge y$. The extremums are unique if exists.

In the case of total ordered set, the minimal is the minimum and the maximal is the maximum.

For a subset $X_0\subset X$, if there is a $y\in X$ that $\forall x\in X_0$ there is $y\ge x$, then $y$ is called an *upper bound* of $X_0$. The minimum in the set of all upper bounds of $X_0$, if exists, is called the *supremum* of $X_0$, denoted as $\sup X_0$. Conversely one can define the *lower bound* and *infimum* of $X_0$, the later denoted as $\inf X_0$.

#### 1.4.4 Well order
For a total order $\le$ on the set $A$, if it also satisfies that
$$
\forall A_0\subset A,(A_0\ne\varnothing\Leftrightarrow\exists\min A_0),
$$
then it is called a *well order*. Such $(A,\le)$ is called a *well ordered set*.

### 1.5 Map
#### 1.5.1 Map
An [[#1.3.3 Possible properties of binary relation|univalent]] binary relation is called a *partial function*. A binary relation that is both [[#1.3.3 Possible properties of binary relation|univalent and total]] is called a *map* or *function*. Here $y$ is called the *value* of $f$ at $x$. One usually denote $(x,y)\in f$ as $f(x)=y$.

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

#### 1.5.2 Injection, surjection and bijection
For a map $f:X\to Y$, if for any two $x_1,x_2\in X$, $x_1\ne x_2\Rightarrow f(x_1)\ne f(x_2)$, then $f$ is called an *injective*. If $\mathrm{ran}(f)=Y$, then $f$ is called a *surjective*. If $f$ is both an injective and a surjective, then it is called a *bijective*.

If the inverse of a map is also a map, then this map is called *invertible*. A map is invertible if and only if it is injective.

#### 1.5.3 Restriction and expansion
For a map $f$ and a set $A$, define the *restriction* of $f$ on $A$ as
$$
f\restriction A\doteq\{(x,y)\in f:x\in A\}.
$$
If $g=f\restriction A$, then $f$ is called the *extension* of $g$.

For two maps $f$ and $g$, they are called *compatible* if for all $x\in(\mathrm{dom}(f)\cap\mathrm{dom}(g))$ one have $f(x)=g(x)$. The intersection of two maps is also a map. The union of two compatible maps is also a map. It is a extension of both maps.

#### 1.5.4 Index system
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

## 2 Number
### 2.1 Natural number
#### 2.1.1 Induction
Remember that *successor* of set $X$ is defined as $S(X)\doteq X\cup\{X\}$. If a set $X$ that satisfies
$$
\varnothing\in X\land\forall x(x\in X\Rightarrow S(x)\in X),
$$
then it is called an *inductive set*. Therefore the [[#1.1.7 Axiom of infinity|axiom of infinity]] can be concluded as *an inductive set exists*.

#### 2.1.2 Natural number
The *set of all natural number* is defined as
$$
\mathbb{N}\doteq\{n:\forall X(X\text{ is inductive}\Rightarrow n\in X)\}.
$$
The elements of $\mathbb{N}$ is called *natural number*. This is a set according to the [[#1.1.3 Axiom schema of separation|axiom schema of separation]] and the [[#1.1.7 Axiom of infinity|axiom of infinity]]. One can prove that $\mathbb{N}$ is inductive and is a subset of any inductive set.

In $\mathbb{N}$, $\varnothing$ is usually denoted as $0$ and for any $n\in\mathbb{N}$, $S(n)$ is usually denoted as $n+1$.

#### 2.1.3 Order of natural number
One can use $\in$ as an order on $\mathbb{N}$. Further define $\underline{\in}$ as
$$
x\underline{\in}y\Leftrightarrow(x\in y\lor x=y).
$$
Denote $\in$ as $<$ and $\underline{\in}$ as $\leq$. It can be proved that $\underline{\in}$ is a well order on $\mathbb{N}$.

#### 2.1.4 Induction principle
For any property $\varphi(p)$, if it satisfies
- $\varphi(0)$,
- $\varphi(n)\Rightarrow\varphi(n+1)$,

then for any natural number $n\in\mathbb{N}$, $\varphi(n)$. This is called the *induction principle* on $\mathbb{N}$.

If a property $\varphi(p)$ satisfies for any $n\in\mathbb{N}$
$$
\forall k<n,\varphi(k)\Rightarrow\varphi(n),
$$
then for any natural number $n\in\mathbb{N}$, $\varphi(n)$. This is called the *second induction principle* on $\mathbb{N}$.

#### 2.1.5 Recursive principle
A map with domain $n$ or $\mathbb{N}$ is called a *sequence*. The former called a *finite sequence* with *length* $n$. The latter called *infinite sequence*.

For any set $A$, any map $a:P\to A$ and $g:P\times A\times\mathbb{N}\to A$, there is one unique map $f:P\times\mathbb{N}\to A$ that
- for all $p\in P$, $f(p,0)=a(p)$;
- for any $n\in\mathbb{N}$ and $p\in P$, $f(p,n+1)=g(p,f(p,n),n)$.

This is called the *recursive principle with parameter*. The version with $P=\{\varnothing\}$ is called *recursive principle*.

#### 2.1.6 Addition and multiplication
With the recursive principle with parameter, one can prove that there is one unique function (*addition*)
$$
+:\mathbb{N}\times\mathbb{N}\to\mathbb{N}
$$
that satisfies
- for all $n\in\mathbb{N}$, $+(n,0)=n$;
- for any $m,n\in\mathbb{N}$, $+(m,n+1)=+(m,n)+1$.

And there is also one unique function (*multiplication*)
$$
\cdot:\mathbb{N}\times\mathbb{N}\to\mathbb{N}
$$
that satisfies
- for all $n\in\mathbb{N}$, $\cdot(n,0)=0$;
- for any $m,n\in\mathbb{N}$, $\cdot(m,n+1)=+(\cdot(m,n),m)$.

One often write $+(m,n)=m+n$ and $\cdot(m,n)=m\cdot n$.

### 2.2 Integer and rational number
#### 2.2.1 Integer
Define an equivalence relation $\sim$ on $\mathbb{N}\times\mathbb{N}$ as follows
$$
(m_1,n_1)\sim(m_2,n_2)\quad\Leftrightarrow\quad m_1+n_2=m_2+n_1.
$$
Define the quotient set under $\sim$ as the *set of integers*, denoted as $\mathbb{Z}\doteq(\mathbb{N}\times\mathbb{N})/\sim$.

Denote $0_\mathbb{Z}\doteq[(0,0)]$.

>[!note]
>Here one view $\mathbb{Z}$ as an extension of $\mathbb{N}$. However, $\mathbb{N}\not\subset\mathbb{Z}$. Rather it is "embedded" in $\mathbb{Z}$ by the map
>$$
>\begin{aligned}
>f:&&\mathbb{N}&\to\mathbb{Z}\\
>&&n&\mapsto[(n,0)].
>\end{aligned}
>$$

#### 2.2.2 Order and operation on $\mathbb{Z}$
The *order* on $\mathbb{Z}$ is defined as
$$
[(m_1,n_1)]\le_\mathbb{Z}[(m_2,n_2)]\quad\Leftrightarrow\quad m_1+n_2\le_\mathbb{N}m_2+n_1.
$$

The *addition* and *multiplication* on $\mathbb{Z}$ is defined as
$$
[(m_1,n_1)]+_\mathbb{Z}[(m_2,n_2)]\doteq[(m_1+m_2,n_1+n_2)]
$$
and
$$
[(m_1,n_1)]\cdot_\mathbb{Z}[(m_2,n_2)]\doteq[(m_1\cdot m_2+n_1\cdot n_2,m_1\cdot n_2+m_2\cdot n_1)].
$$

One can prove that for any $a\in\mathbb{Z}$, there is one unique element $a'\in\mathbb{Z}$ such that
$$
a+a'=0_\mathbb{Z}.
$$
Denote this element as $-a$.

### 2.3 Cardinality
#### 2.3.1 Equivalent set
If there is a bijection that maps $X$ to $Y$, then they are called *equivalent set*, denoted as
$$
|X|=|Y|.
$$

If there is an injection $f:X\to Y$, then it is denoted as
$$
|X|\le|Y|.
$$
This means that $\exists Z\subset Y$ such that $|X|=|Z|$.

#### 2.3.2 Cantor-Bernstein theorem
The *Cantor-Bernstein theorem* states that
$$
(|X|\le|Y|\land|Y|\le|X|)\Rightarrow|X|=|Y|.
$$

This proves that $\le$ forms a partial order.

#### 2.3.3 Finite and infinite set
For any set $X$, if there is an $n\in\mathbb{N}$ such that $|X|=|n|$, then the set is called a *finite set*. Otherwise it is called an *infinite set*.

If $|X|=|\mathbb{N}|$, then the set is called *countable*. Otherwise it is called *uncountable*.

>[!note] Pigeonhole principle
>The *pigeonhole principle* states that for any finite set $X$, there is no bijection between $X$ and its proper subset.

>[!note]
>One way to define a finite set without the concept of $\mathbb{N}$ is that the followings are equivalent.
>- $X$ is finite;
>- There is a total order on $X$ such that any nonempty subset of $X$ has maximum and minimum element;
>- Every nonempty set of subsets of $X$ has maximum element under $\subset$;
>- There is no bijection between $X$ and its proper subset.
>
>The last statement is called *Dedekind finite*.
