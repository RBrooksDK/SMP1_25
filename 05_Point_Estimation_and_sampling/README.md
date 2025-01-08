<h1 align="center">Point Estimation and Sampling</h1>

### Session Preparation:
ASPE: 7 (not 7.3.4 and 7.4.3)

Solve the [exercises from session 4](https://rbrooksdk.github.io/SMP1_25/04_Multivariate_Random_Variables/#exercises) before class.

### Session Material

[Recap Exercises]()

[Session material](https://viaucdk-my.sharepoint.com/:f:/g/personal/rib_viauc_dk/EnYOFBJCZ-hNtWAfipCS0pUB6xsNt8lOW1fDyq_l_vNqUg?e=BSqiaH)

Session from 20/21:

<iframe width="560" height="315" src="https://www.youtube.com/embed/ZBIyMSuUz_Y?si=KxoNdKCAgff7l9ti" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

---

### Session Description

You will most likely experience that the next 2–3 topics are a bit less complex than the previous three topics.

Point estimation and sampling are important concepts in statistics. Point estimation involves using a statistic, such as the sample mean or proportion, to estimate an unknown population parameter. The goal is to find the value of the statistic that is most likely to be the true value of the parameter. Sampling, on the other hand, involves selecting a subset of individuals from a larger population and using their data to make inferences about the entire population. The key to effective sampling is ensuring that the sample is representative of the population and that the sample size is large enough to accurately estimate the population parameter of interest. Together, point estimation and sampling provide a framework for making accurate and reliable statistical inferences.

#### Key Concepts
- Correlation and Covariance (from last week’s topic)
- Sampling Distribution
- Central Limit Theorem
- Standard Error
- Mean Squared Error
- Maximum Likelihood Estimator

---

### Exercises
Full solutions to the book exercises (5-10) can be found in the [general resource folder](https://viaucdk-my.sharepoint.com/:f:/g/personal/rib_viauc_dk/Egbdbeb9oy1Oqk8hReXf2-wBibryPlLiVj2ujGdsvH5--w?e=liO02A)

<style type="text/css">
    ol { list-style-type: lower-alpha; }
</style>

#### Exercise 1
Recap ch. 4.

Let $X \sim N(3,9)$.

1. Find $P(X>0)$.
2. Find $P(-3<X<8)$.
3. Find $P(X>5 | X>3)$.

??? answer
    1. \(P(X>0)=\Phi(1) \approx 0.8413\)
    2. \(P(-3<X<8)=\Phi\left(\frac{5}{3}\right)-\Phi(-2) \approx 0.9295\).
    3. \(P(X>5 \mid X>3)=2 \times\left(1-\Phi\left(\frac{2}{3}\right)\right) \approx 0.5050\)

#### Exercise 2
Recap ch. 4.

Let $X \sim N(3,9)$ and $Y=5-X$.

1. Find $P(X>2)$.
2. Find $P(-1<Y<3)$.
3. Find $P(X>4 |Y<2)$.

??? answer
    1. \(P(X>2)=1-\Phi\left(\frac{1}{3}\right) \approx 0.6306\)
    2. \(P(-1<Y<3)=\Phi\left(\frac{1}{3}\right)-\Phi(-1) \approx 0.4719 \).
    3. \(P(X>4 \mid Y<2)=2\left(1-\Phi\left(\frac{1}{3}\right)\right) \approx 0.7389 .\)

#### Exercise 3
Recap Ch. 5

Consider the set of points in the set \(C\):

\[
C = \{(x, y) \mid x, y \in \mathbb{Z}, x^2 + |y| \leq 2\}.
\]

Suppose that we pick a point \((X, Y)\) from this set completely at random.

1. What probability does each point have of being chosen?

2. Find the joint and marginal PMFs of \(X\) and \(Y\).

3. Find the conditional PMF of \(X\) given \(Y = 1\).

4. Are \(X\) and \(Y\) independent?

5. Find \(E[XY^2]\).

6. Find \(E[X \mid Y = 1]\).

7. Find \(\operatorname{Var}(X \mid Y = 1)\).

8. Find \(E[X \mid |Y| \leq 1]\).

9. Find \(E[X^2 \mid |Y| \leq 1]\).

??? answer
    1. 1/11

    2. Find the joint and marginal PMFs of \(X\) and \(Y\).

        \[
        \begin{aligned}
        & P_{X Y}(x, y)=\left\{\begin{array}{cc}
        \frac{1}{11} & (x, y) \in C \\
        0 & \text { otherwise }
        \end{array}\right. \\
        & P_Y(-2)=P_{X Y}(0,-2)=\frac{1}{11} \\
        & P_Y(-1)=P_{X Y}(0,-1)+P_{X Y}(-1,-1)+P_{X Y}(1,-1)=\frac{3}{11} \\
        & P_Y(0)=P_{X Y}(0,0)+P_{X Y}(1,0)+P_{X Y}(-1,0)=\frac{3}{11} \\
        & P_Y(1)=P_{X Y}(0,1)+P_{X Y}(-1,1)+P_{X Y}(1,1)=\frac{3}{11} \\
        & P_Y(2)=P_{X Y}(0,2)=\frac{1}{11} \\
        & P_X(i)=\left\{\begin{array}{cc}
        \frac{3}{11} & \text { for } i=-1,1 \\
        \frac{5}{11} & \text { for } i=0 \\
        0 & \text { otherwise }
        \end{array}\right.
        \end{aligned}
        \]

    3. Find the conditional PMF of \(X\) given \(Y = 1\).
   
        \[
        \begin{aligned}
        P_{X \mid Y}(i \mid 1) & =\frac{P_{X Y}(i, 1)}{P_Y(1)} \\
        & =\frac{\frac{1}{11}}{\frac{3}{11}}=\frac{1}{3}, \quad \text { for } i=-1,0,1 .
        \end{aligned}
        \]

    4. No

    5. \(E[XY^2]=0\).

    6. \(E[X \mid Y = 1]=0\).

    7. \(\operatorname{Var}(X \mid Y = 1)=2/3\).

    8. \(E[X \mid |Y| \leq 1]=0\).

    9.  \(E[X^2 \mid |Y| \leq 1]=2/3\).

#### Exercise 4
The number of accidents in a certain city is modeled by a Poisson random variable with average rate of 10 accidents per day. Suppose that the number of accidents in different days are independent. Use the central limit theorem to find the probability that there will be more than 3800 accidents in a certain year. Assume that there are 365 days in a year.

??? answer
    \(P(Y \geq 3800) \approx 0.0065\)


#### Exercise 5 (Book 7.2.8)
Scientists at the Hopkins Memorial Forest in western Massachusetts have been collecting meteorological and environmental data in the forest data for more than 100 years. In the past few years, sulfate content in water samples from Birch Brook has averaged \(7.48 \mathrm{mg} / \mathrm{L}\) with a standard deviation of \(1.60 \mathrm{mg} / \mathrm{L}\).

1. What is the standard error of the sulfate in a collection of 10 water samples?
2. If 10 students measure the sulfate in their samples, what is the probability that their average sulfate will be between 6.49 and \(8.47 \mathrm{mg} / \mathrm{L}\) ?
3. What do you need to assume for the probability calculated in (b) to be accurate?

??? answer
    1. \(SE = 0.51\)
    2. \(P(6.49 < \bar{X} < 8.47) = 0.95\)
    3. The samples are independent. And that the population is normally distributed, or the sample size is large.

#### Exercise 6 (Book 7.2.10)
Researchers in the Hopkins Forest (see Exercise 7.2.8) also count the number of maple trees (genus acer) in plots throughout the forest. The following is a histogram of the number of live maples in 1002 plots sampled over the past 20 years. The average number of maples per plot was 19.86 trees with a standard deviation of 23.65 trees.

1. If we took the mean of a sample of eight plots, what would be the standard error of the mean?
2. Using the central limit theorem, what is the probability that the mean of the eight would be within 1 standard error of the mean?
3. Why might you think that the probability that you calculated in (b) might not be very accurate?

??? answer
    1. \(SE = 8.36\)
    2. \(0.68\)
    3. The central limit theorem applies when the sample size $n$ is large. Here $n = 8$ may be too small because the distribution of the counts of maple trees is quite skewed (which you can see in the histogram in the solutions from the book).

---

**Exercises 7 to 10 are fairly advanced, and we did not cover the topic in depth during the session. You can try to solve them if you want to challenge yourself.**

#### Exercise 7 (Book 7.3.3)
Suppose that we have a random sample \(X_1, X_2, \ldots\), \(X_n\) from a population that is \(N\left(\mu, \sigma^2\right)\). We plan to use \(\Theta=\) \(\sum_{i=1}^n\left(X_i-\bar{X}\right)^2 / c\) to estimate \(\sigma^2\). Compute the bias in \(\hat{\Theta}\) as an estimator of \(\sigma^2\) as a function of the constant \(c\).

??? answer
    \(E[\hat{\Theta}]=\frac{n-1}{c}\sigma^2\) and \(\text { Bias }(\hat{\Theta})=\frac{n-1}{c}\sigma^2-\sigma^2\).

#### Exercise 8 (Book 7.3.9)
\(\bar{X}_1\) and \(S_1^2\) are the sample mean and sample variance from a population with mean \(\mu_1\) and variance \(\sigma_1^2\). Similarly, \(\bar{X}_2\) and \(S_2^2\) are the sample mean and sample variance from a second independent population with mean \(\mu_2\) and variance \(\sigma_2^2\). The sample sizes are \(n_1\) and \(n_2\), respectively.

1. Show that \(\bar{X}_1-\bar{X}_2\) is an unbiased estimator of \(\mu_1-\mu_2\).
2. Find the standard error of \(\bar{X}_1-\bar{X}_2\). How could you estimate the standard error?
3. Suppose that both populations have the same variance; that is, \(\sigma_1^2=\sigma_2^2=\sigma^2\). Show that

$$
S_p^2=\frac{\left(n_1-1\right) S_1^2+\left(n_2-1\right) S_2^2}{n_1+n_2-2}
$$

is an unbiased estimator of \(\sigma^2\).

??? answer
    See the solutions from the book.

#### Exercise 9 (Book 7.4.4.a)
Consider the probability density function

$$
f(x)=c(1+\theta x), \quad-1 \leq x \leq 1
$$

1. Find the value of the constant \(c\).

??? answer
    1. \(c = 1/2\)

#### Exercise 10 (Book 7S13)

A random variable \(X\) has probability density function

$$
f(x)=\frac{1}{2 \theta^3} x^2 e^{-x / \theta}, \quad 0<x<\infty, \quad 0<\theta<\infty
$$

Find the maximum likelihood estimator for \(\theta\).

??? answer
    \[\hat{\theta}=\frac{\sum_{i=1}^n x_i}{3 n}\]



