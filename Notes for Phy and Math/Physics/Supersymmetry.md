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

### 2.6 R action

>[!warning]
>To be finished.

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

Under $y,\theta,\bar\theta$, one can write
$$
\begin{aligned}
D_\alpha&=\frac{\partial}{\partial\theta^\alpha}+2i(\sigma^\mu)_{\alpha\dot\beta}\bar\theta^{\dot\beta}\frac{\partial}{\partial y^\mu},\\
\bar{D}_\dot\alpha&=-\frac{\partial}{\partial\bar\theta^\dot\alpha}.
\end{aligned}
$$

### 3.2 Lagrangian
The most general Lagrangian constructed from chiral superfield is given by combination of components that are invariant (up to a total space-time derivative) under supersymmetry transformation
$$
\mathcal{L}\doteq\left.\Phi^\dagger_i\Phi_i\right|_{\theta\theta\bar\theta\bar\theta}+\left[\left.\left(\frac{1}{2}m_{ij}\Phi_i\Phi_j+\frac{1}{3}g_{ijk}\Phi_i\Phi_j\Phi_k+\lambda_i\Phi_i\right)\right|_{\theta\theta}+(\text{Herm. conj.})\right],
$$
where the vertical line $\Phi|_{\theta\theta}$ means to take only $(\theta\theta)$ component and so on. The coupling constants $m_{ij}$ and $g_{ijk}$ are symmetric in indices.

In terms of component field, it is written as
$$
\begin{aligned}
\mathcal{L}=&~i(\partial_\mu\bar\psi_i\bar\sigma^\mu\psi_i)+A^\ast_i\square A_i+F^\ast_iF_i\\
&+\left[m_{ij}\left(A_iF_j-\frac{1}{2}(\psi_i\psi_j)\right)+g_{ijk}(A_iA_jF_k-(\psi_i\psi_j)A_k)+\lambda_iF_i+(\text{Herm. conj.})\right].
\end{aligned}
$$

### 3.3 Auxiliary field
In this Lagrangian, $F_i$ are auxiliary fields while $A_i$ and $\psi_i$ are dynamic fields. The auxiliary fields can be eliminated by field equation
$$
\begin{aligned}
F_i+\lambda^\ast_i+m^\ast_{ij}A^\ast_j+g^\ast_{ijk}A^\ast_jA^\ast_k&=0,\\
F^\ast_i+\lambda_i+m_{ij}A_j+g_{ijk}A_jA_k&=0.
\end{aligned}
$$
This gives the Lagrangian in terms of only dynamic fields
$$
\begin{aligned}
\mathcal{L}=&~i(\partial_\mu\bar\psi_i\bar\sigma^\mu\psi_i)+A^\ast_i\square A_i-\frac{1}{2}m_{ij}(\psi_i\psi_j)-\frac{1}{2}m^\ast_{ij}(\bar\psi_i\bar\psi_j)\\
&-g_{ijk}(\psi_i\psi_j)A_k-g^\ast_{ijk}(\bar\psi_i\bar\psi_j)A^\ast_k-\mathcal{V}(A,A^\ast),
\end{aligned}
$$
where the potential is given by $\mathcal{V}=F^\ast_iF_i$. This is a nonnegative potential.

### 3.4 Field shift
Note that constant $\Phi=a$ is also a chiral superfield. Therefore, one can make a shift $\Phi_i\to\Phi_i+a_i$ to obtain another valid Lagrangian with coefficients
$$
\begin{aligned}
\lambda_i&\mapsto\lambda_i+m_{ij}a_j+g_{ijk}a_ja_k\\
m_{ij}&\mapsto m_{ij}+2g_{ijk}a_k\\
g_{ijk}&\mapsto g_{ijk}.
\end{aligned}
$$

## 4 Vector superfield
### 4.1 General form
A vector superfield satisfies $V=V^\dagger$. The most general form is given by
$$
\begin{aligned}
V=&~C(x)+i\theta\chi(x)-i\bar\theta\bar\chi(x)+\frac{i}{2}(\theta\theta)(M(x)+iN(x))-\frac{i}{2}(\bar\theta\bar\theta)(M(x)-iN(x))-(\theta\sigma^\mu\bar\theta)v_\mu(x)\\
&+i(\theta\theta)\bar\theta_\dot\alpha\left[\bar\lambda^\dot\alpha(x)+\frac{i}{2}(\bar\sigma^\mu)^{\dot\alpha\beta}\partial_\mu\chi_\beta(x)\right]-i(\bar\theta\bar\theta)\theta^\alpha\left[\lambda_\alpha(x)+\frac{i}{2}(\sigma^\mu)_{\alpha\dot\beta}\partial_\mu\bar\chi^\dot\beta(x)\right]\\
&+\frac{1}{2}(\theta\theta)(\bar\theta\bar\theta)\left[D(x)+\frac{1}{2}\square C(x)\right],
\end{aligned}
$$
where the component fields $(C,D,M,N,v_\mu)$ are all real fields.

