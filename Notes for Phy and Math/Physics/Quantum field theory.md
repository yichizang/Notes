---
banner: "![[pics/25f05f0f4a9e6122e756916c4f629e141648009308085.png]]"
banner_y: 0.392
---

>[!abstract]- Pre-knowledge
>- Quantum mechanics
>- [[Classical field theory]]
>- [[Representation of Lorentz algebra]]

# Quantum field theory
## 1 Canonical quantization
### 1.1 Physical picture
#### 1.1.1 General time evolution
For a general description of time evolution, the matrix element satisfies
$$
i\frac{\partial}{\partial t}\braket{\psi(t)|O(t)|\phi(t)}=\braket{\psi(t)|[O(t),H(t)]|\phi(t)}.
$$
If one write
$$
H=M+N
$$
and claim that
$$
\begin{aligned}
i\frac{\partial}{\partial t}O(t)&=[O(t),M(t)],\\
i\frac{\partial}{\partial t}\ket{\psi(t)}&=N(t)\ket{\psi(t)},
\end{aligned}
$$
then the time evolution is governed by seperate equations. In the case when $H$ does not depend on time, the solution can be written as
$$
\begin{aligned}
O(t)&=e^{iM(t-t_0)}O(t_0)e^{-iM(t-t_0)},\\
\ket{\psi(t)}&=e^{-iN(t-t_0)}\ket{\psi(t_0)}.
\end{aligned}
$$

#### 1.1.2 Schrodinger and Heisenberg picture
Under *Schrodinger picture*, one write
$$
M=0,\quad N=H.
$$
The time evolution becomes
$$
\begin{aligned}
O_S(t)&=O_S(t_0),\\
\ket{\psi(t)}_S&=e^{-iH(t-t_0)}\ket{\psi(t_0)}_S.
\end{aligned}
$$

Under *Heisenberg picture*, one write
$$
M=H,\quad N=0.
$$
The time evolution becomes
$$
\begin{aligned}
O_H(t)&=e^{iH(t-t_0)}O_H(t_0)e^{-iH(t-t_0)},\\
\ket{\psi(t)}_H&=\ket{\psi(t_0)}_H.
\end{aligned}
$$

#### 1.1.3 Interaction picture
In the *interaction picture*, one write
$$
M=H_0,\quad N=V,
$$
where $H_0$ is the free Hamiltonian. In this way, the operator evolves in the same way as free theory
$$
O_I(t)=e^{iH_0(t-t_0)}O_I(t_0)e^{-iH_0(t-t_0)}.
$$
That includes the field operators $\phi_I$ and $\pi_I$.

In a general case $V=V(t)$, define the *time evolution operator* as
$$
\ket{\psi(t)}=U(t,t_0)\ket{\psi(t_0)}.
$$

#### 1.1.4 Transition between pictures
Setting the initial condition
$$
O_S=O_H(0),\quad\ket{\psi}_H=\ket{\psi(0)}_S,
$$
one can write the transition between Schrodinger picture and Heisenberg picture
$$
\begin{aligned}
O_H(t)&=e^{iHt}O_Se^{-iHt},\\
\ket{\psi(t)}_S&=e^{-iHt}\ket{\psi}_H.
\end{aligned}
$$

