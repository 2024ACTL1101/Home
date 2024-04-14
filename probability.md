
# Introduction to Probability in Actuarial Studies

## Motivation

### What is Probability?

Probability is the branch of mathematics that studies the possible outcomes of given events together with the outcomes' relative likelihoods and distributions. In common usage, the word "probability" is used to mean the chance that a particular event (or set of events) will occur expressed on a linear scale from 0 (impossibility) to 1 (certainty), also expressed as a percentage between 0 and 100%. [More about Probability](https://mathworld.wolfram.com/Probability.html)

### Why Do We Need Probability in Actuarial Science?

The work of actuaries is intrinsically related to **uncertainty**. Consider questions such as:
- Will life expectancy improve in the next decade?
- At what age are people most likely to retire?
- How many insurance claims will we have this month? How big will they be?
- How much money can we expect to gain (or lose) from our investments in the stock market?

A good understanding of Probability (and Statistics) is necessary to tackle these types of questions.

## Sample Space & Events

### Sample Space and Events

A **random experiment** is an experiment whose outcome is not known in advance with certainty. Example: tossing a dice and recording the result.

The **sample space** of a random experiment (often denoted $\Omega$) is the set of all possible outcomes. In the dice tossing example, $\Omega = \\{1,2,3,4,5,6\\}$.

Any subset $A$ of the sample space is called an **event**. Example: $A = \\{1,3,5\\}$ ('obtaining an odd number') is an event in $\Omega$. $B= \\{1\\}$ ('obtaining 1') is also an event in $\Omega$.

Given a context, we want to determine the probabilities that certain events occur.

## Elementary Rules of Probability

There are a few elementary rules everyone should know. Let $A$ and $B$ be events in the same sample space, then:

- $0 \\leq \\Pr[A] \\leq 1$
- $\\Pr[A] = 1 - \\Pr[A^{\\text{c}}]$
- $\\Pr[A \\cup B] = \\Pr[A] + \\Pr[B] - \\Pr[A \\cap B]$

Where $A^{\\text{c}}$ means not $A$, $A \\cup B$ means $A$ or $B$, while $A \\cap B$ means $A$ and $B$.

## Determining Probabilities

If all outcomes of an experiment are equally likely, a useful formula to determine the probability of an event $A$ is given by:

