---
banner: "![[df0454b50ed54c5c9566a8a361a6f3ab1661704153601.jpeg]]"
banner_y: 0.352
---

>[!abstract]- Pre-knowledge
>- [[Linear algebra]]

>[!note]
>This is a simpler version of differential geometry. This is mainly written for [[Electrodynamics]].

# Vector analysis
## 1 Vector algebra
The *vectors* here are vectors in $\mathbb{R}^3$. Under the standard basis of Cartesian coordinates, a vector can be written as
$$
\pmb{v}=(v_x,v_y,v_z).
$$
The vector adds and substracts as the way described in [[Linear algebra]].

The *dot product* of two vectors is an inner product defined as
$$
\pmb{v}\cdot\pmb{u}\doteq v_xu_x+v_yu_y+v_zu_z.
$$
Using the notation of Einstein summation, this can be written as
$$
\pmb{v}\cdot\pmb{u}=v^au^bg_{ab}.
$$

The *cross product* of two vectors is a non-assiciative multiplication of vectors defined as
$$
\begin{aligned}
\pmb{v}\times\pmb{u}&=\begin{vmatrix}
\pmb{i} & \pmb{j} & \pmb{k}\\
v_x & v_y & v_z\\
u_x & u_y & u_z
\end{vmatrix}\\
&=v^au^b\epsilon_{abc}\pmb{e}^c.
\end{aligned}
$$
Note that the cross product of two vectors is actually a [[Linear algebra#5.1 Dual space|dual vector]].

The Levi-Civita symbol $\epsilon_{abc}$ has the following properties
$$
\begin{aligned}
\epsilon_{abc}\epsilon_{def}&=\begin{vmatrix}
\delta_{ad} & \delta_{ae} & \delta_{af}\\
\delta_{bd} & \delta_{be} & \delta_{bf}\\
\delta_{cd} & \delta_{ce} & \delta_{cf}
\end{vmatrix},\\
\epsilon_{abc}\epsilon^{aef}&=\delta_b^e\delta_c^f-\delta_b^f\delta_c^e,\\
\epsilon_{abc}\epsilon^{abf}&=2\delta_c^f.
\end{aligned}
$$
From these one can derive the operational rules of cross product and dot product.

## 2 Differential
The differential operator of a vector is written as
$$
\nabla\doteq \pmb{i}\frac{\partial}{\partial x}+\pmb{j}\frac{\partial}{\partial y}+\pmb{k}\frac{\partial}{\partial z}
$$
in the Cartesian coordinates.

When applying $\nabla$ on a scalar field $f$, it is called the *gradient* of $f$, defined as
$$
\mathrm{grad}\ f\doteq\nabla f=\frac{\partial f}{\partial x}\pmb{i}+\frac{\partial f}{\partial y}\pmb{j}+\frac{\partial f}{\partial z}\pmb{k}.
$$
It is the directional partial derivative of $f$ on the direction where $f$ grows fastest.

There are two ways to act $\nabla$ on a vector field $\pmb{v}$. The first way is in the form of dot product, called the *divergence* of $\pmb{v}$, defined as
$$
\mathrm{div}\ \pmb{v}\doteq\nabla\cdot\pmb{v}=\frac{\partial v_x}{\partial x}+\frac{\partial v_y}{\partial y}+\frac{\partial v_z}{\partial z}.
$$
It reflects the tendency of convergent or divergent of $\pmb{v}$.

The second way is in the form of cross product, called the *curl* of $\pmb{v}$, defined as
$$
\mathrm{rot}\ \pmb{v}\doteq\nabla\times\pmb{v}=\begin{vmatrix}
\pmb{i} & \pmb{j} & \pmb{k}\\
\partial_x & \partial_y & \partial_z\\
v_x & v_y & v_z
\end{vmatrix}.
$$
It shows the tendency of rotating of $\pmb{v}$ and points at the direction along which $\pmb{v}$ rotates counter-clockwisely.

## 3 Rules of differential
For derivative of products, there are the following rules.
$$
\begin{aligned}
\nabla(fg)&=f\nabla g+g\nabla f,\\
\nabla(\pmb{v}\cdot\pmb{u})&=\pmb{v}\times(\nabla\times\pmb{u})+\pmb{u}\times(\nabla\times\pmb{v})+(\pmb{v}\cdot\nabla)\pmb{u}+(\pmb{u}\cdot\nabla)\pmb{v},\\
\nabla\cdot(f\pmb{v})&=f(\nabla\cdot\pmb{v})+\pmb{v}\cdot(\nabla f),\\
\nabla\cdot(\pmb{v}\times\pmb{u})&=\pmb{u}\cdot(\nabla\times\pmb{v})-\pmb{v}\cdot(\nabla\times\pmb{u}),\\
\nabla\times(f\pmb{v})&=f(\nabla\times\pmb{v})-\pmb{v}\times(\nabla f),\\
\nabla\times(\pmb{v}\times\pmb{u})&=(\pmb{u}\cdot\nabla)\pmb{v}-(\pmb{v}\cdot\nabla)\pmb{u}+\pmb{v}(\nabla\cdot\pmb{u})-\pmb{u}(\nabla\cdot\pmb{v}).
\end{aligned}
$$

For second derivative, define the *Laplace operator* as
$$
\Delta\doteq\nabla^2=\frac{\partial^2}{\partial x^2}+\frac{\partial^2}{\partial y^2}+\frac{\partial^2}{\partial z^2}.
$$
It acts on a scalar field as the divergence of gradient, and acts on a vector field as the gradient of divergence.

Apart from Laplace operator, there are some other second derivatives as follow.
$$
\begin{aligned}
\nabla\times(\nabla f)&=\pmb{0},\\
\nabla\cdot(\nabla\times\pmb{v})&=0,\\
\nabla\times(\nabla\times\pmb{v})&=\nabla(\nabla\cdot\pmb{v})-\Delta\pmb{v}.
\end{aligned}
$$
Note that $\nabla(\nabla\cdot\pmb{v})\ne\Delta\pmb{v}$.

## 4 Integration
The integration of gradient on a curved path is given by
$$
\int_a^b\mathrm{d}\pmb{l}\cdot\nabla f=f(b)-f(a).
$$
This does not depends on the path of integration.

The integration of divergence in a volumn $V$ is given by
$$
\int_V\mathrm{d}\tau(\nabla\cdot\pmb{v})=\oint_S\mathrm{d}\pmb{s}\cdot\pmb{v}.
$$
Here $S$ is the boundary of $V$. This is called the *Gauss theorem*.

The integration of curl on a surface $\Sigma$ is given by
$$
\int_\Sigma\mathrm{d}\pmb{s}\cdot(\nabla\times\pmb{v})=\oint_L\mathrm{d}\pmb{l}\cdot\pmb{v}.
$$
Here $L$ is the boundary of $\Sigma$, and the integration is on the counter-clockwise direction according to the direction of surface. This is called the *Stokes theorem*.

## 5 Arbitrary coordinate
### 5.1 General formalism
Consider an arbitrary orthogonal coordinate system where an infinitesimal displacement can be written as
$$
\mathrm{d}\pmb{l}=g_a\mathrm{d}x^a\pmb{e}_a.
$$
The index of $g_a$ is not counted as proper index when doing Einstein summation. Some examples of $g_a$ are shown as follow.
| coordinate             | $x^1,x^2,x^3$   | $g_1,g_2,g_3$     |
| ---------------------- | --------------- | ----------------- |
| Cartesian coordinate   | $x,y,z$         | $1,1,1$           |
| Spherical coordinate   | $r,\theta,\phi$ | $1,r,r\sin\theta$ |
| Cylindrical coordinate | $\rho,\theta,z$ | $1,\rho,1$        |

### 5.2 Gradient
Write the differential of a scalar function $f$ as
$$
\mathrm{d}f=\frac{\partial f}{\partial x^a}\mathrm{d}x^a.
$$
The gradient satisfies
$$
\mathrm{d}f=\nabla f\cdot\mathrm{d}\pmb{l}.
$$
Since the coordinate is orthogonal, the gradient is then
$$
\nabla f=\frac{1}{g_a}\frac{\partial f}{\partial x^a}\pmb{e}^a.
$$

### 5.3 Divergence
An infinitesimal volume can be written as
$$
\mathrm{d}\tau=g_1g_2g_3\mathrm{d}x^1\mathrm{d}x^2\mathrm{d}x^3.
$$
Each surface of it is then
$$
\mathrm{d}\pmb{s}_a=\pmb{e}_a\sum_{b\ne a}g_b\mathrm{d}x^b.
$$
The flux of $\pmb{v}$ on the surface is
$$
\pmb{v}\cdot\mathrm{d}\pmb{s}_a=v^a\sum_{b\ne a}g_b\mathrm{d}x^b.
$$
The divergence satisfies
$$
\nabla\cdot\pmb{v}\ \mathrm{d}\tau=\sum_a\frac{\partial}{\partial x^a}(\pmb{v}\cdot\mathrm{d}\pmb{s}_a)\mathrm{d}x^a.
$$
So the divergence is then
$$
\nabla\cdot\pmb{v}=\frac{1}{g_1g_2g_3}\frac{\partial}{\partial x^a}\left(g_1g_2g_3\frac{v^a}{g_a}\right).
$$

### 5.4 Curl
Consider an infinitesimal surface. The integration of $\pmb{v}$ on one edge of it is
$$
\pmb{v}\cdot\mathrm{d}\pmb{l}_b=v^bg_b\mathrm{d}x^b,
$$
where the index $b$ is not summed over. The curl satisfies
$$
(\nabla\times\pmb{v})\cdot\mathrm{d}\pmb{s}_a=\frac{\partial}{\partial x^b}(\pmb{v}\cdot\mathrm{d}\pmb{l}_c)\mathrm{d}x^b\epsilon_{abc}
$$

The differential operators are given as follow.
$$
\begin{aligned}
\nabla f&=\frac{1}{g_a}\frac{\partial f}{\partial x^a}\pmb{e}^a;\\
\nabla\cdot\pmb{v}&=\frac{1}{g_1g_2g_3}\left[\frac{\partial}{\partial x^1}(g_2g_3v^1)+\frac{\partial}{\partial x^2}(g_1g_3v^2)+\frac{\partial}{\partial x^3}(g_1g_2v^3)\right];\\
\nabla\times\pmb{v}&=\begin{vmatrix}
g_1\pmb{e}_1 & g_2\pmb{e}_2 & g_3\pmb{e}_3\\
\partial_1 & \partial_2 & \partial_3\\
g_1v_1 & g_2v_2 & g_3v_3
\end{vmatrix}/(g_1g_2g_3);\\
\Delta f&=\frac{1}{g_1g_2g_3}\left[\frac{\partial}{\partial x^1}\left(\frac{g_2g_3}{g_1}\frac{\partial f}{\partial x^1}\right)+\frac{\partial}{\partial x^2}\left(\frac{g_1g_3}{g_2}\frac{\partial f}{\partial x^2}\right)+\frac{\partial}{\partial x^3}\left(\frac{g_1g_2}{g_3}\frac{\partial f}{\partial x^3}\right)\right].
\end{aligned}
$$

## 6 Vector field
### 6.1 Helmholtz theorem
A vector field with given divergence and curl
$$
\left\{
\begin{aligned}
&\nabla\cdot\pmb{F}=\pmb{D}\\
&\nabla\times\pmb{F}=\pmb{C}
\end{aligned}
\right.
$$
is uniquely determined if it goes to $0$ at infinity. This is called the *Helmholtz theorem*.

### 6.2 Potential
A vector field with zero curl can be written as the gradient of a scalar field
$$
\pmb{F}=-\nabla V\quad\Leftrightarrow\quad\nabla\times\pmb{F}=\pmb{0}.
$$
This scalar field $V$ is called the *scalar potential* of $\pmb{F}$. It is determined up to an arbitrary constant.

A vector field with zero divergence can be written as the curl of a vector field
$$
\pmb{F}=\nabla\times\pmb{A}\quad\Leftrightarrow\quad\nabla\cdot\pmb{F}=0.
$$
This vector field $\pmb{A}$ is called the *vector potential* of $\pmb{F}$. It is determined up to a vector field with zero curl, or a gradient field.

## 7 Important results
Some important differential results are listed here. Denote $r=|\pmb{r}^2|$.
$$
\begin{aligned}
\nabla r^2&=2\pmb{r},\\
\nabla\frac{1}{r}&=-\frac{\pmb{r}}{r^3},\\
\nabla\cdot\frac{\pmb{r}}{r^3}&=4\pi\delta^{(3)}(\pmb{r});
\end{aligned}
$$