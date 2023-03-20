---
banner: "![[../pics/IMG_20220912_030632.jpg]]"
banner_y: 0.664
---

>[!abstract]- Pre-knowledge
>- Classical mechanics
>- Special relativity
>- [[Representation of Lorentz algebra]]

# Classical field theory
## 1 Basic concepts
### 1.1 Basic degree of freedom
In a field theory, the fundamental degrees of freedom is the field $\phi(x)$. Defining the value of $\phi(x)$ at every point in the spacetime defines the configuration of the field. This can be considered as a path in the infinite-dimensional configuration space.

Different from classical mechanics where space coordinates are considered as degrees of freedom and time as parameter, in field theory all four spacetime coordinates are considered as parameters. Instead, there are infinitly many degrees of freedom, that is the field at each point of spacetime.

### 1.2 Action and Lagrangian
The least action principle also work for field theory. The *action* here is a functional of field $S[\phi]$. One can write it as
$$
S=\int\mathrm{d}^4x\mathcal{L}(x),
$$
where $\mathcal{L}(x)$ is called the *Lagrange density*, associated with the Lagrangian in classical mechanics by
$$
L=\int\mathrm{d}^3x\mathcal{L}(x).
$$
Sometimes one simply call $\mathcal{L}(x)$ the *Lagrangian*.

There are some constrain on the form of $\mathcal{L}$ due to special relativity and system stability.
- Locality requires the Lagrangian to depend on only one spacetime coordinate $\mathcal{L}=\mathcal{L}(x)$;
- Lorentz invarience requires $\mathcal{L}$ to be a Lorentz scalar;
- Stability requires $\mathcal{L}$ to contain at most the second derivative of field $\mathcal{L}=\mathcal{L}(\phi_\alpha,\partial_\mu\phi_\alpha)$.

### 1.3 Equation of motion
Through the least action principle, which requires
$$
\delta S[\phi]=0,
$$
one can get the equation of motion for field
$$
\frac{\partial}{\partial x^\mu}\frac{\partial\mathcal{L}}{\partial(\partial_\mu\phi_\alpha)}-\frac{\partial\mathcal{L}}{\partial\phi_\alpha}=0.
$$
This is called the *Eular-Lagrangian equation*.

### 1.4 Hamiltonian
From the Hamiltonian point of view, one can define the *conjugate momentum* of field as
$$
\pi^\alpha\doteq\frac{\partial\mathcal{L}}{\partial(\partial_0\phi_\alpha)}.
$$
Then, one can define the *Hamilton density* as
$$
\mathcal{H}\doteq\pi^\alpha\partial_0\phi_\alpha-\mathcal{L}.
$$
This is sometimes called the *Hamiltonian*. The sum over index of field $\alpha$ is also omitted like the index of coordinate.

Equivalent to the least action principle, one can write the *canonical equation*
$$
\begin{aligned}
\frac{\partial\mathcal{H}}{\partial\phi_\alpha}-\frac{\partial}{\partial x^i}\frac{\partial\mathcal{H}}{\partial(\partial_i\phi_\alpha)}&=0,\\
\frac{\partial\mathcal{H}}{\partial\pi^\alpha}-\frac{\partial\phi_\alpha}{\partial x^0}&=0,
\end{aligned}
$$
as the equation of motion.

>[!quote] Comment
>This is really not some elegant approach. (Personal opinion)

---
## 2 Noether's theorem
### 2.1 Noether's theorem
Consider an infinitesimal transformation of field that transforms as
$$
\phi_\alpha\to\phi_\alpha+\epsilon\delta\phi_\alpha,\quad\partial_\mu\phi_\alpha\to\partial_\mu\phi_\alpha+\epsilon\partial_\mu(\delta\phi_\alpha).
$$
If change of Lagrangian under this transformation can be written as
$$
\delta\mathcal{L}=\epsilon\partial_\mu K^\mu,
$$
then one can define a *Noether current* as
$$
J^\mu\doteq\left(\frac{\partial\mathcal{L}}{\partial(\partial_\mu\phi_\alpha)}\delta\phi_\alpha-K^\mu\right).
$$
This current satisfies the conservation function
$$
\partial_\mu J^\mu=0.
$$

The integral of zeroth component over the entire space is called the *Noether charge*
$$
Q\doteq\int\mathrm{d}^3x\ J^0.
$$

