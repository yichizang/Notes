---
banner: "![[../pics/mmexport1663524019607.jpg]]"
banner_y: 0.28
---

>[!abstract]- Pre-knowledge
>- [[Set theory]]
>- [[Linear algebra]]

# Measure theory
## 1 Measure and outer measure
### 1.1 Definition of measure
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
- for any ring (algebra) $\pmb{R}\supset\pmb{E}$, there is $\pmb{R}_0\subset\pmb{R}$.

This is called the ring (algebra) *spanned* by $\pmb{E}$, denoted as $\pmb{R}(\pmb{E})$.

#### 1.1.3 $\sigma$-ring
For a collection $\pmb{R}$, it is called a *$\sigma$-ring* if it satisfies
- $\forall E,F\in\pmb{R}$, $E-F\in\pmb{R}$;
- $\forall\{E_n\}_{\mathbb{N}}\subset\pmb{R}$, its union $\bigcup\{E_n\}\in\pmb{R}$.

A *$\sigma$-ring* is also a ring.

One can also define the span of $\sigma$-ring. Denote such span as $\pmb{S}(E)$. One can prove that
$$
\pmb{S}(\pmb{E})=\pmb{S}(\pmb{R}(\pmb{E})).
$$

#### 1.1.4 Measure
For a *ring* $R$ on $X$, a *pre-measure* on the ring is a [[Set theory#1.4.1 Map|map]] $\mu$ defined as
$$
\mu:R\to[0,+\infty].
$$

This map should satisfies the following.
- The [[Set theory#1.2.1 Empty set|empty set]] has zero measure $\mu\{\varnothing\}=0$;
- For a countable list of disjoint sets $\{E_n\}_{\mathbb{N}}$, if $\bigcup\{E_n\}\in R$, then $\mu\left(\bigcup\{E_n\}\right)=\sum_n\mu(E_n)$.
The last property is called *$\sigma$-additivity*.

A pre-measure on a $\sigma$-ring is called a *measure*.

#### 1.1.5 Outer measure
For a *$\sigma$-ring* $S$ on $X$, an *outer measure* is defined as a map
$$
\mu^\ast:S\to[0,+\infty]
$$
that satisfies the following.
- The empty set has zero measure $\mu^\ast\{\varnothing\}=0$;
- For $E\subset F$, $\mu^\ast(E)\leqslant\mu^\ast(F)$;
- For a $\{E_n\}_{\mathbb{N}}\subset S$, $\mu^\ast\left(\bigcup\{E_n\}\right)\leqslant\sum_n\mu^\ast(E_n)$.

### 1.2 Caratheodory extension
#### 1.2.1 Caratheodory-measurable
For a *$\sigma$-ring* $S$ with an outer measure $\mu^\ast$, its *Caratheodory-measurable* is a set $M$ that
$$
M\doteq\{E\in S:\forall F\in S,\mu^\ast(F)=\mu^\ast(F\cap E)+\mu^\ast(F-E)\}.
$$
This defination means that an element $E$ in $M$ can separately measure any element $F$ in $S$.

One can prove that the Caratheodory-measurable $M$ is also a $\sigma$-ring and $\mu^\ast$ is a measure on it.

#### 1.2.2 Caratheodory extension
For a ring $R$ on $X$, a subset $E\subset X$ is called *$R$-covered* if
$$
\exists\{E_n\}_\mathbb{N}\subset R,E\subset\bigcup\{E_n\}_{\mathbb{N}}.
$$
The set of all $R$-covered subsets forms a $\sigma$-ring
$$
\sigma(R)\doteq\left\{E\subset X:\exists\{E_n\}_\mathbb{N}\subset R,E\subset\bigcup\{E_n\}_{\mathbb{N}}\right\}.
$$
For a pre-measure $\mu$ of $R$, one can construct an outer measure $\mu^\ast:\sigma(R)\to[0,+\infty]$ as the [[Set theory#1.3.7 Extremal, extremum and bound|infimum]]
$$
\mu^\ast(E)\doteq\inf\left\{\sum_{n=1}^\infty\mu(E_n):E\subset\bigcup\{E_n\}_{\mathbb{N}}\right\}.
$$
Denote the Caratheodory-measurable of $\sigma(R)$ as $R^\ast$. One can prove that $\mu^\ast$ is a measure on $R^\ast$. Such a measure is called an *extension* of $\mu$ since $R\subset R^\ast$ and $\mu^\ast=\mu$ on $R$.

### 1.3 Lebesgue-Stieltjes measure
#### 1.3.1 A ring structure on $\mathbb{R}$
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

#### 1.3.2 Pre-measure of $R$
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

#### 1.3.3 Lebesgue-Stieltjes measure
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
