Two types of sym. in SM.:
- Poincare: defines different types of particles
- Internal: don't change type of particle. In SM. $SU(3)\times SU(2)\times U(1)$

In nonrelativistic quark model, the $SU(3)$ can be turned into $SU(6)$. However, this can't be generalized to relativistic case.

No-Go theorem: can't be.

Coleman Mandula theorem: the Lie algebra rep. of a quantum system can have sym. only of Poincare $\times$ Internal.

In SUSY, by generalizing Lie algebra to Lie superalgebra, can break the restriction.

---
$\delta_\xi A=(\xi Q+\bar{\xi}\bar{Q})A$, the operator $Q$ acting on $A$ will raise the dimension by $1/2$. To get a renormalizable field, the dimension needs to be below 2. $\delta_\xi$ acting on the possible fields $A,\psi,F$ gives
$$
\begin{aligned}
&\delta_\xi A=\sqrt{2}\xi\psi,\\
&\delta_\xi\psi=i\sqrt{2}\sigma^\mu\bar{\xi}\partial_\mu A+\sqrt{2}\xi F,\\
&\delta_\xi F=i\sqrt{2}\bar{\xi}\bar{\sigma}^\mu\partial_\mu\psi.
\end{aligned}
$$

### 0.1 Superfield
If one include the Grassman variables $\theta,\bar{\theta}$ into the field of supervector space, the graded Lie bracket becomes a commutator
$$
\{Q,\bar{q}\}\to[\theta Q,\bar{\theta}\bar{Q}].
$$
This forms a Lie algebra, which can generate a Lie group, with its element
$$
G(x^\mu,\theta,\bar{\theta})=\exp(i(-x^\mu p_\mu+\theta Q+\bar{\theta}\bar{Q})).
$$
By left acting $G(0,\xi,\bar{\xi})$ on another group element, it can induce a differential operator.