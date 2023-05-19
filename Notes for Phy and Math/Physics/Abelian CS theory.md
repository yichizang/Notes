# Abelian CS theory
## 1 CS action
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
S=\frac{k}{4\pi}\int_{\mathbb{R}^3}A\wedge\mathrm{d}A.
$$
Note that this is gauge invarient under transformation $A\to A+\mathrm{d}\alpha$ where $\alpha\in C^\infty(\mathbb{R}^3)$.

## 2 Path integral
In quantum physics, one can write the path integral
$$
Z=\int[DA]e^{iS}
$$
where $[DA]$ integrates over all possible configuration (mod gauge transformation). What's more, the two-point Green function is
$$
\braket{A_\mu(x)A_\nu(y)}=\int[DA]A_\mu(x)A_\nu(y)e^{iS}.
$$

## 3 Gaussian integral
For Gaussian integral, one have
$$
\int\mathrm{d}Ve^{V^TCV}\propto\sqrt{\frac{1}{\det C}}
$$
and
$$
\int\mathrm{d}V~V_aV_be^{V^TCV}=\left(C^{-1}\right)_{ab}
$$
for $V$ a vector in $n$ dim and $C$ an invertible $n\times n$ matrix.

In analogue, one can write
$$
\braket{A_\mu(x)A_\nu(y)}\mathrm{d}x^\mu\wedge\mathrm{d}x^\nu=G_{\mu\nu}(x,y)\mathrm{d}x^\mu\wedge\mathrm{d}x^\nu.
$$
Since $G_{\mu\nu}$ should act as $(\mathrm{d})^{-1}$, one should have
$$
\mathrm{d}G_{\mu\nu}(x,y)\wedge\mathrm{d}x^\mu\wedge\mathrm{d}x^\nu=\frac{4\pi}{k}\delta^{(3)}(\pmb{x}-\pmb{y})\mathrm{vol}.
$$
The solution is just the Green function of Poisson equ
$$
G_{\mu\nu}(\pmb{x}-\pmb{y})=\frac{1}{k}\frac{(\pmb{x}-\pmb{y})^\rho}{|\pmb{x}-\pmb{y}|^3}\epsilon_{\mu\nu\rho}.
$$

## 4 Linking number
Consider a Wilson loop with form
$$
W_K=\exp\left[\oint_KA(x)\right].
$$
For two intersecting loops $K_1$ and $K_2$, one can write the correlation function of Wilson loop
$$
\begin{aligned}
\Braket{\exp\left[\oint_{K_1}A(x)\right],\exp\left[\oint_{K_2}A(y)\right]}&=\exp\left[\frac{4\pi i}{k}\int\mathrm{d}x^\mu\int\mathrm{d}y^\nu\frac{(x-y)^\rho}{|x-y|^3}\epsilon_{\mu\nu\rho}\right]\\
&=\exp\left[\frac{4\pi i}{k}Lk(K_1,K_2)\right].
\end{aligned}
$$
