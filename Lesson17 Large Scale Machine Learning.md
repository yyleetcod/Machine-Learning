# Learning With Large Datasets

![enter image description here](https://lh3.googleusercontent.com/RCz_hWnN9gzm9fxT3JdzRQjnUeKCaqSsvVNWIU8a3cwqEWlDB8a2tKOpULYF-z-Q9WPlh669VvU3)
![enter image description here](https://lh3.googleusercontent.com/Kb7vFnl9gkCq-ztL7h0qy5Ei-BHzOtPwuJZkb4Z-PlfaJoGsbb3Z1YRPSsnRIOahK_PEKpkrnfq8)

# Stochastic Gradient Descent

![enter image description here](https://lh3.googleusercontent.com/3cv4hjTheGVT9he-7Zoh4dzzzcB2c2uAJHEmWbG1-cQLxcpyN5W4tgYqvs0fNB3FYRDKAOBByuNr)
![enter image description here](https://lh3.googleusercontent.com/frinOEvXDduLM3GTufHFRv1YrezY2u2qo5slmP3xUvsZJpTUX7g8g-JGbJoEie1SLyBemkNTQ3t_)
When we use stochastic gradient descent, firstly we should randomly shuffle the dataset to make it convergences faster.
![enter image description here](https://lh3.googleusercontent.com/l2-b9fu4bxF0Q2wW7UP4H49jZo1yFrh1GyO4zaOCDzqJCj-Vtd9Isi3_EEk2hF69VnoDGeGu3m-6)

# Mini-Batch Gradient Descent

![enter image description here](https://lh3.googleusercontent.com/Jdmxd5W6Vta2c-AkmSYbag2mLj1YxviGX4ptJagoSvLbkWPUA4nuFrPqY64uvQg_di_rIVW85fdR)
![enter image description here](https://lh3.googleusercontent.com/tAqsKrMm-qU2DHxKdoYX2VikDPYJcEr1CkazRONscwbCVdbfkN7DvJ_GpExcTg8kg3eCEKuJJvSk)
Mini-batch gradient descent may run faster than stochastic gradient descent because of vectorization.

# Stochastic Gradient Descent Convergence

![enter image description here](https://lh3.googleusercontent.com/HgT-tOFofXU_UrOabh8zwvwtr52vSV1hw9EAyUr0WdH3p_1zJaLz08yXrbpJj9smXcrqRkXHkNkM)
![enter image description here](https://lh3.googleusercontent.com/6Rx4TCZQHACu0GgDHo9bbJegMFAebbyIscoP6g5m3UvuWDth1xKaftBzfUG8aCMxojVSTtt8w0jV)
figure1. red: try smaller learning rate $\alpha$
figure2. red: try to use more data to average
figure3. the algorithm doesn't converge.
figure4. try smaller learning rate $\alpha$
![enter image description here](https://lh3.googleusercontent.com/BT9TjgpL8vi_yYxZtU50nECkPpyPO1wxedAgIXAtqL2PMczrMHi-Km5NZCVDEVgCZeds5cfXWhlk)

# Online Learning

![enter image description here](https://lh3.googleusercontent.com/BtEnMinl9ulK_xYE7nUtg2tpGpsjcyAtGtUeaXxdcBl4gnVcycM72cE12-DKENYlhGCbx-Uasmi0)
![enter image description here](https://lh3.googleusercontent.com/ge2Cc118TDzaF4XEXA_TwSEQ9FLGjFJj7I2qr3eSfAmerSo3dE72DGMdRRQSPsHFiaulDIhPxXfq)
We use mini-batch gradient descent where batch size equals to 10.

# Map Reduce and Data Parallelism

![enter image description here](https://lh3.googleusercontent.com/JTxHeZnYACRkzMgP-eAo16Un_AJUN04LFd6k1G5ln7GxLFcviUc8IZb4fEjQXFFJt5Jt3it2KWEA)
![enter image description here](https://lh3.googleusercontent.com/oaKPBq0EDeiUQ9510VbqzbHrJNvPwAzs9_IM1cBB7Axw0EIEwXSh5mKNCZZct1BSQWukapGZ7UG9)
![enter image description here](https://lh3.googleusercontent.com/ZFn8VkfoIoObobzujwfodaw8FcUN7b3v5A1sN1DFij6BVRyHqGcV2uaEbYYN1-57qZQp60XCjGZO)

<!--stackedit_data:
eyJoaXN0b3J5IjpbNzEzNzUyMjgxLDE1OTI0NDc1MTMsLTYxNT
MxODkyNiwtMTYzOTQ3ODExOSwxMTY5NzEwMDg1LDgyMTgxOTE1
MiwtNDYzODA0NjMwXX0=
-->