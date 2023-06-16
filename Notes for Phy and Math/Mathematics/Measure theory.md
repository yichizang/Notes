---
banner: "![[../pics/mmexport1663524019607.jpg]]"
banner_y: 0.28
---

>[!abstract]- Pre-knowledge
>- [[Set theory]]
>- [[Point set on line]]
>- [[Linear algebra]]

# Measure theory
## 1 Measure and outer measure
### 1.1 Ring
#### 1.1.1 Ring of sets
For an arbitary set $X$, a *collection* $\pmb{E}$ is a set whose elements are [[Set theory#1.2.5 Subset|subsets]] of $X$.

For a collection $\pmb{R}$, it is called a *ring* if it satisfies that $\forall E,F\in\pmb{R}$,
$$
\begin{aligned}
&E\cup F\in\pmb{R}\\
&E-F\in\pmb{R}.
\end{aligned}
$$
Since
$$
E\cap F=E\cup F-(E-F)-(F-E),
$$
apparently $E\cap F\in\pmb{R}$ for a ring. If $X\in\pmb{R}$, then $\pmb{R}$ is called an *algebra* on $X$.

>[!warning]
>The terms here have different meanings as in algebra.

#### 1.1.2 Span of ring
One can prove that for any collection $\pmb{E}$ of $X$, there is a ring (algebra) $\pmb{R}_0$ that
- $\pmb{E}\subset\pmb{R}_0$;
- for any ring (algebra) $\pmb{R}\supset\pmb{E}$, there is $\pmb{R}_0\subset\pmb{R}$, which means $\pmb{R}_0$ is the smallest ring containing $\pmb{E}$.

This is called the ring (algebra) *spanned* by $\pmb{E}$, denoted as $\pmb{R}(\pmb{E})$.

#### 1.1.3 $\sigma$-ring
For a collection $\pmb{R}$, it is called a *$\sigma$-ring* if it satisfies
- $\forall E,F\in\pmb{R}$, $E-F\in\pmb{R}$;
- $\forall\{E_n\}_{\mathbb{N}}\subset\pmb{R}$, its union $\bigcup\{E_n\}\in\pmb{R}$.

A *$\sigma$-ring* is also a ring.

One can also define the span of $\sigma$-ring. Denote such span as $\pmb{S}(\pmb{E})$. One can prove that
$$
\pmb{S}(\pmb{E})=\pmb{S}(\pmb{R}(\pmb{E})).
$$

#### 1.1.4 Monotone class
For a collection $\pmb{M}$ of $X$, if any [[Point set on line#1.4 Monotone set|monotune set]] of sets $\{M_n\}\subset\pmb{M}$ satisfies
$$
\lim_{n\to\infty}M_n\in\pmb{M},
$$
then $\pmb{M}$ is called a *monotone class*. The intersection of arbitrary set of monotone classes is also a monotone class.

One can also define the span of monotone class, denoted as $\pmb{M}(\pmb{E})$.

One can prove that
- any $\sigma$-ring is a monotone class;
- any monotone ring is a $\sigma$-ring;
- for a ring $\pmb{R}$, $\pmb{S}(\pmb{R})=\pmb{M}(\pmb{R})$.

### 1.2 Measure
#### 1.2.1 Set function
Consider the set
$$
\hat{\mathbb{R}}\doteq\mathbb{R}\cup\{\pm\infty\}.
$$
Then for a collection $\pmb{E}$, a map $\mu:\pmb{E}\to\hat{\mathbb{R}}$ is called a *set function*.

#### 1.2.2 Measure
For a ring $\pmb{R}$ on $X$, a set function
$$
\mu:\pmb{R}\to\hat{\mathbb{R}}
$$
is called a *measure* on $\pmb{R}$ if it satisfies the following.
- $\mu\{\varnothing\}=0$;
- Nonnegative, that is for any $E\in\pmb{R}$, $\mu(E)\geqslant0$;
- For an at most countable list of disjoint sets $\{E_n\}$, if
$$
\bigcup_nE_n\in\pmb{R},
$$
then
$$
\mu\left(\bigcup_nE_n\right)=\sum_n\mu(E_n).
$$

The last property is called *$\sigma$-additivity*.

#### 1.2.3 $m$ measure on $\pmb{R}_0$
Consider the collection $\pmb{P}\doteq\{(a,b]:a,b\in\mathbb{R}\}$ and the ring $\pmb{R}_0\doteq\pmb{R}(\pmb{P})$. For any $E\in\pmb{R}_0$, one can define a *primary decomposition*
$$
E=\bigcup_{i=1}^n(a_i,b_i],\quad b_i\leqslant a_{i+1}.
$$
Then one can define a set function
$$
\begin{aligned}
m:&&\pmb{R}_0&\to\hat{\mathbb{R}}\\
&&E&\mapsto\sum_{i=1}^n(b_i-a_i).
\end{aligned}
$$
One can prove that $m$ is independent of the choice of decomposition and is a measure on $\pmb{R}_0$.

#### 1.2.4 $g$ measure on $\pmb{R}_0$
As a generalization of $m$ measure, one can define a $g$ measure. For a monotone increasing right-continuous function $g$ on $\mathbb{R}$, define
$$
\begin{aligned}
\mu_g:&&\pmb{R}_0&\to\hat{\mathbb{R}}\\
&&E&\mapsto\sum_{i=1}^n(g(b_i)-g(a_i)).
\end{aligned}
$$
This is also a measure on $\pmb{R}_0$.

### 1.3 Extension of measure
#### 1.3.1 Outer measure
For a *$\sigma$-ring* $\pmb{S}$ on $X$, an *outer measure* is defined as a map
$$
\mu^\ast:\pmb{S}\to\hat{\mathbb{R}}
$$
that satisfies the following.
- $\mu^\ast\{\varnothing\}=0$;
- Nonnegative, that is for any $E\in\pmb{S}$, $\mu^\ast(E)\geqslant0$;
- Monotone, that is if $E\subset F$, then $\mu^\ast(E)\leqslant\mu^\ast(F)$;
- For an at most countable list of sets $\{E_n\}\subset S$,
$$
\mu^\ast\left(\bigcup_nE_n\right)\leqslant\sum_n\mu^\ast(E_n).
$$

#### 1.3.2 Caratheodory extension
For a ring $\pmb{R}$ on $X$, a subset $E\subset X$ is called *$\pmb{R}$-covered* if
$$
\exists\{E_n\}_\mathbb{N}\subset\pmb{R},E\subset\bigcup_{n=1}^\infty E_n.
$$
The set of all $\pmb{R}$-covered subsets forms a $\sigma$-ring
$$
\pmb{\sigma}(\pmb{R})\doteq\left\{E\subset X:\exists\{E_n\}_\mathbb{N}\subset\pmb{R},E\subset\bigcup_{n=1}^\infty E_n\right\}.
$$

>[!example]
>For the ring $\pmb{R}_0$ of $\mathbb{R}$, $\pmb{\sigma}(\pmb{R}_0)$ is simply the [[Set theory#1.1.6 Axiom of power set|power set]] $\mathcal{P}(\mathbb{R})$.

#### 1.3.3 Induced outer measure
For a measure $\mu$ of $\pmb{R}$, one can construct an outer measure $\mu^\ast:\pmb{\sigma}(\pmb{R})\to\hat{\mathbb{R}}$ as the [[Set theory#1.3.7 Extremal, extremum and bound|infimum]]
$$
\mu^\ast(E)\doteq\inf\left\{\sum_{n=1}^\infty\mu(E_n):E\subset\bigcup_{n=1}^\infty E_n\right\}.
$$
This is calle the *induced outer measure* of $\mu$. When limited to the ring $\pmb{R}$, it goes back to $\mu$
$$
\mu^\ast|_{\pmb{R}}=\mu.
$$

The extension is unique in the sense that if $\pmb{R}\subset\pmb{R}'\subset\pmb{\sigma}(\pmb{R})$, then $\pmb{\sigma}(\pmb{R}')=\pmb{\sigma}(\pmb{R})$ and $(\mu')^\ast=\mu^\ast$.

For any set $E\in\pmb{R}$ and any $F\in\pmb{\sigma}(\pmb{R})$, the induced outer measure satisfies
$$
\mu^\ast(F)=\mu^\ast(F\cap E)+\mu^\ast(F-E).
$$
Note that $F=(F\cap E)\cup(F-E)$. The identity shows that any set $E\in\pmb{R}$ can *seperately measure* $\mu^\ast$.

#### 1.3.4 $\mu^\ast$-measurable
For a set $E\in\pmb{\sigma}(\pmb{R})$, if any $F\in\pmb{\sigma}(\pmb{R})$ satisfies
$$
\mu^\ast(F)=\mu^\ast(F\cap E)+\mu^\ast(F-E),
$$
then $E$ is called a *$\mu^\ast$-measurable set*. The set of all $\mu^\ast$-measurable sets is denoted as $\pmb{R}^\ast$. The above condition is called the *Caratheodory condition*.

One can prove that $\pmb{R}^\ast$ is a $\sigma$-ring and $\mu^\ast$ is a measure on $\pmb{R}^\ast$.

>[!note]
>The idea of such construction is simple. If $\mu^\ast$ is a measure on some ring $\pmb{R}'\supset\pmb{R}$, then a set in $\pmb{R}'$ should also seperately measure $(\mu')^\ast=\mu^\ast$ on $\pmb{\sigma}(\pmb{R}')=\pmb{\sigma}(\pmb{R})$. This is exactly the Caratheodory condition.

One can also prove that for any $E\in\pmb{\sigma}(\pmb{R})$ that satisfies $\mu^\ast(E)=0$, $E\in\pmb{R}^\ast$.

#### 1.3.5 Complete measure
For a measure $\mu$ on a ring $\pmb{R}$, the set $E\in\pmb{R}$ that satisfies $\mu(E)=0$ is called a *$\mu$-zero set* or *zero set*.

The subset of a zero set, if also in $\pmb{R}$, is also a zero set. If a measure $\mu$ satisfies that any subset of a zero set is also in $\pmb{R}$, then the measure is called a *complete measure*.

>[!example]
>The extended measure $\mu^\ast$ is a complete measure on $\pmb{R}^\ast$.

### 1.4 Lebesgue-Stieltjes measure
#### 1.4.1 A ring structure on $\mathbb{R}$
Consider $X=\mathbb{R}$. Define a ring on $X$ as
$$
R\doteq\left\{\bigcup\{E_i\}_N:\{E_i\}_N\subset P\right\}
$$
where
$$
P\doteq\{(a,b]:\forall a,b\in\mathbb{R}\}.
$$
One can prove that any $E\in R$ can be finitely decomposed into $E=\bigcup\{E_i\}$ where
$$
\begin{aligned}
&\{E_i\}\subset R,\\
\forall i\ne j,\ &E_i\cap E_j=\varnothing.
\end{aligned}
$$

#### 1.4.2 Pre-measure of $R$
A monotone right-continuous function $g(x)$ naturally generates the following map on $P$
$$
\begin{aligned}
\mu_P:& &P&\to\mathbb{R}\\
&&(a,b]&\mapsto g(b)-g(a).
\end{aligned}
$$
Using the decomposition of $E\in R$, one can extend the definition of $\mu_P$ onto $R$ as
$$
\begin{aligned}
\mu:& &R&\to\mathbb{R}\\
&&\bigcup\{E_i\}&\mapsto\sum_i\mu_P(E_i).
\end{aligned}
$$
This is a well-defined map despite that there are more than one way to decomposite a given $E\in R$. One can prove that $\mu$ is a pre-measure on $R$.

#### 1.4.3 Lebesgue-Stieltjes measure
As a general process of Caratheodory extension, one construct a $\sigma$-ring
$$
\sigma(R)\doteq\left\{E\subset X:\exists\{E_n\}_\mathbb{N}\subset R,E\subset\bigcup_{n=1}^\infty E_n\right\}.
$$
One can prove that this is just the [[Set theory#1.1.6 Axiom of power set|power set]] $\mathcal{P}(\mathbb{R})$. The outer measure generated is
$$
\mu^\ast(E)\doteq\inf\left\{\sum_{n=1}^\infty\mu(E_n):E\subset\bigcup\{E_n\}_{\mathbb{N}}\right\}.
$$
This is a measure of Caratheodory measurable $R^\ast$ called *Lebesgue-Stieltjes measure*.

>[!example]
>- Closed interval $\mu([a,b])=g(b)-g(a-0)$;
>- Open interval $\mu((a,b))=g(b-0)-g(a)$;
>- Point set $\mu(\{a\})=g(a)-g(a-0)$;
>- etc.
