# Gradient Descent for Multiple variables
Denote $x^0=1$
**Hypothesis**
$h_\theta=\theta_0+\theta_1x_1+...+\theta_nx_n=\theta^Tx$

**Parameters**
$\theta_0$、$\theta_1$、...、$\theta_n$(or $\theta$)

**Cost Function**
$J(\theta)=\frac{1}{2m}\sum \limits_{i=1}^{m}(h_\theta(x^{(i)})-y^{(i)})^2$

**Goal**
$\min \limits_{\theta} J(\theta)$

**Gradient desend**
>repeat until convergence{
	$\theta_j:=\theta_j -\alpha\frac{\partial}{\partial\theta_j}J(\theta)$
} (simultaneously update for every $j=0,...,n$)

>repeat until convergence{
	$\theta_j:=\theta_j-\alpha\frac{1}{m}\sum \limits_{i=1}^{m}(h_\theta(x^{(i)})-y^{(i)})x^{(i)}_j$
} (simultaneously update for every $j=0,...,n$)

# Feature Scaling
**Ideal**: Make sure features are on a similar scale, so that it can be easier to converse.
Get every feature into appropriately a $-1{\le}x{\le}1$ range.
**Mean normalization**: Replace $x_i$ with $x_i-\mu_i$ to make features have approximately zero mean.(Do not apply to $x_0=1$).
$x_i:=\frac{x_i-\mu_i}{s_i}$(for every $i=1,2,...,n$)
$\mu_i$:average value of $x_i$ in training set
$s_i$:the range of $x_i$ in training set(max - min), or the standard deviation of $x_i$

# Learning Rate
- For sufficiently small $\alpha$, $J(\theta)$ should decrease after every iteration(have been proved). But if $\alpha$ is too small, gradient descent can be slow to converge.
If $\alpha$ is too small, slow convergence.  
if $\alpha$ is too large, $J(\theta)$ may not decrease on every iteration, may not converge.
- Example automatic convergence test: declare convergence if $J(\theta)$ decrease by less than $\epsilon(e.g.10^{-3})$ in one iteration.
- If gradient descent does't work, use smaller $\alpha$.

# Fatures and Polynomial Regression
e.g.   $h_\theta=\theta_0+\theta_1x+\theta_2x^2+\theta_3x^3$

# Normal Equation
Method to solve for $\theta$ analytically.


$$
x^{(i)}=
 \left[ 
 \begin{matrix} 
x_0^{(i)} \\ 
  x_1^{(i)}\\ 
  ...\\
  x_n^{(i)} 
 \end{matrix} 
 \right]
 \in\Re^{n+1}
 $$
 $$
X=
 \left[ 
 \begin{matrix} 
 (x^{(1)})^T \\ 
 (x^{(2)})^T\\ 
  ...\\
 (x^{(m)})^T 
 \end{matrix} 
 \right]
  \in\Re^{m\times(n+1)}
 $$
 $$
y=
 \left[ 
 \begin{matrix} 
y^{(1)} \\ 
  y^{(2)}\\ 
  ...\\
 y^{(m)} 
 \end{matrix} 
 \right]
 \in\Re^{m}
 $$
 $$
 \theta=(X^TX)^{-1}X^Ty \in\Re^{n+1}
 $$

|                |Gradient Descent|Normal Equation                        |
|----------------|-------------------------------|-----------------------------|
|Advantage|Work well even when $n$ is large.<br>$O(kn^2)$|No need to choose $\alpha$. <br> Don't need to iterate.|
|Disadvantage|Need to choose $\alpha$.<br>Need many iteration.|Need to compute $(X^TX)^{-1}$, which is $(n+1)\times(n+1)$ dimension.Time complexity $O(n^3)$<br> Slow if n is very large.|
With the normal equation, computing the inversion has complexity $O(n^3)$. So if we have a very large number of features, the normal equation will be slow. In practice, when n exceeds 10,000 it might be a good time to go from a normal solution to an iterative process.

# Normal Equation Noninvertibility

What if $X^TX$ is non-invertible?
- Redundant features (linearly dependent).
- Too many features (e.g. $m{\le}n$).(Delete some features, or use regularization.)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwMDkxNzEwODAsODUwMzE4NThdfQ==
-->