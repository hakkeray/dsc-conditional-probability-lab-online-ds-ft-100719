
# Conditional Probability - Lab

## Introduction

In order to be ready for real-world applications of probability, it is important to understand what happens when probabilities are not independent. Very often, the probability of a certain event depends on other events happening! Let's see how this all works in this lab.

## Objectives

You will be able to:

* Differentiate between independent and dependent events
* Use the multiplication rule to find the probability of the intersection of two events

## Exercise 1
A coin is tossed and a single 6-sided dice is rolled. Find the probability of landing on the head side of the coin and rolling a 3 on the dice.


```python
# Independent events : addition rule
# P(heads) = 0.5, P(three) = 1/6 = 0.167
p_h = 1/2
p_3 = 1/6
P = p_h * p_3
print(P)
```

    0.08333333333333333


## Exercise 2


After conducting a survey, one of the outcomes was that 8 out of 10 of the survey subjects liked chocolate chip cookies. If three survey subjects are chosen at random **with replacement**, what is the probability that all three like chocolate chip cookies?


```python
# permutation with replacement 8/10 chance all three times
.80 * .80 *.80
```




    0.5120000000000001



## Exercise 3
70% of your friends like chocolate flavored ice cream, and 35% like chocolate AND like strawberry flavors.

What percent of those who like chocolate also like strawberry?


```python
# P(A) = 0.7, P(B) = 0.35
#P(B|A) = P(Choc and Straw) / P(choc) = .35 / .7 = 0.50
.35 / .7
```




    0.5



50% of your friends who like chocolate also like strawberry

## Exercise 4
What is the probability of drawing 2 consecutive aces from a deck of cards. 


```python
# 4/52
# 3/51
# product rule: P_AB = P_A * P_B_given_A
(4/52)*(3/51)
```




    0.004524886877828055



## Exercise 5
In a manufacturing factory that produces a certain product, there are 100 units of the product, 5 of which are defective. We pick three units from the 100 units at random. 

What is the probability that none of them are defective?
Hint: Use the chain rule here!


```python
P_A = 95/100 # 5 def out of 100
P_BgivA = 94/99 # 5 def out of 99 (removed 1 good)
P_C_givAB = 93/98 # 4 def out 98 (removed 2 good)
P = P_A * P_BgivA * P_C_givAB
print(P)
```

    0.8559987631416203


## Exercise 6

Let's consider the example where 2 dice are thrown. Given that **at least one** of the dice has come up on a number higher than 4, what is the probability that the sum is 8?

Let $i,j$ be the numbers shown on the dice. The events $A$ and $B$ are described below:

* **Event $A$ is when either $i$ or $j$ is 5 or 6** (keep an eye on either - or)
* **Event $B$ is when $i + j = 8$**


* What is the size of sample space $\Omega$ ?
* What is $P(A \cap B)$ ?
* What is $P(A)$ ?
* Use above to calculate $P(B \mid A)$


```python
# Sample space = 6*6 = 36
# P_A = 5 or 6 two rolls = 2 * 2 rolls = 4
# P_B = i + j ; j = 3 or 2 = 3 + 2 = 5
# P_AB = (5*4) = 20

P_BgivA = (4/36)/(20/36)
print(P_BgivA)
```

    0.19999999999999998


## Exercise 7

Let's consider a credit card example. At a supermarket, customers are selected randomly, the store owner recorded whether costumers owned a Visa card (event A) or an Amex credit card (event B). Some customers own both cards.
You can assume that:

- $P(A)$ = 0.5
- $P(B)$ = 0.4
- both $A$ and $B$ = 0.25.


With the knowledge we have about conditional probabilities, compute and interpret the following probabilities:

- $P(B \mid A)$
- $P(B' \mid A)$
- $P(A \mid B)$
- $P(A' \mid B)$



```python
p_A = 0.5
p_B = 0.4
p_AB = 0.25

# 𝑃(𝐵∣𝐴)
p_AgivB = p_AB/p_A
print(p_AgivB)

# 𝑃(𝐵′∣𝐴)
p_Bprime_giv_A = 1 - p_A
print(p_Bprime_giv_A)

# 𝑃(𝐴∣𝐵) 
p_BgivA = p_AB/p_B
print(p_BgivA)

# 𝑃(𝐴′∣𝐵)
p_Aprime_giv_B = 1 - p_BgivA
print(p_Aprime_giv_B)
```

    0.5
    0.5
    0.625
    0.375


## Summary 

In this lab, you practiced conditional probability and its theorem with some simple problems. The key takeaway from this lab is to be able to identify random events as dependent or independent and calculating the probability of their occurrence using appropriate methods. Next, you'll learn about some more conditional probability axioms, building on the knowledge we have so far. 
