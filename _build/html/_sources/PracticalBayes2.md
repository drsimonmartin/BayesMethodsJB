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

# Getting Bayes Done – Pt 2
 
## Introduction

So far the problems looked at in these notes have been fairly abstract and/or simple in order to show the fundemental  principles of bayesian methods. This chapter explores how to move to calculations for realistic data (type and scale of models). There is a reasonable amount that can be done via algebraic methods. However, the maths rapidly gets reasonably complicated and is only tractable for a limited number of cases (data models). Historically this is one of the things that has held back the development of Bayesian methods. Since the 1990s a range of computer based methods have been developed that from the users' point of view sidestep much of the complex mathematics. This chapter will show how these can be used.

The previous chapter shows that for low dimensional problems the calculations can be done by calculating the product of the prior and likelihood distributions. However, as the dimensionality (number of parameters) increases this becomes impossible[^Really] and other methods are required. These other methods are most commonly Monte Carlo methods and it is these that we will concentrate on. Specifically we will use the [PyMC library](https://www.pymc.io/welcome.html) - a modern, python based, system allows probabalistic models to be built in a straightforward way.  

[^Really]: It doesn't take long to get to a model that it would take the most powerful computers the age of the universe to explore.

## Monte Carlo or bust

### The curse of dimensionality

## A first MCMC model


## Bibliography 

```{bibliography}
:filter: docname in docnames

```
