---
banner: "![[pics/3a299b9125e783723b06d7f6e79451b01644306080698.jpeg]]"
banner_y: 0.444
---

# Group theory in a nutshell
## 1 Point group
### 1.1 Notation
- Rotation of $2\pi k/n$ is $c_n^k$, the axis is $C_n$.
- Reflection is $\sigma$,
	- the surface perp to $C_n$, then $\sigma_h$;
	- the surface contain $C_n$, then $\sigma_\nu$;
	- the surface devide $C_A$ and $C_B$ in half, then $\sigma_d$;
- Inverse is $i$.

### 1.2 Equivalence
If $c_m^i$ of axis $C_m$ rotates $C_A$ to $C_B$, then these axes are equivalent.

### 1.3 Rules
1. There is $c_n^k\sigma_h=\sigma_hc_n^k$;
	- As a special case, $c_2^1\sigma_h=i$;
2. For $C_{2A}$ and $C_{2B}$ with angle $\varphi$, there is $c_{2B}^1c_{2A}^1=c_\perp(2\varphi)=\left(c_{2A}^1c_{2B}^1\right)^{-1}$;
	- This rule means that $c_\perp(2\varphi)c_{2A}^1=c_{2B}^1$ generates another $C_2$;
3. For $\sigma_{\nu A}$ and $\sigma_{\nu B}$ with angle $\varphi$, there is $\sigma_{\nu B}\sigma_{\nu A}=c_{2B}^1iic_{2A}^1=c_{2B}^1c_{2A}^1=c_\perp(2\varphi)$.

