
## Exercise 1

A policy is a rule used by the agent to decide what actions to take. There are two main types of policies:
1. **Deterministic**: Model output is fully determined by its inputs
2. **Stochastic**: Model possesses some inherent randomness

Stochastic Policies are further subdivided into two main branches:
1. **Categorical**: Used in discrete action spaces
2. **Diagonal Guassian**: Used in continuous action spaces

There are two key computations which are especially important for training stochastic policies:

+ sampling actions from the policy,
+ computing log likelihoods of particular actions



We are tasked with creating a TensorFlow symbol for computing the log-likelihoods of a batch of diagonal Gaussian distributions.

### What is a Diagonal Gaussian Distribution?

A Gaussian distribution or a normal distribution is a continuous probability distribution.

A multivariate Gaussian distribution is described by 

+ μ is the mean of the distribution
+ σ is the standard deviation
+ σ² is the variance
+ ∑ is the covariance matrix

A diagonal Gaussian distribution is a special case where the covariance matrix only has entries on the diagonal. This can be represented by a vector. 

### What is the log-likelihood?

First of all, we compute the log standard deviations instead of standard deviations as log stds are easier to work with since they are free to take on any values between negative infinity and positive infinity.

The natural logarithm of the likelihood function is called the log-likelihood. Since the logarithm is a strictly increasing function the logarithm of a function achieves its maximum value at the same points as the function itself.

Therefore the log-likelihood can be used in place of the likelihood in maximum likelihood estimation.


### Solution 

To compute the log-likelihoods we use the following equation:

![alt-text](https://spinningup.openai.com/en/latest/_images/math/003c0eae9ef9660bf067815175ddd51b487c5191.svg)

---
