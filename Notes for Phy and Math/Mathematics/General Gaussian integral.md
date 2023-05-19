---
banner: "![[../pics/97a207be2310daa64a824da72516d69e1661965683650.png]]"
banner_y: 0.516
---

# General Gaussian integral
For a vector $\ket{\psi}\in\mathcal{H}$, a general quadratic form can be written as
$$
Q(\psi)=\frac{1}{2}\braket{\psi|A|\psi}+\braket{\phi|\psi}+C,
$$
where $A$ is symmetric and invertible.

The integral
$$
\int_{\mathcal{H}}[D\psi]e^{-Q(\psi)}=\left(\det\frac{A}{2\pi}\right)^{-1/2}e^{-Q(\bar\psi)}
$$
is the Gaussian integral. Here
$$
Q(\bar\psi)=-\frac{1}{2}\braket{\phi|A^{-1}|\phi}+C
$$
and
$$
\ket{\bar\psi}\doteq-A^{-1}\ket{\phi}
$$
is the stationary point of $Q(\psi)$.