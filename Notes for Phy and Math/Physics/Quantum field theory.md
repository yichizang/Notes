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

## 2 Path integral quantization
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

#### 2.1.2 Time ordering
Consider the time-ordering $\braket{\phi_f,t_f|T\phi(\pmb{x}_1,t_1)\phi(\pmb{x}_2,t_2)|\phi_i,t_i}$. It can be written as
$$
\begin{aligned}
\braket{\phi_f,t_f|T\hat{\phi}(\pmb{x}_1,t_1)\hat{\phi}(\pmb{x}_2,t_2)|\phi_i,t_i}&=\theta(t_1-t_2)\braket{\phi_f|\hat{\phi}_1\hat{\phi}_2|\phi_i}+\theta(t_2-t_1)\braket{\phi_f|\hat{\phi}_2\hat{\phi}_1|\phi_i}\\
&=\theta(t_1-t_2)\int\mathrm{d}\phi_1\mathrm{d}\phi_2~\phi_1\phi_2\braket{\phi_f|\phi_1}\braket{\phi_1|\phi_2}\braket{\phi_2|\phi_i}\\
&~~~~~+\theta(t_2-t_1)\int\mathrm{d}\phi_1\mathrm{d}\phi_2~\phi_2\phi_1\braket{\phi_f|\phi_2}\braket{\phi_2|\phi_1}\braket{\phi_1|\phi_i}.
\end{aligned}
$$
Then after inserting the rest of resolution of identity, one can write
$$
\braket{\phi_f,t_f|T\hat\phi(\pmb{x}_1,t_1)\hat\phi(\pmb{x}_2,t_2)|\phi_i,t_i}=\int[D\phi][D\pi]\phi_1\phi_2\exp\left\{i\int_{t_0}^{t_f}\mathrm{d}^4x\left[\pi\dot{\phi}-\mathcal{H}(\phi,\pi)\right]\right\}.
$$
This shows that the path integral will automatically give the time ordering.

#### 2.1.3 Green function
Now consider the Green function $\braket{\Omega|T\hat O_1\hat O_2\cdots|\Omega}$. It can be written as
$$
\begin{aligned}
\braket{O_1O_2\cdots}&=\int\mathrm{d}\phi_f\mathrm{d}\phi_i\braket{\Omega|\phi_f,+\infty}\Braket{\phi_f,+\infty|T\hat O_1\hat O_2\cdots|\phi_i,-\infty}\braket{\phi_i,-\infty|\Omega}\\
&=\int[D\phi][D\pi]\braket{\Omega|\phi_f,+\infty}\braket{\phi_i,-\infty|\Omega}\exp\left\{i\int\mathrm{d}^4x\left[\pi\dot{\phi}-\mathcal{H}(\phi,\pi)\right]\right\}O_1O_2\cdots.
\end{aligned}
$$

To work out the "wave function" $\braket{\phi,\pm\infty|\Omega}$, one assume that the interacting field becomes free field at $t=\pm\infty$. Therefore one can use the plane-wave expansion to calculate.

>[!note]- Process
>After applying the plane-wave expansion, one can obtain
>$$
>\int\mathrm{d}^3xe^{-i\pmb{p}\cdot\pmb{x}}\left[\frac{\delta}{\delta\phi}+\omega_p\phi(\pmb{x})\right]\braket{\phi,\pm\infty|\Omega}=0.
>$$
>Try the solution
>$$
>\braket{\phi,\pm\infty|\Omega}=N\exp\left[-\frac{1}{2}\int\mathrm{d}^3x\mathrm{d}^3yK(\pmb{x},\pmb{y})\phi(\pmb{x},\pm\infty)\phi(\pmb{y},\pm\infty)\right].
>$$
>One can solve
>$$
>K(\pmb{x},\pmb{y})=\int\frac{\mathrm{d}^3p}{(2\pi)^3}e^{-i\pmb{p}\cdot(\pmb{x}-\pmb{y})}\omega_p.
>$$
>After using the equation
>$$
>\lim_{\epsilon\to0^+}\epsilon\int_{-\infty}^{+\infty}\mathrm{d}t~f(t)e^{-\epsilon|t|}=f(+\infty)+f(-\infty)
>$$
>with some reasonable approximation, the result is given by
>$$
>\braket{\Omega|\phi,+\infty}\braket{\phi,-\infty|\Omega}=|N|^2\exp\left[-\frac{1}{2}\epsilon\int\mathrm{d}^4x\phi^2(x)\right].
>$$
>This means that there will be an $i\epsilon\phi^2$ attatched to the exponential. This is usually absorbed into $m^2\to m^2-i\epsilon$.

