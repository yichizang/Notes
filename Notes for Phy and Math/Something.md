Consider the 2-form
$$
F_{\mu\nu}\mathrm{d}x^\mu\wedge\mathrm{d}x^\nu=(\partial_\mu A_\nu-\partial_\nu A_\mu)\mathrm{d}x^\mu\wedge\mathrm{d}x^\nu.
$$
The important thing is that $F=\mathrm{d}A$. The action is then
$$
S=\int F\wedge\ast F,
$$
which is valid in any dimension. But in $\mathbb{R}^3$ as a special case, one can write
$$
S=\frac{k}{4\pi}\int_{\mathbb{R}^3}A\mathrm{d}A.
$$
Note that this is gauge invarient under transformation $A\to A+\mathrm{d}\alpha$ where $\alpha\in C^\infty(\mathbb{R}^3)$.

In quantum physics, one can write the path integral
$$
Z=\int[DA]e^{iS}
$$
where $[DA]$ integrates over all possible configuration. What's more, the Green function is
$$
\braket{A_\mu(x)A_\nu(y)}=\int[DA]A_\mu(x)A_\nu(y)e^{iS}.
$$

For Gaussian integral, one have
$$
\int\mathrm{d}Ve^{V^TCV}\propto\sqrt{\frac{1}{\det C}}
$$
and
$$
\int\mathrm{d}V~V_aV_be^{V^TCV}=\left(C^{-1}\right)_{ab}
$$
for $V$ a vector in $n$ dim and $C$ an $n\times n$ mat.