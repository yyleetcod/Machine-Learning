# Prioritizing What to Work on
**System Design Example:**

Given a data set of emails, we could construct a vector for each email. Each entry in this vector represents a word. The vector normally contains 10,000 to 50,000 entries gathered by finding the most frequently used words in our data set. If a word is to be found in the email, we would assign its respective entry a 1, else if it is not found, that entry would be a 0. Once we have all our x vectors ready, we train our algorithm and finally, we could use it to classify if an email is a spam or not.

So how could you spend your time to improve the accuracy of this classifier?

-   Collect lots of data (for example "honeypot" project but doesn't always work)
-   Develop sophisticated features (for example: using email header data in spam emails)
-   Develop algorithms to process your input in different ways (recognizing misspellings in spam).

It is difficult to tell which of the options will be most helpful.
# Error Analysis
The recommended approach to solving machine learning problems is to:

-   Start with a simple algorithm, implement it quickly, and test it early on your cross validation data.
-   Plot learning curves to decide if more data, more features, etc. are likely to help.
-   Manually examine the errors on examples in the cross validation set and try to spot a trend where most of the errors were made.

For example, assume that we have 500 emails and our algorithm misclassifies a 100 of them. We could manually analyze the 100 emails and categorize them based on what type of emails they are. We could then try to come up with new cues and features that would help us classify these 100 emails correctly. Hence, if most of our misclassified emails are those which try to steal passwords, then we could find some features that are particular to those emails and add them to our model.

It is very important to get error results as a single, numerical value. Otherwise it is difficult to assess your algorithm's performance. For example if we use stemming, which is the process of treating the same word with different forms (fail/failing/failed) as one word (fail), and get a 3% error rate instead of 5%, then we should definitely add it to our model. However, if we try to distinguish between upper case and lower case letters and end up getting a 3.2% error rate instead of 3%, then we should avoid using this new feature. Hence, we should try new things, get a numerical value for our error rate, and based on our result decide whether we want to keep the new feature or not.

# Error Metrics for Skewed Classes
![enter image description here](https://lh3.googleusercontent.com/QbtUHIhRYwpOcDKlndW2Q_r35p1pno3SECvVPqOPVCBwQvtxESuTuVVVTyQf1l10-XrwiGJlLHQ)

# Trading Off Precision and Recall
Predict $y=1$ if $h_\theta>$threshold 
Large threshold results in higher precision and lower recall.(avoid false positive)
Small threshold results in higher recall and lower precision.(avoid false negative)
![enter image description here](https://lh3.googleusercontent.com/eAKxSQ5ZzzkFgs_yIIjOgd5h7ZyVCE0s_0-8WvnQVxogFuNhklI5jPlD6D5cOOXVJ9oa6PWZSQA)
$P(precision)=\frac{\text{True positive}}{}$
$F_1 Score = \frac{2PR}{P+R}$
# Data For Machine Learning
![enter image description here](https://lh3.googleusercontent.com/81gHxZATB2QSnyg06OGa0_KzP578VArYgVPLMXYHeJhaGFxioIOVdQEm2c_bEfbggUXI3NC7XRI)
![enter image description here](https://lh3.googleusercontent.com/tXsCKrgJQobjPJzBl0wib9B5bQ1jbK2vO5bu3bTc0UDZyEBmlqspLA1xhnVzYkIGBHWmmoAwmD4)
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTIzMTkyMzEzMCwxNDYxNjc5MDIwLC0yNj
g1OTQwNTMsLTEzNTc0NTE2NzEsMjYwMTU4MjAzLDQ2NDU2NDM5
NywtMTUyODczMzM3MV19
-->