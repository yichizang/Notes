---
banner: "![[../pics/92583070_p0.jpg]]"
banner_y: 0.476
---

>[!abstract]- Pre-knowledge
>- [[Mathematical logic]]

# Set theory
## 1 ZFC axioms
### 1.1 Axiom of existence
The axiom of existence states that *there exists a set*
$$
\exists x(x=x).
$$

It provides an ontological support on the theory.

### 1.2 Axiom of extensionality
The axiom of extensionality states that *two sets with equal elements are equal*
$$
\forall X\forall Y(\forall u(u\in X\Leftrightarrow u\in Y)\Rightarrow X=Y).
$$

This axiom shows that a set is determined by its elements.

### 1.3 Axiom schema of separation
The axiom schema of separation states that *for a fomula $\varphi(u)$ and for any set $X$, the set $Y\doteq\{u\in X:\varphi(u)\}$ exists*
$$
\forall X\exists Y\forall u(u\in Y\Leftrightarrow(u\in X\land\varphi(u))).
$$
It is called an axiom schema because it actually represents infinite many axioms for every $\varphi(u)$.

This axiom puts a restriction on the comprehension statement that for any fomula $\varphi(u)$, the set $\{u:\varphi(u)\}$ exists. This unrestricted statement would lead to consiquences like Russell's paradox which is about sets like $\{x:x\notin x\}$. Also, from this axiom one can define the [[Set theory#2.1 Empty set|empty set]] $\varnothing$.

### 1.4 Axiom of pairing
The axiom of pairing states that *for any two $x$ and $y$, exists a set that contains only $x$ and $y$*
$$
\forall x\forall y\exists X\forall z(z\in X\Leftrightarrow(x=z\lor y=z)).
$$
According to axiom of extensionality, the set with only one element $\{x\}=\{x,x\}$ is a set.

### 1.5 Axiom of union
The axiom of union states that *for any set $X$, there is a $Y$ that $u\in Y$ if and only if there is a $z\in X$ that $u\in z$*
$$
\forall X\exists Y\forall u(u\in Y\Leftrightarrow\exists z(z\in X\land u\in z)).
$$
Such a $Y$ is unique and is called the *union* of $X$, denoted as $\bigcup X$. From this axiom one can define the [[Set theory#2.3 Intersection and union|union]] of sets $X\cup Y$.

### 1.6 Axiom of power set
With [[Set theory#2.5 Subset|subset]] defined, the axiom of power set states that *for any set $X$, there exists a set $Y$ that $u\in Y$ if and only if $u\subset X$*
$$
\forall X\exists Y\forall u(u\in Y\Leftrightarrow u\subset X).
$$
Such a set $Y$ is unique and is called the *power set* of $X$, denoted as $\mathcal{P}(X)$.

### 1.7 Axiom of infinity
Define the *successor* of $X$ as $S(X)\doteq X\cup\{X\}$. The axiom of infinity states that *there exists a set $X$ that $\varnothing\in X$ and for any $x\in X$, $S(x)\in X$*
$$
\exists X(\varnothing\in X\land\forall x(x\in X\Rightarrow S(x)\in X)).
$$

### 1.8 Axiom of fundation
The axiom of fundation states that *for any set $X\ne\varnothing$, there exists a $Y\in X$ that $X\cap Y=\varnothing$*
$$
\forall X(X\ne\varnothing\Rightarrow\exists Y(Y\in X\land X\cap Y=\varnothing)).
$$

This axiom shows that for any set $X$, $X\notin X$. It also shows that ordinal rank of sets can be well-defined.

### 1.9 Axiom schema of replacement
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

### 1.10 Axiom of choice
The axiom of choice states that *for any set $X\ne\varnothing$, if $\varnothing\notin X$ and elements in $X$ are disjoint, then exists a set $S$ that for any $x\in X$, $S\cap x$ has only one element*
$$
\forall X((\varnothing\notin X\land\forall x\in X\forall y\in X(x\cap y\ne\varnothing\Leftrightarrow x=y))\Rightarrow\exists S\forall x\in X\exists!y(S\cap x=\{y\})).
$$

There are many equivalent axioms for the axiom of choice, for example the well-ordering axiom. This axiom is independent of the rest axioms. The axiom system that does not accept AC is is called *ZF axiom system*.

## 2 Basic concept
### 2.1 Empty set
For a fomula $\varphi(u)$, if there is a set $X$ that $\forall u(\varphi(u)\Rightarrow u\in X)$, then define
$$
\{u:\varphi(u)\}\doteq\{u\in X:\varphi(u)\}.
$$
One can prove that this set does not depend on the specific choice of $X$. Thus the $X$ here is an arbitrary set that satisfies $\forall u(\varphi(u)\Rightarrow u\in X)$.

Since $x\ne x\Rightarrow x\in X$, one can define the *empty set* as
$$
\varnothing\doteq\{x:x\ne x\}.
$$

### 2.2 Class
For a fomula $\varphi(u)$, the concept $\{u:\varphi(u)\}$ is called a *class*. Note that a class is not necessarily a set. A class that is not a set is called a *proper class*.

The mathematical approach to deal with proper classes is called *virtual class*.

### 2.3 Set operation
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

### 2.4 Operation rule
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

### 2.5 Subset
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
