# Observer 
Is a model of actual plant used to estimate the internal states $\hat{x}(k)$, from input $u(k)$ and measured output $y(k)$

## Types
- [[Prediction observer]]
- [[Current observer]]
- [[Kalman filter]]

## Current vs Prediction observer
- **Use** [[Current observer]]: When fast computer or low sampling frequency
- **Use** [[Prediction observer]]: When slow computer of high sampling frequency

Prediction and current observer gain related as such:
![[Pasted image 20220227163400.png]]

### Timing
Current:
![[Pasted image 20220227162847.png]]
Prediction:
![[Pasted image 20220227162908.png]]

