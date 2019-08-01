{% include lib/mathjax.html %}

# Conjugate Distributions

If the posterior distributions are in the same probability distribution family as the prior probability distribution, the prior and posterior are then called conjugate distributions, and the prior is called a conjugate prior for the likelihood function.

$$p(\theta|x)=\frac{\displaystyle p(x|\theta)p(\theta)}{\displaystyle p(x)}$$

The likelihood function is usually considered fixed; the likelihood function is usually well-determined from the data-generating process. For certain choices of the prior, the posterior has the same algebraic form as the prior (generally with different parameter values). Such a choice is a conjugate prior.

A conjugate prior is an algebraic convenience, giving a closed-form expression for the posterior; otherwise numerical integration may be necessary. Further, conjugate priors may give intuition, by more transparently showing how a likelihood function updates a prior distribution.

## Examples

### Binomial Distribution

Binomial distribution with parameters $$n$$ and $$q$$ is the discrete probability distribution of the number of successes in $$n$$ independent Bernoulli trials with probability of success $$q$$. If $$n=1$$, the binomial distribution is a Bernoulli distribution.

If $$q$$ is the unknown parameter, the conjugate prior is the beta distribution with parameters $$\alpha$$ and $$\beta$$:

$$p(q)=\frac{\displaystyle q^{\alpha-1}(1-q)^{\beta-1}}{\displaystyle \text{B}(\alpha, \beta)}$$

where $$\alpha$$ and $$\beta$$ are chosen to reflect any existing belief or information ($$\alpha=1$$ and $$\beta=1$$ would give a uniform distribution) and $$\text{B}(\alpha,\beta)$$ is the beta function acting as a normalizing constant.

If we observe $$s$$ successes and $$f$$ failures, the posterior distribution is another beta distribution with parameters $$\alpha+s$$ and $$\beta+f$$. This posterior distribution could then be used as the prior for more samples, with the hyper-parameters simply adding each extra piece of information as it comes.

### Possion Distribution

Possion distribution is a discrete probability distribution that expresses the probability of a given number of events occurring in a fixed interval of time or space if these events occur with a known constant rate and independently of the time since the last event:

$$P(k\text{ events in interval})=\frac{\displaystyle \lambda^k e^{-\lambda}}{\displaystyle k!}$$

If $$\lambda$$ is the unknown parameter, the conjugate prior is the gamma distribution with parameters $$\alpha$$ and $$\beta$$:

$$p(\lambda)=\frac{\displaystyle \beta^\alpha \lambda^{\alpha-1}e^{-\beta \lambda}}{\displaystyle \Gamma(\alpha)}$$

where $$\Gamma(\alpha)$$ is the gamma function.

### Multinomial Distribution

The multinomial distribution is a generalization of the binomial distribution. For $$n$$ independent trials each of which leads to a success for exactly one of $$k$$ categories, with each category having a given fixed success probability, the multinomial distribution gives the probability of any particular combination of numbers of successes for the various categories. When $$k=2$$ and $$n>1$$, it is the binomial distribution. When $$k>2$$ and $$n=1$$, it is the categorical distribution.

For a multinomial distribution with parameters $$n$$ and $$\rm\bf p$$, where $${\rm\bf p}=(p_1,\dots,p_k)$$,

$$p(x_1,\dots,x_k)=\frac{\displaystyle n!}{\displaystyle x_1!\cdots x_k!}p_1^{x_1}\times\cdots\times p_k^{x_k},\text{    when }\sum_{i=1}^k x_i=n$$

for non-negative integers $$x_1,\dots,x_k$$.

If $$\rm\bf p$$ is the unknown parameter, the conjugate prior is the Dirichlet distribution with parameters $$\boldsymbol\alpha$$:

$$p(p_1,\dots,p_k)=\frac{\displaystyle 1}{\displaystyle \text{B}({\boldsymbol\alpha})}p_1^{\alpha_1-1}\times\cdots\times p_k^{\alpha_k-1}$$

where the normalizing constant is the multivariate beta function.

### Multivariate Normal Distribution

The multivariate normal distribution of a $$k$$-dimensional random vector with parameters $$\boldsymbol \mu$$ and $$\boldsymbol \Sigma$$ follows

$$p(x_1,\dots,x_k)=\frac{\displaystyle \text{exp}\left(-\frac{1}{2}({\rm\bf x}-{\boldsymbol \mu})^{\text{T}}{\boldsymbol\Sigma}^{-1}({\rm\bf x}-{\boldsymbol \mu})\right)}{\displaystyle \sqrt{(2\pi)^k\text{det}{\boldsymbol\Sigma}}}$$

If $$\boldsymbol\mu$$ is the unknown parameter, the conjugate prior is also a multivariate normal distribution. Such distributions are called self-conjugate.

## Pseudo-observations

It is often useful to think of the hyperparameters of a conjugate prior distribution as corresponding to having observed a certain number of pseudo-observations with properties specified by the parameters. In general, for nearly all conjugate prior distributions, the hyperparameters can be interpreted in terms of pseudo-observations. This can help both in providing an intuition behind the often messy update equations, as well as to help choose reasonable hyperparameters for a prior.

[Go Back to Index](https://laming-chen.github.io/index)
