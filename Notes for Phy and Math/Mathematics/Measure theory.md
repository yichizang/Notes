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

### 1.4 Property of measure
#### 1.4.1 Complete measure
For a measure $\mu$ on a ring $\pmb{R}$, the set $E\in\pmb{R}$ that satisfies $\mu(E)=0$ is called a *$\mu$-zero set* or *zero set*.

The subset of a zero set, if also in $\pmb{R}$, is also a zero set. If a measure $\mu$ satisfies that any subset of a zero set is also in $\pmb{R}$, then the measure is called a *complete measure*.

>[!example]
>The extended measure $\mu^\ast$ is a complete measure on $\pmb{R}^\ast$.

#### 1.4.2 Finiteness of measure
For a measure $\mu$ on a ring $\pmb{R}$, if a set $E\in\pmb{R}$ satisfies $\mu(E)<\infty$, then $E$ has *finite measure*. If any set $E\in\pmb{R}$ has finite measure, then the measure $\mu$ is called a *finite measure*.

If a set $E\in\pmb{R}$ satisfies that there exists a list $\{E_n\}\subset\pmb{R}$ of sets with finite measure that
$$
E\subset\bigcup_{n=1}^\infty E_n,
$$
then $E$ has *$\sigma$-finite measure*. If any set $E\in\pmb{R}$ has $\sigma$-finite measure, then the measure $\mu$ is called a *$\sigma$-finite measure*.

If $\mu$ is $\sigma$-finite on $\pmb{R}$, then $\mu^\ast$ is $\sigma$-finite on $\pmb{R}^\ast$.

### 1.5 Lebesgue-Stieltjes measure

