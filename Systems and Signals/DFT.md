# Discrete Fourier transform
Approximate **spectrum** of non-periodic signals to that of a periodic-signal.
![[Pasted image 20220303100344.png]]
![[Pasted image 20220303100408.png]]
## Properties
![[Pasted image 20220303101252.png]]
[[Even function]] and[[Odd function]]
![[Pasted image 20220303101505.png]]![[Pasted image 20220303102003.png]]
![[Pasted image 20220303102252.png]]
![[Pasted image 20220303102313.png]]
## Method
Let $h_c(t)$ be [[Analog signals]].
 ![[Pasted image 20220303094046.png]]
 Discretise $h_c(t)$ using [[Sampler]] to form [[Discrete time signals]].
 ![[Pasted image 20220303094108.png]]
Window function using [[Windowing]]. Assume finite length rectangular [[Windowing]] function.
![[Pasted image 20220303094157.png]]
Next [[Sampler]] in the frequency domain
![[Pasted image 20220303095242.png]]
Limit time and frequency such that both have a period of **N** samples.
![[Pasted image 20220303095749.png]]
Zero padding can be used to improve display of the [[DFT]]
![[Pasted image 20220303103502.png]]