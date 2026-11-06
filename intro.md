# LLM Embeddings in Psychology

A 90-minute hands-on tutorial on using open-source language models as **measurement instruments for text**. You will turn sentences into vectors, test whether a model's notion of similarity matches what human participants do on a personality questionnaire, and use embeddings as features in an ordinary statistical model.

No GPU, no account and no API key are needed. Every exercise runs on the free Google Colab CPU runtime in a few minutes.

## How this book works

Each chapter has two halves. The first half is **theory**: what the method is, why it works, and what the key figure looks like. The second half is an **exercise** that you run yourself: numbered tasks that ask you to change a line and look at what happens, with a plot or a permutation test behind most of them. Read the theory here, then press the rocket button at the top of the chapter and choose *Colab* to open the exercise in a runnable copy. Sections marked *Optional* are for after the session.

```{admonition} Before the session
:class: tip
Read the [Setup](setup) page and open Chapter 1 in Colab once, so the package install and model download happen before we start.
```

## Schedule

| Time | Block | Where |
|---|---|---|
| 0:00 | Why embeddings: the two things a language model can give you | Slides |
| 0:05 | [Chapter 1](01_vectors): from words to vectors | Theory, then exercise: guess first, a similarity heatmap, word shuffling, negation |
| 0:30 | [Chapter 2](02_personality): sentence embeddings and personality items | Theory, then exercise: nearest items, a permutation test, keying, a map, your own item, the fine-tuned model |
| 1:10 | [Chapter 3](03_features): embeddings as features for prediction | Theory, then exercise: a classifier, you versus the model, permutation and bootstrap |
| 1:25 | Applications in the field, where to go next | Slides and [References](references) |

## What you will be able to do afterwards

- Explain what an embedding is and why cosine similarity is the right comparison.
- Embed any list of texts with three lines of Python and compute a similarity matrix.
- Compare model-predicted similarity against empirical correlations, map items in two dimensions, and classify items by construct.
- Train a classical classifier on embeddings and evaluate it without leaking information from the test set.
- Choose an embedding model from a public leaderboard and know when domain fine-tuning pays off.

## Prerequisites

Basic familiarity with questionnaires and correlation. No Python experience is required: every cell is explained, and the tasks ask you to change a value or a string, not to write code from scratch.

## Credits

The exercises and most figures are adapted from the [LLM4BeSci course](https://github.com/dwulff/LLM4BeSci_2025MetaRep) by Zak Hussain, Taisiia Tikhomirova, Valentin Kriegmair and Dirk Wulff (MPIB Berlin, December 2025), released under CC BY-SA 4.0. The personality analysis follows Wulff and Mata (2025). See [References](references) for the full list and the license of this book.
