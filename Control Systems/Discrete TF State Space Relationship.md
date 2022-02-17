# Discrete TF State Space Relationship
![[Pasted image 20220217120819.png]]
![[Pasted image 20220217124145.png]]
![[Pasted image 20220217124328.png]]


## Derivation
The [[State Space Discrete]] state space model is converted from the time domain to the z domain using the [[Z-Transform]]:
![[Pasted image 20220217121036.png]]
![[Pasted image 20220217121046.png]]
For TF zero intitial confiditons is assumed, meaning $x(0) = 0$:
![[Pasted image 20220217121216.png]]
Make **X(z)** subject:
![[Pasted image 20220217121430.png]]
Sub **X(z)** into output:
![[Pasted image 20220217121455.png]]
Rearrange to find discrete TF **G(z) = Y(z)/U(z)**:
![[Pasted image 20220217121737.png]]
The inverse can also be written in terms of the [[Determinant]] and [[Adjoint matrix]]:
![[Pasted image 20220217124145.png]]