The vector component field $v_\mu$ at $(\theta\sigma^\mu\bar\theta)$ kinds of "represents" the entire vector superfield.

### 4.2 Gauge transformation
For a chiral superfield $\Phi$, the combination $\Phi+\Phi^\dagger$ is also Hermitian. It's component at $(\theta\sigma^\mu\bar\theta)$ is $i\partial_\mu(A-A^\ast)$, which motivates one to define the gauge transformation
$$
V\mapsto V+\Phi+\Phi^\dagger.
$$
Under this gauge transformation, the component fields transform as
$$
\begin{aligned}
C&\mapsto C+A+A^\ast\\
\chi&\mapsto\chi-i\sqrt2\psi\\
M+iN&\mapsto M+iN-2iF\\
v_\mu&\mapsto v_\mu-i\partial_\mu(A-A\ast)\\
\lambda&\mapsto\lambda\\
D&\mapsto D.
\end{aligned}
$$

### 4.3 Wess-Zumino gauge
One can choose a special gauge where $C,\chi,M,N$ all vanish. This is called the *Wess-Zumino (WZ) gauge*. Under this gauge supersymmetry is broken, but the gauge symmetry $v_\mu\mapsto v_\mu+\partial_\mu a$ remains. The superfield under this gauge is given by
$$
\begin{aligned}
V&=-(\theta\sigma^\mu\bar\theta)v_\mu(x)+i(\theta\theta)\bar\theta\bar\lambda(x)-i(\bar\theta\bar\theta)\theta\lambda(x)+\frac{1}{2}(\theta\theta)(\bar\theta\bar\theta)D(x)\\
V^2&=-\frac{1}{2}(\theta\theta)(\bar\theta\bar\theta)v_\mu v^\mu\\
V^3&=0.
\end{aligned}
$$
This can be viewed as a supersymmetric generalization of Yang-Mills potential.

### 4.4 Field strength
The *supersymmetric field strength* is given by
$$
\begin{aligned}
W_\alpha&=-\frac{1}{4}\bar{D}\bar{D}D_\alpha V\\
\bar{W}_\dot\alpha&=-\frac{1}{4}DD\bar{D}_\dot\alpha V.
\end{aligned}
$$
One can prove that $W_\alpha$ is a chiral superfield $\bar{D}_\dot\beta W_\alpha=0$ with additional constraint
$$
D^\alpha W_\alpha=\bar{D}_\dot\alpha W^\dot\alpha.
$$
They are also gauge invariant since $\bar{D}\Phi=0$.

One can write the field strength under component field
$$
W_\alpha=-i\lambda_\alpha(y)+\left[\delta_\alpha{}^\beta D(y)-\frac{i}{2}(\sigma^\mu\bar\sigma^\nu)_\alpha{}^\beta(\partial_\mu v_\nu-\partial_\nu v_\mu)\right]\theta_\beta+(\theta\theta)(\sigma^\mu)_{\alpha\dot\beta}\partial_\mu\bar\lambda^\dot\beta(y).
$$
It contains only gauge invariant fields $D,\lambda_\alpha$ and $v_{\mu\nu}\doteq\partial_{[\mu}v_{\nu]}$.

### 4.5 Lagrangian
One can prove that the $(\theta\theta)$ component of $W^\alpha W_\alpha$ is invariant up to a total derivative under supersymmetry transformation. Therefore, a possible Lagrangian is given by
$$
\mathcal{L}\doteq\frac{1}{4}\left(\left.W^\alpha W_\alpha\right|_{\theta\theta}+\left.\bar{W}_\dot\alpha\bar{W}^\dot\alpha\right|_{\bar\theta\bar\theta}\right).
$$
Equivalent way to write the Lagrangian is
$$
\begin{aligned}
\int\mathrm{d}^4x\mathcal{L}&=\int\mathrm{d}^4x\left[\frac{1}{2}D^2-\frac{1}{4}v^{\mu\nu}v_{\mu\nu}-i(\lambda\sigma^\mu\partial_\mu\bar\lambda)\right]\\
&=\int\mathrm{d}^4x\left.\frac{1}{4}\left(W^\alpha D_\alpha V+\bar{W}_\dot\alpha\bar{D}^\dot\alpha V\right)\right|_{\theta\theta\bar\theta\bar\theta}.
\end{aligned}
$$

If add mass term $m^2V^2$ to Lagrangian, it is no longer gauge invariant and cannot be computed under WZ gauge.

## 5 Gauge invariant interaction
### 5.1 Global $\mathrm{U}(1)$ transformation
A global $\mathrm{U}(1)$ transformation of a chiral superfield is given by
$$
\Phi_l\mapsto e^{-it_l\lambda}\Phi_l,
$$
where $t_l$ is the $\mathrm{U}(1)$ charge of $\Phi_l$ and $\lambda$ is the angle. They are all real constants, which means they are also chiral superfield.

