---
banner: "![[../pics/mmexport1663524019607.jpg]]"
banner_y: 0.28
---

>[!abstract]- Pre-knowledge
>- [[Set theory]]
>- [[Linear algebra]]

# Measure theory
## 1 Measure and external measure
### 1.1 Defination of measure
#### 1.1.1 Ring of sets
For an arbitary set $X$, a *collection* is a set whose elements are subsets of $X$.

For a collection $R$, it is called a *ring* if it satisfies that $\forall E,F\in R$,
$$
\begin{aligned}
&E\cup F\in R,\\
&E-F\in R.
\end{aligned}
$$
Since
$$
E\cap F=E\cup F-(E-F)-(F-E),
$$
apparently $E\cap F\in R$ for a ring.

>[!warning]
>The ring defined here is different from the ring in Algebra.

#### 1.1.2 $\sigma$-ring
For a collection $R$, it is called a *$\sigma$-ring* if it satisfies
$$
\begin{aligned}
&\forall E,F\in R,&&E-F\in R,\\
&\forall\{E_n\}_{n\in\mathbb{N}}\subset R,&&\bigcup_nE_n\in R.
\end{aligned}
$$
A *$\sigma$-ring* is also a ring.

#### 1.1.3 Measure
For a *ring* $R$ on $X$, a *measure* on the ring is a map $\mu$ defined as
$$
\mu:R\to\mathbb{R}+\{+\infty\}.
$$

This map should satisfies the following.
- For any $E\in R$, its measure is nonnegative $\mu(E)\geqslant0$;
- The empty set has zero measure $\mu\{\varnothing\}=0$;
- For a countable list of disjoint sets $\{E_n\}_{n\in\mathbb{N}}$, if $\bigcup_nE_n\in R$, then $\mu\left(\bigcup_nE_n\right)=\sum_n\mu(E_n)$.
The last property is called *$\sigma$-additivity*.

#### 1.1.4 Outer measure
For a *$\sigma$-ring* $S$ on $X$, an *outer meeasure* is defined as a map
$$
\mu^\ast:S\to\mathbb{R}+\{+\infty\},
$$
that satisfies the following.
- For any $E\in S$, its measure is nonnegative $\mu^\ast(E)\geqslant0$;
- The empty set has zero measure $\mu^\ast\{\varnothing\}=0$;
- For $E\subset F$, $\mu^\ast(E)\leqslant\mu^\ast(F)$;
- For a $\{E_n\}_{n\in\mathbb{N}}\subset S$, $\mu^\ast\left(\bigcup_nE_n\right)\leqslant\sum_n\mu^\ast(E_n)$.

#### 1.1.5 Caratheodory collection
A measure has a batter property than an outer measure, and here is a way to turn an outer measure into a measure.

For a *$\sigma$-ring* $S$, its *Caratheodory collection* is defined as
$$
S^\ast\doteq\{E\in S:\forall F\in S,\mu^\ast(F)=\mu^\ast(F\cap E)+\mu^\ast(F-E)\}.
$$
This defination means that an element $E$ in $S^\ast$ can separately measure any element $F$ in $S$.

One can prove that the Caratheodory collection $S^\ast$ is also a $\sigma$-ring and $\mu^\ast$ is a measurement on it.

#### 1.1.6 Caratheodory expansion
For a ring $R$ on $X$, define the *Caratheodory expansion* of $R$ as
$$
H(R)\doteq\left\{E\subset X:\exists\{E_n\}_\mathbb{N}\subset R,E\subset\bigcup_{n=1}^\infty E_n\right\}.
$$
This is a *$\sigma$-ring*. For a measure $\mu$ of $R$, one can construct an outer measure $\mu^\ast:H(R)\to\mathbb{R}+\{+\infty\}$ as
$$
\mu^\ast(E)\doteq\inf\left\{\sum_{n=1}^\infty\mu(E_n):E\subset\bigcup_{n=1}^\infty E_n\right\}.
$$
Then using the concept of Caratheodory collection, $\mu^\ast$ is a measure on $H(R)^\ast$.