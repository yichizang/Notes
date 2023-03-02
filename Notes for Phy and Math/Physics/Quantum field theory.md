---
banner: "![[pics/d8b3bb96cac38fa3c08009a7db66bf711642750972344.jpeg]]"
banner_y: 0.128
---

>[!abstract]- Pre-knowledge
>- Quantum field theory

# Quantum field theory
## 1 QFT1

>[!note]
>Notes on QFT1 will be transfered later.

## 2 Gauge field theory
Write the *action* as
$$
S=\int\mathrm{d}^4x\mathcal{L}(\phi_i,\dot{\phi}_i,g_i)
$$
where $\phi_i$ are fields and $g_i$ are *coupling constances*.

To define a field theory, one need to claim the fields and symmetries in the theory.

### 2.1 Review on interaction field theory
#### 2.1.1 Assumptions
Assumptions on Hilbert space.
1. $\ket{\Omega}$ has zero momentum;
2. $\ket{p}$ satisfies $p^2=m^2\geqslant0$. For now, bounded states are not considered;
3. For multi-particle state, $p^2\geqslant 4m^2$.

#### 2.1.2 Time evolution
Time evolution of an observable $O$ is given by
$$
i\frac{\partial}{\partial t}\braket{\phi|O|\psi}=\braket{\phi|[O,H]|\psi}.
$$
Write $H=M+N$ where both $M$ and $N$ are Hermitian and let
$$
\begin{aligned}
&i\frac{\partial}{\partial t}O=[O,M],\\
&i\frac{\partial}{\partial t}\ket{\psi(t)}=N\ket{\psi(t)}.
\end{aligned}
$$
As an extremum case, in the Heisenberg picture and Schordinger picture of free theory, $N$ and $M$ are taken to be $0$ respectively and the other being $H$.

#### 2.1.3 Interaction picture
In the interaction picture, one take $M=H_0$ as the Hamiltonian of free theory and $N=V_I$ containing information about interaction. It is also required that $H_0$ being independent of time. Then the time evolution of operator is given by
$$
O_I(t)=e^{-iH_0(t-t_0)}O_I(t_0)e^{iH_0(t-t_0)},
$$
and the state given by
$$
\ket{\psi(t)}_I=U_I(t,t_0)\ket{\psi(t_0)}_I,
$$
where the $U_I(t,t_0)$ is the time evolution operator. It can be written as
$$
U_I(t,t_0)=T\exp\left[-i\int^t_{t_0}\mathrm{d}\tau V_I(\tau)\right].
$$

#### 2.1.4 Choice of b.c.
Since the matrix elements of observable does not depend on the choice of picture, one have
$$
_H\braket{\phi|O_H(t)|\psi}_H={}_I\braket{\phi(t)|O_I(t)|\psi(t)}_I.
$$
By choosing the boundary condition of $t_0$ as
$$
\ket{\psi(t_0)}_I=\ket{\psi}_H,
$$
the observable operator can be written as
$$
O_I(t)=U_I^\dagger(t_0,t)O_H(t)U_I(t_0,t).
$$

#### 2.1.5 In- and out- state
In-state and out-state under Heisenberg picture is defined by taking $t\to\pm\infty$. Then these states under interaction picture is given by takeing $t_0=\pm\infty$
$$
\begin{aligned}
&\ket{\{p_i\}(t),\text{in}}_I=U_I(t,-\infty)\ket{\{p_i\},\text{in}}_H,\\
&\ket{\{p_i\}(t),\text{out}}_I=U_I(t,+\infty)\ket{\{p_i\},\text{out}}_H.
\end{aligned}
$$
Here take the assumption of completeness
$$
1_\mathcal{H}=\sum\ket{\{p_i\},\text{in}}_{HH}\bra{\{p_i\},\text{in}}=\sum\ket{\{p_i\},\text{out}}_{HH}\bra{\{p_i\},\text{out}}.
$$

#### 2.1.6 S matrix
The matrix element of $S$ matrix is defined as
$$
S_{\beta\alpha}={}_H\braket{\beta,\text{out}|\alpha,\text{in}}_H.
$$
Followed by the assumption of completeness, one can derive that
$$
SS^\dagger=S^\dagger S=\mathbb{1}.
$$

