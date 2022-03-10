# Reciprocal root locus
Used to solve the [[Optimal Output Regulator]]
![[Pasted image 20220308150157.png]]
![[Pasted image 20220308150233.png]]
## Design
- Find open loop transfer function $G_{ol}(z)$  ([[Discrete TF State Space Relationship]])
- Find $G_{ol}(z^{-1})$ 
- Plot the root locus of $1- \rho G_{ol}(z^{-1})G_{ol}(z) = 0$
- Find the n stable poles corresponding to a choice of $\rho$
- Use pole placement to calculate steady state [[LQR]] gain $K_{\infty}$ that places the closed-loop poles at the desired locations