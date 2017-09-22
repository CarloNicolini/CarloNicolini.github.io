---
layout: post
title: Full Undergraduate Course in Econometrics
categories: science
published: false
date: 2017-09-22
---

# [Populations and samples in econometrics](https://www.youtube.com/watch?v=M9s91hSoNtk&index=5&list=PLwJRxp3blEvZyQBTTOMFRP_TDaSdly3gU)

Econometrics is concerned with how do we come up with estimates of population parameters given a sample.

# [Estimators - the basics](https://www.youtube.com/watch?v=qvR7sSGphQ4&index=6&list=PLwJRxp3blEvZyQBTTOMFRP_TDaSdly3gU)

For example on average what is the effect of one year of education on wages? We only have a sample from the population, say 1000 individuals.
We want to study the linear relation between wages and education using the sample data, for example in the form:

$$wages = \alpha + \beta \textrm{education}$$

Sample estimators are indicated with an hat for example $$\hat{\beta}$$. The idea is to feed the sample data and it outputs the estimate of the population parameter.
There is difference between the estimator $$\hat{\beta}$$ (a function) and the population estimate $$\beta^\star$$ (just a point).

# [Estimators properties](https://www.youtube.com/watch?v=UxbY85Cm9SQ&list=PLwJRxp3blEvZyQBTTOMFRP_TDaSdly3gU&index=7)

What does it mean to be a good estimator?
The sample estimator aren't going to be exactly as the population parameters. In the frequency plot we hope that on average our estimator outputs the population parameters.
We should have the maximum in the frequency plot at the population parameter.
This property is called **unbiased**.

The second property is that increasing the sample size, the estimator are closer and closer to the true population parameter.
Eventually the distribution should become a delta centered in $$\beta^\star$$.
We call this property **consistency** of the estimator.
If I arbitrarily increase my sample size $$n\rightarrow +\infty$$ I get a value which is closer and closer to the population parameter.

# [Unbiasedness and consistency](https://www.youtube.com/watch?v=21lXGc02XwM&list=PLwJRxp3blEvZyQBTTOMFRP_TDaSdly3gU&index=8)

Often unbiasedness and consistency are mixed up but they are not the same.
Unbiasedness indicates that $$E[\hat{\beta}] = \beta^{population}$$.

Consistency means that if I increase the sample size the values I get to the estimator are closer and closer to the population value.
It is possible though to have an estimator that is **biased** but consistent.
Increasing the sample size the estimator gets closer to the population parameter and the estimator gets **consistent**.

It's pretty usual to have an estimator consistent but unbiased, as we don't often have the luxury of having the two properties together.

# [Unbiasedness vs consistency of estimators - an example](https://www.youtube.com/watch?v=6i7mqDJICzQ&index=9&list=PLwJRxp3blEvZyQBTTOMFRP_TDaSdly3gU)

As an example let's take a population with mean $\mu$ that we want to estimate with just a sample from the population.
Use some statistic tool to make some guess about the parameters.

Let's say that
$$
\tilde{x} = \frac{1}{N-1} \sum \limits_{i=1}^N x_i
$$
is this an unbiased estimator?
Given that we know the population process we can apply the expectation operator, then
$$
E[\tilde{x}] = \frac{1}{N-1} \sum \limits_{i=1}^N E[x_i] = \frac{1}{N-1} N \mu = \frac{N \mu}{N-1}
$$
so in general this does not equal $$\mu$$, so we should use the sample mean to estimate the sample mean.
Is this estimator consistent? Yes because in the case $N \rightarrow +\infty$$ the expected value of $$E[\tilde{x}] \rightarrow \mu$$.

So for example the biased estimator $$\tilde{x}$$ is biased but consistent.

# [Efficiency of estimators](https://www.youtube.com/watch?v=6i7mqDJICzQ&index=9&list=PLwJRxp3blEvZyQBTTOMFRP_TDaSdly3gU)