The Green function is then
$$
\braket{O_1O_2\cdots}=|N|^2\int[D\phi][D\pi]\exp\left\{i\int\mathrm{d}^4x\left[\pi\dot{\phi}-\mathcal{H}(\phi,\pi)\right]\right\}O_1O_2\cdots.
$$
This is usually normalized to $\braket{\Omega|\Omega}=1$. Therefore
$$
\braket{O_1O_2\cdots}=\frac{\displaystyle\int[D\phi][D\pi]\exp(\cdots)O_1O_2\cdots}{\displaystyle\int[D\phi][D\pi]\exp(\cdots)}.
$$

#### 2.1.4 Lagrangian path integral
The path integral can be written in the Lagrangian way if
- the Hamiltonian $\mathcal{H}$ is at most quadratic in $\pi$;
- the rest of operators are independent of $\pi$.

Using the [[../Mathematics/General Gaussian integral|Gaussian integral]] method, one can perform the intergal over $[D\pi]$ as
$$
\int[D\pi]\exp\left\{i\int\mathrm{d}^4x\left[\pi\dot{\phi}-\mathcal{H}(\phi,\pi)\right]\right\}=\left(\det\frac{A}{2\pi}\right)^{-1/2}\exp\left\{i\int\mathrm{d}^4x\left[\bar\pi\dot{\phi}-\mathcal{H}(\phi,\bar\pi)\right]\right\}.
$$
According to the equation of motion, the stationary point $\bar\pi(x)$ is given by
$$
\bar\pi(x)=\frac{\partial\mathcal{L}}{\partial\dot\phi(x)}.
$$
Therefore, the path-integral can be written as
$$
\int[D\phi]\left(\det\frac{A}{2\pi}\right)^{-1/2}\exp\left(i\int\mathrm{d}^4x\mathcal{L}\right)=\int[D\phi](\cdots)e^{-iS}.
$$
If $A$ is independent of $\phi$ (for example in Klein-Gorden theory $A=\delta^{(4)}(x-y)$), then the determinant can be pulled out of the integral.

#### 2.1.5 Modified time ordering
To calculate Green functions that include operators dependent of $\pi$ in Lagrangian formalism, one need to introduce the *modified time ordering* $T^\ast$ as
$$
\braket{\Omega|T^\ast\partial_0\phi\cdots|\Omega}=\partial_0\braket{\Omega|T\phi\cdots|\Omega}.
$$
This is related to the ordinary time ordering by some $\delta$ functions.

>[!example]
>The following Green function can be calculated
>$$
>\begin{aligned}
>\braket{\Omega|T\partial_\mu\phi(x)\partial_\nu\phi(y)|\Omega}&=\partial_\mu^x\partial_\nu^y\braket{\Omega|T^\ast\phi(x)\phi(y)|\Omega}-i\delta^0_\mu\delta^0_\nu\delta^{(4)}(x-y)\\
>&=\braket{\Omega|T^\ast\partial_\mu\phi(x)\partial_\nu\phi(y)|\Omega}-i\delta^0_\mu\delta^0_\nu\delta^{(4)}(x-y)\\
>&=|N|^2\int[D\phi]e^{iS}\partial_\mu\phi(x)\partial_\nu\phi(y)-i\delta^0_\mu\delta^0_\nu\delta^{(4)}(x-y).
>\end{aligned}
>$$

In the following, the modified time ordering is simply denoted as $T$.