#### 2.1.7 Green function
The Green function is given by
$$
G(x_1,x_2,\cdots x_n)=\braket{\Omega|T\{\phi(x_1)\phi(x_2)\cdots\phi(x_n)\}|\Omega}.
$$
According to Gell-Mann-Low formula
$$
_H\braket{\Omega,\text{in}|T\{\phi(x_1)\phi(x_2)\cdots\phi(x_n)\}|\Omega,\text{in}}_H=\frac{_I\braket{\Omega,\text{in}|T\{\phi_I(x_1)\cdots\phi_I(x_n)\exp[\cdots]\}|\Omega,\text{in}}_I}{_I\braket{\Omega,\text{in}|T\exp\left[-i\displaystyle\int^{+\infty}_{-\infty}\mathrm{d}\tau V_I(\tau)\right]|\Omega,\text{in}}{}_I}
$$

#### 2.1.8 LSZ reduction
According to Kallen-Lehmann spectral representation, the Fourior transformation of two-point function is given by
$$
\int\mathrm{d}^4xe^{-ip\cdot x}\braket{\Omega|T\phi(x)\phi(y)|\Omega}=\frac{iZ}{p^2-m^2+i\epsilon}+\int^{+\infty}_{\sim 4m}\frac{\mathrm{d}M^2}{2\pi}\rho(M^2)\frac{i}{p^2-M^2+i\epsilon}.
$$

The LSZ reduction fomula is
$$
\begin{aligned}
&\braket{p_1,\cdots,p_n,\text{out}|k_1,\cdots,k_m,\text{in}}\\
=&\left[-i\sqrt{Z}\right]^{-m-n}\prod_i(p_i^2-m^2)\prod_j(k_j^2-m^2)\tilde{G}(p_1,\cdots,p_n,k_1,\cdots,k_m)|_{\text{on shell}}.
\end{aligned}
$$
This reduction process can be considered as cutting off the external legs of the matrix element.

### 2.2 Massive spin-1 theory
#### 2.2.1 Classical field
The Lagrangian is given by
$$
\mathcal{L}=-\frac{1}{4}F_{\mu\nu}F^{\mu\nu}+\frac{1}{2}m^2A_\mu A^\mu.
$$
Here $\mathcal{L}$ does not depend on $\dot{A}^0$, thus $\pi^0=0$, thus the Eular-Lagrange equation gives
$$
(\partial^2+m^2)A^\mu=0,
$$
with a constrain $\partial_\mu A^\mu=0$. Solving the constrain, one get
$$
A^0=-\frac{1}{m^2}\nabla\cdot\pmb{\pi}.
$$
Thus $A^0$ can be removed from the equation of motion.

#### 2.2.2 Polarization
Write the Fourior transformation of field
$$
A^\mu(x)=\sum_{\lambda=1}^3\int\frac{\mathrm{d}^4p}{(2\pi)^4}\epsilon^\mu(p,\lambda)e^{-ip\cdot x}.
$$
Using the constrain, one get
$$
\sum_{\lambda=1}^3p_\mu\epsilon^\mu(p,\lambda)=0
$$
Working in the rest frame where $p^\mu=(m,\pmb{0})$, one can simply construct
$$
\begin{aligned}
&\epsilon^\mu(p,1)=(0,1,0,0),\\
&\epsilon^\mu(p,2)=(0,0,1,0),\\
&\epsilon^\mu(p,3)=(0,0,0,1),
\end{aligned}
$$
to satisfy the constrain. Performing a boost to have $p^\mu=(E,0,0,p_z)$, the first two polarization remains while the third polarization changes into
$$
\epsilon^\mu(p,3)=\frac{1}{m}(p_z,0,0,E).
$$
The polarization also satisfies
$$
\sum_\lambda\epsilon_\mu\epsilon_\nu^\ast=-g_{\mu\nu}+\frac{p_\mu p_\nu}{m^2}.
$$
The mass on the denominator shows that this theory can't be smoothly transformed into massless theory.

