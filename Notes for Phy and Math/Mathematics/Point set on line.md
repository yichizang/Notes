---
banner: "![[../pics/c9049e7481a89b1a1e7eea44608ddb171646629763870.jpeg]]"
banner_y: 0.184
---

>[!abstract]- Pre-knowledge
>- [[Set theory]]

# Point set on line
## 1 Limit of set
### 1.1 Supremum set
Consider a set of sets $\{A_n\}_{n\in\mathbb{N}}$. The *supremum set* of this set of sets is defined as
$$
\lim_{n\to\infty}\sup A_n\doteq\bigcap_{n=1}^\infty\bigcup_{m=n}^\infty A_m.
$$
This is the set of element $x$ that for any $n\in\mathbb{N}$, $x\in\bigcup_{m=n}^\infty A_m$. This can also be understood as the set of element that is in infinite many $A_n$.

### 1.2 Infimum set
The *infimum set* of this set of sets is defined as
$$
\lim_{n\to\infty}\inf A_n\doteq\bigcup_{n=1}^\infty\bigcap_{m=n}^\infty A_m.
$$
This is the set of element that is in all $A_{m>n}$ for some $n\in\mathbb{N}$. This can also be understood as the set of element that is in all except finite many $A_n$.

The supremum and infimum satisfies
$$
\bigcap_{n=1}^\infty A_n\subset\lim_{n\to\infty}\inf A_n\subset\lim_{n\to\infty}\sup A_n\subset\bigcup_{n=1}^\infty A_n.
$$

### 1.3 Limit of set
If the supremum and the infimum of $\{A_n\}$ is equal
$$
\lim_{n\to\infty}\sup A_n=\lim_{n\to\infty}\inf A_n,
$$
then $\{A_n\}$ is *convergent*. The *limit* of the set $\{A_n\}$ is defined as
$$
\lim_{n\to\infty}A_n\doteq\lim_{n\to\infty}\sup A_n=\lim_{n\to\infty}\inf A_n.
$$

### 1.4 Monotone set
If $\{A_n\}$ satisfies that for any $n\in\mathbb{N}$
$$
A_n\subset A_{n+1},
$$
then $\{A_n\}$ is called *monotone increasing*. If it satisfies $A_n\supset A_{n+1}$, then it is called *monotone decreasing*.

All monotone sets are convergent. If it is monotone increasing, then it satisfies
$$
\lim_{n\to\infty}A_n=\bigcup_{n=1}^\infty A_n.
$$
If it is monotone decreasing, then it satisfies
$$
\lim_{n\to\infty}A_n=\bigcap_{n=1}^\infty A_n.
$$

## 2 Point set on line
### 2.1 Interval
An interval is the most common type of point set on line ($\mathbb{R}$).
- An *open interval* is the set $(a,b)\doteq\{x:a<x<b\}$ where $-\infty\leqslant a<b\leqslant+\infty$;
- A *half-open interval* include 2 types of sets:
	- $[a,b)\doteq\{x:a\leqslant x<b\}$ where $-\infty<a\leqslant b\leqslant+\infty$;
	- $(a,b]\doteq\{x:a<x\leqslant b\}$ where $-\infty\leqslant a\leqslant b<+\infty$;
- A *closed interval* is the set $[a,b]\doteq\{x:a\leqslant x\leqslant b\}$ where $-\infty<a\leqslant b<+\infty$.

As 2 special cases, $[a,a]=\{a\}$ and $[a,a)=(a,a]=\varnothing$.

Denote all these intervals as $\braket{a,b}$.

### 2.2 Bounded set
For a subset $A\subset\mathbb{R}$, if there is $c\in\mathbb{R}$ such that for any $x\in A$, $x\leqslant c$, then $A$ is called a *right-bounded set*. For such right-bounded set, there is one unique $m\in\mathbb{R}$ that
- for any $x\in A$, there is $x\leqslant m$;
- for any $\epsilon>0$, there is $x\in A$ such that $x>m-\epsilon$.

This number is called the *supremum* of $A$, denoted as $\sup A$.

In the same manner, one can define a *left-bounded set* and the *infimum* of the set, denoted as $\inf A$.

### 2.3 Neighbourhood
For a point $x\in\mathbb{R}$, an open interval $(a,b)$ that contains $x$ is called a *neighbourhood* of $x$. As a special case, for an $\epsilon>0$, the interval $(x-\epsilon,x+\epsilon)$ is called the *$\epsilon$-neighbourhood* of $x$, denoted as $O(x,\epsilon)$.

For a nonempty set $A\subset\mathbb{R}$ and a point $x\in A$, if there is a neighbourhood $x\in(a,b)\subset A$, then $x$ is called an *interior point* of $A$.

>[!example]
>As an example, any point in $\braket{a,b}$ except $a$ and $b$ is an interior point of $\braket{a,b}$.

### 2.4 Open set
For a nonempty set $A\subset\mathbb{R}$, if every point $x\in A$ is an interior point of $A$, then the set is called an *open set*. As a special case, $\varnothing$ is an open set.

Open sets satisfy
- $\varnothing$ and $\mathbb{R}$ are both open sets;
- the union of an arbitrary set of open sets is an open set;
- the finite intersection of open sets is an open set.

One can prove that any nonempty open set $A$ on $\mathbb{R}$ can be written as (at most countable) union of non-intersecting intervals
$$
A=\bigcup_i(a_i,b_i),\quad \forall i\ne j,(a_i,b_i)\cap(a_j,b_j)=\varnothing.
$$