### 2.2 Generating functional
#### 2.2.1 Generating functional
Define the generating functional as the path integral with an arbitrary external source
$$
Z_0[J]\doteq|N|^2\int[D\phi]\exp\left[i\int\mathrm{d}^4x(\mathcal{L}+J\phi)\right].
$$
The Green function can then be obtained by taking functional derivative of $J$ and then setting $J=0$
$$
\braket{\phi(x_1)\phi(x_2)\cdots}=\left.(-i)\frac{\delta}{\delta J(x_1)}(-i)\frac{\delta}{\delta J(x_2)}\cdots Z_0[J]\right|_{J=0}.
$$

>[!example]
>For free Klein-Gorden theory, the generating functional can be simplified using the Gaussian integral
>$$
>\begin{aligned}
>Z_0[J]&=|N|^2\int[D\phi]\exp\left\{i\int\mathrm{d}^4x\left[-\frac{1}{2}\phi(\partial^2+m^2)\phi+J\phi\right]\right\}\\
>&=\exp\left[-\frac{1}{2}\int\mathrm{d}^4x\mathrm{d}^4y~J(x)\Delta_F(x-y)J(y)\right],
>\end{aligned}
>$$
>where
>$$
>\Delta_F(x-y)=\int\frac{\mathrm{d}^4p}{(2\pi)^4}e^{-ip\cdot(x-y)}\frac{i}{p^2-m^2+i\epsilon}
>$$
>is the propagator of the field.

#### 2.2.2 Pertubation expansion
Consider a Lagrangian with interaction $\mathcal{L}=\mathcal{L}_0+\mathcal{L}_{\text{int}}$. Assume that the interaction is weak so that the path integral can be expanded as
$$
\int[D\phi]\exp\left(i\int\mathrm{d}^4x\mathcal{L}_0\right)\sum_n\frac{1}{n!}\int\mathrm{d}^4z_1\cdots\mathrm{d}^4z_n~\mathcal{L}_{\text{int}}(z_1)\cdots\mathcal{L}_{\text{int}}(z_n)\phi(x_1)\cdots,
$$
where every term is a Green function in free theory.

#### 2.2.3 Connected Green function
The *connected Green function* is defined by induction
$$
\begin{aligned}
G(x_1)&=G^c(x_1)\\
G(x_1,x_2)&=G^c(x_1,x_2)+G^c(x_1)G^c(x_2)\\
G(x_1,x_2,x_3)&=G^c(x_1,x_2,x_3)+G^c_{12}G^c_3+G^c_{13}G^c_2+G^c_{23}G^c_1+G^c_1G^c_2G^c_3\\
&\cdots
\end{aligned}
$$

The generating functional $iW[J]$ of connected Green function is given by
$$
Z[J]=e^{iW[J]}.
$$

>[!example]
>For free Klein-Golden theory, the generating functional is
>$$
>iW[J]=-\frac{1}{2}\int\mathrm{d}^4x\mathrm{d}^4yJ(x)\Delta_F(x-y)J(y).
>$$
>This implies that the only non-vanishing connected Green function for free scalar is 2-point function.

>[!note]
>Note that the terms in generating functional $Z[J]=e^{iW[J]}$ "remain" after a functional derivative, while the terms in $iW[J]$ are simply "consumed" after a functional derivative.
>
>One can view this difference as drawing cards with/without putting back, which leads to the difference between Green functions generated.

#### 2.2.4 One-particle irreducible diagram
To calculate the 1-PI diagrams, one define the *classical field*
$$
\phi_c\doteq\frac{\delta W}{\delta J}=\braket{\Omega|\hat\phi_J|\Omega}
$$
and the *effective action*
$$
\Gamma[\phi_c]\doteq W[J]-\int\mathrm{d}^4x~J\phi_c.
$$