A Lagrangian invariant under this gauge can be constructed as
$$
\mathcal{L}\doteq\left.\Phi^\dagger_l\Phi_l\right|_{\theta\theta\bar\theta\bar\theta}+\left[\left.\left(\frac{1}{2}m_{ij}\Phi_i\Phi_j+\frac{1}{3}g_{ijk}\Phi_i\Phi_j\Phi_k\right)\right|_{\theta\theta}+(\text{Herm. conj.})\right].
$$
Here $m_{ij}=0$ if $t_i+t_j\ne0$ and $g_{ijk}=0$ if $t_i+t_j+t_k\ne0$. The latter term is also called *superpotential*.

### 5.2 Local $\mathrm{U}(1)$ transformation
A local $\mathrm{U}(1)$ transformation of a chiral superfield is defined as
$$
\begin{aligned}
\Phi_l&\mapsto e^{-it_l\Lambda}\Phi_l,&\bar{D}_\dot\alpha\Lambda&=0;\\
\Phi^\dagger_l&\mapsto e^{it_l\Lambda^\dagger}\Phi^\dagger_l,&D_\alpha\Lambda^\dagger&=0,
\end{aligned}
$$
where $\Lambda$ is a chiral superfield depending on $x$.

To maintain the gauge invariance of Lagrangian, one introduce a vector superfield with the following gauge transformation
$$
V\mapsto V+i(\Lambda-\Lambda^\dagger).
$$
Then the Lagrangian is given by
$$
\begin{aligned}
\mathcal{L}\doteq&~\frac{1}{4}\left(\left.W^\alpha W_\alpha\right|_{\theta\theta}+\left.\bar{W}_\dot\alpha\bar{W}^\dot\alpha\right|_{\bar\theta\bar\theta}\right)+\left.\Phi^\dagger_le^{t_lV}\Phi_l\right|_{\theta\theta\bar\theta\bar\theta}\\
&+\left[\left.\left(\frac{1}{2}m_{ij}\Phi_i\Phi_j+\frac{1}{3}g_{ijk}\Phi_i\Phi_j\Phi_k\right)\right|_{\theta\theta}+(\text{Herm. conj.})\right].
\end{aligned}
$$
One can check that the Lagrangian is renormalizable by expanding the interaction term under WZ gauge.

### 5.3 Non-Abelian case for chiral superfield
A generalization to non-abelian case is given by
$$
\Phi\mapsto e^{-i\Lambda}\Phi,\quad\Phi^\dagger\mapsto\Phi^\dagger e^{i\Lambda^\dagger},
$$
where $\Lambda$ is a matrix. One can expand it as
$$
\Lambda=\Lambda_aT^a,
$$
where $T^a$ are (representation of) Hermitian generators of the gauge group and $\Lambda_a$ are coefficients. It is normalized to $\mathrm{Tr}(T^aT^b)=k\delta^{ab}$.

### 5.4 Non-Abelian gauge field
The corresponding gauge transformation of vector superfields $V_{ij}$ is given by
$$
e^V\mapsto e^{-i\Lambda^\dagger}e^Ve^{i\Lambda}.
$$
Here $V$ can also be expanded under $T^a$. Using Hausdorff's formula, one can expand the infinitesimal gauge transformation as
$$
V\mapsto V+i\rm{ad}_{V/2}\left[(\Lambda+\Lambda^\dagger)+\coth\rm{ad}_{V/2}(\Lambda-\Lambda^\dagger)\right]+\cdots,
$$
where $\mathrm{ad}_A$ means [[../Mathematics/Lie algebra and Lie group#3.4 Adjoint action|adjoint action]] $[A,\cdot]$.

The supersymmetric field strength can be defined as
$$
W_\alpha\doteq-\frac{1}{4}\bar{D}\bar{D}e^{-V}D_{\alpha}e^V.
$$
The gauge transformation for it is
$$
W_\alpha\mapsto e^{-i\Lambda^\dagger}W_\alpha e^{i\Lambda}.
$$

### 5.5 Lagrangian for non-abelian gauge
The gauge invariant Lagrangian is given by
$$
\begin{aligned}
\mathcal{L}\doteq&~\frac{1}{16kg^2}\mathrm{Tr}\left(\left.W^\alpha W_\alpha\right|_{\theta\theta}+\left.\bar{W}_\dot\alpha\bar{W}^\dot\alpha\right|_{\bar\theta\bar\theta}\right)+\left.\Phi^\dagger e^V\Phi\right|_{\theta\theta\bar\theta\bar\theta}\\
&+\left[\left.\left(\frac{1}{2}m_{ij}\Phi_i\Phi_j+\frac{1}{3}g_{ijk}\Phi_i\Phi_j\Phi_k\right)\right|_{\theta\theta}+(\text{Herm. conj.})\right].
\end{aligned}
$$
Here, gauge invariance requires that $m_{ij}$ and $g_{ijk}$ to be total symmetric and invariant under gauge group.