# Integral control
Ensure zero steady state error even with plant model mismatch.
![[Pasted image 20220304185310.png]]
![[Pasted image 20220304203310.png]]
## Method
1. Determine if the system is [[Controllable]]
2. Determine desired **closed-loop** poles
3. Calculate equivalent **closed-loop** poles in z plane with $Z_{CL} = e^{s_{CL}T}$ where T is the sampling period
4. Construct the augmented state space model $\bar{F}$ and $\bar{g}$.
5. Design the augmented controller gain $\bar{k}$ via [[Control Canonical Form]]
	1.  Get **open-loop** coefficients $\alpha_{1}, \alpha_{2},$ etc. from **open-loop** char equation
	2. Get the desired **closed-loop** coefficients $a_{1}, a_{2},$ etc. from desired **closed-loop** poles in the z-plane
	3. Calculate the controller gains **k**
	 ![[Pasted image 20220304203225.png]]
6. Construct transformation matrix **P** ([[Control Canonical Form]]) to transform back to normal form.
![[Pasted image 20220304203545.png]]
7. Calculate feed forward gain $\bar{N}$ to cancel slow closed loop pole at $z_{i} = 0.9$ 
 ![[Pasted image 20220304203746.png]]
## Derivation
- [[State Space System Derivation]]
- [[Feed Forward Derivation]]
