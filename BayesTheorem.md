---
jupytext:
  formats: md:myst
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.11.5
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---

# Probability and Bayes' theorem
Bayes' theorem is a powerful, yet simple, piece of maths that allows us to ask questions of the form: 'What is the probability that a model is correct given that we have this data?'

Probability can be considered as being a measure of how likely a specific event (e.g. a flipped coin comes up heads, a covid test gives a false negative, etc.) is to occur. Typically we assign a number to this probability - with zero corresponding to the event will not happen, and a value of one guaranteeing that it will happen.

In many areas of science and engineering we want to be able to assess how well a model fits some data (or what parameter values give the best fit to some data). In probality terms this is asking what is the probability that the model is right given the data? However, we can't measure this probability. What we can measure is the related question: what is the probability of the data given a model? Bayes' theorem provides a logical link between the two questions and importantly a

## Conditional Probability
The probability that event $A$ will happen notwithstanding any other events is given by:

$$P(A)$$

The probability that event $A$ will happen given that some other event ($B$) has occured is 

$$P(A|B)$$

This is an example of *conditional probability*.

Using this notation, there are a couple of important probability results that we need moving forward. First:

$$P(A|I) + P(\bar{A}|I) = 1$$(probsum)

The bar is a logical $not$ operation. Equation {eq}`probsum` tells us that probabilities of events predicted must add to one. Note, $I$ is commonly used to represent all the background information relevant to the system. The second result is:

$$P(A,B|I) = P(A|B,I)P(B|I)$$(joint)

Here the comma indicates the logical and operation. This equation tells us that the probability of both $A$ and $B$ occuring given $I$ is the probability that $A$ happens given $B$ has happened multiplied by the probability of $B$ occuring.

## Bayes' Theorem and Marginalisation
We can also write:

$$P(B,A|I) = P(B|A,I)P(A|I)$$(joint2)

If $A$ and $B$ are independant events then equations {eq}`joint` and {eq}`joint2` must be equal and we can equate the right hand sides of these equations:

$$P(A|B,I)P(B|I)=P(B|A,I)P(A|I)$$

Which rearranges to give us Bayes' theorem: 

$$P(A|B,I)=\frac{P(B|A,I)P(A|I)}{P(B|I)}$$(bayes)

To see why this unprepossessing equation is so useful, replace $A$ and $B$ by $hypothesis$ and $data$ respectively:

$$P(hypothesis|data,I)\propto P(data|hypothesis,I)P(hypothesis)$$(bayesprop)

This tells us that the probability of the hypothesis (i.e. the model of the data) given the data obtained which is something we cannot measure/assess is proportional to the product of the probability that the hypothesis would give that data multiplied by the probability of the hypothesis.

The components of {eq}`bayes` have special terminology associated with them:

$P(A|B,I)\rightarrow\textnormal{Posterior probability}$
 
$P(B|A,I)\rightarrow\textnormal{Likelihood}$

$P(A|I)\rightarrow\textnormal{Prior probability}$

$P(B|I)\rightarrow\textnormal{Evidence}$

As you get more familiar with Bayesian methods this terminology will make more sense. However, it is worth spending a moment to consider the Prior probability. This term tells us that it contains what we know about the system before the measurement being considered was made. One of the powerful aspects of bayesian methods is that we can update our calculation when new information/data is arrived at. We can use the posterior probability from one iteration as the prior probability for the next.

### Marginalisation

It can be shown (e.g. Lambert{cite}`lambertStudentGuideBayesian2018`) that equations {eq}`joint` and {eq}`probsum` can be used to give the following result:

```{math}
:label: margn
 P(X|I) = \int\limits_{-\infty}^{\infty}P(X,Y|I)dY
```

Thus, the evidence for a particular parameter can be found by integrating over the other parameters of the system. This is known as *marginalisation*. This is one of the key advantages of bayesian analysis over frequentist approaches. In the later it is often extremely difficult if not impossible to remove the effect of what are known as *nuisance* parameters.

### Next steps
We now have the basic relations that we need to start doing Bayesian analysis. The chapters that follow will illustrate how to use these in order to do science and engineering relevent data analysis. Parameter estimation will be introduced first followed by a look at model selection.

## Bibliography
```{bibliography}
:filter: docname in docnames
```