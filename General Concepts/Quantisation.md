# Quantisation
- Approximates continuous value to set of discrete values
- Suitable for storage in computer memory
![[Quantisation.png]]
## Errors
- **Granular noise**: Small, due to difference between actual value and [[Quantisation]] level.
- **Overload noise**: Large, occurs when actual value falls outside minimum/maximum of [[Quantisation]] range

## Granular nosie
For every extra ADC bit the SQNR improves by 6.02 bits
Modeled as additive noise $e_{q}[n]$ 
![[Granular nosie.png]]
Bounded in magnitude by half [[Quantisation]] interval $\Delta$  
![[Pasted image 20220219142028.png]]
Determine signal-to-[[Quantisation]]-noise ratio:
![[Pasted image 20220219142129.png]]
- $P_{V}$ is the signal [[Power]]
- $P_{q}$ is the quantisation noise [[Power]]

##### Assumptions made for analysis:
Approximately true if $\Delta$ is small and the difference between samples span several $\Delta$s
- $e_{q}[n]$ is uniformly distributed over the interval -$\frac{\Delta}{2}$, $\frac{\Delta}{2}$
- $e_{q}[n]$ is zero-mean stationary [[White Noise]]:
![[Pasted image 20220219142653.png]]
- $e_{q}[n]$ is not [[Correlation]] with the signal $v[n]$ 

Then the noise power is given by the [[Expectation]] of $e_{q}^2[n]$:
![[Pasted image 20220219143441.png]]

If the ADC has B bits and an input range of -$\frac{R}{2}$, $\frac{R}{2}$ then:
$$\Delta = \frac{R}{2^B}$$
Then the [[Quantisation]] noise [[Power]] is:
$$P_{q} = \frac{R^2}{12*2^{2B}}$$
Finally the signal-to-[[Quantisation]]-noise ratio is:
![[SQNR.png]]

### SQNR for [[Sinusoidal]] signal
![[Pasted image 20220219144929.png]]

### SQNR for [[Gaussian]] signal with [[Standard Deviation]]
Thus signal [[Power]] is the [[Variance]] of the signal
![[Gaussian SQNR.png]]