# Kalman filter
The [[Kalman filter]] is a state observer.
![[Pasted image 20220410164427.png]]![[Pasted image 20220410171125.png]]
The [[Kalman filter]] thus acts as a [[Current observer]] with a time varying gain **L(k)**
![[Pasted image 20220410171330.png]]
## Steady state gain
![[Pasted image 20220410172219.png]]![[Pasted image 20220410172321.png]]
## With reciprocal root locus
Only for SISO system.
![[Pasted image 20220410174425.png]]
## Derivation
With [[Least squares estimation]] the states of a **static** state vector is estimated, the [[Kalman filter]] uses [[RLS]] to do so for a **dynamic** state vector.
![[Pasted image 20220410165211.png]]![[Pasted image 20220410165336.png]]
![[Pasted image 20220410165823.png]]![[Pasted image 20220410165948.png]]
Then the new sensor measurements are used to calculate the new state estimate covariance matrix using [[RLS]].
![[Pasted image 20220410170118.png]]
![[Pasted image 20220410170519.png]]
![[Pasted image 20220410170656.png]]
![[Pasted image 20220410170832.png]]![[Pasted image 20220410170911.png]]