#### 2.2.3 Quantumization
Write the Fourior decomposition of field operator as
$$
A_\mu=\int\frac{\mathrm{d}^3p}{(2\pi)^3}\frac{1}{\sqrt{2\omega_{\pmb{p}}}}\sum_{\lambda=1}^3\left[\epsilon_\mu(\pmb{p},\lambda)a_{\pmb{p},\lambda}e^{-i\pmb{p}\cdot\pmb{x}}+\epsilon_\mu^\ast(\pmb{p},\lambda)a_{\pmb{p},\lambda}^\dagger e^{i\pmb{p}\cdot\pmb{x}}\right].
$$
The exited state is then
$$
\ket{\pmb{p},\lambda}\doteq\sqrt{2\omega_{\pmb{p}}}a_{\pmb{p},\lambda}^\dagger\ket{0}.
$$
The commutator of annihilation and creation operator is
$$
\left[a_{\pmb{p},\lambda},a_{\pmb{p}',\lambda'}^\dagger\right]=(2\pi)^3\delta_{\lambda\lambda'}\delta^{(3)}(\pmb{p}-\pmb{p}').
$$
From this one can derive the commutator
$$
[A_\mu(x),A_\nu(y)]=\left(-g_{\mu\nu}-\frac{1}{m^2}\partial_\mu\partial_\nu\right)D(x-y),
$$
where $D(x-y)=[\phi(x),\phi(y)]$ for scalar field.

#### 2.2.4 Hamiltonian
The hamiltonian of the theory is given by
$$
\mathcal{H}=\sum_{\lambda=1}^3\int\mathrm{d}^3p\ \omega_{\pmb{p}}a_{\pmb{p},\lambda}a_{\pmb{p},\lambda}^\dagger.
$$
Similarly, the momentum operator is
$$
P^i=\sum_{\lambda=1}^3\int\mathrm{d}^3p\ p^ia_{\pmb{p},\lambda}a_{\pmb{p},\lambda}^\dagger.
$$

>[!warning]
>I'm too sleepy right now. Finish the note later zzz.

### 2.3 Massless spin-1?
#### 2.3.1 Vector field
For a vector field
$$
\mathcal{L}=-\frac{1}{4}F_{\mu\nu}F^{\mu\nu}-j_\mu A^\mu,
$$
the EOM is
$$
\partial_\mu F^{\mu\nu}=j^\nu.
$$
It has a gauge invarience under gauge transformation
$$
A^\mu\to A^\mu+\partial^\mu\Lambda.
$$
One can check this by working out
$$
j_\mu A^\mu\to j_\mu(A^\mu+\partial^\mu\Lambda)=j_\mu A^\mu+\partial^\mu(j_\mu\Lambda)-\Lambda\partial\cdot j=j_\mu A^\mu.
$$
The last equality holds for $j\to0$ at infinity.

#### 2.3.2 Different gauge
The Lorentz gauge is
$$
\partial_\mu A^\mu=0,
$$
which leaves some unphysical state to be get rid of. A better gauge in this sense is *Coulomb gauge*
$$
\nabla\cdot\pmb{A}=0.
$$
Another possible gauge is *Axial gauge*
$$
A_z=0.
$$

Focusing on the Coulomb gauge, one write the zeroth component of EOM as
$$
\partial_i F^{i0}=j^0,
$$
which can be transformed into
$$
-\Delta A^0=j^0
$$
by gauge condition. The solution is then
$$
A^0(t,\pmb{x})=\int\mathrm{d}^3y\frac{j^0(t,\pmb{y})}{4\pi|\pmb{x}-\pmb{y}|}.
$$

