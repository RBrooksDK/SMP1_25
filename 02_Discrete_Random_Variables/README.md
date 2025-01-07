<h1 align="center">Discrete Random Variables</h1>

### Session Preparation:
ASPE: 3

Solve the [exercises from session 1](https://rbrooksdk.github.io/SMP1_25/01_Introduction_%2B_Recap_Probability_%2B_Stochastic_Variables/#exercises) before class.

### Session Material

[Recap and Exercises - notes]()

[Session notes]()

[Session material](https://viaucdk-my.sharepoint.com/:f:/g/personal/rib_viauc_dk/EthiTapbBz1JrNRDVKsHTnkB2LPmmbKwlY22zvyaCJMI9Q?e=0ggVfo)

Session from 20/21:

<iframe width="560" height="315" src="https://www.youtube.com/embed/cXtY94_iETI?si=-dXqhYd_ByMZMCIK" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

---

### Session Description
In this session, we look at a variety of discrete probability distributions, laying the foundation for analysing and modelling random processes. We begin with the Bernoulli distribution, which describes experiments with two possible outcomes, and extend this to the Binomial and Geometric distributions. Building on these, we we move on to the Negative Binomial (Pascal) distribution and the Hypergeometric distribution, highlighting their applications in scenarios where sampling without replacement plays a role. 

The Poisson distribution, a model for counting events over time or space, is introduced, along with its use as an approximation for the Binomial distribution under specific conditions. Finally, we discuss key properties of these distributions, including their probability mass function (PMF) and cumulative distribution functions (CDFs), expectations, and variances.

#### Key Concepts
- Bernoulli Distribution
- Geometric Distribution
- Binomial Distribution
- Negative Binomial (Pascal) Distribution
- Hypergeometric Distribution
- Poisson Distribution
- Poisson as an Approximation for Binomial
- Probability Mass Function (PMF)
- Cumulative Distribution Function (CDF)
- Expectation and Variance

---

### Exercises
Full answers to the exercises can be found in [Session material](https://viaucdk-my.sharepoint.com/:f:/g/personal/rib_viauc_dk/EthiTapbBz1JrNRDVKsHTnkB2LPmmbKwlY22zvyaCJMI9Q?e=0ggVfo).

<style type="text/css">
    ol { list-style-type: lower-alpha; }
</style>

Note, sometimes we use '$=$' instead of '$\approx$' when we state probabilities with a given decimal precision.

#### Exercise 1
A computer system uses passwords that are exactly six
characters and each character is one of the 26 letters (a-–z) or
10 integers (0-–9). Suppose that 10,000 users of the system have
unique passwords. A hacker randomly selects (with replacement)
100,000 passwords from the potential set, and a match to a user’s
password is called a hit.

1. What is the distribution of the number of hits?
2. What is the probability of no hits?
3. What are the mean and variance of the number of hits?

??? answer
    1. The distribution of the number of hits is Binomial with $n = 10^5$ and \(p=\frac{10^5}{36^6}\)
    2. \(P(X=0) = 0.6317\)
    3. \(\mu = \sigma^2 = 0.4594\)

#### Exercise 2
Because all airline passengers do not show up for
their reserved seat, an airline sells 125 tickets for a flight that holds
only 120 passengers. The probability that a passenger does not
show up is 0.10, and the passengers behave independently.

1. What is the probability that every passenger who shows up can take the flight?
2. What is the probability that the flight departs with empty seats?

??? answer
    1. \(p = 0.9961 \)
    2. \(p = 0.9886\)

#### Exercise 3
A player of a video game is confronted with a series
of opponents and has an 80\% probability of defeating each one.
Success with any opponent is independent of previous encounters.
Until defeated, the player continues to contest opponents.

1. What is the probability mass function of the number of opponents contested in a game?
2. What is the probability that a player defeats at least two opponents in a game?
3. What is the expected number of opponents contested in a game?
4. What is the probability that a player contests four or more opponents in a game?
5. What is the expected number of game plays until a player contests four or more opponents?

??? answer
    1. \(P(X=k) = 0.8^{k-1} \cdot 0.2\)
    2. \(p = 0.64\)
    3. \(E[X] = 5\)
    4. \(p = 0.512\)
    5. \(E[Y] \approx 1.9531\)

#### Exercise 4
Astronomers treat the number of stars in a
given volume of space as a Poisson random variable. The density
in the Milky Way Galaxy in the vicinity of our solar system is one
star per 16 cubic light-years.

1. What is the probability of no stars in 16 cubic light-years?
2. What is the probability of two or more stars in 16 cubic light-years?
3. How many cubic light-years of space must be studied so that the probability of one or more stars exceeds 0.95?

??? answer
    1. \(P(X=0)=e^{-1} \approx 0.3679\)
    2. \(P(X \geq 2) \approx 0.2642\)
    3. At least 48 cubic light-years of space must be studied.

#### Exercise 5
A congested computer network has a 1% chance of losing a data packet that must be resent, and packet losses are independent events. An e-mail message requires 100 packets.

1. What is the distribution of the number of packets in an e-mail message that must be resent? Include the parameter values.
2. What is the probability that at least one packet is resent?
3. What is the probability that two or more packets are resent?
4. What are the mean and standard deviation of the number of packets that are resent?
5. If there are 10 messages and each contains 100 packets, what is the probability that at least one message requires that two or more packets be resent?

??? answer
    1. \(X \sim \operatorname{Binomial}(n=100, p=0.01)\)
    2. \(P(X \geq 1)=0.634\)
    3. \(P(X \geq 2)=0.2642\)
    4. \(\mu = 1, \sigma = 0.995\)
    5. \(P(Y \geq 1)=0.9535\)

#### Exercise 6
A manufacturer of a consumer electronics product expects 2% of units to fail during the warranty period. A sample of 500 independent units is tracked for warranty performance.

1. What is the probability that none fails during the warranty period?
2. What is the expected number of failures during the warranty period?
3. What is the probability that more than two units fail during the warranty period?

??? answer
    1. \(P(X=0) \approx 0.0000\)
    2. \(E[X] = 10\)
    3. \(P(X > 2) \approx 0.9974\)

#### Exercise 7
The probability that a patient recovers from a rare blood disease is 0.4. If 15 people are known to have contracted this disease, what is the probability that:

1. At least 10 survive

2. From 3 to 8 survive

3. Exactly 5 survive

4. Find the mean and variance.

??? answer
    1. \(P(X \geq 10) \approx 0.0338\)
    2. \(P(3 \leq X \leq 8) \approx 0.8778\)
    3. \(P(X=5) \approx 0.1859\)
    4. \(\mu = 6, \sigma^2 = 3.6\)

#### Exercise 8
A large chain retailer purchases a certain kind of electronic device from a manufacturer. The manufacturer indicates that the defective rate of the device is 3%.

1. The inspector of the retailer randomly picks 20 items from a shipment. What is the probability that there will be at least one defective item among them?

2. Suppose that the retailer receives 10 shipments in a month and the inspector randomly tests 20 devices per shipment. What is the probability that there will be 3 shipments containing at least one defective device?

??? answer
    1. \(P(X \geq 1) \approx 0.4562\)
    2. \(P(Y=3) \approx 0.1602\)

#### Exercise 9
High flows result in the closure of a causeway. From past records, the road is closed for this reason on 10 days during a 20-year period. At an adjoining village, there is concern about the closure of the causeway because it provides the only access. The villagers assume that the probability of a closure of the road for more than one day during a year is less than 0.10. Is this correct? Please show using the Poisson distribution.

??? answer
    The probability of a closure of the road for more than one day during a year is 0.0902.

#### Exercise 10
A company performs inspection on shipments from suppliers in order to detect nonconforming products. Assume a lot contains 1000 items and 1% is nonconforming. Assuming that the number of nonconforming products in the sample is binomial, what sample size is needed so that the probability of choosing at least one nonconforming item in the sample is at least 0.9?

??? answer
    A sample size of at least 230 is needed.

#### Exercise 11
The number of errors in a textbook follows a Poisson distribution with a
mean of 0.01 error per page. What is the probability that there are three
or less errors in 100 pages?

??? answer
    \(P(X \leq 3) \approx 0.981\)

#### Additional Exercises

``` py linenums="1"
while student is "bored":
    additional_exercises = [
        "Exam 2014.3 (a-c)",
        "Exam 2016 New Test.2",
        "Exam 2018.2"
    ]
```
