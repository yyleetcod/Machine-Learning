# Hypothesis Representation
**Logistic regression model:**

$h_\theta=\frac{1}{1+e^{-\theta^Tx}}$
**Interpretation of hypothesis output:** $h_\theta=$ estimated probability that y = 1 on input x. In other word, $h_\theta=P(y=1|x;\theta)$.
$P(y=0|x;\theta)=1-P(y=1|x;\theta)$

# Decision Boundary
Suppose predict 
- "$y = 1$" when $h_\theta\ge0.5$, $h_\theta\ge0.5$ when and only when $\theta^Tx\ge0$.
- "$y = 0$" when $h_\theta<0.5$, $h_\theta<0.5$ when and only when $\theta^Tx<0$.
-

Decision boundary is decided by $\theta$.
e.g. $x = [1;x_1;x_2;x_1^2;x_2^2]$,$\theta=[1;0;0;1;1]$, then the boundary is $x_1^2+x_2^2=1$

# Cost Function
$J(\theta)=\frac{1}{m}\sum \limits_{i=1}^mcost(h_\theta(x^{(i)}),y^{(i)})$
- For linear regression, $cost(h_\theta(x),y)=\frac{1}{2}(h_\theta(x)-y)^2$.But when we use it into logistic regression, where $h_\theta=\frac{1}{1+e^{-\theta^Tx}}$, we will get a non_convex $J(\theta)$.
- For logistic regression, define $$cost(h_\theta(x),y)=  
\begin{cases}  
-log(h_\theta(x))& \text{if y = 1}\\  
-log(1-h_\theta(x))& \text{if y = 0}  
\end{cases}$$
we can prove that $J(\theta)$ is a convex function, which has only one global optimum.

# Simplified Cost Function and Gradient Descent
$cost(h_\theta(x),y)=-ylog(h_\theta(x))-(1-y)log(1-h_\theta(x))$
$$
J(\theta)=\frac{1}{m}\sum\limits_{i=1}^mcost(h_\theta(x^{(i)}),y^{(i)})=-\frac{1}{m}\sum\limits_{i=1}^mylog(h_\theta(x))+(1-y)log(1-h_\theta(x))$$(Max likehood estimation)

**Goal**
$\min \limits_\theta J(\theta)$
To make a prediction given new $x$: Output $h_\theta=\frac{1}{1+e^{-\theta^Tx}}$

**Gradient Desent**
>repeat until convergence{
	$\theta_j:=\theta_j -\alpha\frac{\partial}{\partial\theta_j}J(\theta)$
} (simultaneously update for every $j=0,...,n$)

>repeat until convergence{
	$\theta_j:=\theta_j-\alpha\frac{1}{m}\sum \limits_{i=1}^{m}(h_\theta(x^{(i)})-y^{(i)})x^{(i)}_j$
} (simultaneously update for every $j=0,...,n$)

Gradient descend is the same as the case in linear regression, but $h_\theta=\frac{1}{1+e^{-\theta^Tx}}$ here while $h_\theta=\theta^Tx$ in linear regression.

# Advanced Optimization

# 
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTE0NDc1Mjg0OCwtMTIyMTMyNzUyMSw5ND
AyMjY2XX0=
-->