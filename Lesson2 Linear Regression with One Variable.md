# Cost Function
**Hypothesis**
$h_\theta=\theta_0+\theta_1x$

**Parameters**
$\theta_0$、$\theta_1$


**Cost Function**

$J(\theta_0,\theta_1)=\frac{1}{2m}\sum \limits_{i=1}^{m}(h_\theta(x^{(i)})-y^{(i)})^2$
used to measure the accuracy of our hypothesis function

**Goal**
$\min \limits_{\theta_0,\theta_1} J(\theta_0,\theta_1)$

$J(\theta_0,\theta_1)$: Bowl shaped surface
Contour figure/plots(等高图)

# Gradient descent
Arrived at a local optimum
Gradient descent algorithm
>repeat until convergence{
	$\theta_j:=\theta_j -\alpha\frac{\partial}{\partial\theta_j}J(\theta_0,\theta_1)$ (for $j=0$ and $j=1$)
}
$:=:$denote assignment
$\alpha:$learning rate, a positive number

>$\frac{\partial}{\partial\theta_j}J(\theta_0,\theta_1)=\frac{\partial}{\partial\theta_j}\{\frac{1}{2m}\sum \limits_{i=1}^{m}(h_\theta(x^{(i)})-y^{(i)})^2\}=\frac{\partial}{\partial\theta_j}\{\frac{1}{2m}\sum \limits_{i=1}^{m}(\theta_0+\theta_1x^{(i)}-y^{(i)})^2\}$
$j=0:\frac{\partial}{\partial\theta_0}J(\theta_0,\theta_1)=\frac{1}{m}\sum \limits_{i=1}^{m}(h_\theta(x^{(i)})-y^{(i)})$
$j=1:\frac{\partial}{\partial\theta_1}J(\theta_0,\theta_1)=\frac{1}{m}\sum \limits_{i=1}^{m}(h_\theta(x^{(i)})-y^{(i)})x^{(i)}$
repeat until convergence{
	$\theta_0:=\theta_0-\alpha\frac{1}{m}\sum \limits_{i=1}^{m}(h_\theta(x^{(i)})-y^{(i)})$
	$\theta_1:=\theta_1-\alpha\frac{1}{m}\sum \limits_{i=1}^{m}(h_\theta(x^{(i)})-y^{(i)})x^{(i)}$
}

we should simultaneously update $\theta_0$ and $\theta_1$
>$temp_0:=\theta_0 -\alpha\frac{\partial}{\partial\theta_0}J(\theta_0,\theta_1)$
$temp_1:=\theta_1 -\alpha\frac{\partial}{\partial\theta_1}J(\theta_0,\theta_1)$
$\theta_0:=temp_0$
$\theta_1:=temp_1$

**rather than**

>$temp_0:=\theta_0 -\alpha\frac{\partial}{\partial\theta_0}J(\theta_0,\theta_1)$
$\theta_0:=temp_0$
$temp_1:=\theta_1 -\alpha\frac{\partial}{\partial\theta_1}J(\theta_0,\theta_1)$
$\theta_1:=temp_1$

Gradient descent can converge to a local minimum, even with the $\alpha$ fixed. As we approach a local minimum, gradient descent will automatically take small steps. So, no need to decrease $\alpha$ over time.
If the goal function is a convex function, it doesn't have any local optima, except for the one global optima.

**"Batch" Gradient Descent**: Each step of gradient descent uses all the training examples.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE0MzIwMDUyMDgsLTE5MDc2MDUzMzYsLT
gzNjc1NDUwMV19
-->