# Dimentionality reduction
Two types:
- Principal Component Analysis (PCA)
- Linear Discriminant Analysis (LDA)

## PCA
Approximate data by constructing **new charactarestics** from **linear combination** of **existing characteristics**.

Characteristics with following **properties**, these two are **equivalent**.
- Characteristics with most variation across data
- Characteristics that allow best reconstuction of original data
![[lNHqt.gif]]
- **Remove** dependency on imput axis
	- Translating (Centering)
	- Scaling
	- Reflecting
	- Rotating

## Method
For **d x N** feature matrix with **d** features and **N** samples
- Center data, matrix **D**
- First component (PC1) **maximizes [[Variance]]** of **projected points**
- Following components (PCn) are [[Orthonormal]] to previous components
- Use [[Eigen Value]] of PCs to find PCs accounting for **high variation**
- **Reduce dimentionality** by **dropping PCs** accounting for **low variation** and projecting to remaining PCs

#### Projection
For projection matrix $Q$, **d x m** containing base vectors of PCs.
- **d**: Input dimentions
- **m**: Output  dimentions
**Input to output:**
$$z^{(n)} = Q^TD^{(n)}$$
**Output to input (approximated):**
$$ \hat{D}^{(n)} = Qz^{(n)}$$
- With $z$ being the projected feature data **column** vector, **n** length 
- $x$ being inpout data **column** vector, **n** length

### Find $Q$ :
$SQ = \lambda Q$, with $S$ the feature [[Covariance]] matrix. 

#### By [[Eigendecomposition]] 
- Find feature [[Covariance]] **d x d** matrix **S**
- Apply [[Eigendecomposition]] to **S**
- [[Eigen Vector]]s (**Q**) give PC axes
- [[Eigen Value]]s ($\Lambda$) indicats PC number, larges value is PC1, etc.
- **Limit** dimentions to **v** thus $S = Q_{v}\Lambda_{v} Q_{v}^{-1}$
	- $\Lambda_{v}$ contains larges [[Eigen Value]]s on diagonal

#### By [[SVD]]
Using [[SVD]] allows PCA without the need to calculate the [[Covariance]] matrix, thus more numeric stability.

[[Eigen Vector]]s: $Q = U$
[[Eigen Value]]s: $\Lambda = \frac{1}{N}\Sigma_{+} ^2$

- Perform [[SVD]] on the centered data **D**:
	- $D = U\Sigma V^T$
- Sub into formula for the[[Eigendecomposition]] of [[Covariance]] matrix **S**:
	- $cov(D) = S = \frac{1}{N}(U\Sigma V^T)(U\Sigma V^T)^T = \frac{1}{N}U\Sigma^2 U^-1 = Q\Lambda Q^-1$
	- Thus: $Q = U$ and $\Lambda = \frac{1}{N}\Sigma ^2$ 
	- Meaning the [[Covariance]] of **D** Does not have to be calculated

#### Useful resources
https://youtu.be/g-Hb26agBFg

## LDA
projects onto eigenvectors of the transofmerd between class scatter (using whitening transform of the wihin class scatter)