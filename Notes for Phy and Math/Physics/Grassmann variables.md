---
banner: "![[../pics/97a207be2310daa64a824da72516d69e1661965683650.png]]"
banner_y: 0.508
---

>[!abstract]- Pre-knowledge
>- [[../Mathematics/Linear algebra|Linear algebra]]

# Grassmann variables
## 1 Definition
### 1.1 Grassmann algebra
Consider an $n$-dimensional complex vector space $V$ with basis $\{\theta_i\}$. One can define the following *Grassmann algebra*
$$
\Lambda(V)\doteq\mathbb{C}\oplus V\oplus(V\wedge V)\oplus\cdots\oplus\wedge^nV.
$$
This is a vector space of dimension $2^n$. It forms an algebra under exterior product $\wedge$.

### 1.2 Grassmann numbers
An element in this algebra is called a *Grassmann number* or *Grassmann variable*. Its general form is
$$
z=c_0+\sum_{k=1}^n\sum_{i_1<\cdots<i_k}c_{i_1\cdots i_k}\theta_{i_1}\cdots\theta_{i_k}.
$$
Here the symbol $\wedge$ is omitted.

The complex part $c_0$ is also called the *body* of $z$, denoted as $z_B$. The rest part is called the *soul* of $z$, denoted as $z_S$.

### 1.3 Conjugation
As an analogue to complex conjugate, one can define a *conjugation* of a Grassmann number as
$$
\begin{aligned}
(\theta_i)^\ast&\doteq\theta_i,\\
(c\theta_{i_1}\cdots\theta_{i_k})^\ast&\doteq c^\ast\theta_{i_k}\cdots\theta_{i_1}.
\end{aligned}
$$

A different convention is to define $(\theta_k)^\ast=i\theta_k$.

### 1.4 C-number and a-number
The products of even numbers of generators $(\theta_{i_1}\cdots\theta_{i_{2n}})$ and their linear combinations are called  *c-numbers*. And the products of odd numbers of generators $(\theta_{i_1}\cdots\theta_{i_{2n+1}})$ and their linear combinations are called *a-numbers*.

A c-number commutes with any Grassmann number, while a-numbers anticommute with each other. Therefore, this forms a [[Supersymmetry algebra#1 Basic concept|superalgebra]].

## 2 Analysis
### 2.1 Grassmann function
Generally, a Grassmann function (with a Grassmann number value) has the form
$$
f(\theta)=A\theta+B,\quad A,B\in\mathbb{C}
$$
since higher order terms vanishes.

### 2.2 Integral and differential
The integral and differential operator of Grassmann number are the same
$$
\frac{\partial}{\partial\theta}\theta=1,\quad\frac{\partial}{\partial\theta}1=0
$$
and
$$
\begin{aligned}
\int1~\mathrm{d}\theta&=0,\\
\int\theta~\mathrm{d}\theta&=1.
\end{aligned}
$$