One can prove that
$$
\begin{aligned}
\frac{\delta}{\delta J(x)}&=i\int\mathrm{d}^4y~\braket{\phi(x)\phi(y)}_{\text{conn}}^J~\frac{\delta}{\delta\phi_c(y)},\\
\braket{\phi(x)\phi(y)}_{\text{conn}}^J&=\left[\frac{\delta^2\Gamma[\phi_c]}{\delta\phi_c(x)\delta\phi_c(y)}\right]^{-1}.
\end{aligned}
$$
Taking functional derivative on the second identity gives
$$
\braket{xyz}_{\text{conn}}^J=i\int\mathrm{d}^4u\mathrm{d}^4v\mathrm{d}^4w\braket{xu}_{\text{conn}}^J\braket{yv}_{\text{conn}}^J\braket{zw}_{\text{conn}}^J\frac{\delta^3\Gamma[\phi_c]}{\delta\phi_c(u)\delta\phi_c(v)\delta\phi_c(w)},
$$
which means that
$$
\frac{\delta^3\Gamma[\phi_c]}{\delta\phi_c(u)\delta\phi_c(v)\delta\phi_c(w)}
$$
gives the 3-point 1-PI Green functions.

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
with the mass dimension $[\mu]=[\tilde{\mu}]=1$.

The integral can be performed as
$$
\begin{aligned}
\int\frac{\mathrm{d}^dk_E}{(2\pi)^d}&=\int\frac{\mathrm{d}\Omega^{(d)}}{(2\pi)^d}\int_0^{+\infty}\mathrm{d}(k_E^2)\frac{1}{2}(k_E^2)^{d/2-1}\\
&=\frac{1}{(4\pi)^{d/2}}\frac{1}{\Gamma(d/2)}\int_0^{+\infty}\mathrm{d}(k_E^2)(k_E^2)^{d/2-1}.
\end{aligned}
$$

>[!note]
>The divergent terms in dim reg and cut-off are related by
>$$
>\frac{1}{\epsilon}-\ln\frac{\Delta}{\mu^2}\leftrightarrow\ln\frac{\Lambda^2}{\Delta^2}.
>$$

### 3.2 Renormalization

>[!note] Claim
> In this section one take $\phi^4$ theory as an example model. The Lagrangian of the $\phi^4$ theory is given by
>$$
>\mathcal{L}=\frac{1}{2}(\partial^\mu\phi_0\partial_\mu\phi_0-m_0^2\phi_0^2)-\frac{\lambda_0}{4!}\phi_0^4,
>$$
>where the downscript $X_0$ means *bare terms* or terms without renormalization.

#### 3.2.1 Self energy correction
Consider the propogator of a $\phi^4$ particle
$$
\begin{aligned}
\int\mathrm{d}^4xe^{ip\cdot x}\braket{\Omega|T\phi_0(x)\phi_0(0)|\Omega}&=(\text{propogator})+(\text{pr})(\text{1PI})(\text{pr})+(\text{pr})(\text{1PI})(\text{pr})(\text{1PI})(\text{pr})+\cdots\\
&=\frac{i}{p^2-m_0^2+i\epsilon}+\frac{i}{p^2-m_0^2+i\epsilon}\left[-i\Pi(p^2,m_0^2)\right]\frac{i}{p^2-m_0^2+i\epsilon}+\cdots\\
&=\frac{i}{p^2-m_0^2-\Pi(p^2,m_0^2)+i\epsilon}.
\end{aligned}
$$
This provides a correction to the bare mass. The *physical mass* $m$ is defined as the pole of the renormalized propagator, that is
$$
\left[p^2-m_0^2-\Pi(p^2,m_0^2)\right]_{p^2=m^2}=0.
$$

Write the propagator near the pole as
$$
\frac{iZ_m}{p^2-m^2+i\epsilon}
$$
where $Z_m$ is a *renormalization factor* given by
$$
Z_m^{-1}=1-\left.\frac{\partial\Pi}{\partial p^2}\right|_{p^2=m^2}.
$$

#### 3.2.2 Correction to interaction


#### 3.2.3 Pertubation expansion
Doing a perturbation expansion to the first order, one can write
$$
\begin{aligned}
\Pi(p^2,m_0^2)&=\lambda_0\Pi^{(1)}+\lambda_0^2\Pi^{(2)}+\cdots\\
&=\frac{1}{2}(-i\lambda_0)\int\frac{\mathrm{d}^4k}{(2\pi)^4}\frac{i}{k^2-m_0^2+i\epsilon}+O(\lambda_0^2).
\end{aligned}
$$
After Wick rotation and doing a momentum cut-off at $k_E^2=\Lambda^2$,
