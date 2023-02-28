---
banner: "![[../pics/40627989846bd5390600a850ac3a03031668187767940.jpeg]]"
---

>[!info]-
>- **by** Edward Witten
>- **Subject**: supersymmetry; TQFT
>- **Abstract**: It is shown that the Morse inequalities can be obtained by consideration of a certain supersymmetric quantum mechanics Hamiltonian. Some of the implications of modern ideas in mathematics for supersymmetric theories are discussed.

# Supersymmetry and Morse theory
## 1 A simple essence noted by Satoshi
### 1.1 Localization of an integral
Consider the integral
$$
Z=\int^{+\infty}_{-\infty}\frac{\mathrm{d}x}{\sqrt{2\pi}}\exp\left[-\frac{1}{2}s^2(x)\right]\frac{\mathrm{d}s}{\mathrm{d}x}.
$$
After doing a change of variable, one can see that the value of $Z$ only depends on the behavior of $s(x)$ at $x\to\pm\infty$. For instance, when $s(x)\to+\infty$ at both $x\to\pm\infty$, the integral vanishes as
$$
Z=\int^{+\infty}_{+\infty}\frac{\mathrm{d}s}{\sqrt{2\pi}}\exp\left[-\frac{1}{2}s^2\right]=0.
$$
On the other hand, when $s(x)\to\pm\infty$ as $x\to\pm\infty$, the integral becomes
$$
Z=\int^{+\infty}_{-\infty}\frac{\mathrm{d}s}{\sqrt{2\pi}}\exp\left[-\frac{1}{2}s^2\right]=1.
$$
Etc.

Since the value of $Z$ only depend on the asymptotic behavior of $s(x)$, multiplying a constant $t$ onto $s(x)$ won't change $Z$. Therefore
$$
Z=\int^{+\infty}_{-\infty}\frac{\mathrm{d}x}{\sqrt{2\pi}}\exp\left[-\frac{1}{2}t^2s^2(x)\right]t\frac{\mathrm{d}s}{\mathrm{d}x}.
$$
If put $t\to+\infty$, the value of the exponential vanishes everywhere except for $s(x)=0$. Actually the kernal forms a $\delta$ function. Thus the value of the integration becomes
$$
Z=\sum_{x_0:s(x_0)=0}\mathrm{sign}\left.\frac{\mathrm{d}s}{\mathrm{d}x}\right|_{x_0}.
$$
This means that the integral is localized to the zero points of $s(x)$. It has the similar property as a topological invarient does.

### 1.2 Introduction to TQFT
Introduce *Grassmann variables* $\rho,\chi$ that satisfies
$$
\rho\chi=-\chi\rho,
$$
and their integration
$$
\int\mathrm{d}\chi\ \chi=\int\mathrm{d}\rho\ \rho=1,\quad\text{others}=0.
$$
Then, rewrite $Z$ as
$$
\begin{aligned}
Z&=\int\frac{\mathrm{d}x}{\sqrt{2\pi}}\mathrm{d}\chi\mathrm{d}\rho\exp\left[-\frac{1}{2}s^2(x)+\rho\frac{\mathrm{d}s}{\mathrm{d}x}\chi\right]\\
&=\int\frac{\mathrm{d}x}{\sqrt{2\pi}}\mathrm{d}\chi\mathrm{d}\rho\exp\left[-\frac{1}{2}s^2(x)\right]\left(1+\rho\frac{\mathrm{d}s}{\mathrm{d}x}\chi+\cdots\right)\\
\text{(using integration rules)}&=\int\frac{\mathrm{d}x}{\sqrt{2\pi}}\exp\left[-\frac{1}{2}s^2(x)\right]\frac{\mathrm{d}s}{\mathrm{d}x}.
\end{aligned}
$$
The exponent here can be viewed as a Lagrangian
$$
\mathcal{L}=-\frac{1}{2}s^2(x)+\rho\frac{\mathrm{d}s}{\mathrm{d}x}\chi.
$$
This Lagrangian has BRST symmetry that is invarient under
$$
x\to x+\chi,\quad\rho\to\rho+s(x),\quad\chi\to\chi.
$$
One can check that $\delta\mathcal{L}=0$ under BRST symmetry. Imposing the equation of motion as
$$
s'(x)\chi=0,
$$
one derive that the BRST symmetry becomes involutory
$$
\delta^2x=0,\quad\delta^2\rho=s'(x)\chi=0.
$$
The zero points of $s(x)$ can be understood as invarient points of BRST symmetry for $\rho$.

### 1.3 $n$-dimensional model
Generalizing the integral $Z$ to $n$-dimensional case, one have
$$
Z=\int\frac{\mathrm{d}^nx}{\sqrt{2\pi}^n}\exp\left[-\frac{1}{2}\sum_i(\partial_iW(x))^2\right]\det(\partial_i\partial_jW(x)),
$$
where $s(x)$ is replaced with $\partial_iW(x)$.