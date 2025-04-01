<h1 align="center">08 Regression</h1>


## Material:

ASPE: 11 (not 11.9)

[Recap notes](https://drive.google.com/file/d/1Qsuum2ke2f8gCUyeP1wcFHkusnbBqSU6/view?usp=sharing)

[Session notes](https://drive.google.com/file/d/1N_hUEd6Hwn93dVtaSWHsFqe9N47E2WRg/view?usp=sharing)

[Session material](https://viaucdk-my.sharepoint.com/:f:/g/personal/rib_viauc_dk/Ev05wEbMShxPn7BZdA0uAncBwWrvATthywVt7NfsbGJo6w?e=GGnrFa)

Session from 20/21: 

<iframe width="560" height="315" src="https://www.youtube.com/embed/XmV8qxDEfkE?si=BPL580E9-aOvoiYk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

---

### Session Description

Linear regression is a statistical method used to model the relationship between a dependent variable and one or more independent variables. The key elements of linear regression include the dependent variable, independent variable(s), regression coefficients, intercept, and residual error. The regression coefficients represent the change in the dependent variable associated with a one-unit change in the independent variable, while the intercept represents the expected value of the dependent variable when all independent variables are equal to zero. The residual error is the difference between the observed values of the dependent variable and the values predicted by the regression model. The goal of linear regression is to find the best-fitting line that minimizes the sum of the squared residual errors. Linear regression is a widely used method in various fields to make predictions or estimate the strength and direction of relationships between variables.

#### Key Concepts
- Least Squares Estimates
- Regression Equation
- Correlation
- Coefficient of determination
- Prediction
- Residual Analysis

I've added a [page](Calculating_metrics.md) with all the useful formulas for calculating the parameters as well as the performance metrics, $r$ and $r^2$

---

### Exercises

<!-- If nothing is noted, assume it is “Exam”. If it is the reexam, it will be stated. -->
<!-- 2020.4 (not f), 2020.5, 2020.6, 2020.7, Reexam 2018.4, Reexam 2018.5, Reexam 2018.6, 2018.6, 2017.4, 2017.5, 2017.6 -->

<style type="text/css">
    ol { list-style-type: lower-alpha; }
</style>

#### Exercise 1 (2020.4)

Hydrocarbon emissions from cars are known to have decreased dramatically during the 2010s. A study was conducted to compare the hydrocarbon emissions at idling speed, in parts per million (ppm), for automobiles from 2010 and 2020. Fifty cars of each model year were randomly selected, and their hydrocarbon emission levels were recorded. The data is displayed in "HydroCarbonEmissions.xlsx".

1. Determine estimates for the quartiles, average emission, standard deviation and variance of each model year.
2. Setup $95 \%$ confidence intervals for the mean of each model year, and accompany the intervals with plots that display the rejection region
3. Is it reasonable to assume that the emission of each model year is normally distributed? Explain using plots and discussing skewness and kurtosis.
4. Setup a $99 \%$ confidence interval for the mean emission difference between the two model years and accompany the intervals with plots that display the rejection region.
5. Is there significant evidence to support the claim that the mean emission difference between the two model years differ from one another?

??? answer

            df = pd.read_excel("HydroCarbonEmissions.xlsx")
            df.head()

    1. 

            display(Latex("For 2010 model:"))
            display(Latex("$$Q_1 = {}$$".format(np.percentile(df['2010s models'], 25))))
            display(Latex("$$Q_2 = {}$$".format(np.percentile(df['2010s models'], 50))))
            display(Latex("$$Q_3 = {}$$".format(np.percentile(df['2010s models'], 75))))
            display(Latex("$$\mu = {}$$".format(df['2010s models'].mean())))
            display(Latex("$$\sigma = {}$$".format(round(df['2010s models'].std(ddof=1), 2))))
            display(Latex("$$\sigma^2 = {}$$".format(round(df['2010s models'].var(ddof=1), 2))))

            display(Latex("For 2020 model:"))
            display(Latex("$$Q_1 = {}$$".format(np.percentile(df['2020s models'], 25))))
            display(Latex("$$Q_2 = {}$$".format(np.percentile(df['2020s models'], 50))))
            display(Latex("$$Q_3 = {}$$".format(np.percentile(df['2020s models'], 75))))
            display(Latex("$$\mu = {}$$".format(df['2020s models'].mean())))
            display(Latex("$$\sigma = {}$$".format(round(df['2020s models'].std(ddof=1), 2))))
            display(Latex("$$\sigma^2 = {}$$".format(round(df['2020s models'].var(ddof=1), 2))))

        For 2010 model: 

        \begin{gathered}
        Q_1=258.0 \\
        Q_2=396.5 \\
        Q_3=506.75 \\
        \mu=391.6 \\
        \sigma=180.95 \\
        \sigma^2=32743.31
        \end{gathered}

        For 2020 model:

        \begin{aligned}
        &Q_1=92.75\\
        &Q_2=201.0\\
        &Q_3=306.0\\
        &\mu=197.44\\
        &\sigma=115.54\\
        &\sigma^2=13349.39
        \end{aligned}

    2. 

            n10 = len(df['2010s models'])
            m10 = np.mean(df['2010s models'])
            SE10 = stats.sem(df['2010s models'])
            Level = 0.95

            CI10 = stats.t.interval(Level, n10-1, loc=m10, scale=SE10)

            n20 = len(df['2020s models'])
            m20 = np.mean(df['2020s models'])
            SE20 = stats.sem(df['2020s models'])

            CI20 = stats.t.interval(Level, n20-1, loc=m20, scale=SE20)

            display(Latex('A ' + repr(int(Level*100)) + ' % confidence interval for the sample mean of the 2010 models is ['+
                        repr(round(CI10[0],3)) + ' ; ' + repr(round(CI10[1],3)) + ']'))
            display(Latex('A ' + repr(int(Level*100)) + ' % confidence interval for the sample mean of the 2020 models is ['+
                        repr(round(CI20[0],3)) + ' ; ' + repr(round(CI20[1],3)) + ']'))


            # Confidence interval calculations
            CI10 = stats.norm.interval(0.95, loc=m10, scale=SE10)
            CI20 = stats.norm.interval(0.95, loc=m20, scale=SE20)

            # Plotting
            plt.figure(figsize=(10, 6))
            x10 = np.linspace(m10 - 4*SE10, m10 + 4*SE10, 1000)
            z10 = np.linspace(CI10[0], CI10[1], 1000)
            y10 = stats.norm.pdf(x10, m10, SE10)
            plt.plot(x10, y10, color='blue', label='2010s models PDF')
            plt.fill_between(z10, stats.norm.pdf(z10, m10, SE10), color='blue', alpha=0.5, label='2010s CI')

            x20 = np.linspace(m20 - 4*SE20, m20 + 4*SE20, 1000)
            z20 = np.linspace(CI20[0], CI20[1], 1000)
            y20 = stats.norm.pdf(x20, m20, SE20)
            plt.plot(x20, y20, color='green', label='2020s models PDF')
            plt.fill_between(z20, stats.norm.pdf(z20, m20, SE20), color='green', alpha=0.5, label='2020s CI')

            plt.title('Probability Density Function and Confidence Intervals for 2010s and 2020s Models')
            plt.xlabel('Value')
            plt.ylabel('Probability Density')
            plt.legend()
            plt.grid(True)
            plt.show()

        A 95 % confidence interval for the sample mean of the 2020 models is [164.604 ; 230.276]

        <img src="src/ex1_2.png" alt="Confidence Intervals for 2010s and 2020s Models" width="600"/>



#### Exercise 2 (2020.5)

The dataset for this assignment is "Wages_and_Work_Hour.xlsx". This workbook contains data on fulltime workers in East North Central United States from the March 1999 CPS. The objective is to determine whether Education, Income, and Gender differ.

Variable notes:

- Education Level: Group 1 has less than 13 years of education. Group 2 has between 13 and 15 years of education (both included). Group 3 has 16 years or more of education.
- Income Group: Group 1 has less than or equal to $\$ 20,000$ in income. Group 2 has between $\$ 20,000$ and $\$ 48,000$ in income (both included). Group 3 has more than $\$ 48,000$ in income. 

<br>

1. Create a contingency table, placing Gender on the vertical axis and Education Level on the horizontal axis, and test whether gender is independent of level of education.
2. Create a contingency table, placing Gender on the vertical axis and Income Group on the horizontal axis, and test whether gender is independent of income.
3. Create a contingency table, placing Education Level on the vertical axis and Income Group on the horizontal axis, and test whether Education Level is independent of Income Group.

#### Exercise 3 (2020.6)

State the null and alternative hypotheses to be used in testing the following claims and determine generally where the rejection region is located (i.e. is it a right-, left- or two-tailed test):

1. The mean snowfall at Bygholm during the month of February is 21.8 centimeters.
2. No more than $20 \%$ of the faculty at VIA are competent teachers.
3. On the average, children attend schools within 2.62 kilometres of their homes in Denmark.
4. The proportion of voters favoring the incumbent in the upcoming American election is 0.38 .
5. The average cabbage at the grocery store weighs at least 240 grams (Source: our colleague Jakob Knop Rasmussen).

#### Exercise 4 (2020.7)

A professor in the School of Engineering in a university polled a dozen colleagues about the number of professional meetings they attended in the past five years $(x)$ and the number of papers they submitted to refereed journals $(y)$ during the same period. The summary data are given as follows:

$$
\begin{aligned}
n & =12, \quad \bar{x}=4, \quad \bar{y}=12 \\
\sum_{i=1}^n x_i^2 & =232, \quad \sum_{i=1}^n x_i y_i=318
\end{aligned}
$$


Fit a simple linear regression model between $x$ and $y$ by finding out the estimates of intercept and slope. Hint: Use the Least Squares Estimates formula from the book.

#### Exercise 5 (Reexam 2018.4)

Two producers of batteries measure the longevity of 30 batteries of the same type, which were randomly chosen from a larger batch of such batteries. The lifetime (in hundreds of hours) is displayed "Batteries.xlsx".

1. Check the dataset for outliers and replace any outliers with the mean lifetime of the producer in question. Use this cleaned dataset in the following questions.
2. Determine estimates for the quartiles, average lifetime, standard deviation and variance of each producer's battery
3. Setup $95 \%$ confidence intervals for each mean battery lifetime from the two producers, and accompany the intervals with plots that display the rejection region.
4. Is it reasonable to conclude that the lifetime of the two producer's battery follow a normal distribution? Explain using plots and discussing skewness and kurtosis.
5. Setup a $95 \%$ confidence interval for the difference between the two producer's battery, and accompany the intervals with plots that display the rejection region.
6. Is there significant evidence to support the claim that the mean lifetime of the batteries from the two producers differ from one another?
7. Setup a test to test whether the standard deviations of the two batteries differ significantly.

#### Exercise 6 (Reexam 2018.5)

Data collected in 1960 from the National Cancer Institute provides the per capita numbers of cigarettes sold along with death rates for various forms of cancer (see "Smoking and Cancer.xlsx").
1. Build regression models with cigarettes sold as the independent variable and each of the four cancer types as the dependent variable. Accompany each model with a scatterplot and a trend line as well as confidence intervals for the regression parameters.
2. For each model, inspect the residuals to confirm that the assumptions about normality and non-patterns are met.
3. Which of the four cancer types exhibit the best correlation with cigarettes sold? Assess using the correlation coefficient.
4. In which data pairs is cigarettes sold a good predictor for the type of cancer? Assess using the correlation of determination and interpret the meaning of this number.
5. For the model that has the best correlation, find the predicted value of deaths per 100 k for 40 and 50 cigarettes sold per capita. Feel free to include $95 \%$ prediction intervals to your predictions.

#### Exercise 7 (Reexam 2018.6)

The dataset for this assignment is the infamous Titanic data set (please see "Titanic.xlsx"). The objective is to determine whether the survival rates differ between selected variables.

Variable notes:

- pclass: A proxy for socio-economic status
- 1st $=$ Upper
- 2nd $=$ Middle
- 3rd $=$ Lower
- age: Age is fractional if less than 1. If the age is estimated, is it in the form of xx.5
- sibsp: The dataset defines family relations in this way...
- Sibling = brother, sister, stepbrother, stepsister
- Spouse $=$ husband, wife (mistresses and fiancés were ignored)
- parch: The dataset defines family relations in this way...
    - Parent $=$ mother, father
    - Child $=$ daughter, son, stepdaughter, stepson
    - Some children travelled only with a nanny, therefore parch=0 for them.
- alone: is a variable that was created from combining sibsp and parch.

<br>

1. Create a contingency table, placing survived on the vertical axis and pclass on the horizontal axis.
2. Test whether survival rate is independent of pclass.
3. Create a contingency table, placing survived on the vertical axis and sex (gender) on the horizontal axis.
4. Test whether survival rate is independent of sex (gender).
5. Create a contingency table, placing survived on the vertical axis and alone on the horizontal axis.
6. Test whether survival rate is independent of whether a person travelled alone or not.

#### Exercise 8 (2018.6)

The data in [Salary.xlsx](Salary.xlsx) show the (monthly) salary along with years of experience of 31 software developers.

1. Create a complete regression analysis of the data mentioned above. Your analysis must include a plot of the data, considerations about outliers, estimates for the regression parameters and confidence intervals for these, considerations about the assumptions of the model, as well as an assessment of the adequacy of the model.
2. According to the model, what salary can a newly graduated software developer with no experience expect?
3. Assuming the developer starts his/her career at 27 and retires when he/she is 67 , what will be the salary of the developer when he/she retires? Does this sound plausible?

#### Exercise 9 (2017.4)

An industrial safety program was recently instituted in the computer chip industry. The average weekly loss (averaged over 1 month) in labor-hours due to accidents in 10 similar plants both before and after the program are as follows:
<div class="center-table" markdown>
| Plant | Before | After |
| :--- | :--- | :--- |
| 1 | 30.5 | 23 |
| 2 | 18.5 | 21 |
| 3 | 24.5 | 22 |
| 4 | 32 | 28.5 |
| 5 | 16 | 14.5 |
| 6 | 15 | 15.5 |
| 7 | 23.5 | 24.5 |
| 8 | 25.5 | 21 |
| 9 | 28 | 23.5 |
| 10 | 18 | 16.5 |
</div>

1. Determine whether the safety program has had a significant effect on reducing labor-hours due to accidents in the 10 plants.
2. Is there evidence to support the claim that the program has had an effect at the $1 \%$ level of significance?

#### Exercise 10 (2017.5)

A recent study among 254 computer science graduates from Aarhus University was made in order to determine how successful the former students were in their current employment. 98 of these students had taken a course in linear algebra and of these 92 were classified as "successful" in their current employment. 136 of the students who had not taken a course in linear algebra were classified as "successful" in their current employment.

1. Is the evidence to support the claim that computer science graduates who had taken a linear algebra course were more successful in their current employment than those who had not taken such a course?
2. Explain the meaning of the p-value obtained in question (a), i.e. what does this probability refer to?

#### Exercise 11 (2017.6)

As part of their final project, two ICT students are working on a data warehouse support system. The major workload is the warehouse orders. Thus, the key business metric is identified as number of order lines. The students want to find a method to predict CPU utilization based on the number of order lines entered into the system and have collected 31 samples of CPU utilization and number of order line entries

<div class="center-table" markdown>
| Sample # | CPU Utilisation | Order lines per day |
| :--- | :--- | :--- |
| 1 | 27.01 | 16483 |
| 2 | 32.43 | 13142 |
| 3 | 21.74 | 12015 |
| 4 | 20.56 | 11986 |
| 5 | 2.85 | 1119 |
| 6 | 1.41 | 0 |
| 7 | 1.45 | 0 |
| 8 | 46.38 | 12259 |
| 9 | 21.95 | 6531 |
| 10 | 29.55 | 14086 |
| 11 | 30.04 | 12797 |
| 12 | 28.08 | 13141 |
| 13 | 3.26 | 454 |
| 14 | 1.62 | 1 |
| 15 | 29.41 | 5971 |
| 16 | 40.02 | 10901 |
| 17 | 29.86 | 14271 |
| 18 | 28.34 | 13728 |
| 19 | 34.82 | 12938 |
| 20 | 3.22 | 1158 |
| 21 | 1.43 | 0 |
| 22 | 34.22 | 11450 |
| 23 | 23.58 | 5311 |
| 24 | 33.66 | 17073 |
| 25 | 23.36 | 11336 |
| 26 | 26.76 | 7340 |
| 27 | 4.31 | 11330 |
| 28 | 2.62 | 0 |
| 29 | 33.44 | 10679 |
| 30 | 29.19 | 12803 |
| 31 | 28.11 | 12827 |
</div>

1. Create a complete regression analysis of the data above. Your analysis must include a plot of the data, considerations about outliers, estimates for the regression parameters and confidence intervals for these, considerations about the assumptions of the model, as well as an assessment of the adequacy of the model.