### 2.2 Noether's theorem with transformation of spacetime
If an infinitesimal transformation also involves spacetime, that is
$$
x^\mu\to x^\mu+\epsilon\delta x^\mu,\quad\phi_\alpha\to\phi_\alpha+\epsilon\delta\phi_\alpha,
$$
and the change of Lagrangian can be written as
$$
\delta\mathcal{L}=\epsilon\partial_\mu K^\mu,
$$
then the *Noether current* can be written as
$$
J^\mu\doteq\left(-\frac{\partial\mathcal{L}}{\partial(\partial_\mu\phi_\alpha)}\partial_\nu\phi_\alpha+\mathcal{L}\ \delta^\mu{}_\nu\right)\delta x^\nu+\frac{\partial\mathcal{L}}{\partial(\partial_\mu\phi_\alpha)}\delta\phi_\alpha-K^\mu.
$$

### 2.3 Energy and momentum
As a special case, consider spacetime translation $x^\mu\to x^\mu+\epsilon a^\mu$ that leaves the field invarient. The corresponding Noether currents form a tensor called the *energy momentum tensor*
$$
T^\mu{}_\nu\doteq-\frac{\partial\mathcal{L}}{\partial(\partial_\mu\phi_\alpha)}\partial_\nu\phi_\alpha+\mathcal{L}\ \delta^\mu{}_\nu.
$$
One can symmetrize its indices by constructing a tensor $S^{\rho\mu\nu}=-S^{\mu\rho\nu}$ and define
$$
\Theta^{\mu\nu}\doteq T^{\mu\nu}+\partial_\rho S^{\rho\mu\nu}.
$$
The four Noether charges forms the *4-momentum* of the field
$$
\begin{aligned}
P^0&\doteq\int\mathrm{d}^3x\ T^{00}=\int\mathrm{d}^3x\ \mathcal{H},\\
P^i&\doteq\int\mathrm{d}^3x\ T^{0i}=-\int\mathrm{d}^3x\ \pi^\alpha\partial_i\phi_\alpha.
\end{aligned}
$$

### 2.4 Angular momentum and spin
Another special case is rotation, generated by the elements of [[Representation of Lorentz algebra|Lorentz algebra]]. One can write an infinitesimal rotation as
$$
x^\mu\to x^\mu+\omega^\mu{}_\nu x^\nu,\quad\phi_\alpha\to\phi_\alpha+\frac{i}{2}\omega_{\mu\nu}(J^{\mu\nu})^\beta_\alpha\phi_\beta.
$$
Then the Noether current is (after antisymmetrize)
$$
M^{\mu\nu\sigma}=T^{\mu\nu}x^\sigma-T^{\mu\sigma}x^\nu+i\frac{\partial\mathcal{L}}{\partial(\partial_\mu\phi_\alpha)}(J^{\nu\sigma})^\beta_\alpha\phi_\beta.
$$
One can work out the Noether charge, which is called the *angular momentum tensor*
$$
J^{\mu\nu}=\int\mathrm{d}^3x\left[T^{0\mu}x^\nu-T^{0\nu}x^\mu+i\pi^\alpha(J^{\mu\nu})^\beta_\alpha\phi_\beta\right].
$$
When considering only space components, it is the angular momentum of the field
$$
J^{ij}=\int\mathrm{d}^3x\ \pi^\alpha\left[(x^i\partial^j-x^j\partial^i)\delta^\beta_\alpha+i(J^{ij})^\beta_\alpha\right]\phi_\beta,
$$
where the first term is the *orbital angular momentum* and the second term is the *spin angular momentum* of the field.

## 3 Klein-Gorden Field
### 3.1 Lorentz invarience of scalar
The Lorentz invarient one can construct from a scalar field $\phi$ other than the power of $\phi$ is $\partial^2\phi$ and $(\partial\phi)^2$. 

### 3.2 Lagrangian
The Lagrangian for the Klein-Gordan field is
$$
\mathcal{L}=\frac{1}{2}\partial_\mu\phi\partial^\mu\phi-\frac{1}{2}m^2\phi^2.
$$
The equation of motion is given by
$$
(\partial_\mu\partial^\mu+m^2)\phi=0.
$$

