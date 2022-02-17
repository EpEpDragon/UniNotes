# Discrete state space
**Basic digital control**
![[Pasted image 20220217102329.png]]

## Model
The state vector at the next sampling instant is a function of the current state vector x(k) and the current input u(k). The output signal is a fucntion of the current state vector and current input.

Note **d**, and **c** is the same as in the [[State Space Continuous]] model.
Note **integrator block** in [[State Space Continuous]] replaced with **unit delay**.
![[Pasted image 20220217103510.png]]
![[Pasted image 20220217104217.png]]

## Transfer fucntion G(z) vs State Space
- Both describ same system
- G(z) only describe input, output
- State space describes full internal state
- [[Discrete TF State Space Relationship]]

## Eigen values and poles
From the [[Matrix Eigen Value]] and [[Discrete TF State Space Relationship]] it can be seen that the eigen values of the system matrix **F** are equal to the poles of the system.

Matlab:
	poles = eig(F)

## Design
- Obtain [[State Space Discrete]] plant model using:
	-  **Matlab c2d** or 
	- The [[State Space Continuous-Discrete relationship]]
		- By approximation $e^{At}$ to finite terms or
		- Calculate $e^{At}$ exactly using the [[Laplace transform]]
