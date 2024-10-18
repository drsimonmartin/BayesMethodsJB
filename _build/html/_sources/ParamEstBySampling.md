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
# Real world Bayesian Parameter Estimation

## Why sampling methods are used for Bayesian analysis

Recap Bayes theorem: $$P(\theta|data,I)=\frac{P(data|\theta,I)P(\theta|I)}{P(data|I)}$$

where $\theta$ are the parameters of a model, $data$ are the measurements/results, and $I$ is the information we know about the system.




Typically we want to know how well a model fits the data – what sort of spread of values fits the data in a credible way, an idea of the optimum parameters, etc.? To get these results we need the posterior probability distribution