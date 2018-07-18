# Model Selection and Train/Validation/Test Sets
![enter image description here](https://lh3.googleusercontent.com/kJXNYkQLHGG7LbppzjfPDvRv754SnpCynXJlue_hsb7sCurR-5xBMgXUB3LimOG85v0UtV2OF0g)
One way to break down our dataset into the three sets is:

-   Training set: 60%
-   Cross validation set: 20%
-   Test set: 20%

We can now calculate three separate error values for the three different sets using the following method:

1.  Optimize the parameters in $\Theta$ using the training set for each polynomial degree.
2.  Find the polynomial degree d with the least error using the cross validation set.
3.  Estimate the generalization error using the test set with $J_{test}(\Theta^{(d)})$, ($\Theta^{(d)}:$ from polynomial with lower error);
# Diagnosing Bias vs. Variance
![enter image description here](https://lh3.googleusercontent.com/beTGeArw5TayCfVykKOtIg6itLRsC7tMJltl9xoAQHrJPGZsZO65eEV_r1C9iyBOOtSD_kDn_L8)

# Regularization and Bias/Variance
![enter image description here](https://lh3.googleusercontent.com/6dp7_UKdi6l6e8Airrqu7UfQ5wPkgGlWMiAWhDVLewWCGzc7w3jdVjbtEDljP5KQxi9jQS-SrQM)
![enter image description here](https://lh3.googleusercontent.com/BOLkogc0PP_1azr7A1El-AtblGPG_WnTPL7BU9ROSpE4juFK5YbeuVN_mXgPL4KrZKHy0M7uIKE)
![enter image description here](https://lh3.googleusercontent.com/o_RE00gBhg-ZnnFrvRffKED7cxiiZfwgcj6w3Rpj43psUvXKkqhyYOmdh78iBXPuIvUD_KKMTcA)

# Learning Curves

![enter image description here](https://lh3.googleusercontent.com/5QTuKqI_0xoqVhSByFoWDIyuFxHhJKpDr_yQE3IxrUyoZOQ9YvwhZD0HBLcPpotG73HJbWl7KEk)
![enter image description here](https://lh3.googleusercontent.com/pUqXO-7He2IOPL5moAnFo6Gxz3pLrrN1QUYUfcY2L0qFOLeiYRGNnyAdae5WZ3dWPvoiuVBOEOM)
![enter image description here](https://lh3.googleusercontent.com/O7rY_hN8Oc49weUlMwpcGdisrbNU_ikeP1N1U4eGrcfn3WiwI9mEk3PYWIj3kLPugEETopG4pPU)

# Deciding What to do Next Revisited
![enter image description here](https://lh3.googleusercontent.com/H7_wH31HxJ3Z52mN2qcv9GW5sAVtMy95mQWLuHSD1o36NHYSfL2QP5BZbqZYmFBkndGu326MD7g)
![enter image description here](https://lh3.googleusercontent.com/LVYAZhncz2DbmbI9YFlTBS3q0FaG4llT2NY4ZgRkp7PRbe5KGLVim8EKvUOtKSMUP_t0M6-DTN4)
**Model Complexity Effects:**

-   Lower-order polynomials (low model complexity) have high bias and low variance. In this case, the model fits poorly consistently.
-   Higher-order polynomials (high model complexity) fit the training data extremely well and the test data extremely poorly. These have low bias on the training data, but very high variance.
-   In reality, we would want to choose a model somewhere in between, that can generalize well but also fits the data reasonably well.


<!--stackedit_data:
eyJoaXN0b3J5IjpbOTk1MTkyMDY2LDc3NzIwNzA1OCwtMjAzOD
YwNTE5MSwtMTQ2MTY2Njg2OCwtMTgwNzE0MzA4MywxOTgwMjgw
MDI0LC01MDM5ODUzNzFdfQ==
-->