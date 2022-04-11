# Least squares estimation
For a static system (state vector **x** does not change) we wish to determine **x** using noisy output measurements **y(k)**:
$$y(k) = Cx + v(k)$$
Where **C** is the output matrix that relates **y(k)** to **x** and **v(k)** the noise.

The states can be estimated as follows
![[Pasted image 20220410162501.png]]
With the following covariance matrix
![[Pasted image 20220410162533.png]]

## Weighted least squares: [[WLS]]
## Recursive Least Squares: [[RLS]]

## Derivation
For **N** measurements:
![[Pasted image 20220410160848.png]]![[Pasted image 20220410160956.png]]![[Pasted image 20220410161128.png]]![[Pasted image 20220410161208.png]]![[Pasted image 20220410161321.png]]![[Pasted image 20220410161445.png]]![[Pasted image 20220410161627.png]]