On the other hand, for an arbitrary $\pmb{A}$, one can construct a gauge transformation to match the Coulomb gauge by
$$
\pmb{A}'=\pmb{A}-\nabla\Lambda,
$$
where
$$
\Lambda(t,\pmb{x})=-\int\mathrm{d}^3y\frac{\nabla_y\cdot\pmb{A}(t,\pmb{y})}{4\pi|\pmb{x}-\pmb{y}|}.
$$
One can then decomposite $\pmb{A}$ into a physical DOF $\pmb{A}_\perp$ and a nonphysical DOF $\pmb{A}_{//}$
$$
\pmb{A}=(P_\perp+P_{//})\pmb{A}
$$
where
$$
\begin{aligned}
&(P_\perp)_{ij}\doteq\delta_{ij}-\partial_i\frac{1}{\Delta}\partial_j,\\
&(P_{//})_{ij}\doteq\partial_i\frac{1}{\Delta}\partial_j.
\end{aligned}
$$

#### 2.3.3 Polarization
Write two polarizations as
$$
\begin{aligned}
&\epsilon^\mu(\pmb{k},1)=(0,\pmb{\epsilon}(\pmb{k},1)),\\
&\epsilon^\mu(\pmb{k},2)=(0,\pmb{\epsilon}(\pmb{k},2))
\end{aligned}
$$
with constrain
$$
\pmb{k}\cdot\pmb{\epsilon}=0,\quad\pmb{\epsilon}(\pmb{k},\lambda_1)\pmb{\epsilon}(\pmb{k},\lambda_2)=\delta_{\lambda_1\lambda_2}.
$$
Only considering $\pmb{A}=\pmb{A}_\perp$, one can quantumize the field as
$$
[A^i(t,\pmb{x}),\pi^j(t,\pmb{y})]=-i\delta_{\perp ij}^{(3)}(\pmb{x}-\pmb{y}),
$$
where
$$
\delta_{\perp ij}^{(3)}\doteq(P_\perp)_{ij}\delta^{(3)}.
$$
After writting the plane-wave decomposition, one can obtain the commutator
$$
[a_{p_1,\lambda_1},a_{p_2,\lambda_2}^\dagger]=(2\pi)^3\delta_{\lambda_1\lambda_2}\delta^{(3)}(\pmb{p}_1-\pmb{p}_2).
$$
When doing plane-wave decomposition, it involves the completeness relation
$$
\sum_\lambda\epsilon^i\epsilon^j=\delta^{ij}-\frac{k^ik^j}{|\pmb{k}|^2}
$$
where the RHS is $\delta_\perp$ in momentum space.

#### 2.3.4 Propogator
The propogator is
$$
D^{\mu\nu}_F(x-y)\doteq\braket{0|TA^\mu(x)A^\nu(y)|0}.
$$
The physical components are
$$
D^{ij}_F(x-y)=\theta(x^0-y^0)\left(\delta^{ij}-\frac{\partial^i\partial^j}{\Delta}\right)D(x-y)
$$
according to completeness relation. Then one can write
$$
D^{\mu\nu}_F(x-y)=\int\frac{\mathrm{d}^4k}{(2\pi)^4}\frac{iP^{\mu\nu}(k)}{k^2+i\epsilon}e^{-ik\cdot(x-y)},
$$
where
$$
P^{ij}\doteq\delta^{ij}-\hat{k}^i\hat{k}^j,\quad P^{0\mu}=0.
$$
To regain Lorentz covarience of $D_F$, one introduce unphysical polarization
$$
\begin{aligned}
&\epsilon^\mu(\pmb{k},0)=(1,\pmb{0}),\\
&\epsilon^\mu(\pmb{k},3)=(0,\hat{k}).
\end{aligned}
$$
Then the completeness relation becomes
$$
\sum_{\lambda_1,\lambda_2}\epsilon_\mu\epsilon_\nu^\ast g_{\lambda_1\lambda_2}=g_{\mu\nu}.
$$
By substracting the unphysical polarizations again, one can write
$$
P_{\mu\nu}=-g_{\mu\nu}-\frac{k_\mu k_\nu-(k_\mu n_\nu+k_\nu n_\mu)k\cdot n+n_\mu n_\nu k^2}{(k\cdot n)^2-k^2}
$$
where $n^\mu=\epsilon^\mu(0)$. Note that a propogator is always coupled with a conserved current, for instance $j^\mu$. Therefore any term with $k_\mu$ will be turned into a derivative and becomes zero applying on $j^\mu$.

What's left can be written as
$$
\begin{aligned}
D^{\mu\nu}_F(x-y)&=\int\frac{\mathrm{d}^4k}{(2\pi)^4}\frac{i}{k^2+i\epsilon}\left(-g_{\mu\nu}-\frac{n_\mu n_\nu k^2}{|\pmb{k}|^2}\right)e^{-ik\cdot(x-y)}\\
&=(D_F^{\text{eff}})^{\mu\nu}+(D_F^{\text{Coul}})^{\mu\nu}.
\end{aligned}
$$
Here the Coulomb proporgator gives
$$
(D_F^{\text{Coul}})^{\mu\nu}=-ig^{\mu0}g^{\nu0}\delta(x^0-y^0)\frac{1}{4\pi|\pmb{x}-\pmb{y}|}.
$$

#### 2.3.5 Hamiltonian
Write the Lagrangian as
$$
\mathcal{L}_0=\frac{1}{2}(E_{//}^2+E_\perp^2-B^2)
$$
with
$$
\pmb{E}_{//}=-\dot{\pmb{A}},\quad\pmb{E}_\perp=-\nabla A^0.
$$
The Hamiltonian is then
$$
\mathcal{H}=\mathcal{H}_0+\mathcal{V}=\mathcal{H}_0+\frac{1}{2}A^0j^0-\pmb{j}\cdot\pmb{A}=\mathcal{H}_0+\mathcal{V}_{\text{Coul}}+\bar{V}.
$$

Expanding the interaction
$$
\begin{aligned}
&\braket{0|T\exp\left[-i\int\mathrm{d}\tau V_I(t)\right]|0}\\
=&\braket{0|1-i\int\mathrm{d}tV_{\text{Coul}}(t)+\frac{(-i)^2}{2!}\int\mathrm{d}^4x\mathrm{d}^4y(\cdots)|0}.
\end{aligned}
$$

### 2.4 Symmetry
Consider a theory with 2 Dirac fermion
$$
\mathcal{L}=\bar{\psi}_1(i\not\partial-m_1)\psi_1+\bar{\psi}_2(i\not\partial-m_2)\psi_2.
$$
It has two $U(1)$ symmetries. If taken $m_1=m_2$, then the symmetry is expanded to $U(2)$ by writing
$$
\mathcal{L}=\bar{\Psi}(i\not\partial-m)\mathbb{1}_2\Psi,
$$
where
$$
\Psi\doteq\begin{pmatrix}
\psi_1\\
\psi_2
\end{pmatrix}.
$$
Note that $U(2)=SU(2)\times U(1)$.

#### 2.4.1 Rep. of SU(N)
Fundamental rep. and adjoint rep.. For fundamental rep.
$$
\psi_i\to\psi_i+ig\alpha^a(T_{\text{fund}}^a)_{ij}\psi_j,
$$
where $a,b,\cdots$ label generators and $i,j,k,\cdots$ label flavors/colors.

| group name | generator         |
| ---------- | ----------------- |
| SU(2)      | $T^1=\sigma^a/2$  |
| SU(3)      | $T^a=\lambda^a/2$ |

$$
\sum_{c,d}f^{acd}f^{bcd}=N\delta^{ab},\quad\mathrm{Tr}(T^aT^b)=\frac{1}{2}\delta^{ab}.
$$
For adjoint rep.
$$
(T_{\text{adj}}^a)^{bc}=-if^{abc}.
$$

### 2.5 Yang-Mills
Consider $N$ fields with same mass
$$
\Psi=\begin{pmatrix}
\psi_1\\
\vdots\\
\psi_N
\end{pmatrix}.
$$
The symmetry is $SU(N)$ that
$$
\Psi(x)\to V(x)\Psi(x).
$$
Consider a gauge transition function such that
$$
U(y,x)\to V(y)U(y,x)V^\dagger(x).
$$
Write it in the infinitesimal form
$$
U(x+\epsilon n,x)=1+ig\epsilon n^\mu A_\mu(x)+\cdots
$$
where $A_\mu$ are traceless unitary matrices. One can derive that $A_\mu$ transforms as
$$
A_\mu(x)\to V(x)\left(A_\mu(x)+\frac{i}{g}\partial_\mu\right)V^\dagger(x).
$$
