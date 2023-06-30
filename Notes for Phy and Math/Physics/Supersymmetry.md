---
banner: "![[pics/16954eb1021274b16f71614046f8d88f1662693445927.jpeg]]"
banner_y: 0.308
---

>[!abstract]- Pre-knowledge
>- [[Physics/Supersymmetry algebra|Supersymmetry algebra]]
>- [[Representation of Lorentz algebra]]
>- [[Physics/Grassmann variables|Grassmann variables]]
>- [[../Mathematics/Lie algebra and Lie group|Lie algebra and Lie group]]
>- [[Physics/Quantum field theory|Quantum field theory]]

# Supersymmetry
## 1 Component field

>[!warning]
>For now only $N=1$ case is concerned.

### 1.1 SUSY transformation
Note that the generators $Q$ and $\bar{Q}$ of [[Supersymmetry algebra#2 Supersymmetry algebra|supersymmetry algebra]] satisfies anticommutation relations. If including [[Grassmann variables|Grassmann variables]] by including [[Representation of Lorentz algebra#2.4 Dotted-undotted notation|Weyl spinor]]s $\theta_\alpha$, one can turn anticommutators into commutators
$$
\begin{aligned}[]
[(\theta Q),(\bar\theta\bar{Q})]&=2(\theta\sigma^\mu\bar\theta)P_\mu,\\
[(\theta Q),(\theta Q)]&=[(\bar\theta\bar{Q}),(\bar\theta\bar{Q})]=0,\\
[P_\mu,(\theta Q)]&=[P_\mu,(\bar\theta\bar{Q})]=0.
\end{aligned}
$$

In this way, it forms a [[../Mathematics/Lie algebra and Lie group#2 Lie algebra|Lie algebra]], which can generate a [[../Mathematics/Lie algebra and Lie group#3 Lie algebra of Lie group|Lie group]] by exponential map
$$
G(x^\mu,\theta,\bar\theta)\doteq\exp i\left[-x^\mu P_\mu+(\theta Q)+(\bar\theta\bar{Q})\right].
$$

### 1.2 Component field
A *component multiplet* is a set of field $(A,\cdots)$ that transforms under infinitesimal transformstion $G(0,\xi,\bar\xi)$ when $\xi\to0$ as
$$
\delta_\xi A\doteq\left[(\xi Q)+(\bar\xi\bar{Q})\right]A.
$$
By working on commutator $[\delta_\xi,\delta_\eta]$ and dimensional analysis, the possible component fields are $A,\psi,F$. The infinitesimal transformations are
$$
\begin{aligned}
&\delta_\xi A=\sqrt{2}\xi\psi,\\
&\delta_\xi\psi=i\sqrt{2}\sigma^\mu\bar{\xi}\partial_\mu A+\sqrt{2}\xi F,\\
&\delta_\xi F=i\sqrt{2}\bar{\xi}\bar{\sigma}^\mu\partial_\mu\psi.
\end{aligned}
$$

Among these component fields, $A$ and $F$ are scalars, while $\psi$ is spinor, which means it's value is Grassmann variable.

### 1.3 Lagrangian and field equation
Possible ways to construct supersymmetry invariant Lagrangians are
$$
\begin{aligned}
\mathcal{L}_0&\doteq i\partial_\mu\bar\psi\bar\sigma^\mu\psi+A^\ast\square A+F^\ast F,\\
\mathcal{L}_m&\doteq AF+A^\ast F^\ast-\frac{1}{2}(\psi\psi)+\frac{1}{2}(\bar\psi\bar\psi).
\end{aligned}
$$
The complete Lagrangian is then $\mathcal{L}\doteq\mathcal{L}_0+m\mathcal{L}_m$. The corresponding field equations are
$$
\begin{aligned}
i\bar\sigma^\mu\partial_\mu\psi+m\bar\psi&=0,\\
F+mA^\ast&=0,\\
\square A+mF^\ast&=0.
\end{aligned}
$$

Note that the Lagrangian is invariant under normal ordering $\mathcal{L}=:\mathcal{L}:$, which is the consiquence of the fact that there are equal number of fermionic and bosonic states in supersymmetry at given mass.

## 2 Superfield
### 2.1 Superspace
An element in the *super space* is labeled as $z=(x^\mu,\theta,\bar\theta)$. One can consider this a Lie group element. A group multiplication $G(0,\xi,\bar\xi)G(x^\mu,\theta,\bar\theta)$ actually induces a map
$$
g(\xi,\bar\xi):(x^\mu,\theta,\bar\theta)\mapsto\left(x^\mu+i(\theta\sigma^\mu\bar\xi)-i(\xi\sigma^\mu\bar\theta),\theta+\xi,\bar\theta+\bar\xi\right).
$$
The corresponding infinitesimal generator is given by
$$
\xi Q+\bar\xi\bar{Q}\doteq\xi^\alpha\left(\frac{\partial}{\partial\theta^\alpha}-i(\sigma^\mu)_{\alpha\dot\beta}\bar\theta^{\dot\beta}\partial_\mu\right)+\bar\xi_{\dot\alpha}\left(-\frac{\partial}{\partial\bar\theta_{\dot\alpha}}+i\theta^\gamma(\sigma^\mu)_{\gamma\dot\beta}\epsilon^{\dot\beta\dot\alpha}\partial_\mu\right).
$$
Their anticommutator, however, gives $\{Q_\alpha,\bar{Q}_\dot\beta\}=2i(\sigma^\mu)_{\alpha\dot\beta}\partial_\mu$, which is inconsistent with $P_\mu\to-i\partial_\mu$. This is due to the difference between left and right group action.

### 2.2 Differential operators
To get the differential operator representation of $Q$ and $\bar{Q}$ that satisfy proper anticommutation relation, one define
$$
\begin{aligned}
D_\alpha&\doteq\frac{\partial}{\partial\theta^\alpha}+i(\sigma^\mu)_{\alpha\dot\beta}\bar\theta^{\dot\beta}\partial_\mu,\\
\bar{D}_{\dot\beta}&\doteq-\frac{\partial}{\partial\bar\theta^{\dot\alpha}}-i\theta^\alpha(\bar\sigma^\mu)_{\alpha\dot\beta}\partial_\mu.
\end{aligned}
$$
They satisfy the anticommutation relation
$$
\begin{aligned}
\{D_\alpha,\bar{D}_{\dot\beta}\}&=-2i(\sigma^\mu)_{\alpha\dot\beta}\partial_\mu,\\
\{D_\alpha,D_\beta\}&=\{\bar{D}_{\dot\alpha},\bar{D}_{\dot\beta}\}=0.
\end{aligned}
$$
Also note that $D$ and $Q$ anticommute.

### 2.3 Superfield
A *superfield* is a field over the super space. One can write the series expansion
$$
\begin{aligned}
F(x,\theta,\bar\theta)=&~f(x)+\theta\phi(x)+\bar\theta\bar\chi(x)\\
&+(\theta\theta)m(x)+(\bar\theta\bar\theta)n(x)+(\theta\sigma^\mu\bar\theta)v_\mu(x)\\
&+(\theta\theta)\bar\theta\bar\lambda(x)+(\bar\theta\bar\theta)\theta\psi(x)+(\theta\theta)(\bar\theta\bar\theta)d(x).
\end{aligned}
$$
The coefficients $f,\phi,\bar\chi,\cdots$ are all component fields.

The infinitesimal transformation of a superfield is given by the infinitesimal transformations on each component field, or defined by
$$
\delta_\xi F(x,\theta,\bar\theta)\doteq(\xi Q+\bar\xi\bar{Q})F
$$
where $Q$ and $\bar{Q}$ are the differential operators defined above.

### 2.4 Chiral and vector superfield
The sum of superfields is also a superfield. Therefore, it forms a (usually reducible) representation of supersymmetry algebra. One can use constraints to find a subrepresentation.

A superfield $\Phi$ that satisfies $\bar{D}\Phi=0$ is called a *chiral superfield* or *scalar superfield*. One can put further constraints as
- $DD\Phi=\bar{D}\Phi=0$ gives massless field equation;
- $D\Phi=\bar{D}\Phi=0$ gives constant field.

A superfield $V$ that satisfies $V=V^\dagger$ is called a *vector superfield*.

The product of superfields is also a superfield of the same type.

### 2.5 Construct superfield
To construct a superfield from a component field (for example $A$), one simply apply
$$
\begin{aligned}
F(x^\mu,\theta,\bar\theta)&\doteq\exp\left[(\theta Q)+(\bar\theta\bar{Q})\right]A\\
&=A+\delta_\theta A+\cdots.
\end{aligned}
$$
One can check that the transformation of such a field is
$$
\delta_\xi F(x^\mu,\theta,\bar\theta)=\left[(\xi Q)+(\bar\xi\bar{Q})\right]F.
$$

## 3 Chiral superfield
### 3.1 General form
Chiral superfield satisfies the constraint
$$
\bar{D}_{\dot\alpha}\Phi=0.
$$
Using the fact that
$$
\bar{D}_{\dot\alpha}\left[x^\mu+i(\theta\sigma^\mu\bar\theta)\right]=\bar{D}_{\dot\alpha}\theta=0,
$$
one can prove that (denoting $y^\mu\doteq x^\mu+i(\theta\sigma^\mu\bar\theta)$) the general form of a chiral superfield is
$$
\begin{aligned}
\Phi=&~A(y)+\sqrt{2}\theta\psi(y)+(\theta\theta)F(y)\\
=&~A(x)+i(\theta\sigma^\mu\bar\theta)\partial_\mu A(x)+\frac{1}{4}(\theta\theta)(\bar\theta\bar\theta)\square A\\
&+\sqrt2\theta\psi(x)-\frac{i}{\sqrt2}(\theta\theta)\left(\partial_\mu\psi(x)\sigma^\mu\bar\theta\right)+(\theta\theta)F(x).
\end{aligned}
$$
