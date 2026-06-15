# Predicting Future Behaviors in Reasoning Models Enables Better Steering
Evgenii Kortukov, Piotr Komorowski, Florian Klein, Paula Engl, Gabriele Sarti, Seong Joon Oh, Sebastian Lapuschkin, Wojciech Samek


>teaser figure

Interpretability tools that predict and control model behaviors typically rely on contrastive input pairs.
This binary data hides the probabilistic nature of language model decision making.
During reasoning, LLMs can keep track of multiple behavioral options before committing.
We find that these future behavior distributions are reflected in their representations.
We can steer the behavioral outcome by choosing the reasoning sentences that maximize the estimated probability of a future behavior.