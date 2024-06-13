# All about Probability
### Link: [Bayes Theorem Notebook](https://github.com/DataByteSun/Revision/blob/a918c0425db8890148d5edb1037a94bf818006b6/Descriptive%20statistics/Notebooks/Bayes%20Theorem.ipynb)
## Introduction to Probability:
Probability theory is a fundamental concept in data science, providing a framework for quantifying uncertainty. It allows us to make informed decisions in the presence of randomness or uncertainty. <br/>
## Sample Spaces and Events:
- **Sample Space (S):** The sample space is the set of all possible outcomes of a random experiment. It is denoted by $S$.
- Example: When flipping a coin, the sample space is $S$ = \{ $\{H, T\}\$ \}, where $H$ represents heads and $T$ represents tails.
- **Event (E):** An event is any subset of the sample space, representing a particular outcome or a combination of outcomes.
- Example: In the coin flip experiment, if we define $E$ as getting heads ($H$), then $E$ = \{ $H$ \}.

## Probability Axioms:
- **Axiom 1: Non-negativity:** The probability of any event is a non-negative real number.
$P(E) \geq 0 \quad \text{for all events } E.$
- **Axiom 2: Normalization:** The probability of the entire sample space is 1.
$P(S) = 1.$
- **Axiom 3: Additivity:** The probability of the union of two mutually exclusive events is the sum of their individual probabilities. <br/>
If $E_1$ and $E_2$ are mutually exclusive events (i.e., they cannot occur simultaneously), then
$P(E_1 \cup E_2) = P(E_1) + P(E_2).$

## Basic Properties of Probability:
- **Complement Rule:** The probability of the complement of an event $E$ (denoted by $E^c$) is 1 minus the probability of $E$.
$P(E^c) = 1 - P(E).$
- **Addition Rule:** The probability of the union of two events is the sum of their individual probabilities minus the probability of their intersection.
$P(E_1 \cup E_2) = P(E_1) + P(E_2) - P(E_1 \cap E_2).$

## Conditional Probability:
- **Definition:** The conditional probability of event $E$ given event $F$ is the probability of $E$ occurring, given that $F$ has already occurred, and denoted by $P(E|F)$.
$P(E|F) = \frac{P(E \cap F)}{P(F)}, \text{ where } P(F) > 0.$
- **Application:** Conditional probability is widely used in various real-world scenarios, such as medical diagnosis, weather forecasting, and marketing analytics, where events depend on each other's occurrence. <br/>

## Independence:
- **Definition:** Two events $E$ and $F$ are independent if the occurrence of one event does not affect the occurrence of the other.
Mathematically, $E$ and $F$ are independent if $P(E \cap F) = P(E) \cdot P(F)$.

## Bayes' Theorem:
- **Statement:** Bayes' theorem provides a way to update the probability of a hypothesis based on new evidence. It is a fundamental concept in Bayesian statistics and machine learning.
- **Bayes' Theorem** provides a way to update the probability of a hypothesis $H$ given evidence $E$ by considering the likelihood of $E$ given $H$ and the prior probability of $H$.
$P(H|E) = \frac{P(E|H) \cdot P(H)}{P(E)}.$
- **Usage:** Bayes' theorem is applied in diverse fields, including medical diagnosis, spam filtering, and risk assessment, to update beliefs or probabilities based on new information.

## Random Variables:
- **Definition:** A random variable is a variable whose possible values are outcomes of a random phenomenon. It assigns a numerical value to each outcome in a sample space.
- **Types:** Random variables can be discrete or continuous. Discrete random variables take on a countable number of distinct values, while continuous random variables can take any value within a specified range.
- **Probability Distribution:** Random variables are associated with probability distributions that describe the likelihood of each possible outcome.
__________________________________
## Example: Application of Bayes' Theorem in Medical Diagnosis
Suppose we have a population of 10,000 individuals, among whom 500 have a certain rare disease. A diagnostic test for this disease has been developed, and clinical studies have shown that the test correctly identifies the presence of the disease (true positive) 99% of the time and correctly identifies the absence of the disease (true negative) 98% of the time. <br />
We want to determine the probability that an individual selected at random from the population actually has the disease given that the test result comes back positive. <br/>
### 1. Define Events:
Let: <br/>
- $D$ be the event that an individual has the disease. 
- $D^c$ be the event that an individual does not have the disease. 
- $T^+$ be the event that the test result is positive. 
- $T^-$ be the event that the test result is negative.

### 2. Given Information:
- $P(D) = \frac{500}{10000} = 0.05$ (prevalence of the disease) 
- $P(D^c) = 1 - P(D) = 0.95$ 
- $P(T^+|D) = 0.99$ (true positive rate) 
- $P(T^-|D^c) = 0.98$ (true negative rate)

### 3. Calculate $P(T^+)$ (Total Probability of a Positive Test Result):
- $P(T^+) = P(T^+ \cap D) + P(T^+ \cap D^c)$
  - $P(T^+ \cap D) = P(T^+|D) \cdot P(D) = 0.99 \times 0.05 = 0.0495$
  - $P(T^+ \cap D^c) = P(T^+|D^c) \cdot P(D^c) = 0.02 \times 0.95 = 0.019$ <br/>
$\Rightarrow P(T^+) = 0.0495 + 0.019 = 0.0685$

###  Apply Bayes' Theorem:
- We want to find $P(D|T^+)$, the probability that an individual has the disease given that the test result is positive. <br/>
$P(D|T^+) = \frac{P(T^+|D) \cdot P(D)}{P(T^+)}$
$= \frac{0.99 \times 0.05}{0.0685}$
$\approx \frac{0.0495}{0.0685}$
$\approx 0.7225$

### Interpretation:
The probability that an individual selected at random from the population actually has the disease given that the test result comes back positive is approximately 0.7225 or 72.25%. <br/>
