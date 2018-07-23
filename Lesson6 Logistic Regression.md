# Hypothesis Representation
"Sigmoid Function," also called the "Logistic Function": $g(z)=\frac{1}{1+e^{-z}}$
**Logistic regression model:**

$h_\theta=\frac{1}{1+e^{-\theta^Tx}}$
**Interpretation of hypothesis output:** 
$h_\theta=$ estimated probability that y = 1 on input x. 
$h_\theta=P(y=1|x;\theta)$.
$P(y=0|x;\theta)=1-P(y=1|x;\theta)$

# Decision Boundary
The **decision boundary** is the line that separates the area where $y = 0$ and where $y = 1$. It is created by our hypothesis function.
Suppose predict 
- "$y = 1$" when $h_\theta\ge0.5$, $h_\theta\ge0.5$ when and only when $\theta^Tx\ge0$.
- "$y = 0$" when $h_\theta<0.5$, $h_\theta<0.5$ when and only when $\theta^Tx<0$.

Decision boundary is decided by $\theta$.
Again, the input to the sigmoid function g(z) (e.g.  $\theta^TX$) doesn't need to be linear, and could be a function that describes a circle (e.g.  $z=\theta_0+\theta_1x_1^2+\theta_2x_2^2$) or any shape to fit our data.
e.g. $x = [1;x_1;x_2;x_1^2;x_2^2]$,$\theta=[1;0;0;1;1]$, then the boundary is $x_1^2+x_2^2=1$

# Cost Function
To attempt classification, one method is to use linear regression and map all predictions greater than 0.5 as a 1 and all less than 0.5 as a 0. However, this method doesn't work well because classification is not actually a linear function.

$J(\theta)=\frac{1}{m}\sum \limits_{i=1}^mcost(h_\theta(x^{(i)}),y^{(i)})$
- For linear regression, $cost(h_\theta(x),y)=\frac{1}{2}(h_\theta(x)-y)^2$.But when we use it into logistic regression, where $h_\theta=\frac{1}{1+e^{-\theta^Tx}}$, we will get a non_convex $J(\theta)$, which has many local optima.
- For logistic regression, define $$cost(h_\theta(x),y)=  
\begin{cases}  
-log(h_\theta(x))& \text{if y = 1}\\  
-log(1-h_\theta(x))& \text{if y = 0}  
\end{cases}$$
we can prove that $J(\theta)$ is a convex function, which has only one global optimum.

# Simplified Cost Function and Gradient Descent
$cost(h_\theta(x),y)=-ylog(h_\theta(x))-(1-y)log(1-h_\theta(x))$

**Hypothesis**
$h_\theta=\frac{1}{1+e^{-\theta^Tx}}$
**Cost function**
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

$\theta:=\theta-\frac{\alpha}{m}X^T(g(X\theta)-y)$ (in Matlab)
The gradient descend algorithm is the same as the one in linear regression, but $h_\theta=\frac{1}{1+e^{-\theta^Tx}}$ here while $h_\theta=\theta^Tx$ in linear regression.

# Advanced Optimization

**Optimization algorithms:**

- Gradient descent;
- Conjugate gradient;
- BFGS;
- L-BFGS

**Advantages:**

- No need to manually pick $\alpha$
- Often faster than gradient descent

**Disadvantages:**

- more complex

How to use advanced optimization?
e.g. $J(\theta)=(\theta_1-5)^2+(\theta_2-5)^2$
> function[jval, gradient] = costFunction(theta)
> jval = (theta(1)-5)^2+...
>           (theta(1)-5)^2
> gradient = zeros(2,1);
> gradient(1)= 2*(theta(1)-5);
> gradient(2)= 2*(theta(2)-5);

>options = optimset('GradObj', 'on', 'MaxIter', 100);

>initiaTheta = zeros(2,1);

>[optTheta, functionval, exitFlag]=...
>fminunc(@costFunction, initialTheta, options);

# Multiclass Classification
**One-vs-all**
Train a logistic regression classifier $h_\theta^{(i)}$ for each class $i$ to predict the probability that $y = i$.
 $h_\theta^{(i)}=P(y=i|x;\theta)$ 
On a new input $x$, to make a prediction, pick the class $i$ that maximizes $\max \limits_ih_\theta^{(i)}(x)$
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTExMjM2NDczLDcyNDA3MDM4OSwtMTgwMD
c5OTQ0MSw4MTQ4NzEyNTQsLTY4NTc5OTg5MywtMTAyNTgxOTc5
NiwtMTgxMjgxNTM5MywtNTc5MTM4MDk2LDE4NTcxNjIwNywtMj
A2NDk3MzA1MCwtMTM2NzAyNjU3NiwtMTIyMTMyNzUyMSw5NDAy
MjY2XX0=
-->