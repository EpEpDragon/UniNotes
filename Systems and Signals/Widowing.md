# Widowing
Extract part of signal.
![[Pasted image 20220224172211.png]]
Ideally this should not change the frequency respose, but this requires the **w(t)** to be a inpulse function, which would result in no [[Widowing]]. Larger window will minimize the frequency distortion ([[Spectral Leakage]])
![[Pasted image 20220224172530.png]]![[Pasted image 20220224172819.png]]
## Different window functions:
- Rectangular
	- Smallest main lobe
	- Large side lobes
- Hamming
	- Larger main lobe
	- Much smaller side lobes
- Blackman
	- Even larger main lobe
	- Even smaller side lobes
	
![[Window functions.png]]
### Rectangular
![[Rectangular.png]]
### Hamming
![[Hamming.png]]
### Blackman
![[Blackman.png]]