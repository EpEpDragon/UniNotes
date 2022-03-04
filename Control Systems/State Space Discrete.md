# Discrete state space
**Basic digital control**
![[Pasted image 20220217102329.png]]

## Model
The state vector at the next sampling instant is a function of the current state vector x(k) and the current input u(k). The output signal is a function of the current state vector and current input.

Note **d**, and **c** is the same as in the [[State Space Continuous]] model.
Note **integrator block** in [[State Space Continuous]] replaced with **unit delay**.
![[Pasted image 20220217103510.png]]
![[Pasted image 20220217104217.png]]

## Transfer function G(z) vs State Space
- Both describe same system
- G(z) only describe input, output
- State space describes full internal state
- [[Discrete TF State Space Relationship]]

## State space forms
There are infinitely many state vector choices and thus infinite forms, there are however some special forms that reduce complexity:
- [[Control Canonical Form]] (First companion form)
- [[Observer Canonical Form]] (Second companion form)

These states can be found from the transfer function see: [[Discrete TF State Space Relationship]].

Or by using the [[Control Canonical Form]] [[Observer Canonical Form]] relationship

## Eigen values and poles
From the matrix [[Eigen Value]] and [[Discrete TF State Space Relationship]] it can be seen that the eigen values of the system matrix **F** are equal to the poles of the system.

Matlab:
	poles = eig(F)
	
## [[Observer]]
Used to approximate internal states

## Design
- Obtain [[State Space Discrete]] plant model using:
	-  **Matlab c2d** or 
	- The [[State Space Continuous-Discrete relationship]]
		- By approximation $e^{At}$ to finite terms or
		- Calculate $e^{At}$ exactly using the [[Laplace transform]]
- controller and observer can be designed separately due to [[Separation Principle]]
- Design a controller architecture:
	- [[State Regulator]]
	- [[Servo Controller]]
	- [[Integral Control]]
- Design [[Observer]] 
- [[Combine Controller Observer]]
