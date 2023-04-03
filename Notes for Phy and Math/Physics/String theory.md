---
banner: "![[../pics/45f567ee181d880789343b243aecd69c1669915701984.jpeg]]"
banner_y: 0.228
---

>[!abstract]- Pre-knowledge
>- [[../Mathematics/Differential geometry|Differential geometry]]
>- [[Quantum field theory]]
>- [[Representation of Lorentz algebra]]
>- General relativity

# String theory
## 1 Classical theory
There is only one free parameter in string theory $\alpha'$. The typical size of the string is given by
$$
l_S=\sqrt{2\alpha'},
$$
which is much smaller than the resolution of accelerator.

The Minkowski metrics takes the sign
$$
\eta=\mathrm{diag}\{-1,1,1,\cdots\}.
$$

### 1.1 Actions
#### 1.1.1 $p$-brane
In an analogue to point particle, one can introduce a *$p$-brane* with $p$ spacial dimensions and tension (or energy density) $T_p=1/2\pi\alpha'$. Its time evolution generates a $(p+1)$ dimensional world volume $\Sigma_p$.

Denote coordinate on $\Sigma_p$ as $\sigma^i$ and the coordinate on the background spacetime as $X^\mu$. Then one can define the [[../Mathematics/Differential geometry#1.4.3 Immersion and embedding|embedding]]
$$
\Sigma_p\ni\sigma^\alpha\mapsto X^\mu(\sigma)\in\mathbb{R}^{1,D}.
$$
Such embedding induces a [[../Mathematics/Riemannian geometry#1.1 Definition of Riemannian metrics|metrics]] on $\Sigma_p$
$$
G_{\alpha\beta}=g_{\mu\nu}\frac{\partial X^\mu}{\partial\sigma^\alpha}\frac{\partial X^\nu}{\partial\sigma^\beta}.
$$

#### 1.1.2 Nambu-Goto action
The action of a free $p$-brane is proportional to the $(p+1)$ volume
$$
S_p\doteq-T_p\int\mathrm{d}^{p+1}\sigma\sqrt{-\det G_{\alpha\beta}}.
$$
This is called the *Nambu-Goto action*.

Consider the $p=1$ case and take the coordinate
$$
\begin{aligned}
&\sigma^0=\tau\in(-\infty,\infty),\\
&\sigma^1=\sigma\in(0,\pi).
\end{aligned}
$$
The action of the $1$-brane, or *string* can be written as
$$
S_{\text{NG}}\doteq-T\int\mathrm{d}\tau\mathrm{d}\sigma\sqrt{(\dot{X}\cdot X')^2-\dot{X}^2X'^2}.
$$

#### 1.1.3 String sigma model action
The N-G action is hard to quantize due to the square root. An equivalent action can be written as
$$
S_\sigma\doteq-\frac{1}{2}T\int\mathrm{d}^2\sigma\sqrt{-h}h_{\alpha\beta}(\partial_\alpha X)\cdot(\partial_\beta X),
$$
which is called the *sigma model action*. The $h_{\alpha\beta}$ is introduced as an auxiliary metrics field.

Since there are no kinetic term for $h_{\alpha\beta}$, the energy-momentum tensor must vanish
$$
T_{\alpha\beta}=-\frac{2}{T}\frac{1}{\sqrt{-h}}\frac{\delta S_\sigma}{\delta h^{\alpha\beta}}=0.
$$
This gives the equation of motion for $h_{\alpha\beta}$
$$
\partial_\alpha X\cdot\partial_\beta X-\frac{1}{2}h_{\alpha\beta}h^{\gamma\delta}\partial_\gamma X\cdot\partial_\delta X=0.
$$

#### 1.1.4 Symmetry of sigma model action
The sigma model action has 3 types of symmetry.
- [[Representation of Lorentz algebra|Poincare symmetry]], which is a global symmetry under the transformation
$$
X^\mu\to\Lambda^\mu{}_\nu X^\nu+d^\mu;
$$
- Reparameterization symmetry, which is a local symmetry
$$
\sigma\to f(\sigma),\quad h_{\alpha\beta}(f)=\frac{\partial\sigma^\gamma}{\partial f^\alpha}\frac{\partial\sigma^\delta}{\partial f^\beta}h_{\gamma\delta}(\sigma);
$$
- Weyl symmetry, which is also a local symmetry
$$
h_{\alpha\beta}\to e^{\phi(\sigma)}h_{\alpha\beta}.
$$

Considering only Minkowski space-time, a cosmological term and a [[../Mathematics/Riemannian geometry#4.3 Ricci and scalar curvature|scalar curvature]] term can be added to the action preserving Poincare symmetry and renormalizability
$$
S_1=\Lambda\int\mathrm{d}^2\sigma\sqrt{-h},\quad S_2=\lambda\int\mathrm{d}^2\sigma\sqrt{-h}R(h).
$$

#### 1.1.5 Gauge fixing
The last two local symmetries provide a freedom for gauge fixing. When the world sheet has zero Eular characteristic, one can fix the metrics to be
$$
h_{\alpha\beta}=\eta_{\alpha\beta}.
$$
Under *light-cone coordinate* on the world sheet
$$
\sigma^\pm\doteq\tau\pm\sigma,
$$
the metrics is
$$
\mathrm{d}s^2=-\mathrm{d}\sigma^+\mathrm{d}\sigma^-.
$$

For 2 dimensional Minkowski space-time, there is an extra type of symmetry called *conformal symmetry* that leaves the metrics invariant.

### 1.2 Solution
#### 1.2.1 Equation of motion
Under Minkowski metrics, the sigma action becomes
$$
S_\sigma=-\frac{1}{2}T\int\mathrm{d}^2\sigma\left(\dot{X}^2-X'^2\right).
$$
The Eular-Lagrangian equation is then
$$
\left(\frac{\partial^2}{\partial\sigma^2}-\frac{\partial^2}{\partial\tau^2}\right)X^\mu=0,
$$
or
$$
\frac{\partial}{\partial\sigma^+}\frac{\partial}{\partial\sigma^-}X^\mu=0.
$$

Another constrain is that the energy-momentum tensor is zero.

#### 1.2.2 Boundary condition
There are two types of boundary conditions for string.
- Closed string has periodic boundary condition
$$
X^\mu(\sigma,\tau)=X^\mu(\sigma+\pi,\tau)\quad\text{or}\quad X^\mu(\sigma^\pm)=X^\mu(\sigma^\pm\pm\pi);
$$
- Open string has Neumann boundary condition
$$
\left.\frac{\partial}{\partial\sigma}X^\mu\right|_{\sigma=0,\pi}=0\quad\text{or}\quad(\partial_+-\partial_-)X^\mu|_{\sigma^+-\sigma^-=0,\pi}=0;
$$
- Dirichlet boundary condition for open string
$$
\left.X^\mu\right|_{\sigma=0,\pi}=X^\mu_{0,\pi}
$$
for $D-2$ coordinates and Neumann b.c. for the other 2 coordinates. This breaks the Poincare symmetry.

#### 1.2.3 Solution to equation of motion
Under light-cone coordinate, the equation of motion and vanishing of energy-momentum tensor gives
$$
\begin{aligned}
\partial_+\partial_-X^\mu&=0\\
T_{++}=\partial_+X^\mu\partial_+X_\mu&=0\\
T_{--}=\partial_-X^\mu\partial_-X_\mu&=0.
\end{aligned}
$$
The general solution would be a sum of *right-mover* and *left-mover*
$$
X^\mu(\tau,\sigma)=X^\mu_{\text{R}}(\tau-\sigma)+X^\mu_{\text{L}}(\tau+\sigma)
$$
with constraints
$$
(\partial_-X_{\text{R}})^2=(\partial_+X_{\text{L}})^2=0.
$$

#### 1.2.4 Mode expansion for closed string
The general form of solution for closed string is
$$
\begin{aligned}
X^\mu_{\text{R}}&=\frac{1}{2}x^\mu+\frac{1}{2}l_s^2p^\mu\sigma^-+\frac{i}{2}l_s\sum_{n\ne0}\frac{1}{n}\alpha^\mu_ne^{-2in\sigma^-}\\
X^\mu_{\text{L}}&=\frac{1}{2}x^\mu+\frac{1}{2}l_s^2p^\mu\sigma^++\frac{i}{2}l_s\sum_{n\ne0}\frac{1}{n}\tilde{\alpha}^\mu_ne^{-2in\sigma^+}
\end{aligned}
$$
where $x^\mu$ is the coordinate of center of mass and $p^\mu$ is the total momentum of string. The real condition requires
$$
\alpha^\mu_{-n}=(\alpha^\mu_n)^\ast,\qquad\tilde{\alpha}^\mu_{-n}=(\tilde{\alpha}^\mu_n)^\ast.
$$

The mode expansion of derivatives is
$$
\begin{aligned}
\partial_-X^\mu_{\text{R}}&=l_s\sum_{m=-\infty}^{+\infty}\alpha^\mu_me^{-2im\sigma^-}\\
\partial_+X^\mu_{\text{L}}&=l_s\sum_{m=-\infty}^{+\infty}\tilde{\alpha}^\mu_me^{-2im\sigma^+}
\end{aligned}
$$
where
$$
\alpha^\mu_0=\tilde{\alpha}^\mu_0=\frac{1}{2}l_sp^\mu.
$$

#### 1.2.5 Mode expansion for open string
For open string with Neumann boundary condition, the mode expansion is
$$
X^\mu=x^\mu+l_s^2p^\mu\tau+il_s\sum_{m\ne0}\frac{1}{m}\alpha^\mu_me^{-im\tau}\cos(m\sigma).
$$
Different from closed string, open string only has one set of modes $\alpha^\mu_m$. This is because the boundary condition requires the left-moving and right-moving wave to combine into one stationary wave.

The mode expansion of dericatives is
$$
\partial_\pm X^\mu=\frac{1}{2}l_s\sum_{m=-\infty}^{+\infty}\alpha^\mu_me^{-im\sigma^\pm},
$$
where
$$
\alpha^\mu_0=l_sp^\mu.
$$

#### 1.2.6 Poisson bracket
The canonical momentum is
$$
P^\mu\doteq\frac{\delta S}{\delta\dot{X}_\mu}=T\dot{X}^\mu.
$$
The equal time Poisson bracket is
$$
\{P^\mu,P^\nu\}=\{X^\mu,X^\nu\}=0,\quad\{P^\mu(\sigma,\tau),X^\nu(\sigma',\tau)\}=\eta^{\mu\nu}\delta(\sigma-\sigma').
$$
Note that the Dirac delta function is defined with periodic boundary. Doing the mode expansion, one can get
$$
\{x^\mu,p^\nu\}=i\eta^{\mu\nu},\quad\{\alpha^\mu_m,\alpha^\nu_n\}=\{\tilde{\alpha}^\mu_m,\tilde{\alpha}^\nu_n\}=im\eta^{\mu\nu}\delta_{m,-n},\quad\{\alpha^\mu_m,\tilde{\alpha}^\nu_n\}=0.
$$
This also holds for open string.

### 1.3 Energy and momentum
#### 1.3.1 Noether current for Lorentz transformation
For Lorentz transformation, the Noether current is
$$
\begin{aligned}
P^\mu_\alpha&=T\partial_\alpha X^\mu,\\
J^{\mu\nu}_\alpha&=T(X^\mu\partial_\alpha X^\nu-X^\nu\partial_\alpha X^\mu).
\end{aligned}
$$

#### 1.3.2 Hamiltonian
The Hamiltonian is given by
$$
H=\int_0^\pi\mathrm{d}\sigma\left(\dot{X}_\mu P^\mu-\mathcal{L}\right)=\int_0^\pi\mathrm{d}\sigma\left(\dot{X}^2+X'^2\right).
$$
Under mode expansion, the Hamiltonian is
$$
\begin{aligned}
H_{\text{closed}}&=\sum_{n=-\infty}^{+\infty}\left(\alpha_{-n}\cdot\alpha_n+\tilde{\alpha}_{-n}\cdot\tilde{\alpha}_n\right),\\
H_{\text{open}}&=\frac{1}{2}\sum_{n=-\infty}^{+\infty}\alpha_{-n}\cdot\alpha_n.
\end{aligned}
$$

#### 1.3.3 Energy-momentum tensor
For closed string, write the energy-momentum tensor as mode expansion
$$
\begin{aligned}
T_{--}&=2l_s^2\sum_{n=-\infty}^{+\infty}L_ne^{-2in\sigma^-},\\
T_{++}&=2l_s^2\sum_{n=-\infty}^{+\infty}\tilde{L}_ne^{-2in\sigma^+},
\end{aligned}
$$
where $L_n$ and $\tilde{L}_n$ are the *Virasoro generators*
$$
L_n\doteq\frac{1}{2}\sum_{m=-\infty}^{+\infty}\alpha_{n-m}\cdot\alpha_m,\quad\tilde{L}_n\doteq\frac{1}{2}\sum_{m=-\infty}^{+\infty}\tilde{\alpha}_{n-m}\cdot\tilde{\alpha}_m.
$$
They form the *Virasoro algebra*
$$
\{L_m,L_n\}=i(m-n)L_{m+n}.
$$

The Hamiltonian can be written as
$$
H_{\text{closed}}=2(L_0+\tilde{L}_0),\quad H_{\text{open}}=L_0.
$$

#### 1.3.4 On shell condition
Since the energy-momentum tensor is zero, the Fourier modes are all zero
$$
L_m=0
$$
For open string, the vanishing of $L_0$ gives
$$
L_0=\sum_{n=1}^\infty\alpha_{-n}\cdot\alpha_n+\frac{1}{2}\alpha_0^2=\sum_{n=1}^\infty\alpha_{-n}\cdot\alpha_n+\frac{1}{2}l_s^2p^2=0,
$$
which gives the mass
$$
M^2=\frac{1}{\alpha'}\sum_{n=1}^\infty\alpha_{-n}\cdot\alpha_n.
$$
For closed string, the mass is
$$
M^2=\frac{2}{\alpha'}\sum_{n=1}^\infty(\alpha_{-n}\cdot\alpha_n+\tilde{\alpha}_{-n}\cdot\tilde{\alpha}_n).
$$

### 1.4 Light-cone gauge
#### 1.4.1 Residual symmetry
For infinitesimal reparameterization $\xi(\sigma)$ and Weyl scaling $\Lambda$, if the following is satisfied
$$
\partial^\alpha\xi^\beta+\partial^\beta\xi^\alpha=\Lambda\eta^{\alpha\beta},
$$
then the metrics remains invarient. The solution is the transformation
$$
\xi=\xi^\pm(\sigma^\pm),\quad\Lambda=(\partial_+\xi^++\partial_-\xi^-).
$$

The set of infinitesimal transformation generator for closed string is
$$
V^\pm_n\doteq\frac{1}{2}e^{2in\sigma^\pm}\frac{\partial}{\partial\sigma^\pm}.
$$
For open string, the generator is
$$
V_n\doteq e^{in\sigma^+}\frac{\partial}{\partial\sigma^+}+e^{in\sigma^-}\frac{\partial}{\partial\sigma^-}.
$$

#### 1.4.2 Light-cone gauge
Introduce the *light-cone coordinate* as follows
$$
\begin{aligned}
X^\pm=-X_\mp&\doteq\frac{1}{\sqrt{2}}(X^0\pm X^{D-1}),\\
X^i=X_i&\doteq X^i,\qquad 0<i<D-1.
\end{aligned}
$$

## 2 Quantum string
### 2.1 Canonical quantization
#### 2.1.1 Creation and annihilation
Define the creation/annihilation operator as
$$
a^\mu_m\doteq\frac{1}{\sqrt{m}}\alpha^\mu_m,\quad a^{\mu\dagger}_m\doteq\frac{1}{\sqrt{m}}\alpha^\mu_{-m}\quad\text{for }m>0,
$$
then canonical quantization gives the following commutation relation
$$
[x^\mu,p^\nu]=\eta^{\mu\nu},\qquad[a^\mu_m,a^{\nu\dagger}_n]=[\tilde{a}^\mu_m,\tilde{a}^{\nu\dagger}_n]=\eta^{\mu\nu}\delta_{mn}\quad\text{for }m>0.
$$

The ground state $\ket{0}$ is defined by
$$
a^\mu_m\ket{0}=0.
$$
Note that normalizing $\braket{0|0}=1$ will give negative norm states
$$
a^{0\dagger}_m\ket{0}:\quad\braket{0|a^0_ma^{0\dagger}_m|0}=-1,
$$
which will be fixed later.

#### 2.1.2 Virasoro algebra
When quantizing the Virasoro generators $L_m$, one take the normal ordered operator
$$
L_m\doteq\frac{1}{2}\sum_{n=-\infty}^{+\infty}:\alpha_{m-n}\cdot\alpha_n:,
$$
with $L_{-m}=L_m^\dagger$. This only effects $L_0$ according to the commutative relation
$$
\begin{aligned}
L_0&=\frac{1}{2}\alpha_0^2+\sum_{n=1}^\infty\alpha_n\cdot\alpha_{-n}\\
&=(L_0)_{\text{no normal order}}+\sum_{n=1}^\infty n[a_n^\mu,a_n^{\nu\dagger}]\eta_{\mu\nu}\\
&=(L_0)_{\text{no normal order}}-\frac{D}{12}.
\end{aligned}
$$
Then the Virasoro algebra becomes
$$
[L_m,L_n]=(m-n)L_{m+n}+\frac{D}{12}m(m^2-1)\delta_{m+n,0}.
$$

#### 2.1.3 Physical states
It is required that for physically allowed states, there is
$$
(L_0-a)\ket{\text{Phy}}=(\tilde{L}_0-a)\ket{\text{Phy}}=0,\quad L_m\ket{\text{Phy}}=\tilde{L}_m\ket{\text{Phy}}=0\quad\text{for}\quad m>0
$$
where $a$ is a constant.

Define the *number operator* as
$$
N\doteq\sum_{n=1}^\infty\alpha_{-n}\cdot\alpha_n=\sum_{n=1}^\infty na_n^\dagger\cdot a_n.
$$
Then the mass of open string is given by
$$
M^2=\frac{1}{\alpha'}(N-a).
$$
For closed string, the mass is
$$
M^2=\frac{4}{\alpha'}(N-a)=\frac{4}{\alpha'}(\tilde{N}-a).
$$

The condition $N=\tilde{N}$ is called the *level-matching condition*.

#### 2.1.4 Spurious states
A *spurious state* is a state that satisfies mass-shell condition and is orthogonal to any physical states
$$
(L_0-a)\ket{\text{Spr}}=L_m\ket{\text{Spr}}=0,\quad\braket{\text{Phy}|\text{Spr}}=0.
$$