What is the efficiency of an estimator?
Suppose to have an unbiased estimator $$\hat{\beta}$$ and another estimator $$\tilde{\beta}$$ which outputs a range of $$\beta$$ closer to the parameter.
In this case the $$\tilde{\beta}$$ is more **efficient** than $$\hat{\beta}$$ and has to be preferred.

Although in real-world situations it's often the case that with a more efficient estimator has some degree of bias.

# [Good estimator properties summary](https://www.youtube.com/watch?v=uh4zUdKvxPA&index=11&list=PLwJRxp3blEvZyQBTTOMFRP_TDaSdly3gU)

1. Unbiased: $$E[\hat{\beta}] = \beta^{population}$$
2. Consistency: as $$n \rightarrow \infty$$ it must be $$\hat{\beta} \rightarrow \beta^{population}$$.
3. Efficiency
4. Linearity in parameters: $$\hat{\beta}$$ must be linear in parameters of the sample.

# [Lines of best fit in econometrics](https://www.youtube.com/watch?v=KIQbe-FJoa8&list=PLwJRxp3blEvZyQBTTOMFRP_TDaSdly3gU&index=12)
Fitting is a way to estimate population parameters. Suppose there is some relation between education years and wages. We hypothesize there is some positive correlation between the two.
How does education affects the average wage of an individual?
Doing that is like drawing a line through the points in the 2D space x-y. The line tells us how much increase of education is needed to have an y increase in wage.
The slope of the line is the $$\beta^{pop}$$.
This is a relation of the form $$y= \alpha + \beta x$$.

Now given a sample of the population, can I draw a line, i.e. draw an estimate of the population parameter (slope of the line).

# [The mathematics behind drawing a line of best fit](https://www.youtube.com/watch?v=YL-NNb4gojA&index=13&list=PLwJRxp3blEvZyQBTTOMFRP_TDaSdly3gU)

One idea is to fit a line to minimize the sum of distances between the line and the points.
Use $$x_i$$ to predict $$y_i$$.
For example 

$$ S = \sum \limits_{i=1}^N \|(y_i - \hat{y}_i)\| $$.

This allows us to get $$\hat{\alpha}$$ and $$\hat{\beta}$$. The sum has to have modulus here.
This is one way: the problem of the modulus function is that is hard to differentiate.
It's better using a square sum:

$$ S = \sum \limits_{i=1}^N (y_i - \hat{y}_i)^2 $$.

In minimizing the sum of the square I don't care about small deviations from the line as from big deviations from the line, so outliers counts a lot and anomalous points move the fitted line close to them because of the square contribution.
Perhaps we can generalize for example to the fourth-power

$$ S = \sum \limits_{i=1}^N (y_i - \hat{y}_i)^4 $$

This would count big deviations a lot more. There are many different ways to fit a straight line to data, but actually the default is the sum of squares minimization.

# [Least squares estimators as BLUE](https://www.youtube.com/watch?v=vOBtEiij-fA&index=14&list=PLwJRxp3blEvZyQBTTOMFRP_TDaSdly3gU)

What does it mean to **least squares** estimators to be good?
This means that I have built some sort of population and an underlying process in the population that connects wages with the average wage. The problem in econometrics is that we don't have the entire population but only a sample.
We use some mathematical functions to make inferences to have estimates of $$\alpha^{pop}$$ and $$\beta^{pop}$$.

For an estimator to be good it must be **unbiased**, **consistent** and **efficient**.
The condition for an estimator to be good are called **BLUE**.

BLUE stands for **B**est **L**inear **U**nbiased **E**stimator.
These assumptions are called the Gauss-Markov assumptions.
The least-square estimator is a BLUE estimator. There are no other linear estimator that give us good unbiased estimate of the parameters.

# [Deriving least squares estimators - part 1](https://www.youtube.com/watch?v=Hi5EJnBHFB4&index=15&list=PLwJRxp3blEvZyQBTTOMFRP_TDaSdly3gU)

The Least Squares estimator is defined as

$$ S = \sum \limits_{i=1}^N (y_i - \hat{y}_i)^2$$

