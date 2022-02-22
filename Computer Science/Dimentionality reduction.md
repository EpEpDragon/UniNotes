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

#### By [[Eigendecomposition]] 
- Find [[Covariance]] **d x d** matrix **S**
- Apply [[Eigendecomposition]] to **S**
- [[Eigen Vector]]s (**Q**) give PC axes
- [[Eigen Value]]s ($\Lambda$) indicats PC number, larges value is PC1, etc.
- **Limit** dimentions to **v** thus $S = Q_{v}\Lambda_{v} Q_{v}^{-1}$
	- $\Lambda_{v}$ contains larges [[Eigen Value]]s on diagonal

#### By SVD
Using SVD allows PCA without the need to calculate the [[Covariance]] matrix


#### Useful resources
https://youtu.be/g-Hb26agBFg