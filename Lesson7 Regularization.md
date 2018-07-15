# The Problem of Overfitting
**"Underfit"**: high bias;
**"Overfit"**: high variance. It happens when we have too many features with too few training examples.
**Way to solve overfitting:**
1.Reduce number of features, but we may loss some information.

- Manually select which features to keep.
- Model selection algorithm.

2.Regularization

- Keep all the features, but reduce magnitude/values of parameters $\theta_j$. it works well when we have a lot of features, each of which contributes a bit to predicting $y$.

# Cost Function
We add one term in the cost function to make every parameter smaller.
$J(\theta)=\frac{1}{2m}\sum \limits_{i=1}^{m}[(h_\theta(x^{(i)})-y^{(i)})^2+\lambda\sum \limits_{j=1}^n\theta_j^2]$(we regularize $\theta_1$ through $\theta_n$, without $\theta_0$)
If $\lambda$ is

- too large to make every $\theta_i,i=1,2,...,n$ approximately equals to 0. Underfit, high bias.
- too small, overfit, high variance.

# Regularized Linear Regression
**Gradient descent:**
>repeat until convergence{
>$\theta_0:=\theta_0-\alpha\frac{1}{m}\sum \limits_{i=1}^{m}(h_\theta(x^{(i)})-y^{(i)})x^{(i)}_0$
	$\theta_j:=\theta_j-\alpha[\frac{1}{m}\sum \limits_{i=1}^{m}(h_\theta(x^{(i)})-y^{(i)})x^{(i)}_j+\frac{\lambda}{m}\theta_j]$
	(simultaneously update for every $j=1,...,n$)
} 

$\theta_j:=\theta_j(1-\alpha\frac{\lambda}{m})-\alpha\frac{1}{m}\sum \limits_{i=1}^{m}(h_\theta(x^{(i)})-y^{(i)})x^{(i)}_j$
	(every $j=1,...,n$)
$(1-\alpha\frac{\lambda}{m})$ is less than 1. It means we will shrink the parameter a little bit after every iteration.

**Normal equation:**
$$
\theta=(X^TX+
 \left[ 
 \begin{matrix} 
0 & 0 & 0 & 0 & 0\\ 
1 & 0 & 0 & 0 & 0\\ 
0 & 1 & 0 & 0 & 0\\ 
... & ... & ... & ... & ...\\
0 & 0 & 0 & 0 & 1 
 \end{matrix} 
 \right])^{-1}X^Ty
 $$
 It can be proved that 
 $$(X^TX+
 \left[ 
 \begin{matrix} 
0 & 0 & 0 & 0 & 0\\ 
1 & 0 & 0 & 0 & 0\\ 
0 & 1 & 0 & 0 & 0\\ 
... & ... & ... & ... & ...\\
0 & 0 & 0 & 0 & 1 
 \end{matrix} 
 \right])$$
 is invertibility when $\lambda>0$.
 
# Regularized Logistic Regression
$$
J(\theta)=-[\frac{1}{m}\sum\limits_{i=1}^mylog(h_\theta(x))+(1-y)log(1-h_\theta(x))]+\frac{\lambda}{2m}\sum \limits_{j=1}^n\theta_j^2$$

>repeat until convergence{
>$\theta_0:=\theta_0-\alpha\frac{1}{m}\sum \limits_{i=1}^{m}(h_\theta(x^{(i)})-y^{(i)})x^{(i)}_0$
	$\theta_j:=\theta_j-\alpha[\frac{1}{m}\sum \limits_{i=1}^{m}(h_\theta(x^{(i)})-y^{(i)})x^{(i)}_j+\frac{\lambda}{m}\theta_j]$
	(simultaneously update for every $j=1,...,n$)
} 
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE0Mjc4NTUyMzJdfQ==
-->