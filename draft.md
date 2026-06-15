# Predicting Future Behaviors in Reasoning Models Enables Better Steering
Evgenii Kortukov, Piotr Komorowski, Florian Klein, Paula Engl, Gabriele Sarti, Seong Joon Oh, Sebastian Lapuschkin, Wojciech Samek



Interpretability tools that predict and control model behaviors typically rely on contrastive input pairs.
This binary data hides the probabilistic nature of language model decision making.
During reasoning, LLMs can keep track of multiple behavioral options before committing.
We find that these future behavior distributions are reflected in their representations.
We can steer the behavioral outcome by choosing the reasoning sentences that maximize the estimated probability of a future behavior.

>teaser figure

---

## Probabilistic view of LRM decision-making

Analyzing a single roll-out of a reasoning model is not enough to understand its behavior.
Instead, we resample after every reasoning step to get a probability of a future behavior happening after this step.
This allows us to see where the model commits to act in a certain way.

>figure on behavior distribution dynamics

## Predicting future behaviors $\neq$ detecting current behaviors

We train a probe to predict these future behavior probabilities.
Typically, one can estimate the most likely behavior with high accuracy.
[Click here to explore how these probe predictions look like](https://behavior-distributions-demo.github.io/).

Binary classifiers on contrastive data, typically used for detection and steering, are bad predictors of future behaviors.
Models represent behaviors that already happened differently from the ones that will happen in the future.

> figure of detection vs. prediction features

## Steering the model towards a desired future behavior

Estimating the probability of a future behavior can be used to steer the model towards a desired outcome.
We propose a simple algorithm that samples multiple candidates for each sentence, and selects the best using an activation probe that predicts future behavior likelihoods.

> FPCG algorithm 