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