Here the $$\hat{y}_i = \hat{\alpha} + \hat{\beta} x_i$$ while $$y=\mu x + c$$. This is equivalent to 

$$ S = \sum \limits_{i=1}^N (y_i - \hat{\alpha} \hat{\beta} x_i)^2$$

To mimimize $$S$$ we need to differentiate with respect to $$\hat{\alpha}$$ and $$\hat{\beta}$$. In other words we have to set:

$$
\frac{\partial S}{\partial \hat{\alpha}}=0, \frac{\partial S}{\partial \hat{\beta}}=0
$$

The derivative with respect to $$\hat{\alpha}$$ results:

$$
\begin{equation}
\frac{\partial S}{\partial \hat{\alpha}}= -2 \sum \limits_{i=1}^N(y_i - \hat{\alpha} - \hat{\beta} x_i) = 0 \tag{I}\label{eq:partiallsalpha}
\end{equation}
$$

the one with respect to $$\hat{\beta}$$ is:

$$
\begin{equation}
\frac{\partial S}{\partial \hat{\beta}}= -2 \sum \limits_{i=1}^N x_i (y_i - \hat{\alpha} - \hat{\beta} x_i = 0 \tag{II}\label{eq:partiallsbeta}
\end{equation}
$$

These two conditions give us the estimates $$\hat{\alpha}$$ and $$\hat{\beta}$$.

# [Deriving least squares estimators - part 2](https://www.youtube.com/watch?v=hGv9fnmlYaU&index=16&list=PLwJRxp3blEvZyQBTTOMFRP_TDaSdly3gU)

We want to derive some useful statistical relationships, they are

$$
\sum \limits_{i=1}^N x_i = N \bar{x} \qquad \sum \limits_{i=1}^N y_i = N \bar{y} 
$$

These corresponds to computing the sample mean of $$x$$ and $$y$$.
This relation instead

$$
\sum \limits_{i=1}^N (x_i - \bar{x})(y_i - \bar{y}) = \sum \limits_{i=1}^N y_i(x_i -\bar{x}) = \sum \limits_{i=1}^N x_i(y_i - \bar{y})
$$

corresponds to computing the covariance between $$x_i$$ and $$y_i$$. It can be rewritten as

$$
\sum \limits_{i=1}^N x_i y_i - \bar{y} \sum \limits_{i=1}^N x_i - \bar{x} \sum \limits_{i=1}^N y_i + \bar{x}\bar{y} \sum \limits_{i=1}^N 1
$$

but the second and term summands correspond to the sample mean times $$N$$, so we obtain:

$$
\sum \limits_{i=1}^N x_i y_i - N \bar{y}\bar{x} - N \bar{y}\bar{x} + N \bar{y}\bar{x} = \sum \limits_{i=1}^N x_i y_i - N \bar{x} \bar{y}
$$

and this leads to the above said relationships.

# [Deriving least squares estimators - part 3](https://www.youtube.com/watch?v=jF3_s2wqPGQ&index=17&list=PLwJRxp3blEvZyQBTTOMFRP_TDaSdly3gU)

We can now use the above mentioned relationships and apply the zero derivative conditions to obtain the LS estimators. We rewrite the conditions here:

$$
\frac{\partial S}{\partial \hat{\alpha}}= -2 \sum \limits_{i=1}^N(y_i - \hat{\alpha} - \hat{\beta} x_i) = 0
$$

$$
\frac{\partial S}{\partial \hat{\beta}}= -2 \sum \limits_{i=1}^N x_i (y_i - \hat{\alpha} - \hat{\beta} x_i) = 0
$$

We use the two relationships to obtain:

$$
N \bar{y} = \hat{\alpha}N + \hat{\beta}N \bar{x}
$$

and we obtain:

$$
\bar{y} = \hat{\alpha} + \hat{\beta} \bar{x} \tag{III}
$$

This tells me that the line of best fit goes through $$\bar{y}$$ and $$\bar{x}$$. We use the other conditions to derive the values of $$\hat{\alpha},\hat{\beta}$$.

# [Deriving Least Squares Estimators - part 4](https://www.youtube.com/watch?v=AIjuYfjU9dc&list=PLwJRxp3blEvZyQBTTOMFRP_TDaSdly3gU&index=18)

$$\hat{\alpha},\hat{\beta}$$ has to be chosen such that the line of best fit goes through the sample mean. We use the derivative w.r.t $$\hat{\beta}$$ to impose the second condition.


$$
\sum \limits_{i=1}^N x_i y_i = \hat{\alpha} N \bar{x} + \hat{\beta} \sum \limits_{i=1}^N x_i^2 = (\bar{y}-\hat{\beta} \bar{x} + \hat{\beta} \sum \limits_{i=1}^N x_i^2
$$

and we finally obtain

$$
\sum \limits_{i=1}^N x_i y_i = N \bar{x}\bar{y} - \hat{\beta}N \bar{x}^2 + \hat{\beta} \sum \limits_{i=1}^N x_i^2
$$

# [Deriving Least Squares Estimators - part 5](https://www.youtube.com/watch?v=JC0Tm9j-k80&index=19&list=PLwJRxp3blEvZyQBTTOMFRP_TDaSdly3gU)

These are the least squares estimators $$\hat{\alpha},\hat{\beta}$$. These are BLUE estimators.

$$
\begin{equation}
\hat{\alpha} = \bar{y} - \hat{\beta} \bar{x}
\end{equation}
$$

$$
\begin{equation}
\hat{\beta} = \frac{\textrm{Cov}(x_i,y_i)}{\textrm{Var}(x_i)}
\end{equation}
$$


# [Least Squares Estimators - in summary](https://www.youtube.com/watch?v=y5INeKvfpcQ&list=PLwJRxp3blEvZyQBTTOMFRP_TDaSdly3gU&index=20)

# [Taking expectations of a random variable](https://www.youtube.com/watch?v=6XqICKT1Kug&index=21&list=PLwJRxp3blEvZyQBTTOMFRP_TDaSdly3gU)

The expectation of a random variable is defined in the discrete case as:

$$
E[X] = \sum \limits_{x} P(X=x)X
$$

where $$x$$ is the set of all possible values that the variable $$X$$ can take, or also called the *support* of $$X$$.
In the case of a fair dice with 6 faces, this is obviously computed as $$P(X=1)1 + P(X=2)2 + \ldots + P(X=6)6 = 21/6 = 3.5$$

In the case of continuous random variable we use the integral over the support of the random variable:

$$
E[X] = \int \limits_{-\infty}^{\infty} f_x(X) dx
$$

where $$f_x(X)$$ is called the probability density function of the random variable $$X$$.

# [Moments of a random variable](https://www.youtube.com/watch?v=U2L809GBMcI&list=PLwJRxp3blEvZyQBTTOMFRP_TDaSdly3gU&index=22)

The higher order moment of a random variable 

$$
E[X^k] = \int \limits_{-\infty}^{+\infty} x^k f_x(X) dx
$$

This is called the $$k$$-th moment of the distribution. For example the $$4$$-th moment is interesting in statistics.

# [Central moments of a random variable](https://www.youtube.com/watch?v=BXN8jgQTjao&list=PLwJRxp3blEvZyQBTTOMFRP_TDaSdly3gU&index=23)

Suppose a p.d.f of a random variable peaked at 10. The expectation of such delta distributed variable is the integral of a Dirac delta function $$\delta(x-10)$$.
In this case the expectation of $$E[x^2]$$ is 100.
Instead the expectation of $$E[(x-10)^2]=0$$. This is called the second central moment of the distribution, or $$\textrm{Var}(X)$$. It's the spread of the points around the mean.
The variance of $$X$$ is computed as 

$$\mathrm{Var}[X] = E[(X-E[X])^2]$$

Higher order moments tell about the tails of the distribution.
The central moments of a distribution are indicated as: 

$$
\mu_k = E[(X-E[X])^k] = \int \limits_{-\infty}^{\infty}(x-\mu)^k f(x) dx
$$

1. The zeroth central moment $$\mu_0$$ is 1.
2. The first central moment $$\mu_1$$ is 0 (not to be confused with the first (raw) moment itself, the expected value or mean).
3. The second central moment $$\mu_2$$ is called the **variance**, and is usually denoted $$\sigma^2$$, where $$\sigma$$ represents the standard deviation.
4. The third and fourth central moments are used to define the standardized moments which are used to define **skewness** and **kurtosis**, respectively.

# [Kurtosis](https://www.youtube.com/watch?v=Pf7awGwzy4k&index=24&list=PLwJRxp3blEvZyQBTTOMFRP_TDaSdly3gU)

Kurtosis is the 4-th central moment of a distribution.
Two variables can have same expected value and variance but if one has a fatter tail it's impossible to say because variance is relative to points near the expected value.

$$\textrm{Kur}[X] = E\left[\left(\frac{(x-\bar{x})}{\sigma}\right)^4\right ] = \frac{\mu_4}{\sigma^4}$$

where $$\mu_4$$ is the fourth central moment and $$\sigma$$ is the standard deviation.
Typically one refers to the measure $$\Gamma$$:

$$\Gamma[X] = \frac{\textrm{Kur[X]}}{\sigma^4} - 3$$

where the $$-3$$ is called the excess kurtosis compared to the kurtosis of the normal distribution.

# [Skewness](https://www.youtube.com/watch?v=z3XaFUP1rAM&list=PLwJRxp3blEvZyQBTTOMFRP_TDaSdly3gU&index=25)

Skewness is the 3rd central moment of a distribution. Skewness refers to the symmetry of the random	variable around the mean: the distribution has long positive tails.

Skewness is computed as:

$$Skewness[X] = E[(x - \bar{x})^3]$$

# [Expectations and Variance properties](https://www.youtube.com/watch?v=NcJdOXuUdgU&list=PLwJRxp3blEvZyQBTTOMFRP_TDaSdly3gU&index=26)

We know the definition of the expectation of a random variable $$X$$ computed as 

$$
E[X] = \int \limits_{-\infty}^{\infty} f_x(X) dx
$$

The expectation operator is a **linear** operator. In other words $$E[a X + b Y] = a E[X] + b E[Y]$$.
Instead for the variance this is not true as

$$\textrm{Var}[aX] = E[(aX - a \mu_x )^2] = a^2 \textrm{Var}[X].$$

We can compute also how the variance behaves in the case of linear combination of random variables $$X,Y$$:

$$
\textrm{Var}[aX + bY] = E[(aX + bY - a \mu_x - b\mu_y)^2] = a^2 \textrm{Var}[X] + b^2 \textrm{Var}[Y] + 2ab \textrm{Cov}[X,Y]
$$

# [Covariance and correlation](https://www.youtube.com/watch?v=KDw3hC2YNFc&list=PLwJRxp3blEvZyQBTTOMFRP_TDaSdly3gU&index=27)

Let's think about if we had two random variance $$X,YY$$ such that if $$X$$ increases also $$Y$$ increases. Mathematically we can say that $$X$$ and $$Y$$ are positively correlated. In mathematical terms we define the covariance as 

$$
\textrm{Cov}[X,Y] = E[(X-\mu_x)(Y-\mu_y)]
$$

We can normalize the covariance using the **correlation** between $$X,Y$$: this is based on the division by the square root of the product of the variance of $$X$$ and $$Y$$ individually:

$$
\textrm{Corr}[X,Y] = \frac{\textrm{Cov}[X,Y]}{\sqrt{\textrm{Var}[X] \textrm{Var}[Y]}} := \rho
$$

the correlation is bounded in  $$[-1,1]$$.

# [Population vs sample quantiles](https://www.youtube.com/watch?v=fOAZQ_U7-qk&index=28&list=PLwJRxp3blEvZyQBTTOMFRP_TDaSdly3gU)
