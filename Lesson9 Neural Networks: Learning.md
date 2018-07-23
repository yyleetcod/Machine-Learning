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
In fact, $\delta_j^{(l)}=\frac{\partial}{\partial z_j^{(l)}}cost^{(i)}$
Then, $\frac{\partial}{\partial\Theta_{ij}^{(l)}}J(\Theta)=a_j^{(l)}\delta_i^{(l+1)}$

$cost^{(i)}=-y^{(i)}log(h_\theta(x^{(i)}))-(1-y^{(i)})log(1-h_\theta(x^{(i)}))$

For each output unit(layer L = 4)
$\delta_j^{(4)}=a_j^{(4)}-y_i$
$\delta_j^{(3)}=(\Theta^{(3)})^T\delta^{(4)}.*g'(z^{(3)})=(\Theta^{(3)})^T\delta^{(4)}.*a^{(3)}.*(1-a^{(3)})$
$\delta_j^{(2)}=(\Theta^{(2)})^T\delta^{(3)}.*g'(z^{(2)})=(\Theta^{(2)})^T\delta^{(3)}.*a^{(2)}.*(1-a^{(2)})$
**Note**: We don't associate an error term with the input layer($\delta^{(1)}$)

Then, $\frac{\partial}{\partial\Theta_{ij}^{(l)}}J(\Theta)=a_j^{(l)}\delta_i^{(l+1)}$
![enter image description here](https://lh3.googleusercontent.com/HPIWWws2FQmhvh7-pKg9TR4j6--o-EC6LCZ3I6ZEDmx6_OJtd-QxrAdDEYncCCMNIg9q78zlm3A)


**Back propagation algorithm**
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

# Gradient Checking
![enter image description here](https://lh3.googleusercontent.com/I1rbHB80EA0JKmPvIaXJGEWXEg_O669R7rQJY5ecZUiPHd932OD8VQcqegcpuvZI70idMLUOVIc)
![enter image description here](https://lh3.googleusercontent.com/khiZhhDb_JtNRDjF6wchFfC67y2pESDSHB8iavv0r1Scq4VbK6QRdScZ21C2-el-_vZOV9DbUaw)
![enter image description here](https://lh3.googleusercontent.com/UClWOB3pOdjaWZ6ijKMsiORIHcyEQ_B-b3jwA8BqCzCURPIv0qQ-Ys9PREE6_py5bYgsegbYGSM)
![enter image description here](https://lh3.googleusercontent.com/7odNCOMqt9GfCN8rUmx9OCNnnSptQCXvluaDGBRmbtwNTUCGzYkOpSJgz155oKWXLJNt_cQjVyc)

# Random Initialization
![enter image description here](https://lh3.googleusercontent.com/-hhkn7fv2u3x2odWS5E2R5dAkxdU5wEvRruzEBVYLstgvIA_-W9ymCLyKLKKA4-WhuqlpXN9E8Y)
Initializing all theta weights to zero does not work with neural networks. When we backpropagate, all nodes will update to the same value repeatedly. Instead we can randomly initialize our weights for our $\Theta$ matrices using the following method:
![enter image description here](https://lh3.googleusercontent.com/2lkcfKVUDw5f8QRk_uJBQJ164Lk_GNyQovVGi5IhU2aftHAC1kZpvfra2uX3Sa4ZorgcRcZgAuU)

# Put It Together
![enter image description here](https://lh3.googleusercontent.com/sVHBVoqwD904GfstFgRoL3viXBxm9DuBOqmY_r8NHn9hSOzqyTymwD1N2I0z6UcwXkUuZ7X_2Tg)
![enter image description here](https://lh3.googleusercontent.com/Ee5OGbw-AqzpYKtShiXdA2nAo379Z_7GphnvR0rcesMKzaDDh_YjVa2lNKTH16cOQl7EoNd_3lo)
![enter image description here](https://lh3.googleusercontent.com/7MQpgqPjKyQ5CCHr5IljTZybUKet1J2ZhNaocyUgA0YqMEMogZPF6Cjc8ET3MwUv7gz6KlnVRIA)

First, pick a network architecture; choose the layout of your neural network, including how many hidden units in each layer and how many layers in total you want to have.

-   Number of input units = dimension of features  $x^{(i)}$
-   Number of output units = number of classes
-   Number of hidden units per layer = usually more the better (must balance with cost of computation as it increases with more hidden units)
-   Defaults: 1 hidden layer. If you have more than 1 hidden layer, then it is recommended that you have the same number of units in every hidden layer.

**Training a Neural Network**

1.  Randomly initialize the weights
2.  Implement forward propagation to get  $h_\Theta(x^{(i)}$)  for any  $x^{(i)}$
3.  Implement the cost function
4.  Implement backpropagation to compute partial derivatives
5.  Use gradient checking to confirm that your backpropagation works. Then disable gradient checking.
6.  Use gradient descent or a built-in optimization function to minimize the cost function with the weights in theta.

When we perform forward and back propagation, we loop on every training example:
```
for i = 1:m,
   Perform forward propagation and backpropagation using example (x(i),y(i))
   Get activations a(l) and delta terms d(l) for l = 2,...,L
   ```
   Ideally, you want $h_\Theta(x^{(i)}) \approx y^{(i)}$. This will minimize our cost function. However, keep in mind that $J(\Theta)$ is not convex and thus we can end up in a local minimum instead.
<!--stackedit_data:
eyJoaXN0b3J5IjpbODgxMDgxOTQ1LDE0OTA2ODg2MywtNTU2Mz
A3MzE5LC0xNjY4MDQ0NjE0LDIwNDg3NjIyNjcsLTEwOTk4MzA4
NzcsLTEwODA5Mzc4MjIsLTE4MDg3ODEwMCwtOTU5NTM3MDgyLC
0xMjQ4MTA5NzM3LDY5OTMyOTQyOCwxODYwOTM3NDg5XX0=
-->