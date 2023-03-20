---
banner: "![[../pics/mmexport1663523939450.jpg]]"
banner_y: 0
---

>[!abstract]- Pre-knowledge
>- [[Abstract group theory]]
>- [[Linear algebra]]

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