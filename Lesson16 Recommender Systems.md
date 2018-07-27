# Problem Formulation

![enter image description here](https://lh3.googleusercontent.com/bam6g1xOTfLCyVyuyaQ2RJSfrXy07gh6qKw_SfukhdP2ei8PWVpHQnSO8JUxM1r4IUFpn46aCyoe)

# Content Based Recommendations

![enter image description here](https://lh3.googleusercontent.com/th_lhTYdyy2AbfDCBxH3xwPK9rLXlndJJAv0eFiXonY_Kqwj5efrnVz3PZjPokydszaggNjpPYGP)
![enter image description here](https://lh3.googleusercontent.com/4B9av8NPJ-QyAIUFwl6CzT1hqIyatkc3BydlFWDn_MJ0PwEBhV70oc4wO0NqrAh7gNrdoa0rwAWT)
![enter image description here](https://lh3.googleusercontent.com/yhEwmlQa6ybroAlL0eCzRjBgPsAWF67oh_9A14NVoysgIVfN342xqTEdj0c3RhIKEecvm9K_WExP)
![enter image description here](https://lh3.googleusercontent.com/m0eQhb-QMIuQns0KORdr7x_ySOSSq6oOf97SusopySatHRF0UvBVFms6lfQmX8D3tPKLXd64JxRk)

# Collaborative Filtering

![enter image description here](https://lh3.googleusercontent.com/_7KKwcXDbdVoukUMc8zSDmYb7Fwp2lyIMJaXKSz38EfKbt7Nxq_wlUIoJiaGbcBq82vRh54tyM-9)
![enter image description here](https://lh3.googleusercontent.com/GOetGYQStGdM2WECJQ6Cgf0PZf5rusNE8HgHfwW0cQ9BfKZ-YzkyRyX5RNOo5h6pLUdaeAEcON3-)
![enter image description here](https://lh3.googleusercontent.com/skyPI_SFafAUy9RO5wqm04v04-ycA_T23HzLWTxCZuGLjF8EbiW5V3iNp7YRYT0hmORNkfMlt8F3)

# Collaborative Filtering Algorithm

![enter image description here](https://lh3.googleusercontent.com/0DQQ3PXqWNcrgeyOJbnSFTpBXHgf1LGgD6MN8s-Ql7HEscm8NimUXxXksVsoQ7tvzAUiYg6ClHJt)
Here, we ignore the feature $x_0=1$ and the parameter $\theta_0$. It means that $\theta\in\Re^n,x\in\Re^n$. Because if we need a feature fixed at 1, the algorithm will learn by itself.
![enter image description here](https://lh3.googleusercontent.com/rcklwMewr4kCu100kSuANEBSTfT0O1lLF94-zQ1Wg0Sa0KMIWWAM-9G5ka5Knqp6wt9CMvAfiRRp)

# Vectorization: Low Rank Matrix Factorization

![enter image description here](https://lh3.googleusercontent.com/PEjxjtsndVXU2pM0I3epDjTcUL4CqAuBK8yGimHZD-LmiEZaNgb8t23rYkBBxBZxXuBezr8YTb_Y)
$X\Theta^T$ is a low rank matrix.
We may never know what the features we learned mean.
![enter image description here](https://lh3.googleusercontent.com/nL4hgzsNpvnAKcfvKF-SnK4ksjb98stHEaJiGML2tRjnIG5k2rCi6CX18tUs4a5PnIlwWQBygNn1)

# Implementational Detail: Mean Normalization


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3NTI3OTc1MzUsLTE0NzM1NjMzNTAsLT
ExNjEwNDA5MTAsLTMxMzg0ODg2MiwyMTA0ODE0NDEwLDE5MDU0
NDg2MjMsMTY4Mzk4NjY1NywtOTExMjE4MTE4LC0xNzg5NzMxMT
I5LDE0NjE3NTAyMDgsLTQzNTkxNTc2N119
-->