 # Sampler
![[Common images/Sampler.png]]
- The sampler will sample a continuoius time signal each sampling period **T**, thus producing a discrete signal
- Implemented by multiplying signal by [[Impulse Train]]
![[Pasted image 20220219135144.png]]

![[Sampling.png]]

## Frequency domain
Using the [[Fourier transform]] the frequency domain representation can be found. This leads to the [[Nyquist Theorem]]
![[SamplerFrequencyDomain.png]]
Sampling in the frequency domain leads to a periodic time signal:
![[Pasted image 20220224164832.png]]
 From the [[Periodic Fourire Transform]] and [[DTFT]] the frequency time relationship can be found as such:
 ![[Pasted image 20220224171737.png]]