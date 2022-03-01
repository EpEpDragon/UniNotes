# Prediction observer
When the output diff is used to correct predicted states $\hat{x}(k+1)$ it is a prediction observer. Thus does not use the latest information to correct.
![[Pasted image 20220227153537.png]]
![[Pasted image 20220227154015.png]]
The state error vector $\tilde{x}(k)$ is the difference between $x(k)$ and $\hat{x}(k)$ :
![[Pasted image 20220227154203.png]]
Thus:
![[Pasted image 20220227154237.png]]
Where $F_{obs}$ is the observer error system matrix.

The poles of the observer error dynamics can be found using the [[Eigen Value]]s:
![[Pasted image 20220227154443.png]]
Calculate required gain by **comparing** this to required poles.

## Design
- By hand
	1. Check [[Observable]]
	2. Specify desired observer poles
	3. Calculate equivalent desired poles in z-plane using $z_{obs} = e^{S_{obs}T}$ where $T$ is sampling period
	4. Construct the observer charateristic equation:
	![[Pasted image 20220227154443.png]]
	5. Construct desired characteristic equation as function of desired observer poles:
	![[Pasted image 20220227155224.png]]
	6. Calculate required gain $m_{p}$ by comparing step **4.** and **5.**
- Matlab
![[Pasted image 20220227160120.png]]