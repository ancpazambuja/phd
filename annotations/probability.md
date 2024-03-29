
# Probability
Formally (somewhat), Kolmogorov defined these axioms below:

- K0: a non-deterministic experiment can be described by the probability space $(\Omega, \mathcal{F}, P)$, where:
  - $\Omega$ is the sample space (set of possible outcomes),
  - $\mathcal{F}$ is the set of possible events ( $\mathcal{P}(\Omega)$, power set of $\Omega$ ) and
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

$X = ${ $x_1, x_2, x_3, x_4, ..., x_N$ } from which we can build a histogram. In this context,
we can define: 

$P(X=x_i) = \frac{hist(x_i)}{N}$

For example, if we consider a fair die, we have:

$$\Omega = \\{ 1, 2, 3, 4, 5, 6 \\}$$

And we can think a random variable X as the result of rolling a die several times:

$$X = \\{ 2, 4, 2, 1, 5, 3, 4, 5, 6, 1, 6, 3 \\}$$ 

And we may ask the probability of getting an odd number:

$$P(X \text{ is odd}) = P( \\{1\\} \cup \\{3\\} \cup \\{5\\} ) = P(\\{1\\}) + P(\\{3\\} + P(\\{5\\}) = \frac{hist(1) + hist(3) + hist(5)}{12} = \frac{6}{12} = 0,5$$

**Note:** "X is odd" is an event (e.g. $A=${1, 3, 5}).

  
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

**Probability Distribution Function (PDF)**

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

