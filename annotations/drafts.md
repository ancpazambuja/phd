# Just some drafts - possibly unfinished ones

# Perceptron

## Definition
In machine learning, the perceptron (or McCulloch–Pitts neuron) is an algorithm for supervised learning of binary classifiers.


## History

### McCulloch-Pitts

**1943 - A Logical Calculus of the Ideas Immanent in Nervous Activity**

It the was the first computational model of the neuron and allowed the establishment of a conceptual connection between the neuron and propositional logic.

It was the basis of the Rosenblatt's Perceptron.

### Rosenblatt

**1957 - The Perceptron: a perceiving and recognizing automaton**

**1958 - The perceptron: A probabilistic model for information storage and organization in the brain**

**1962 - Principles of Neurodynamics: Perceptrons and the Theory of Brain Mechanism**

Mathematical definition:

$$f(x) = \theta(w.x + b)$$

where:
 - $w \in \mathbb{R}^n$
 - $x \in \mathbb{R}^n$
 - $b \in \mathbb{R}$
 - $\theta$ is the heaviside step-function

#### Heaviside step-function

$$
H(x) = 
\begin{cases}
 & 1\text{, if } x >= 0 \\ 
 & 0 \text{, otherwise }
\end{cases}
$$


![650px-Dirac_distribution_CDF svg](https://github.com/ancpazambuja/phd/assets/36957087/85d6d1b6-4c2f-41c5-8f97-652eb9a6b162)

The perceptron is also known as a single-layer perceptron and it is the simples feedfoward neural network. 

The perceptron was intended to be a machine but it was first simulated algorithmically on a IBM 704 and after that implemented in custom-built hardware as the "Mark I Perceptron". 

### Thomas M. Cover
**1964 - Geometrical and Statistical Properties of Linear Threshold Devices**

From an information theory point of view, Cover demonstrate that a single perceptron with k vectors $x_i, i \in [k]$ has a capacity of $2k$ bits of information.

#### Cover's Theorem or Cover's Couting Function Theorem
It expresses the number of homogeneously linearly separable sets of $N$ points in $D$ dimensions as an explicit counting function $C(N,D)$, since the points are in [general position](https://en.wikipedia.org/wiki/General_position).

$$
C(N,D) = 2 \sum_{i=0}^{D-1}\big \dfrac{N-1}{i}
$$









### Minsky and Papert
**1969 - Perceptrons: an introduction to computational geometry**








