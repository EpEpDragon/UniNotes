# Current observer
Uses the latest information in the current output $y(t)$ to correct the current state $\hat{x}(k)$.

**Downside**: Have to sample current output, correct current state and calculate new input before control signal can be output. If this takes a significant fraction of sampling period a unmodeled delay is introduced.
![[Pasted image 20220227161437.png]]
![[Pasted image 20220227160855.png]]
- The next state estimate $\bar{x}(k+1)$ is predicted based on the current corrected state estimate $\hat{x}(k)$
- After one samplimg period $\bar{x}(k+1)$ becomes $\bar{x}(k)$
- The predicted state estimate $\bar{x}(k)$ is then corrected based on the current output measurment $y(k)$ to become the corrected state estimate $\hat{x}(k)$

Substitute **correction** into **prediction** equation:
![[Pasted image 20220227163236.png]]
This is the same as for the [[Prediction observer]] except:
![[Pasted image 20220227163259.png]]
Thus:
![[Pasted image 20220227163400.png]]

## Design
1. Design [[Prediction observer]]
2. **Convert** to current observer using:
![[Pasted image 20220227163400.png]]
