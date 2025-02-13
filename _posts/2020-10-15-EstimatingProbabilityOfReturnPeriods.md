---
title: 'Estimating the Probability a Flood Occurs over the Length of Your Mortgage'
date: 2020-10-15
permalink: /posts/2020/10/15/Estimating-the-Probability-a-Flood-Occurs-over-the-Length-of-Your-Mortgage
tags:
  - Statistics
  - Flooding
  - Miscommunicating Engineering Terms
  - CC
---

# Calculating Flood Risk

If at some point you ever want to buy a house near water, a variation of this question will undoubtedly pass through your head:

*What are the chances my {insert name of your expensive piece of property close to water} floods?*

In this post we will calculate the chance of an event happening, ie. the chance your beautiful riverside property floods over the life of your 30-year mortgage.
We will do this using our understanding of probability and statistics.
The result will be a pretty figure and useful table you can return to when you want to understand the likelihood of something happening.
As a tl;dr, I'll put them here at the top too:

<img src="https://gregjewi.github.io/images/flood-stats-table.png">

<img src="https://gregjewi.github.io/images/FloodExcedanceCurves.svg">

## Laying the groundwork
In my experience the question of understanding the probability of flood exceedance is a great example of where calculating the probability of something **not** happening is more intuitive and easier to understand.
It also shows how flood terminology obscures/confuses the probabilistic nature of estimating a chance of flooding.

## Flood Events, Return Periods, and Probability
I have found that there is a fundamental misunderstanding of the vocabulary used to communicate the probability of a flood event.
You may have heard something like this before:

*"Bob, the heavy rains north of Waterville were responsible for the 100-year flood event downtown."*

or

*"The city updated their flood maps to include our house in the 100-year floodplain"*

Do you know what is *really* meant by the term "100-year Flood"?
It is **NOT** the case that this event will *only* happen once every 100 years.

**Definition**: a "X-year Flood" conveys that *in any given year* there is a $\frac{1}{X}$ chance that a flood event of that magnitude will occur. 
The name 100-year Flood conveys that there is a $\frac{1}{100}$, or 0.01 (1%,) chance of that magnitude event occurring; for a 50-year flood, 0.02 (2%); 2-year flood, 0.5 (50%.)

Of course, all of these probabilities describe the chance an event happens *in a single year*.
What is more helpful, is knowing the probability that an event occurs at least once over multiple years.
Let's calculate that.

## Formulating Exceedance Probability
To make this calculation tractable, we first make some assumptions.
(This is not just me making these assumptions, a lot of engineering design calculations are based upon these assumptions.)
We assume that the probabilities of flooding each year are *independent* and *stationary*.
Independence means that the probability of occurrence of a certain size flood in one year does not change the probability of a flood in any other years.
Stationary means that the probability does not change over time; i.e. in 30 years the probability and size of a 100-year flood will be the same as today.

Next, we must reconsider the question:
we want to know what the probability is of a certain sized flood happening *at least once* over $n$ consecutive years.
The complement of this question would be:

*What is the probability that a flood of size X **does not** occur during the next $n$ consecutive year?*

In any given year it is 100% likely that it will or will not flood to a certain extent.
Therefore, the probability that a flood of size X **does not** flood is the *complement* of the probability that it will, or 

$$P(X > x) = 1 - P(X < x)$$

Because the No-Flood condition,  $P(X < x)$, for each year is independent of each other, their joint probability is their product.
Thus, the probability that a flood of size X does not occur during $n$ consecutive years is

$$P(X > x)_{n} = (1 - P(X < x))_{1} \times (1 - P(X < x))_{2} \times \cdots (1 - P(X < x))_{n} $$

or,

$$P(X > x)_{n} = \left(1 - P(X < x)\right)^{n}$$

We now have a formula to calculate the probability that a flood of size X will not occur over $n$ consecutive years.
Now we can take its complement to determine the probability that a flood of size X will occur *at least once* over $n$ consecutive years.

$$P(X < x)_{n} = 1 - \left(1 - P(X < x)\right)^{n}$$

## Calculating Exceedance Probabilities
Equation in hand, we can plug in any combination values we are interested in!
The table below shows the probability that a flood of various sizes will occur at least once over a 30 year period.

<img src="https://gregjewi.github.io/images/flood-stats-table.png">

The graph below shows how these probabilities grow over the course of 30 years.

<img src="https://gregjewi.github.io/images/FloodExcedanceCurves.svg">

You now can determine the chances your house will flood over any length of time for any size flood. 
This, however, will not help you build a castle on a swamp. 
For that, you will need to consult [this guy](https://youtu.be/w82CqjaDKmA).

**Footnote**: 
You may be asking, how does one estimate the flood extent for an event with 1% chance of happening every year?
Great question.
I might write about that in the future.
Stay tuned.