# Non-linear Hypothesis
When the number of features is very large, it's not a good idea to use logistic regression as a classifier. Now we should turn to neural networks.

# Model Representation
Sigmoid(logistic) activation function: $g(z) = \frac{1}{1+e^{-z}}$
$\theta$: weights\parameters
$x_0$: bias unit
Input layer, hidden layer, output layer
$a_i^{(j)}$: activation of unit i in layer j
$\Theta^{(j)}$: matrix of weights controlling function mapping from layer $j$ to layer $j+1$.
If network have $s_j$ units in layer $j$, $s_{j+1}$ unit in layer $j+1$, then $\Theta^{(j)}$ will be of dimension $s_{j+1}\times{(s_j+1)}$
The last hidden layer to output layer works like logistic regression, but it use $a^{(j)}_0,a^{(j)}_1,...,a^{(j)}_n$ as features instead of $x^{(j)}_0,x^{(j)}_1,...,x^{(j)}_n$

**Forward propagation**:
$z^{(j+1)}=\Theta^{(j)}{a^{(j)}}$
$a^{(j+1)}=g(z^{(j+1)})\in\Re^{n}$
add $a^{(j+1)}_0=1\in\Re^{n+1}$
In this **last step**, between layer j and layer j+1, we are doing **exactly the same thing** as we did in logistic regression. Adding all these intermediate layers in neural networks allows us to more elegantly produce interesting and more complex non-linear hypotheses.

$z=\theta_0+\theta_1x_1+\theta_2x_2+\theta_3x_3=\theta^Tx$
$a=h_\theta(z)=\frac{1}{1+e^{-z}}$
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTk4MTg3Njg0MywtNjUwNzIwODEwLDE0MD
c4MTQ2MTAsLTU3NDg1MTMzMyw5ODcxOTM4NjldfQ==
-->