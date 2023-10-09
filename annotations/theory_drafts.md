# Some annotation from my studies

## Probability
Formally (somewhat), Kolmogorov defined these axioms below:

- K0: a non-deterministic experiment can be described by the probability space $(\Omega, \mathcal{F}, P)$, where:
  - $\Omega$ is the sample space (set of possible outcomes),
  - $\mathcal{F}$ is the set of possible events ( $\mathcal{P}(\Omega)$ ) and
  - $P: \mathcal{F} \rightarrow \mathbb{R}$ is the probability function.

- K1: Non-negativity::  $P(A) \geq 0, \forall A \in \mathcal{F}$ is the probability function.

- K2: Unit normalization:: $P(\Omega) = 1$
  
- K3: Aditivity:: $A \cap B = \varnothing \rightarrow P(A \cup B) = P(A) + P(B)$

- K4: $\sigma$-Aditivity:: if $A_i$ are disjoint sets:

  $P({\bigcup}_{i=1}^{\infty}A_i) = P(A_1) + P(A_2) + \cdots =$
  
  ${\sum}_{i=1}^{\infty}P(A_i)$

  
### Classical view
**Laplace (1814)**

For equiprobable outcomes, $P(a \in \Omega) = \frac{1}{|\Omega|}$. 
Thus, we use tools such as combinatorial analysis and set theory to count the number of outcomes in some event $A \in \mathcal{F}$ 
in order to calculate:

$P(A) = \frac{|A|}{|\Omega|}$ 

or 

$P(A|B) = \frac{P(A \cap B)}{P(B)}$

### Frequentist view
**Venn (1876)**

#### Discrete events
When outcomes are not equiprobable, one can count outcomes frequencies (histograms) in the limit of infinity experiments.

We use the notion of n-sample to describe a population.

Then, we have:

$P(A) = \frac{n(A)}{n}$

or 

$P(A|B) = \frac{n(A \cap B)}{n(B)}$

where $n(A)$ is the number of times A has happened in the sample.


#### Continuous events 

In order to have to find out The F(x) -> Cumulative Distribution Function (CDF)

and

f(x) = F'(x) -> Probability Density Function (PDF)

or 

p(x) -> Probability Mass Function (PMF)

Pr(X)

#### Note
Frequentist Probability may also be describe as:

Pr(A) = 


## Random Variables
A random variable is a collection of outcomes from an experiment run several times under the same conditions. The outcomes are non-deterministic. 

A random variable X can be defined by enumeration: 

X = {x1, x2, x3, x4, ..., xN} from which we can build a histogram. In this context,
we can define: 

Pr(X=xi) = hist(xi) / N

as a collection
Two main views

