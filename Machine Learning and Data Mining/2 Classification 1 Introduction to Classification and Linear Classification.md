# Classification: Introduction to Classification and Linear Classification

## Introduction
classification = concept learning methods dominate ML.

often no convenient mathematical properties like regression

&nbsp;&nbsp;&nbsp;&nbsp;=> more complicated to analyze

the idea is to learn a "classifier" = usually a function mapping from an *input data* point to *one of a set of discrete outputs* = the **classes**

### Example: Classifying sea bass vs. salmon
Imagine that we want to automate sorting incoming fish in a fish-packing plant. 
As a pilot, we start by separating sea bass from salmon using some collected through sensing.

![The objects to be classified; a. Sea bass, and b. salmon.](https://www.byclb.com/TR/Tutorials/neural_networks/images/fig1.4.jpg)

Features that can be used: width, length, weight, lightness, fins, eyes/mouth position, etc.

#### __Question: how to separate these two classes?__

We might find a line that separates the two classes.

![The two features of lightness and width for sea bass and salmon.](https://www.byclb.com/TR/Tutorials/neural_networks/images/fig1.8.jpg)

If we find the line that separates the two classes, then how does our algorithm make a prediction?

The linear equation will look like: $ax_1 + bx_2 + c = 0$

We can define $a, b$ & $c$ such that:

&nbsp;&nbsp;&nbsp;&nbsp;for any point above the line:

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;$ax_1 + bx_2 + c > 0$, vice versa.

This type of classifier is called __linear classifier__.

Also a type of __discriminative learning algorithm__.

### Alternative way: __Generative Learning Algorithm__
Instead of finding a discriminative line -> 

&nbsp;&nbsp;&nbsp;&nbsp;focus one one class at a time => build a model = describing how that class looks like

&nbsp;&nbsp;&nbsp;&nbsp;-> Do the same for the other class

_Generavie vs. Discriminative Learning ALgorithm_

![generative vs discriminative](https://www.baeldung.com/wp-content/uploads/sites/4/2021/04/gen_vs_disc-versus-1.png)

![generative vs discriminative table](https://www.baeldung.com/wp-content/ql-cache/quicklatex.com-42db9c8d268c78bc42ac756aed6f9f45_l3.svg)

|Examples|Generative Algorithms|Discriminative Algorithms|
|---|---|---|
||Naive Bayes Classifier|k-nearest neighbors (k-NN)|
||Generative Adversarial Networks|Logistic regression|
||Gaussian Mixture Model|Support Vector Machines (SVMs)|
||Hidden Markov Model|Decision Trees|
||Probabilistic context-free grammar|Random Forest|
|||Artificial Neural Networks (ANNs)

## _Generavie vs. Discriminative Learning ALgorithm_
__Generative Algorithm__: 

1. Build some __"models"__ for each of the __classes__ i.e., build models for different classes
2. Make classification predictions based on looking at the test example
3. See it is more similar to which of the models

  - __Learns $p(x|y)$__ and also $p(y)$ := class prior
                                     = an estimate of the probability "that randomly sampling an instance from a population" will yield the given class (regardless of any attributes of the instance).
  - $p(x, y) = p(x|y)p(y)$
  - Learns the mechanism by which the data has been generated

&nbsp;&nbsp;&nbsp;&nbsp;To predict the output for sample $x$, in a **generative algorithm**, we have to estimate $p(y|x)$:
    
$$p(y = 0|x) = \frac{p(x|y = 0)p(y = 0)}{p(x)}$$
    

$$p(y = 1|x) = \frac{p(x|y = 1)p(y = 1)}{p(x)}$$
    

$p(y = 0|x) > p(y = 1|x)$ => $x$ belongs to class $y = 0$ OTHERWISE to calss $y = 1$.

__ Disciriminative Algorithm__:

Finding a decision boundary that separates classes
  - Learns $p(y|x)$

Directly have $p(y = 0|x)$ and $p(y = 1x)$ and similar to above.

$p(y = 0|x) > p(y = 1|x)$ => $x$ belongs to class $y = 0$ and OTHERWISE to class $y = 1$.

## Linear Classification in Two Dimensions

![image](https://github.com/Eidellin/interview_preparation/assets/83224546/6486cb41-0b55-4e42-b922-1ee9f9b79860)

- Find the **line** that **separates the two classes**: $ax_1 + bx_2 + c = 0$
- Define a **weight vector** $w^T = [a, b]$, $x^T = [x_1, x_2]$
- SO, the line can be defined by $x^Tw = -c = t$
- $w$ is **perpendicular** to **decision boundary** in **direction of + class**
- $t$ is the **decision threshold** i.e., $x^Tw > t$ => $x$ belongs to + class, vice versa.

## Basic Linear Classifier
Construct a **decision boundary** by half-way intersecting the line between the + and - centers of mass.

![image](https://github.com/Eidellin/interview_preparation/assets/83224546/6fe6de77-2cf1-4117-bbef-f80d360618c8)

The basic linear classifier is DESCRIBED by the **equation** $x^Tw = t$ & $w = p - n$.

$\frac{p+n}{2}$ = "mid point of n and p" is on the decision boundary.

&nbsp;&nbsp;&nbsp;&nbsp;=> $t = (\frac{p + n}{2})^T \cdot (p - n) = \frac{\|p\|^2 - \|n\|^2}{2}$

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;where $\|x\|$, denotes the length of vector $x$.