#### 1.1.5 Eigenstate under pictures
Under Heisenberg picture, consider a state $\ket{\phi,t_0}_H$ that satisfies
$$
\phi_H(\pmb{x},t_0)\ket{\phi,t_0}_H=\phi(\pmb{x},t_0)\ket{\phi,t_0}_H.
$$
Such a state is an [[../Mathematics/Linear algebra#6.3 Eigenvector|eigenstate]] of field operator at time $t=t_0$.

>[!note]
>The state $\ket{\phi,t_0}_H$ does not evolve with time since it's under Heisenberg picture. The $t_0$ is simply to label of which operator this eigenstate is.

Under Schrodinger picture, an eigenstate is $\ket{\phi}_S$ that
$$
\phi_S(\pmb{x})\ket{\phi(t)}_S=\phi(\pmb{x},t)\ket{\phi(t)}_S.
$$

These two are related by
$$
\ket{\phi(t)}_S=e^{-iHt}\ket{\phi,t}_H.
$$

## 2 Path integral formalism
### 2.1 Path integral
#### 2.1.1 Feynman kernal
Write the transition amplitude of two eigenstates as
$$
U(\phi_f,t_f;\phi_0,t_0)\doteq{}_H\braket{\phi_f,t_f|\phi_0,t_0}_H.
$$
This is called the *Feynman kernal*. Under Schrodinger picture, it can be written as
$$
U(\phi_f,t_f;\phi_0,t_0)\doteq{}_S\braket{\phi_f|e^{-iH(t_f-t_0)}|\phi_0}_S.
$$

Using the resolution of identity for both field and momentum, one can get
$$
\begin{aligned}
U(\phi_f,t_f;\phi_0,t_0)&=\lim_{n\to\infty}\braket{\phi_f|(1-iH\delta)^n|\phi_0}\\
&=\lim_{n\to\infty}\int\mathrm{d}\phi\prod_{i=1}^n\braket{\phi_i|(1-iH\delta t)|\phi_{i-1}}\\
&=\lim_{n\to\infty}\int\mathrm{d}\phi\mathrm{d}\pi\prod_{i=1}^n\braket{\phi_i|\pi_{i-1}}\braket{\pi_{i-1}|(1-iH\delta t)|\phi_{i-1}},
\end{aligned}
$$
where the integral $\mathrm{d}\phi$ and $\mathrm{d}\pi$ integrates over all fields and momenta except $\phi_0$ and $\phi_n\doteq\phi_f$.

>[!warning]
>NOT FINISHED

Expressing the Hamiltonian as a function of $\phi$ and $\pi$, the Feynman kernal can be written as
$$
U(\phi_f,t_f;\phi_0,t_0)=\int[D\phi][D\pi]\exp\left\{i\int_{t_0}^{t_f}\mathrm{d}^4x\left[\pi\dot{\phi}-\mathcal{H}(\phi,\pi)\right]\right\}.
$$
The terms on the index are all numbers instead of operators. Here the normalization factors are absorbed in $[D\phi]$ and $[D\pi]$.

#### 2.1.2 Lagrangian formalism

#### 2.1.3 Time ordering


## 3 Renormalization and regularization
### 3.1 Regularization
#### 3.1.1 Feynman parameters
The *Feynman parameter* is a method using the identity
$$
\frac{1}{A_1\cdots A_n}=\int_0^1\mathrm{d}x_1\cdots\mathrm{d}x_n\ \delta\left(\sum x_i-1\right)\frac{(n-1)!}{\left(\sum x_iA_i\right)^n}
$$
to work out the correlation function or scattering amplitude. A typical scattering amplitude may have the form
$$
\begin{aligned}
&\int\frac{\mathrm{d}^4k}{(2\pi)^4}f(k^\mu,\cdots)\frac{1}{k^2-m_1^2+i\epsilon}\frac{1}{(k-q)^2+i\epsilon}\frac{1}{(k-p)^2-m_2^2+i\epsilon}\\
=&\int_0^1\prod\mathrm{d}x_i\ \delta(\cdots)\int\frac{\mathrm{d}^4k}{(2\pi)^4}f(k^2,\cdots)\frac{2}{D^3}
\end{aligned}
$$
where
$$
D=k^2+\Delta+i\epsilon
$$
and $\Delta$ is some function independent of $k$. This step may require some change in variable.

The $f(k^\mu,\cdots)$ on the numerator can be written as $f(k^2,\cdots)$ using the identity
$$
\int\frac{\mathrm{d}^4k}{(2\pi)^4}\frac{k^\mu}{D^3}=0,\qquad\int\frac{\mathrm{d}^4k}{(2\pi)^4}\frac{k^\mu k^\nu}{D^3}=\int\frac{\mathrm{d}^4k}{(2\pi)^4}\frac{1}{d}\frac{\eta^{\mu\nu}k^2}{D^3}.
$$

#### 3.1.2 Wick rotation
When doing an integral of a Lorentz vector $k^\mu$ with form
$$
\int\mathrm{d}^4k\ f(k^2),
$$
one can perform a change of variable
$$
\pmb{k}_E\doteq\pmb{k},\quad k_E^0=-ik^0
$$
into an Euclidean vector. Then doing a change of contour called *Wick rotation* (in the case when there's no poles on the path of rotation) to obtain
$$
\begin{aligned}
\int\mathrm{d}^4k\ f(k^2)&=\int_{-\infty}^\infty\mathrm{d}k^0\int\mathrm{d}^3\pmb{k}\ f(k^2)\\
&=\int_{-i\infty}^{+i\infty}\mathrm{d}k^0\int\mathrm{d}^3\pmb{k}\ f(k^2)\\
&=i\int_{-\infty}^{+\infty}\mathrm{d}k_E^0\int\mathrm{d}^3\pmb{k}_E\ f(-k_E^2)\\
&=i\int\mathrm{d}^4k_E\ f(-k_E^2).
\end{aligned}
$$
This is an integral of Euclidean vector, which can be done by
$$
\int\mathrm{d}^4k_E=\int\mathrm{d}\Omega^{(4)}\int_0^{+\infty}\mathrm{d}(k_E^2)\frac{k_E^2}{2}=\pi^2\int_0^{+\infty}\mathrm{d}(k_E^2)\ k_E^2.
$$

After Wick rotation, the shift $+i\epsilon$ on the denominator can be omitted.

#### 3.1.3 Momentum cut-off
The *cut-off* regularization means that the momentum integral cuts off at some finite scale
$$
\int_0^{+\infty}\mathrm{d}(k_E^2)\to\int_0^{\Lambda^2}\mathrm{d}(k_E^2).
$$

>[!example]
>As an example, the integral
>$$
>\int_0^{+\infty}\mathrm{d}(k_E^2)\frac{k_E^2}{(k_E^2+\Delta)^n}
>$$
>needs to be regularized in the case of $n=1,2$.
>
>After the cut-off, the $n=1$ case becomes
>$$
>\Lambda^2-\Delta\ln\frac{\Lambda^2}{\Delta}+O(\frac{\Delta}{\Lambda^2})
>$$
>with both direct divergence $\Lambda^2$ and logarithm divergence $\ln\Lambda$.
>
>The $n=2$ case becomes
>$$
>\ln\frac{\Lambda^2}{\Delta}-1+O(\frac{\Delta}{\Lambda^2})
>$$
>with logarithm divergence.

>[!note]+ Pauli-Villars regularization
>A similar approach is the *Pauli-Villars regularization*, which puts the cut-off $\Lambda$ on the denominator
>$$
>\frac{1}{k^2-m^2+i\epsilon}\to\frac{1}{k^2-m^2+i\epsilon}-\frac{1}{k^2-m^2-\Lambda^2+i\epsilon}.
>$$
>Sometimes in the massless case, one also put an infrared cut-off $\mu^2\to0$ in the first term.

#### 3.1.4 Dimensional regularization
The *dimensional regularization* means to work on the $d$ dimensional space-time instead of 4 dimensional one. The integral then becomes
$$
\int\frac{\mathrm{d}^4k_E}{(2\pi)^4}\to\tilde{\mu}^{4-d}\int\frac{\mathrm{d}^dk_E}{(2\pi)^d},\qquad\tilde{\mu}\doteq\mu\sqrt{\frac{e^{\gamma_E}}{4\pi}},
$$
where has the mass dimension $[\mu]=[\tilde{\mu}]=1$.

The integral can be performed as
$$
\begin{aligned}
\int\frac{\mathrm{d}^dk_E}{(2\pi)^d}&=\int\frac{\mathrm{d}\Omega^{(d)}}{(2\pi)^d}\int_0^{+\infty}\mathrm{d}(k_E^2)\frac{1}{2}(k_E^2)^{d/2-1}\\
&=\frac{1}{(4\pi)^{d/2}}\frac{1}{\Gamma(d/2)}\int_0^{+\infty}\mathrm{d}(k_E^2)(k_E^2)^{d/2-1}.
\end{aligned}
$$

### 3.2 Renormalization
#### 3.2.1 $\phi^4$ theory as an example
The Lagrangian of the $\phi^4$ theory is given by
$$
\mathcal{L}=\frac{1}{2}(\partial^\mu\phi_0\partial_\mu\phi_0-m_0^2\phi_0^2)-\frac{\lambda_0}{4!}\phi_0^4,
$$
where the downscript $X_0$ means *bare terms* or terms without renormalization.

#### 3.2.2 Self energy correction
Consider the propogator of a $\phi^4$ particle
$$
\begin{aligned}
\int\mathrm{d}^4xe^{ip\cdot x}\braket{\Omega|T\phi_0(x)\phi_0(0)|\Omega}&=(\text{propogator})+(\text{1PI})+(\text{1PI})(\text{1PI})+\cdots\\
&=\frac{i}{p^2-m_0^2+i\epsilon}+\frac{i}{p^2-m_0^2+i\epsilon}\left[-i\Pi(p^2,m_0^2)\right]\frac{i}{p^2-m_0^2+i\epsilon}+\cdots\\
&=\frac{i}{p^2-m_0^2-\Pi(p^2,m_0^2)+i\epsilon}.
\end{aligned}
$$
This provides a correction to the bare mass.

Doing a perturbation expansion to the first order, one can write
$$
\begin{aligned}
\Pi(p^2,m_0^2)&=\lambda_0\Pi^{(1)}+\lambda_0^2\Pi^{(2)}+\cdots\\
&=\frac{1}{2}(-i\lambda_0)\int\frac{\mathrm{d}^4k}{(2\pi)^4}\frac{i}{k^2-m_0^2+i\epsilon}+O(\lambda_0^2).
\end{aligned}
$$
After Wick rotation and doing a momentum cut-off at $k_E^2=\Lambda^2$,
