---
banner: "![[../pics/e89c13e28827073cc0d224fca09aa8011661042690083.png]]"
banner_y: 0.46
---

>[!abstract]- Pre-knowledge
>- Mathematical analysis

# Complex function
## 1 Complex function
### 1.1 Complex number
The *complex field* $\mathbb{C}$ is the set $\mathbb{R}\times\mathbb{R}$ equipped with field addition and multiplication
$$
\begin{aligned}
(x_1,y_1)+(x_2,y_2)&\doteq(x_1+x_2,y_1+y_2),\\
(x_1,y_1)\cdot(x_2,y_2)&\doteq(x_1x_2-y_1y_2,x_1y_2+x_2y_1).
\end{aligned}
$$
The additional identity and multiplication identity are $(0,0)$ and $(1,0)$ respectively. An element in the complex field is called a *complex number*, denoted as
$$
z=x+iy\doteq(x,y).
$$
Here $x$ is called the *real part* of $z$ and $y$ is called the *imaginary part* of $z$.

A complex number with zero imaginary part is also called a real number since
$$
\{(x,0),x\in\mathbb{R}\}\cong\mathbb{R}.
$$
A complex number with zero real part and nonzero imaginary part is called an *imaginary number*.

An alternative way is to think of $i$ as the square root of $1$. The complex field is then naturally generated from
$$
\mathbb{C}=\mathbb{R}+i\mathbb{R}.
$$
In this way, the field multiplication rule is more naturally defined as
$$
(x_1+iy_1)(x_2+iy_2)=x_1x_2-y_1y_2+i(x_1y_2+x_2y_1),
$$
with $i^2=-1$.

### 1.2 Complex plane
Since $\mathbb{C}$ comes from $\mathbb{R}^2$, one can identify the complex field with a 2-dimensional plane, where each complex number is associated with a point on the plane. This plane is called the *complex plane*.

The point for $0$ is called the *origin* of the complex plane. The set of real numbers
$$
\{(x,0):x\in\mathbb{R}\}
$$
corresponds to a line passing the origin which is called the *real axis*. Similarly, the set of imaginary numbers
$$
\{(0,y),y\in\mathbb{R}\}
$$
corresponds to a line perpendicular to the real axis and also passes the origin. It is called the *imaginary axis*.

In some cases one includes the *complex infinity* as another point into the complex plane, denoted as $\mathbb{C}+\{\infty\}$. This structure is sometimes called the *Riemann sphere*.

### 1.3 Complex conjugate
The *complex conjugate* of a complex number $z=x+iy$ is defined as
$$
z^\ast\doteq x-iy.
$$
One can express the real part and imaginary part of $z$ with $z$ and its conjugate
$$
\begin{aligned}
x&=\frac{1}{2}(z+z^\ast),\\
y&=\frac{1}{2}(z-z^\ast).
\end{aligned}
$$

### 1.4 Norm and argument
The *norm* of a complex number $z$ is defined as
$$
|z|\doteq\sqrt{x^2+y^2}.
$$
Apparently $|z|^2=zz^\ast$. The norm of a complex number is actually the distance to the origin on the complex plane.

The *argument* of a complex number $z$ is defined as the angle it takes to rotate the complex number to the real axis clockwisely, denoted as $\arg z$. Note that there is some arbiguity of $2k\pi$ that will be determined later.

### 1.5 Complex function