### 3.3 Hamiltonian
The conjugate momentum of this field is
$$
\pi(x)=\dot{\phi}(x).
$$
Therefore, the Hamiltonian and total momentum is given by
$$
\begin{aligned}
H&=\int\mathrm{d}^3x\ \mathcal{H}=\int\mathrm{d}^3x\left[\frac{1}{2}\pi^2+\frac{1}{2}(\nabla\phi)^2+\frac{1}{2}m^2\phi^2\right],\\
P^i&=-\int\mathrm{d}^3x\ \pi\partial^i\phi.
\end{aligned}
$$

## 4 Dirac field
### 4.1 Lorentz invarience of spinor
For a Dirac spinor
$$
\psi=\begin{pmatrix}
\psi_L\\
\psi_R
\end{pmatrix},
$$
one can define $\bar{\psi}\doteq\psi^\dagger\gamma^0$. Then, the following Lorentz invarient can be constructed from them
$$
\bar{\psi}\psi,\quad\bar{\psi}\gamma^\mu\psi A_\mu,\quad\bar{\psi}\gamma^\mu\partial_\mu\psi,\quad\bar{\psi}\gamma^5\psi,\quad\bar{\psi}\gamma^\mu\gamma^5\psi A_\mu,\quad\bar{\psi}\gamma^\mu\gamma^5\partial_\mu\psi,\quad\cdots
$$

### 4.2 Lagrangian
For Dirac field, the Lagrangian is
$$
\mathcal{L}=\bar{\psi}(i\gamma^\mu\partial_\mu-m)\psi.
$$
The equation of motion is given by
$$
\begin{aligned}
(i\gamma^\mu\partial_\mu-m)\psi&=0,\\
-i\partial_\mu\bar{\psi}\gamma^\mu-m\bar{\psi}&=0.
\end{aligned}
$$
This can be written in the form of Weyl spinor
$$
\psi=\begin{pmatrix}
\psi_L\\
\psi_R
\end{pmatrix}.
$$
With the notation in [[Dirac algebra]], the equation of motion is
$$
\begin{pmatrix}
-m & i\sigma^\mu\partial_\mu\\
i\bar{\sigma}^\mu\partial_\mu & -m
\end{pmatrix}\begin{pmatrix}
\psi_L\\
\psi_R
\end{pmatrix}=0.
$$
When $m=0$, the equation of two Weyl spinors decouples into
$$
i\bar{\sigma}^\mu\partial_\mu\psi_L=0,\quad i\sigma^\mu\partial_\mu\psi_R=0.
$$

### 4.3 Plane-wave solution
Expand the field under momentum representation, one get
$$
\psi=\int_{p^0\geqslant0}\frac{\mathrm{d}^3p}{(2\pi)^3}\left(u(\pmb{p})e^{-i\pmb{p}\cdot\pmb{x}}+v(\pmb{p})e^{i\pmb{p}\cdot\pmb{x}}\right).
$$
The Dirac equation can be written as
$$
(\not p-m)u(\pmb{p})=0,\quad-(\not p+m)v(\pmb{p})=0
$$
where $\not p\doteq\gamma^\mu p_\mu$. The solution can be written as
$$
u(\pmb{p})=\begin{pmatrix}
\sqrt{p\cdot\sigma}\xi\\
\sqrt{p\cdot\bar{\sigma}}\xi
\end{pmatrix},\quad v(\pmb{p})=\begin{pmatrix}
\sqrt{p\cdot\sigma}\eta\\
-\sqrt{p\cdot\bar{\sigma}}\eta
\end{pmatrix}
$$
where $\xi$ and $\eta$ are orthogonal Weyl spinors to denote the spin. One can denote the spin with an upper index $u^s$ and $v^r$. Some identities are given here.
$$
\begin{aligned}
&\bar{u}{}^r(\pmb{p}_1)u^s(\pmb{p}_1)=2m\delta^{rs},&&u^{r\dagger}(\pmb{p}_1)u^s(\pmb{p}_1)=2p_1^0\delta^{rs},\\
&\bar{v}{}^r(\pmb{p}_1)v^s(\pmb{p}_1)=-2m\delta^{rs},&&v^{r\dagger}(\pmb{p}_1)v^s(\pmb{p}_1)=2p_1^0\delta^{rs},\\
&\sum_su^s(\pmb{p}_1)\bar{u}{}^s(\pmb{p}_1)=\not{p}_1+m\times1_\gamma,&&\sum_sv^s(\pmb{p}_1)\bar{v}{}^s(\pmb{p}_1)=\not{p}_1-m\times1_\gamma.
\end{aligned}
$$

### 4.4 Helicity