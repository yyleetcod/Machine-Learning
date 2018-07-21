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
given $x$,  $f_i=similarity(x,l^{(i)})=e^{}$
# Kernels II

# Using An SVM
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTU3MDcwNzkwMCwtMTU3Mzk5NDU5MF19
-->