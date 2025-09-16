# STATS506HW2
Homework #2 Repo
Margaret Miles

Link: https://dept.stat.lsa.umich.edu/~jerrick/courses/stat506_f25/ps02.html

Problem 1 - Modified Random walk
Consider a 1-dimensional random walk with the following rules:

Start at 0.
At each step, move +1 or -1 with 50/50 probability.
If +1 is chosen, 5% of the time move +10 instead.
If -1 is chosen, 20% of the time move -3 instead.
Repeat steps 2-4 
 times.
(Note that if the +10 is chosen, it’s not +1 then +10, it is just +10.)

Write a function to determine the end position of this random walk.

The input and output should be:

Input: The number of steps
Output: The final position of the walk
> random_walk(10)
 [1]  4

> random_walk(10)
 [1]  -11

We’re going to implement this in different ways and compare them.

Implement the random walk in these three versions:

Version 1: using a loop.
Version 2: using built-in R vectorized functions. (Using no loops.) (Hint: Does the order of steps matter?)
Version 3: Implement the random walk using one of the “apply” functions.
Demonstrate that all versions work by running the following:

random_walk1(10)
random_walk2(10)
random_walk3(10)
random_walk1(1000)
random_walk2(1000)
random_walk3(1000)

Demonstrate that the three versions can give the same result. Show this for both n=10 and n=1000. (You will need to add a way to control the randomization.)

Use the microbenchmark package to clearly demonstrate the speed of the implementations. Compare performance with a low input (1,000) and a large input (100,000). Discuss the results.

What is the probability that the random walk ends at 0 if the number of steps is 10? 100? 1000? Defend your answers with evidence based upon a Monte Carlo simulation.

Problem 2 - Mean of Mixture of Distributions
The number of cars passing an intersection is a classic example of a Poisson distribution. At a particular intersection, Poisson is an appropriate distribution most of the time, but during rush hours (hours of 8am and 5pm) the distribution is really normally distributed with a much higher mean.

Using a Monte Carlo simulation, estimate the average number of cars that pass an intersection under the following assumptions:

From midnight until 7 AM, the distribution of cars per hour is Poisson with mean 1.
From 9am to 4pm, the distribution of cars per hour is Poisson with mean 8.
From 6pm to 11pm, the distribution of cars per hour is Poisson with mean 12.
During rush hours (8am and 5pm), the distribution of cars per hour is Normal with mean 60 and variance 12
Accomplish this without using any loops.

(Hint: This can be done with extremely minimal code.)

Problem 3 - Linear Regression
Use the following code to download the YouTube Superbowl commercials data:

youtube <- read.csv('https://raw.githubusercontent.com/rfordatascience/tidytuesday/master/data/2021/2021-03-02/youtube.csv')

Information about this data can be found at https://github.com/rfordatascience/tidytuesday/tree/main/data/2021/2021-03-02. The research question for this project is to decide which of several attributes, if any, is associated with increased YouTube engagement metrics.

Often in data analysis, we need to de-identify it. This is more important for studies of people, but let’s carry it out here. Remove any column that might uniquely identify a commercial. This includes but isn’t limited to things like brand, any URLs, the YouTube channel, or when it was published.

Report the dimensions of the data after removing these columns.

For each of the following variables, examine their distribution. Determine whether i) The variable could be used as is as the outcome in a linear regression model, ii) The variable can use a transformation prior to being used as the outcome in a linear regression model, or iii) The variable would not be appropriate to use as the outcome in a linear regression model.

For each variable, report which category it falls in. If it requires a transformation, carry such a transformation out and use that transformation going forward.

View counts
Like counts
Dislike counts
Favorite counts
Comment counts
(Hint: At least the majority of these variables are appropriate to use.)

For each variable in part b. that are appropriate, fit a linear regression model predicting them based upon each of the seven binary flags for characteristics of the ads, such as whether it is funny. Control for year as a continuous covariate.

Discuss the results. Identify the direction of any statistically significant results.

Consider only the outcome of view counts. Calculate 
 manually (without using lm) by first creating a proper design matrix, then using matrix algebra to estimate 
. Confirm that you get the same result as lm did in part c.
