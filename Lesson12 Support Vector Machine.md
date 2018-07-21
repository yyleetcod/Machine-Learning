# Optimization Objective
**Logistic regression**
$J(\theta)=\frac{1}{m}[\sum\limits_{i=1}^my^{(i)}(-log(h_\theta(x^{(i)})))+(1-y^{(i)})(-log(1-h_\theta(x^{(i)})))]+\frac{\lambda}{2m}\sum\limits_{j=1}^n\theta_j^2$

**SVM**(large margin classifiers)
$J(\theta)=\frac{1}{m}\sum\limits_{i=1}^m[y^{(i)}cost_1(\theta^Tx^{(i)})+(1-y)cost_0(\theta^Tx^{(i)})]+\frac{\lambda}{2m}\sum\limits_{j=1}^n\theta_j^2$
for convention, we define $J(\theta)$ as:
$J(\theta)=C\sum\limits_{i=1}^m[y^{(i)}cost_1(\theta^Tx^{(i)})+(1-y)cost_0(\theta^Tx^{(i)})]+\frac{1}{2}\sum\limits_{j=1}^n\theta_j^2$
Hypothesis:
$$
h_\theta(x)=
\begin{cases}  
1 & \text{if $\theta^Tx\ge0$}\\
0& \text{otherwise}
\end{cases}$$

# Large Margin Intuition
$J(\theta)=C\sum\limits_{i=1}^m[y^{(i)}cost_1(\theta^Tx^{(i)})+(1-y)cost_0(\theta^Tx^{(i)})]+\frac{1}{2}\sum\limits_{j=1}^n\theta_j^2$
**When C is very large**, we want the first term in $J(\theta)$ approximately equal to 0, that means :
 
 - If $y = 1$, we want $\theta^Tx\ge1$(not just $\ge0$)
 - If $y = 0$, we want $\theta^Tx\le1$(not just $<0$)

$\min \frac{1}{2}\sum\limits_{i=1}^{n}\theta_i^2$
s.t.
$\theta^Tx^{(i)}\ge1$ if $y^{(i)}=1$
     $\theta^Tx^{(i)}\ge1$ if $y^{(i)}=1$
When we use SVM as a large margin classifier(set C too large), it can be sensitive to outliers. 

# The mathematics Behind Large Margin Classification

$\min \frac{1}{2}\sum\limits_{i=1}^{n}\theta_i^2=\frac{1}{2}||\theta||^2$(ignore $\theta_0$)
s.t.
$\theta^Tx^{(i)}\ge1$ if $y^{(i)}=1$
     $\theta^Tx^{(i)}\ge1$ if $y^{(i)}=1$

$\min \frac{1}{2}||\theta||^2$(ignore $\theta_0$)
s.t.
$p^{(i)}||\theta||\ge1$ if $y^{(i)}=1$
$p^{(i)}||\theta||\le-1$ if $y^{(i)}=1$
If $p^{(i)}$ is very small, that means we need $||\theta||$ to be very large, resulting in a large $J(\theta)$. It's why SVM will choose $\theta$ which makes $p^{(i)}$ be large.

# Kernels I

given $x$,  $f_i=similarity(x,l^{(i)})=k(x,l^{(i)})=e^{-\frac{||x-l^{(i)}||^2}{2\sigma^2}}$
where $l^{(i)}=x^{(i)},||x-l^{(i)}||^2=\sum\limits_{j=1}^n(x_j-l_j^{(i)})^2,i=1,2,...,m$

here we use gaussian kernel
If $x\approx l^{(i)},f_i\approx 1$
If $x$ is far from $l^{(i)},f_i\approx 0$

Predict "1" when $\theta^Tf\ge0$

# Kernels II

**SVM  with Kernels**
Hypothesis: 
Given $x$, compute features $f\in\Re^{m+1}$,predict "$y=1$" if $\theta^Tf\ge0$
Training:
$J(\theta)=C\sum\limits_{i=1}^m[y^{(i)}cost_1(\theta^Tf^{(i)})+(1-y)cost_0(\theta^Tf^{(i)})]+\frac{1}{2}\sum\limits_{j=1}^n\theta_j^2$
Regularization item: $\frac{1}{2}\sum\limits_{j=1}^n\theta_j^2=\frac{1}{2}\theta^T\theta$
Sometimes we may replace it with $\frac{1}{2}\theta^TM\theta$ for computational efficiency.

Using kernels in logistic regression will be very slow.

**SVM parameters**

$C(=\frac{1}{\lambda})$.
Large C(small $\lambda$): lower bias, high variance.
Small C(large $\lambda$): higher bias, low variance.
$\sigma^2$
Large $\sigma^2$: Features $f_i$ vary more smoothly. Higher bias, low variance.(Underfit)
Small $\sigma^2$: Features $f_i$ vary less smoothly. Lower bias, high variance.(Overfit)

# Using An SVM

Need to specify:

- Choice of parameter C
- Choice of kernel(similarity function):
E.g. 
**No kernel("linear kernel")**:Predict "$y=1$" if $\theta^Tx\ge0$
**Gaussian kernel**:$f_i=e^{-\frac{||x-l^{(i)}||^2}{2\sigma^2}}$
where $l^{(i)}=x^{(i)}$, need to choose $\sigma^2$
We choose no kernel when $n$ is large while $m$ is small, $x\in\Re^{n+1}$ and we want to get a linear decision boundary.
We choose gaussian kernel when $n$ is small while $m$ is large, $f\in\Re^{m+1}$ and we want to get a nonlinear decision boundary.

We need feature scaling when we use kernels to compute feature $f_i$.

Many off-the-shelf kernels available:

- Polynomial kernel
- String kernel
- Chi-squre kernel 
- Histogram intersection kernel

If $n$ is large(relative to $m$)($n>m$): use logistic regression, or SVM without a kernel("linear kernel")
e.g. $n=1000,m=10-1000$

If $n$ is small, $m$ is intermediate: use SVM with gaussian kernel
e.g. $n=1-1000,m=10000$

If $n$ is small, $m$ is large: create/add featr
e.g. $n=1-1000,m=50000+$

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTQ5MjYwNzI2Miw3NzQzNzc5MzQsNTE1OD
gwOTE2LC05NDg2MzEwNjEsMjAyOTM1MTk3NywyMDcyNjM2ODYy
LC0xNTA5NjU0OTk5LDE5MjgzMjI4MDMsMTEyNjMyODg4NiwtMT
U3Mzk5NDU5MF19
-->