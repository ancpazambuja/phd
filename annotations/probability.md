# First Notes
There are several ways to explain the ideas below. Each author has chosen his own strategy depend on the target readers, goals and so on.
I have read some sources of information (wikipedia, youtube, books and lectures) with different levels of details and have tried to understand (I start knowing just the basics about probability and statistics) and have written down what I could understand. 

The main objective here is keeping a summary I think will be useful for me as a (somewhat) quick reference.

While writing this text, I have realized I prefer keep some mathematical formalism, as much as I can keep (and it is not too much).

But, as I mentioned before, there are ways of doing this. I choose to omit some fundamental knowledge in the main text, but keep in mind they are there implicitly. 
I will start with the notion of **probability space**, but behind it there are many concepts which builds the necessary mathematical fundations like:
- **$\sigma$-field** or $\sigma$-algebra  $\mathcal{F} \subseteq 2^\Omega$,
- **topology** $\mathcal{T} \subseteq 2^\Omega$,
- **measurable space**, $\\{\Omega, \mathcal{F}\\}$,
- **topological space**, $\\{\Omega, \mathcal{T}\\}$,
- **measure** $\mu : \mathcal{F} \rightarrow [0, \inf]$,
- **measure space** ($\Omega$, $\mathcal{F}$, \mu).
- **finite measure**,
- **$\sigma$-finite measure**,
- **measurable function**.

  

# Probability
Formally (somewhat), Kolmogorov defined these axioms below:

- K0: a non-deterministic experiment can be described by the probability space $(\Omega, \mathcal{F}, P)$, where:
  - $\Omega$ is the sample space (set of possible outcomes),
  - $\mathcal{F}$ is the set of possible events ( $\mathbb{P}(\Omega)$, power set of $\Omega$ ) and
  - $P: \mathcal{F} \rightarrow \mathbb{R}$ is the probability function.

- K1: Non-negativity::
  $$P(A) \geq 0, \forall A \in \mathcal{F}$$

- K2: Unit normalization::
  
  $$P(\Omega) = 1$$
  
- K3: Aditivity:: $A \cap B = \varnothing \rightarrow P(A \cup B) = P(A) + P(B)$

- K4: $\sigma$-Aditivity:: if $A_i$ are pairwise disjoint sets:

  $$P({\bigcup}_{i=1}^{\infty}A_i) =$$

  $$= P(A_1) + P(A_2) + \cdots = $$
  
  $$= {\sum}_{i=1}^{\infty}P(A_i)$$

## Random Variables
A random variable is a collection of outcomes from an experiment run several times under the same conditions. The outcomes are non-deterministic. 

A random variable X can be defined by enumeration: 

$X = \\{ x_1, x_2, x_3, x_4, ..., x_N \\}$ from which we can build a histogram. 

In this context, we can define: 

$P(X=x_i) = \frac{hist(x_i)}{N}$

For example, if we consider a fair die, we have:

$$\Omega = \\{ 1, 2, 3, 4, 5, 6 \\}$$

And we can think a random variable X as the result of rolling a die several times:

$$X = \\{ 2, 4, 2, 1, 5, 3, 4, 5, 6, 1, 6, 3 \\}$$ 

And we may ask the probability of getting an odd number:

$$P(X \text{ is odd}) = P( \\{1\\} \cup \\{3\\} \cup \\{5\\} ) = P(\\{1\\}) + P(\\{3\\}) + P(\\{5\\}) = \frac{hist(1) + hist(3) + hist(5)}{12} = \frac{6}{12} = 0,5$$

**Note 1:** "X is odd" is an event (e.g. $A=${1, 3, 5}).

**Note 2:** Formally a random variable is a measurable function $\mu : \Omega_1 \rightarrow \Omega_2$, where $\\{\Omega_1, \mathcal{F}_1\\}$ is a measurable space and $\\{\Omega_2, \mathcal{F}_2\\}$ is another measurable space.

  
## Classical View of Probability
**Laplace (1814)**

For equiprobable outcomes, $P(a) = \frac{1}{|\Omega|}; \forall a \in \Omega$. 
Thus, we use tools such as combinatorial analysis and set theory to count the number of outcomes in some event $A \in \mathcal{F}$ 
in order to calculate:

$$P(A) = \frac{|A|}{|\Omega|}$$ 

or 

$$P(A|B) = \frac{P(A \cap B)}{P(B)}$$

## Frequentist View of Probability
**Venn (1876)**

When outcomes are not equiprobable, one can count outcomes frequencies (histograms) in the limit of infinity experiments.

We use the notion of n-sample to describe a population. A n-sample is a random variable. 

Then, if we have a random variable $X = ${ $x_1, x_2, x_3, x_4, ..., x_N$ }$, we can write:

