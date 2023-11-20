
# Finite Probability Space 

F.P.S. are used in situations where an experiment with an finite number of outcomes can be repeated an infinite number of times.

It is defined as $(\Omega,\textbf {P}(\Omega),P)$

---

### Definitions :

- An experiment (trial) is any procedure that can be repeated an infinite number of times and has a finite number of outcomes. The outcome of such an experiment is usually denoted **ω**.
- The set of all possible outcome of an experiment is called the sample space and is denoted **Ω.**
- An event is a set of outcomes from the experiment [i.e.](https://fr.wikipedia.org/wiki/Id_est) a subset of **Ω.**
- An elementary event is an event whose cardinality is 1 (singleton)
- The set of all events of an experiment is **P(Ω)**.
- The opposite event of $A$ is denoted $\overline A$

$P(A\cap B) = P(A) * P_A(B)$

$P(A\cup B) = P(A) + P(B) - P(A\cap B)$

>[!warning] 
>$\{w\} \not = w$

elementary event $\not =$ outcome

>[!info]
> $A1 \bigsqcup A2 = \Omega \iff A2 = \overline {A1}$

---

### Basic axioms of the probability function and proofs:

_those are very much needed to prove theorems_

$P(\Omega) = 1$

$P(A \bigsqcup B) = P(A) + P(B)$

---

### Law of total probability :

$$ P(A) = \sum_{i=1}^n P(A\cap B_n) $$

---

### Conditional probabilities :


$$ P(A \backslash B) = P(A) - P(A \cap B) $$

$$ \text {A and B independent} \iff P(A \cap B) = P(A) * P(B) $$

---

### Bayes Theorem :

$$ P (A \space| \space B) = P_B(A) = \frac {P(A\cap B)} {P(B)} = \frac {P(A) * P_A(B)} {P(B)} $$

>[!info] 
>**M.E.C.E.** means Mutually Exclusive Collectively Exhaustive. (a partition of $\Omega$)

---

### Random variables


>[!info] 
>A Finite Random Variable (F.R.V.) is a map/function mapping every element from the set of outcomes $\Omega$ to a real number.


**Bernoulli Distribution** : one trial, two outcomes : success or failure.

$$ \begin{aligned}
&X : B(p) \implies \\
& \qquad X(\Omega) = \{0,1\} \\
& \qquad P(X = 1) = p \\
& \qquad P(X = 0) = 1 - p \\
\end{aligned}$$

**Binomial Distribution** : we repeat the same trial n times. The trials are **identical** and **independent**

$$ X : B(n,p) $$

$$ \forall k \in X(\Omega),\space P(X = k) = {n \choose k}p^k(1-p)^{n-k} $$

---

### Expected value

The expected value is the average outcome (the sum of all outcomes times their probability of occurrence)

$$ \mathbb {E} (X) = \sum_{i=1}^n P(X = x_i) * x_i $$

properties on $\mathbb E$ :

- $\mathbb {E}(aX) = a\mathbb{E}(X)$
- $\mathbb {E}(X + Y) = \mathbb{E}(X) + \mathbb{E}(Y)$
- $\mathbb{E}(aX + bY) = a\mathbb{E}(X) + b\mathbb{E}(Y)$
- $\mathbb {E}(aX + b) = a\mathbb{E}(X) + b$

---

### Variance


The variance translates how the values of X are spread.

$$ \mathbb{V}(X) = \mathbb{E}((X-\mathbb{E}(X))^2) $$

$$ \mathbb{V}(X) = \mathbb{E}(X^2) -\mathbb{E}^2(X) $$

properties on $\mathbb V$ :

$\mathbb{V}(aX + b) = a^2\mathbb{V}(X)$

if X and Y are independent then :

- $\mathbb {V}(X + Y) = \mathbb{V}(X) + \mathbb{V}(Y)$

---

### Standard deviation


The standard deviation is that, unlike the variance, it is expressed in the same unit as the data.

$$ \sigma(X) = \sqrt{\mathbb{V}(X)} $$ 

# Infinite Probability Space


---

### Generating functions

>[!tip] 
>The generating function of a discrete random variable contains all the distribution data.


We can compute the discrete random variable expected value and variance.

Let $X$ an integer random variable with $X(\Omega)$ _(the range of $X$)_

We call the generating function of $X$ the following polynomial :

$$
\mathbb{R} \mapsto \mathbb{R} $$
$$ 
G_X \colon t \to \sum_{k=0}^n P(X = k)\times t^k = \mathbb{E}(t^k) $$

---

### Expectation and Variance

Let $X$ a Finite integer random variable (F.I.R.V.) such that $X(\Omega) = [\![ 0,n ]\!]$ and $G_X$ the GF

$$ 
\mathbb{E}(X) = G_X'(1) $$
$$
\mathbb{V}(X) = G_X''(1) + G_X(1)' - G_X'(1)^2 $$

---

### G.F. of a sum of two finite integer random variables


Let $X$ and $Y$ two F.I.R.V. with $G_X$ and $G_Y$ their generating functions. Then : $X + Y = Z$

$$
\mathbb{R} \mapsto \mathbb{R} $$
$$
G_{X + Y} \colon t \to G_X(t) \times G_Y(t) \\ \iff G_Z = G_X \times G_Y $$

as a consequence :

$$ 
\mathbb{E} (X + Y) = \mathbb{E}(X) + \mathbb{E}(Y) \\ \mathbb{V} (X + Y) = \mathbb{V}(X) + \mathbb{V}(Y) $$

True for $\mathbb{V}$ if $X$ and $Y$ are independent.

>[!tip]
> $G_x(1) = 1$ because $G_x(1) = \sum_{k=0}^{X(\Omega)} P(X = k)$

---

### Bernoulli Distribution


The notation $X \sim \text{Bernoulli}(p)$ means that the random variable $X$ follows a Bernoulli distribution with parameter $p$. Let’s take the example : $X \sim \text{Bernoulli}(1/3)$, it means that $X$ is a Bernoulli random variable with a probability of success $p$ equal to $1/3$.

In the context of a Bernoulli distribution, the random variable $X$ can take on one of two possible values, usually denoted as 0 and 1. The distribution is given by:

$$ 
P(X = k) = \begin{cases} p & \text{if } k = 1 \\ 1-p & \text{if } k = 0 \end{cases}
$$

Here, $p$ is the probability of success (in your case, $1/3$), and $(1-p)$ is the probability of failure.

So, for $(X \sim \text{Bernoulli}(1/3))$, you have:

$$ \begin{aligned}
& P(X = 0) = \frac{2}{3} \\
& \qquad  P(X = 1) = \frac{1}{3}
\end{aligned}$$

This distribution is often used to model binary outcomes where there are only two possible outcomes, such as success/failure, heads/tails, etc.

----

### Geometric distribution

The geometric distribution is a probability distribution that models the number of independent and identically distributed Bernoulli trials needed before a success occurs. 

It's distribution is :

$$ P(X = k) = (1 - p)^{k-1} \cdot p $$

where:
- $X$ is the random variable representing the number of trials needed to obtain the first success.
- $p$ is the probability of success on a single trial.
- $k$ is the number of trials.

The expected value (mean) of the geometric distribution is $\frac{1}{p}$, and its variance is $\frac{1-p}{p^2}$. 

It is important to note that the geometric distribution assumes a fixed probability of success on each trial and that the trials are independent of each other.

---

### Poisson distribution

The Poisson distribution is a probability distribution that describes the number of events that occur within a fixed interval of time or space. It is named after the French mathematician Siméon Denis Poisson, who introduced it in the early 19th century.

The Poisson distribution is often used in situations where events are rare and occur independently. The distribution is characterized by a single parameter, denoted by $\lambda$, which represents the average rate of occurrence of the events in the given interval. The random variable $X$, representing the number of events, follows a Poisson distribution with parameter $\lambda$, and is denoted as $X \sim \text{Poisson}(\lambda)$.

The probability mass function (PMF) of a Poisson-distributed random variable $X$ is given by:

$$ 
P(X = k) = \frac{e^{-\lambda} \cdot \lambda^k}{k!} $$

where:
- $e$ is the mathematical constant approximately equal to 2.71828.
- $k$ is a non-negative integer (0, 1, 2, ...) representing the number of events.
- $\lambda$ is the average rate of events occurring in the given interval.

The mean ($\mu$) and variance ($\sigma^2$) of a Poisson distribution are both equal to $\lambda$, making the distribution particularly useful for modeling situations where events occur with a known average rate.

---

### Pascal distribution

The Pascal distribution, also known as the negative binomial distribution, is a probability distribution that models the number of independent and identically distributed Bernoulli trials needed to achieve a fixed number of successes. It is named after the French mathematician Blaise Pascal. The distribution is often denoted as Pascal($r, p$), where $r$ is the number of successes desired and $p$ is the probability of success on each trial.

The probability mass function (PMF) of a Pascal-distributed random variable $X$ is given by:

$P(X = k) = \binom{k-1}{r-1} \cdot p^r \cdot (1-p)^{k-r}$

where:
- $k$ is the total number of trials needed to achieve $r$ successes.
- $p$ is the probability of success on each individual trial.
- $\binom{k-1}{r-1}$ is the binomial coefficient, representing the number of ways to choose $r-1$ successes from $k-1$ trials.

The mean ($\mu$) and variance ($\sigma^2$) of a Pascal distribution are given by:

$\mu = \frac{r}{p}$
$\sigma^2 = \frac{r(1-p)}{p^2}$

The Pascal distribution is related to the geometric distribution, which models the number of trials needed to achieve the first success. In the Pascal distribution, we generalize this concept to the number of trials needed to achieve a fixed number $r$ of successes.


