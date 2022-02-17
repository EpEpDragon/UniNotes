# Relationship between continouts and discrete state space models
The following shows the relationship between [[State Space Continuous]] and [[State Space Discrete]] models

![[Pasted image 20220217110049.png]]

#### **F** can be calculated using the power series representation of $e^{At}$ :
![[Pasted image 20220217110445.png]]
Or using the [[Laplace transform]] relationship with $e^{At}$ :
![[Pasted image 20220217112621.png]]
With **t** (after laplace) equals to the sampling time **T**
 
#### Similarly **g** can be calculated:
![[Pasted image 20220217110630.png]]
Or if **F** is known :
![[Pasted image 20220217113253.png]]
Thus:
![[Pasted image 20220217113305.png]]



## Derivation
- The **D/A** converter is modeled as a [[ZOH]]
- The **A/D** converter is modeled as a [[Sampler]]

![[Pasted image 20220217113744.png]]
Equivalent system:
![[Pasted image 20220217114410.png]]

From [[State Space Continuous]]:
![[Continuous state space solution.png]]
To solve $e^{A(t-t_{0})}$ the [[Exponential Power Series]] can be used:
![[Pasted image 20220217115235.png]]
![[Pasted image 20220217115445.png]]![[Pasted image 20220217115804.png]]