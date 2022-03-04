# State regulator
A [[State Space Continuous]] or [[State Space Discrete]] control system that does **not** have a reference input, hold system at zero.
 ## Discrete
![[Pasted image 20220227135843.png]]
The open-loop model of the system is as follows:
![[Pasted image 20220227140556.png]]
The **open-loop** poles system are the [[Eigen Value]]s of the **open-loop** system matrix $F$
![[Pasted image 20220227140707.png]]
The closed-loop system is obtained by substituting the control into the open-loop system, with $F-gk = F_{CL}$
 ![[Pasted image 20220227140928.png]]
The **closed-loop** poles are also obtained using the [[Eigen Value]]s:
![[Pasted image 20220227141453.png]]
If the system is [[Controllable]] the poles can be placed at the desired locations

## Design
- Using pole placement coefficient comparison:
	1. Determine if the system is [[Controllable]]
	2. Determine desired **closed-loop** poles
	3. Calculate equivalent **closed-loop** poles in z plane with $Z_{CL} = e^{s_{CL}T}$ where T is the sampling period
	4. Construct the **closed-loop** characteristic equation as function the controller gain **k**
	![[Pasted image 20220227142559.png]]
	5. Construct the **closed-loop** characteristic equation as function of desired **closed-loop** poles: 
	![[Pasted image 20220227142735.png]]
	6. Calculate elements of **k** by comparing step **4.** and **5.**


- Using pole placement in [[Control Canonical Form]]
	1. SameAsPrevious
	2. SAP
	3. SAP
	4. Get **open-loop** coefficients $\alpha_{1}, \alpha_{2},$ etc. from **open-loop** [[State Space Discrete]] model in [[Control Canonical Form]]:
	 ![[Pasted image 20220227150005.png]]
	 5. Get the desired **closed-loop** coefficients $a_{1}, a_{2},$ etc. from desired **closed-loop** poles in the z-plane
	 ![[Pasted image 20220227150142.png]]
	 6. Calculate the controller gains **k**
	 ![[Pasted image 20220227150250.png]]
	 7. If the original form is not [[Control Canonical Form]] the gain can be transformed to the original gain using the transformation matrix **P**
	 ![[Pasted image 20220227151231.png]]
- Use pole placement with Matlab
![[Pasted image 20220227152641.png]]