>[!recall]+
>Recall the $m$ measure and the $g$ measure on $\pmb{R}_0$.
>- [[Measure theory#1.2.3 $m$ measure on $ pmb{R}_0$|m measure]]: $m(E)=\sum(b_i-a_i)$;
>- [[Measure theory#1.2.4 $g$ measure on $ pmb{R}_0$|g measure]]: $\mu_g(E)=\sum[g(b_i)-g(a_i)]$.
>
>Below denote $g\doteq\mu_g$ when there is no ambiguity.

#### 1.5.1 Lebesgue measure
Consider the induced outer measure $m^\ast$ on $\pmb{\sigma}(\pmb{R}_0)=\mathcal{P}(\mathbb{R})$. An $m^\ast$-measurable is also called a *Lebesgue measurable* or *L-measurable*. The set of all L-measurables is denoted as $\pmb{L}$.

One can prove that the measure $m^\ast$ can be written as
$$
m^\ast(E)=\inf\{m(O):O\supset E\text{ is an open set}\}.
$$

As mentioned in the general case, $\pmb{L}$ is a $\sigma$-algebra and $m^\ast$ is a complete measure on $\pmb{L}$. This measure is called the *Lebesgue measure*. When there is no ambiguity, denote $m\doteq m^\ast$.

Replacing $m$ with $g$ gives the definition of *Lebesgue-Stieltjes measurable* and the *Lebesgue-Stieltjes measure*. The set of all L-S measurable sets is denoted as $\pmb{L}^g$.

#### 1.5.2 Borel set
Since $\pmb{L}^g$ depends on specific choice of function $g$, and $\pmb{L}^g\supset\pmb{S}(\pmb{R}_0)$, one can consider only L-S measure restricted on $\pmb{S}(\pmb{R}_0)$. A set in $\pmb{S}(\pmb{R}_0)$ is called a *Borel set* and denote $\pmb{B}\doteq\pmb{S}(\pmb{R}_0)$.

Some of Borel sets are listed here.

| Set name                                 | Expression          | Lebesgue measure                  |
| ---------------------------------------- | ------------------- | --------------------------------- |
| Point sets (and at most countable union) | $\{x_n\}$           | $0$                               |
| Intervals                                | $\braket{a,b}$      | $b-a$                             |
| Open sets                                | $\bigcup(a_i,b_i)$  | $\sum(b_i-a_i)$                   |
| Closed sets                              | $F\subset(a,b)$     | $(b-a)-m((a,b)-F)$                |
| -                                        | $F\not\subset(a,b)$ | $\lim_{n\to\infty}m(F\cap[-n,n])$ |


#### 1.5.3 Lebesgue measurable
A set $E\in\mathbb{R}$ is an L-measurable if and only if any of the following.
- For any $\epsilon>0$, there is an open set $O\supset E$ that satisfies
$$
m^\ast(O-E)<\epsilon;
$$
- For any $\epsilon>0$, there is a closed set $F\subset E$ that satisfies
$$
m^\ast(E-F)<\epsilon;
$$
- For any $\epsilon>0$, there is an open set and a closed set $F\subset E\subset O$ that satisfies
$$
m^\ast(O-F)<\epsilon.
$$

#### 1.5.4 Invariance of L-measure
Consider the *translation map*
$$
\begin{aligned}
\tau_\alpha:&&\mathcal{P}(\mathbb{R})&\to\mathcal{P}(\mathbb{R})\\
&&E&\mapsto\{x+\alpha:x\in E\}
\end{aligned}
$$
and the *reflection map*
$$
\begin{aligned}
\tau:&&\mathcal{P}(\mathbb{R})&\to\mathcal{P}(\mathbb{R})\\
&&E&\mapsto\{-x:x\in E\}.
\end{aligned}
$$

One can prove that L-measure is invariant under these two maps
$$
m^\ast(E)=m^\ast(\tau_\alpha(E))=m^\ast(\tau(E)).
$$
Moreover, when $E\in\pmb{L}$, $\tau_\alpha(E)\in\pmb{L}$ and $\tau(E)\in\pmb{L}$.

#### 1.5.5 Lebesgue immeasurable
To construct an L-immeasurable set $Z$, consider a list of number $\{a_n\}$. Denote $Z_n\doteq\tau_{a_n}(Z)$. If it satisfies
- $\bigcup Z_n$ contains an interval;
- each $Z_n$ is non-intersecting with others;
- $\bigcup Z_n$ is [[Point set on line#2.1.2 Bounded set|bounded]],

then one can prove that
$$
m\left(\bigcup Z_n\right)=\sum_{n=1}^\infty m(Z)
$$
has to be a finite non-zero value, which is impossible. This means that $Z$ is immeasurable.

One can prove that
$$
x\sim y\quad\Leftrightarrow\quad x-y\in\mathbb{Q}
$$
is an [[Set theory#1.3.4 Equivalence relation|equivalance relation]] on $[0,1]$. Take a representitive element in each [[Set theory#1.3.5 Equivalence class|equivalance class]] to define the set $Z$. One can prove that this satisfies the conditions if take
$$
\{a_n\}=\mathbb{Q}\cap[0,1].
$$
Therefore, this $Z$ is an Lebesgue immeasurable set.

>[!note]
>This construction would require the [[Set theory#1.1.10 Axiom of choice|axiom of choice]].

## 2 Measurable function and integral
### 2.1 Measurable function
#### 2.1.1 Measurable space
For a $\sigma$-ring $\pmb{S}$ on $X$, if it satisfies
$$
X=\bigcup_{E\in\pmb{S}}E,
$$
then $(X,\pmb{S})$ is called a *measurable space*. An element $E\in\pmb{S}$ is called a *measurable set* on $(X,\pmb{S})$.

As a special case, $(\mathbb{R},\pmb{L})$ is called *Lebesgue measurable space*, $(\mathbb{R},\pmb{L}^g)$ is called *Lebesgue-Stieltjes measurable space* and $(\mathbb{R},\pmb{B})$ is called *Borel measurable space*.

#### 2.1.2 Measurable function
Consider a measurable space $(X,\pmb{S})$, a subset $E\subset X$ and a real function $f:E\to\mathbb{R}$. If for any $c\in\mathbb{R}$, the set
$$
E(c\leqslant f)\doteq\{x\in E:c\leqslant f(x)\}
$$
is a measurable set on $(X,\pmb{S})$, then $f$ is called a *measurable function* on $E$ (with respect to $(X,\pmb{S})$).

The following are equivalent definitions.
- For any $c\in\mathbb{R}$, $E(c<f)$ is measurable set;
- For any $c\in\mathbb{R}$, $E(c>f)$ is measurable set;
- For any $c\in\mathbb{R}$, $E(c\geqslant f)$ is measurable set;
- For any $c,d\in\mathbb{R}$, $E(f\in\braket{c,d})$ is measurable set.

#### 2.1.3 Property of measurable function
For a measurable space $(X,\pmb{S})$, measurable functions $f,g$ on $E\subset X$ satisfies
- for any $a,b\in\mathbb{R}$, $af+bg$ is a measurable function;
- $f\cdot g$ is a measurable function;
- if $f$ is nonzero on $E$, then $1/f$ is a measurable function;
- $\max\{f,g\}$ and $\min\{f,g\}$ are measurable functions.

Consider the limit of measurable functions. For a list of measurable functions $\{f_n\}$ on $E\subset X$, the supremum, infimum
$$
\sup f_n\doteq\lim_{n\to\infty}\max\{f_1,\cdots,f_n\},\quad\inf f_n\doteq\lim_{n\to\infty}\min\{f_1,\cdots,f_n\}
$$
and the upper/lower limit
$$
\lim_{n\to\infty}\lim_{m\to\infty}\max\{f_n,\cdots,f_m\},\quad\lim_{n\to\infty}\lim_{m\to\infty}\min\{f_n,\cdots,f_m\}
$$
are measurable functions if they are finite respectively.