$$P(A) = \frac{n(A)}{n}$$

or 

$$P(A|B) = \frac{n(A \cap B)}{n(B)}$$

where $n(A)$ is the number of times A has happened in the sample.


### For Continuous Events 

One way to extend probability to continuous events is not defining a random variable by enumeration, but define it 
in terms of special functions. 

**Cumulative Distribution Function (CDF)**

$$F(x) = P(X < x) = {\int}_{-\infty}^{x} f(x')dx'$$

**Probability Density Function or Probability Distribution Function (PDF)**

From the __fundamental theorem of calculus__:

$$f(x) = F'(x) = {\lim}_{dx \rightarrow 0}\frac{F(x+dx) - F(x)}{dx} = $$

$$={\lim}_{dx \rightarrow 0}\frac{P(X < x+dx)- P(X < x)}{dx} = $$

$$={\lim}_{dx \rightarrow 0}\frac{P(x \leq X < x + dx)}{dx} $$

**Notes**

We can use the CDF inverse to compute quantiles.

We can use PDFs to compute the probability:

$$P(x \leq X < x+dx ) \approx f(x) = f(X=x)$$


### For Discrete Events
The same approach above can be used for discrete random variables.

**Probability Mass Function (PMF)**

$$p(x) = P(X=x)$$

# Statistical Inference

Statitiscal inference, or "learning" as it is called in computer science, is the process of using data to infer the distribution from which the data was generated.
 
So, in statistical learning, given a sample $X_1, X_2, X_3, ..., X_n \sim F$, how do we infer $F$?

**Philosophycal note**: 

In inference we see just the random variable, which is a mapping over the true measurable space $\\{\Omega_1\\, \mathcal{F}_1\\}$ to another measurable space $\\{\Omega_2\\, \mathcal{F}_2\\}$. We don't see the actual sample space $\Omega_1$ and yet we could learn the distribution over $\Omega_2$. This is similar of Plato called "Allegory of the cave".

## Statistical Model
A set, $\mathcal{F}$, of functions is a statistical model when these functions are distributions, regressions or densities. 

An statitiscal model may take the form $\mathcal{F} = \\{f_{\theta}(x) : \theta \in \Theta\\}$, where $f_{\theta}(x)$ means $f$ is parameterized by $\theta$ from a set $\Theta$ of possible parameters.

When $\theta$ has finite number of parameters we say the $\mathcal{F}$ if a **parametric model**. If $\mathcal{F}$ can't be defined by a finite number of parameters, we say $\mathcal{F}$ is a **nonparametric model**. 

An example of parametric model could be a family of linear functions:

$$\mathcal{F} = \\{ f_{m,b}(x) = mx + b; m \in \mathbb{R}, b \in \mathbb{R}\\}$$

Or a family of normal distributions:

$$\mathcal{F} = \\{ f_{\mu,\sigma}(x) = \frac{1}{\sigma\sqrt{2\pi}} e^{-\frac{1}{2} {(\frac{x-\mu}{\sigma})}^2}; \mu \in \mathbb{R}, \sigma \in \mathbb{R^+}\\}$$

### Prediction, Regression and Classification ###
**Supervised Learning** is an important case of ML and deserves special attention since its setup slightly differs from the classical inference problems.

In the **classical inference** we aim to discover $F$ from which a random variable of interested $X$ is generated. In most cases, the distribution already describes the error. In other cases, like in physics or other sciences, we may explicit model the measurement error saying that $X = W + \sigma$ and $W \sim F$.

But in supervised learning, we have what is called the **regression setup**, which contains two types of variables: **independent variable**, $X$, and **dependent variable**, $Y$. $X$ and $Y \sim F$, the joint probability function.The hypothesis in supervised learning is that $Y$ depend on $X$, i.e., for each value of $x_i$ we associate an **outcome** $y_i$. Thus, there is a **regression function**: 

$$r(X) = \mathbb{E}[Y|X]$$.

The actual regression function, r, is unknow and, most of times, unknownable. So we have to estimate it from a sample $X \sim F$,  creating a function $\hat{r}(X)$. 

The systematic way of estimating $\hat{r}$ from a sample X_i can be referenced by $\mathcal{A}(X_i)$. **$r(X)$ is the estimand, $\mathcal{A}(X_i)$ is the estimator and $\hat{r}(X)$ is the estimate.** 

With $\hat{r}(X)$, we can estimate a future value of Y from a new value of X, which is called **prediction**. When $Y$ is discrete, we have a **classification** and when $Y$ is continuous, we have a **regression**.

We can always rewrite a regression model as:

$$Y = r(X) + \epsilon$$

where $\epsilon$ is called **irreducible error**. It is independent from $X$ and $\mathbb{E}(\epsilon) = 0$. In this formulation, $r$ accounts for the systematic information $X$ provides about $Y$.
 
It is important to notice $\mathbb{E}[\epsilon]=0$ is consequence of the definition $r(X)=\mathbb{E}[Y|X]$. In fact:

$$Y = r(X) + \epsilon \rightarrow \epsilon = Y - r(X)$$

$$ \mathbb{E}[\epsilon] = \mathbb{E}[Y - r(X)]$$

Using the **Law of Iterated Expectation** we have:

$$\mathbb{E}[Y - r(X)] = \mathbb{E}[\mathbb{E}[Y-r(X)|X]] = \mathbb{E}[\mathbb{E}[Y|X] - \mathbb{E}[r(X)|X]] = \mathbb{E}[\mathbb{E}[Y|X] - r(X)] $$

Since $r(X)=\mathbb{E}[Y|X]$:

$$\mathbb{E}[\mathbb{E}[Y|X] - r(X)] = \mathbb{E}[r(X) - r(X)] = \mathbb{E}[0] = 0$$

## Typical Inferential Problems ##
In statistical learning, most of the time we are facing one of these three problems:
 - point estimation;
 - confidence sets;
 - hypothesis testing.

### Point Estimation
Point estimation refers to providing a good approximation to an unkown quantity of interest like: 
- a parameter of a parametric model;
- a cdf $F$;
- a PDF $f$;
- a regression function $r$;
- a future value of $Y$ given a new value of $X$.

By convetion, we call the unknown quantity and its point estimation, respectivelly, $\theta$ and $\hat{\theta}$.

Formally, given a vector of IID random variables $X_1, X_2,..., X_n \sim F$, a point estimation $\hat{\theta}$ is a function of $X_i$:

$$\hat{\theta} = g(X_1, X_2,..., X_n)$$

Attention for the fact that $\theta$ is a value while $\hat{\theta}$ is a function of the data $X$, so its is a random variable.

We define the bias of an estimator by:

$$bias(\hat{\theta}) = \mathbb{E}[\hat{\theta}] - \theta$$

So, by definition, we say a estimator is **unbiased** if $bias(\hat{\theta}) = 0 \leftrightarrow \mathbb{E}[\hat{\theta}] = \theta$.  





 ### Confidence Intervals/Sets
 Draft: Confidence sets are a way to measure how confidence we are about the process that generate an estimation. It is often misunderstood as a way to measure the condidence about the measure itself. 

It can be built to any estimative based on a random variable.

#### Empirical Confidence Intervals/Sets
 In many practical cases, the true distribution is unkown and we have access to just one sample from the true distribution. If we couldn't assume as prior knowledge the pdf or the true distribution, we have to rely in methods like bootstraping to build confidence intervals. In this case, we say we are building **empirical confidence intervals**.

 ### Hyphotesis Testing

(to do)

------------------------------------------------------------------------------------------

# Appendix

## Law of Large Numbers (LLN) and Central Limit Theorem (CLT)
Consider $X \sim \mathcal{F}$ and let:
- $\mu = \mathbb{E}[\mathcal{F}]$ be the unknown distribution mean (population mean);
- $x_i, i \in {1,2,...,n}$ be a distribution sample;
- $n$ be the sample size;
- $\theta(x) = \bar{x}$ be the sample mean.

LLN tells $\bar{x} \rightarrow \mu$ when $n \rightarrow \infty$.

And CLT tells the distribution of $\bar{x}$ tends to a normal distribution when $n \rightarrow \infty$ - even when $\mathcal{F}$ is not normal.

 ## Bootstrap
**Draft:** 

Briefly, it is a method to obtain additional information about an estimator, $\mathbb{R}$, without having access to more samples of the distribution. 

It is based on the premiss below:


$$LLN(R(X_1^′,...,X_n^′)) \sim LLN(R(X_1^∗,...,X_n^∗)),$$


where $X_i^′$ is a bootstrap sample and $X_i^*$ is the original sample.


So, we can infer the distribution of the statistic given by R from bootstrap samples $X^*$. 

A bootstrap sample, $X^′$, is a new artificial sample with size $n$ where each value is randomly choosen from $X^*$ with replacement.

So, if we would like to infer the statistic $R(X,\mathcal{F})$, we can do this by calculating $m$ bootstrap samples, $X_{j}^′$, from $X^*$ and building 
$m$ different statistics $R_j(X_j^′, \mathcal{\hat{F}})$, where $j \in {1,2,...,m}$ and $\mathcal{\hat{F}}$ is the empirical distribution of $X^′$. 

With this set of bootstrap statistics we can build confidence intervals, histograms, etc.

-------------------------------------------------------

# Common Misconceptions (Be Careful)

## About Confidence Intervals
Confidence intervals are not claims about the parameter being estimated. They are claims about the estimator (the process which generates the estimation).

**Empirical CI:** In all practical cases, when we build a confidence interval we are talking about empirical confidence interval. The true confidence interval is something we never know.


## About Bootstrap (my conversation with Copilot)

**Me**:
I thought: **bootstrap approximates the variability of the geological distribution** and can be **used to understand the variability of the training process over a set of samples from the approximated distribution**.

Is my thougth wrong? If so, why?


**Copilot said**:


Antonio — this is the key conceptual point, and your doubt is completely valid.
Let me put it plainly:

❗ Your thought is not exactly wrong — but it is incomplete, and fixing that incompleteness resolves the confusion.
You said:

Bootstrap approximates the variability of the geological distribution and can be used to understand the variability of the training process over a set of samples from the approximated distribution.

There is one extra step in your mental model that is not correct:

➤ **BOOTSTRAP DOES NOT APPROXIMATE THE VARIABILITY OF THE GEOLOGICAL DISTRIBUTION**
Instead:

⭐ **Bootstrap approximates the variability of the empirical distribution,
not the underlying population/geological distribution.**

This subtle distinction explains everything.

Let’s go step by step, slowly and clearly.

🎯 1. Two distributions exist
Let’s name them:

F = true geological/population distribution
Unknown. Very complex. Manifold. Constant pdf on support.

F̂ₙ = empirical distribution
A discrete distribution that puts mass 1/n on each observed training pair.

Bootstrap samples from F̂ₙ, not from F.

🎯 2. **The classical misconception is this:**
**“Bootstrap samples approximate the true distribution F.”**

This is false in general.

It is false for images.
It is false for manifolds.
It is even false for real-valued heavy-tailed distributions.
It is false for almost every interesting real-world dataset.

And **bootstrap does not require F̂ₙ ≈ F.**

This was your mistaken assumption.

🎯 3. So what does bootstrap approximate?
**Bootstrap approximates: The distribution of your estimator T under F by The distribution of your estimator T under F̂ₙ.**

In symbols:

$$Law(T(X_1^′,...,X_n^′)) \sim Law(T(X_1^∗,...,X_n^∗)).$$

Bootstrap makes no claim that:

$$\hat{F}_n \sim F.$$

Bootstrap only requires a much weaker statement:

**Perturbations drawn from $\hat{F}_n$ affect T the same way as perturbations from $F$.**

This is a statement about the smoothness and stability of the estimator,
NOT about the smoothness or continuity of the underlying F.

🎯 4. Now the key point:
**In regression with images, the estimator IS smooth enough,
so bootstrap works even if the geological distribution is not.**

This is why:

Neural networks,
least squares regression,
kernel regression,
random forests,
gradient boosting
can all be bootstrapped, regardless of the complexity of the input distribution.

The estimator is stable enough under resampling that the bootstrap distribution gives you the correct variability.

In other words:

The bootstrap is estimating model variance, not geology variance.
⭐ So your thought is almost correct — but missing one crucial distinction
Let’s rewrite your idea in correct form:

❌ Incorrect (your original thought):
“Bootstrap approximates the variability of the geological distribution.”

✔ Correct (the truth):
Bootstrap approximates the variability of the empirical distribution
and uses that to estimate the variability of the estimator.

✔ Also correct:
Bootstrap does not need to replicate geological variability.
It only needs to replicate how the estimator responds to data perturbations.

🎯 5. Example to make it crystal clear
The underlying geological distribution F might lie on a crazy manifold.
The empirical distribution F̂ₙ is just n atoms.

Bootstrap resamples those atoms:

It will never produce a new geological structure.
It will never approximate the manifold.
It does not mimic geological variability.
But:

If you changed your dataset slightly,
your trained neural network would change slightly,
bootstrap resampling mimics this kind of perturbation.
Thus bootstrap gives a good estimate of:

variance of MSE
variance of predictions
stability of training
confidence intervals
Even though it gives a terrible estimate of F.

And that’s fine, because that’s not what you need.

⭐ Final Summary (the exact answer to your confusion)
Your mistake was assuming that bootstrap works by approximating the data distribution.
It does not.

Bootstrap works by approximating:

The distribution of the estimator under hypothetical resampling,
not the distribution of the underlying geological data.

And because neural networks + MSE regression are smooth enough functionals of the empirical distribution, bootstrap is valid for:

- estimating MSE confidence intervals
- evaluating training stability
- estimating generalization variability
- computing prediction uncertainty (via bagging)

even when:

- the true pdf is constant on a manifold
- the support is highly structured
- the data distribution is unknown or discontinuous




