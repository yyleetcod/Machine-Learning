# Cost Function
**Logistic regression**
$J(\theta)=-[\frac{1}{m}\sum\limits_{i=1}^mylog(h_\theta(x))+(1-y)log(1-h_\theta(x))]+\frac{\lambda}{2m}\sum \limits_{j=1}^n\theta_j^2$

**Neural network**
$J(\Theta)=-[\frac{1}{m}\sum\limits_{i=1}^m\sum\limits_{k=1}^K y_k^{(i)}log(h_\theta(x^{(i)}))_k+(1-y_k^{(i)})log(1-h_\theta(x^{(i)})_k)]+\frac{\lambda}{2m}\sum \limits_{l=1}^{L-1}\sum \limits_{i=1}^{s_l}\sum \limits_{j=1}^{s_{l+1}}(\Theta_{ji}^{(l)})^2$
$L=$ total no. of layers in network
$s_l=$ no. of units(not counting bias unit) in layer $l$
$K=$ no. of output units/classes

# Back Propagation Algorithm
**Goal**:$\min \limits_\Theta J(\Theta)$
Need code to compute 

- $J(\Theta)$
- $\frac{\partial}{\partial\Theta_{ij}^{(l)}}J(\Theta)$

**Back propagation algorithm**
$\delta_j^{(l)}=$ "error" of node $j$ in layer $l$

For each output unit(layer L = 4)
$\delta_j^{(4)}=a_j^{(4)}-y_i$
$\delta_j^{(3)}=(\Theta^{(3)})^T\delta^{(4)}.*g'(z^{(3)})=(\Theta^{(3)})^T\delta^{(4)}.*a^{(3)}.*(1-a^{(3)})$
$\delta_j^{(2)}=(\Theta^{(2)})^T\delta^{(3)}.*g'(z^{(2)})=(\Theta^{(2)})^T\delta^{(3)}.*a^{(2)}.*(1-a^{(2)})$
**Note**: We don't associate an error term with the input layer($\delta^{(1)}$)

Then, $\frac{\partial}{\partial\Theta_{ij}^{(l)}}J(\Theta)=a_j^{(l)}\delta_i^{(l+1)}$

Training set $\{(x^{(1)},y^{(1)}),...,(x^{(m)},y^{(m)})\}$
Set $\Delta_{ij}^{(l)}=0$(for all $l,i,j$)(use to compute $\frac{\partial}{\partial\Theta_{ij}^{(l)}}J(\Theta)$)
For $i=1$ to $m$
- Set $a^{(1)}=x^{(i)}$
- Perform forward propagation to compute $a^{(l)}$ for $l=2,3,...,L$
- Using $y^{(i)}$, compute $\delta^{(L)}=a^{(L)}-y^{(i)}$
- Compute $\delta^{(L-1)},\delta^{(L-2)},...,\delta^{(2)}$
- $\Delta_{ij}^{(l)}:=\Delta_{ij}^{(l)}+a_j^{(l)}\delta_i^{(l+1)}$ or $\Delta^{(l)}:=\Delta^{(l)}+\delta^{(l+1)}(a^{(l)})^T$


Update $D{ij}^{(l)}$:
$$
D{ij}^{(l)}=\frac{1}{m}
\begin{cases}  
\Delta_{ij}^{(l)}+\lambda\Theta_{ij}^{(l)}& \text{if $j\ne0$}\\
\Delta_{ij}^{(l)}& \text{if $j=0$}
\end{cases}
$$

Then $\frac{\partial}{\partial\Theta_{ij}^{(l)}}J(\Theta)=D_{ij}^{(l)}$
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTk1OTUzNzA4MiwtMTI0ODEwOTczNyw2OT
kzMjk0MjgsMTg2MDkzNzQ4OV19
-->