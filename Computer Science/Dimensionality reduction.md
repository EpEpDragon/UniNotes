# Dimensionality reduction
Two types:
- Principal Component Analysis (PCA)
- Linear Discriminant Analysis (LDA)

## PCA
Approximate data by constructing **new characteristics** from **linear combination** of **existing characteristics**.

Characteristics with following **properties**, these two are **equivalent**.
- Characteristics with most variation across data
- Characteristics that allow best reconstruction of original data
![[lNHqt.gif]]
- **Remove** dependency on impute axis
	- Translating (Cantering)
	- Scaling
	- Reflecting
	- Rotating

## Method
For **d x N** feature matrix with **d** features and **N** samples
- Centre data, matrix **D**
- First component (PC1) **maximizes [[Variance]]** of **projected points**
- Following components (PCn) are [[Orthonormal]] to previous components
- Use [[Eigen Value]] of PCs to find PCs accounting for **high variation**
- **Reduce dimensionality** by **dropping PCs** accounting for **low variation** and projecting to remaining PCs

#### Projection
For projection matrix $Q$, **d x m** containing base vectors of PCs.
- **d**: Input dimensions
- **m**: Output  dimensions
**Input to output:**
$$z^{(n)} = Q^TD^{(n)}$$
**Output to input (approximated):**
$$ \hat{D}^{(n)} = Qz^{(n)}$$
- With $z$ being the projected feature data **column** vector, **n** length 
- $x$ being input data **column** vector, **n** length

### Find $Q$ :
$SQ = \lambda Q$, with $S$ the feature [[Covariance]] matrix. 

#### By [[Eigendecomposition]] 
- Find feature [[Covariance]] **d x d** matrix **S**
- Apply [[Eigendecomposition]] to **S**
- [[Eigen Vector]]s (**Q**) give PC axes
- [[Eigen Value]]s ($\Lambda$) indicates PC number, larges value is PC1, etc.
- **Limit** dimensions to **v** thus $S = Q_{v}\Lambda_{v} Q_{v}^{-1}$
	- $\Lambda_{v}$ contains larges [[Eigen Value]]s on diagonal

#### By [[SVD]]
Using [[SVD]] allows PCA without the need to calculate the [[Covariance]] matrix, thus more numeric stability.

[[Eigen Vector]]s: $Q = U$
[[Eigen Value]]s: $\Lambda = \frac{1}{N}\Sigma ^2$

- Perform [[SVD]] on the cantered data **D**:
	- $D = U\Sigma V^T$
- Sub into formula for the[[Eigendecomposition]] of [[Covariance]] matrix **S**:
	- $cov(D) = S = \frac{1}{N}(U\Sigma V^T)(U\Sigma V^T)^T = \frac{1}{N}U\Sigma^2 U^-1 = Q\Lambda Q^-1$
	- Thus: $Q = U$ and $\Lambda = \frac{1}{N}\Sigma ^2$ 
	- Meaning the [[Covariance]] of **D** Does not have to be calculated

#### Useful resources
https://youtu.be/g-Hb26agBFg

## LDA
Projects onto eigenvectors of the transformer between class scatter (using whitening transform of the within class scatter)

**Within class scatter:**
$$S_{W} = \sum_{j}\frac{N_{j}}{N}S_{j}$$
Where $S_{j}$ = covariance matrix of class $j$
Between class scatter:
$$S_{B} = \sum_{j}\frac{N_{j}}{N}(m_{j}-m)(m_{j}-m)^T$$
Find transformation matrix $W$ that whitens $S_{W}$ and diagonalizes $S_{B}$:
$$W^TS_{W}W = I$$
$$W^TS_{B}W = D_{B}$$
## Method

**If Sw invertible:**
1. Calculate $S_{W}$ and $S_{B}$ 
2. Perform [[Eigendecomposition]] of $S^{-1}_WS_{B}$
	- $S^{-1}_WS_{B} = Q\Lambda Q^T$ 
3. Choose first $d'$ eigenvectors
4. Thus $W = Q_{d'}$ 
5. Transform data
	- $y = W^Tx$

**Otherwise:**
$S_{w}$ will not be [[Full Rank]] and have some zero [[Eigen Value]]s
1. Calculate $S_{W}$
2. Apply [[Eigendecomposition]] to $S_{W}$
	- $S_{W} = Q\Lambda Q^T$ 
3. Remove zero variance values, i.e. only take first $r$ non zero values
	- $S_{W} = Q_{r}\Lambda_{r} Q_{r}^T$ 
	- Thus $S_{W}$ whitened is $\Lambda_{r}^{-1/2}Q^T_{r}S_{W}Q_{r}\Lambda_{r}^{-1/2} = I_{r}$ 
	- Similarly for $S_{B}$ whitened $\Lambda_{r}^{-1/2}Q^T_{r}S_{B}Q_{r}\Lambda_{r}^{-1/2} = S^z_{B}$
4. Apply [[Eigendecomposition]] to $S^z_{B}$
	- $S^z_{B} = U_{B}D_{B}U^T_{B}$ 
5. Diagonalize $S^z_{B}$ using above:
	- $U^T_{B}\Lambda_{r}^{-1/2}Q^T_{r}S_{B}Q_{r}\Lambda_{r}^{-1/2}U_{B} = D_{B}$
7. Take $d'$ larges dimensions of $U_{B}$
8. Thus $W = Q_{r}\Lambda_{r}^{-1/2}U_{d'}$ 
	- $WS_{W}W^T = I_{r}$
	- $WS_{B}W^T = D_{d'}$
9. Transform data
	- $y = W^Tx$