$$\\Pr[A] = \\frac{\\text{\\# favourable cases to } A}{\\text{\\# of total cases}}$$

Example: what is the probability of getting an odd number upon rolling a fair dice?

$$\\frac{\\text{\\# favourable cases}}{\\text{\\# total cases}} = \\frac{3}{6} = \\frac{1}{2}.$$

## Permutations & Combinations

## Permutations

Given Given a list of **distinct** objects, any **distinct arrangement** of them is called a **permutation**. For example, given the three letters _abc_, the possible permutations are: _abc, acb, bac, bca, cab, cba_.

In general, the number of possible permutations for $n$ different objects is:

$$
n! = n \cdot (n-1) \cdot (n-2) \cdot \ldots \cdot 2 \cdot 1
$$

**Proof**: Consider this as allocating $n$ objects within $n$ 'spots'. Then:

- The first spot has $n$ options.
- The second spot has $n-1$ options, as one object is already placed in the first 'spot'.
- ...
- The last spot has only 1 option.

## Combinations

Given a list of **distinct** objects, a selection of them for which **the order of the selected items does not matter**, is called a **combination**.

Given $n$ distinct objects, the number of ways to select $k$ (where $k \leq n$) of them (where the order of selection does not matter) is:

$$
{n \choose k} = \frac{n!}{k!(n-k)!}
$$

**Example**: If there are initially 49 participants at _The Voice_, and Delta Goodrem needs to create a team of 10, how many different teams can she possibly create?

**Solution**: Delta can choose from 49 distinct people, but the order in which she chooses does not influence the team. Hence, the answer is:

$$
{49 \choose 10} \approx 8.2 \text{ billions}
$$

## Random Variables

A **random variable** $X$ is a function that assigns values to the possible outcomes of a random experiment. For example, in the experiment of tossing two dice, a random variable $X$ could represent the sum of both dice. Another random variable $Y$ could represent the minimum of the two dice, etc.

**Discrete random variables**: These are variables where the number of possible values is finite or countably infinite.

**Continuous random variables**: These variables have possible values that appear on a continuous spectrum (hence are uncountably infinite).

## Random Variables: Examples in Actuarial Studies

### Discrete Random Variables
- Number of motor vehicle accidents occurring during a particular month.
- Number of lives lost to cancer during a particular time period.

### Continuous Random Variables
- Time until the first accident on a car insurance policy.
- Claim payment for a fire insurance policy.

## Probability Mass Function (PMF)

For a **discrete random variable** $X$, the PMF $p(x)$ is the probability that $X$ takes a particular value $x$:
$$
p(x) = \Pr(X = x),
$$
with
$$
p(x) \geq 0,
$$
and
$$
\sum_{\text{all } x} p(x) = 1.
$$

## Probability Density Function (PDF)

For a **continuous random variable** $X$, the PDF $f(x)$ is defined such that:
$$
\Pr(a \leq X \leq b) = \int_{a}^{b} f(x) \, dx,
$$
with
$$
f(x) \geq 0 \text{ for } -\infty < x < \infty,
$$
and
$$
\int_{-\infty}^{\infty} f(t) \, dt = 1.
$$

## Cumulative Distribution Function (CDF)

For **any** random variable $X$, the CDF, denoted $F(x)$, is defined as:
$$
F(x) = \Pr(X \leq x).
$$
It gives the probability a random variable $X$ is **less than or equal to** a specified value $x$. The CDF always satisfies:
$$
F(-\infty) = 0,
$$
and
$$
F(\infty) = 1.
$$

### CDF: Discrete vs Continuous Case

For a **discrete random variable** $X$, the CDF of $X$ can be computed as:
$$
F(x) = \Pr(X \leq x) = \sum_{k \leq x} p(k).
$$

For a **continuous random variable** $X**, the CDF of $X$ can be computed as:
$$
F(x) = \Pr(X \leq x) = \int_{-\infty}^{x} f(t) \, dt,
$$
and we also have:
$$
f(x) = \frac{d}{dx} F(x).
$$

## Expectation

The **expectation** (or **expected value**) of a random variable $X$, denoted $E[X]$ (and sometimes $\mu$) is the weighted average of all possible values $X$ can take, each value being weighted by the probability that $X$ assumes it. For discrete random variables:
$$
E[X] = \mu = \sum_{\text{all } x} x p(x)
$$
For continuous random variables:
$$
E[X] = \mu = \int_{-\infty}^{\infty} x f(x) \, dx
$$

## Expectation of a Function of $X$

It is often useful to compute the expectation of a **function of** a random variable, $g(X)$:
- For discrete random variables:
$$
E[g(X)] = \sum_{\text{all } x} g(x) p(x)
$$

- For continuous random variables:
$$
E[g(X)] = \int_{-\infty}^{\infty} g(x) f(x) \, dx
$$

- Moments (about the origin) of a random variable are given by:
$$
E[X^r] \text{ for } r=1,2,3,\ldots
$$


## Common Probability Distributions

### Binomial Distribution
Characteristics and typical applications of the binomial distribution in actuarial studies.

### Normal Distribution
Importance of the normal distribution, including its role in the central limit theorem.

### Other Distributions
Brief exploration of other key distributions like Poisson and exponential distributions.

## Joint Distributions

### Joint Probability Functions
How joint probabilities are defined for pairs of random variables and their implications.

### Independence of Random Variables
What independence entails for random variables and its effects on joint distributions.

### Covariance and Correlation
Definitions and the difference between these measures of relationship.

## Conditional Probability

### Basics of Conditional Probability
Explanation of conditional probability and how it is calculated.

### Bayes’ Theorem
Presentation of Bayes’ Theorem with examples of its application in actuarial practice.

## Risk and Insurance Examples

### Practical Applications
Examples of how probability theories are applied in risk assessment and insurance pricing.

### Case Studies
Mini case studies demonstrating practical applications of probability in real-world actuarial problems.

## Summary
Recap of the topics covered and their significance in further actuarial studies.

## References
- Textbook on Probability and Statistics
- Articles and papers on actuarial applications of probability
