{% include lib/mathjax.html %}

# Non-parametric Models

**Parametric models** assume some **finite** set of parameters $$\theta$$. Given the parameters, future predictions are independent of the observed data. Therefore $$\theta$$ captures everything about the data. So the complexity of the model is bounded even if the amount of data is unbounded.

**Non-parametric models** assume that the data distribution cannot be defined in terms of such a finite set of parameters. But they can often be defined by assuming an infinite dimensional $$\theta$$. Usually we think of $$\theta$$ as a **function**. The amount of information that $$\theta$$ can capture about the data can grow as the amount of data grows. This makes them more flexible.

## Gaussian Process

Gaussian processes define a distribution of functions

$$f\sim \text{GP}(\cdot|\mu,c)$$

where $$\mu$$ is the mean function and $$c$$ is the covariance function. We can think of Gaussian processes as "infinite-dimensional" Gaussians.

## Dirichlet Process

Dirichlet process is the infinite-dimensional generalization of the Dirichlet distribution. In other words, a Dirichlet process is a probability distribution whose range is itself a set of probability distributionns.

The Dirichlet process is specified by a base distribution $$H$$ and a positive real number $$\alpha$$ called the concentration paramster. The base distribution is the expected value of the process, i.e., the Dirichlet process draws distribution "around" the base distribution.

The formal difinition is given as follows. Given a measurable set $$S$$, a base probability distribution $$H$$ and a positive real number $$\alpha$$, the Dirichlet process $$\text{DP}(H,\alpha)$$ is a stochastic process whose sample path is a probability distribution over $$S$$, such that the following holds. For any measurable finite partition of $$S$$, denoted $$\{\text{B}_{i}\}_{i=1}^{n}$$, if $$X\sim\text{DP}(H,\alpha)$$, then

$$(X(B_1),\dots,X(B_n))\sim\text{Dir}(\alpha H(B_1),\dots,\alpha H(N_n))$$

where $$\text{Dir}$$ denotes the Dirichlet distribution.

[Go Back to Index](https://laming-chen.github.io/index)
