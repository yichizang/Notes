---
banner: "![[../pics/mmexport1663524028536.jpg]]"
banner_y: 0.4
---

>[!abstract]- Pre-knowledge
>- [[Abstract group theory]]
>- [[Complex function]]

# Elliptic curve
## 1 Quotient of a lattice
Consider $\mathbb{C}$ as an addition group and $\tau\in\mathbb{C}$ with nonzero imaginary part, then $\Lambda\doteq\mathbb{Z}+\tau\mathbb{Z}$ is a subgroup of $\mathbb{C}$ in the form of a 2-dimensional lattice. The elements in $\Lambda$ have the form
$$
z=m+\tau n,\quad m,n\in\mathbb{Z}.
$$

Since $\mathbb{C}$ is abelian, one have the quotient group $\mathbb{C}/\Lambda$ in the form of a torus. This quotient group is isomorphic to $U(1)\times U(1)$. The explicit isomorphism is given as
$$
(\sigma_1+\tau\sigma_2)+\Lambda\mapsto(e^{2\pi i\sigma_1},e^{2\pi i\sigma_2}).
$$

## 2 Elliptic curve
Consider the algebraic equation
$$
y^2=x^3+fx+g,
$$
where $(x,y)\in\mathbb{C}^2$ and $f,g\in\mathbb{C}$. The solution set of this equation is called an *elliptic curve*. They can be identified as the torus minus the origin $\mathbb{C}/\Lambda-\{0\}$.

## 3 Weierstress function
This identification is done through the following holomorphic function known as the *Weierstrass function*
$$
\wp(z|\tau)\doteq\frac{1}{z^2}+\sum_{w\in(\Lambda-\{0\})}\left[\frac{1}{(z-w)^2}-\frac{1}{w^2}\right].
$$
Here $z\notin\Lambda$. This series converges absolutely and it is doubly-periodic as
$$
\forall m,n\in\mathbb{Z},\quad\wp(z+m+\tau n|\tau)=\wp(z|\tau).
$$
Therefore, it is a meromorphic function on $\mathbb{C}/\Lambda$ with a second order pole at $z=0$. Expanding the function at this pole, one gets
$$
\wp(z|\tau)=\frac{1}{z^2}+\sum_{k=1}^\infty(2k+1)G_{2k+2}z^{2k},
$$
where
$$
G_{2k+2}\doteq\sum_{(m,n)\in(\mathbb{Z}^2-\{(0,0)\})}\frac{1}{(m+\tau n)^{2k+2}}.
$$
This is called the *Eisenstein series*.