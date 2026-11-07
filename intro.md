# LLM Embeddings in Psychology

Psychological and neurodevelopmental tests are made of language: every item is a piece of text carrying assumptions about what it measures. Sentence-embedding models make that text computationally tractable by mapping items into a vector space where geometric proximity corresponds to semantic similarity. This opens a sample-independent window on old psychometric questions: Which items belong together? Do test constructs match their semantic structure? Where do two editions of a test diverge?

In this 90-minute hands-on seminar you build the complete pipeline in Python with open-source tools and openly accessible items. Starting from raw item text, you extract embeddings, compute pairwise similarities, compare them with the observed correlations between participants' responses, map the item space in two dimensions, and attempt to recover the test's construct structure without any response data, discussing where and why this fails.

No prior experience with language models is required. Basic familiarity with Python helps but is not needed: every cell is explained, and the tasks ask you to change a value or a line of text. Everything runs on the free Google Colab CPU runtime, so there is nothing to install.

## How this book works

Each part has a **theory page** and an **exercise notebook**. The theory page is read here. The notebook opens in Colab from the rocket button at the top of its page. It has no outputs yet: they appear as you run the cells. The main blocks are run together, with the group; the **TASK** cells are yours to explore at your own pace, and the bonus tasks are for afterwards.

```{admonition} Before the session
:class: tip
Read the [Setup](setup) page and open Exercise 1 in Colab once, so that the package install and the model download happen before we start.
```

## Programme

| Time | Block | Where |
|---|---|---|
| 0:00 | Why items are text, and what an embedding gives you | Slides |
| 0:10 | [Part 1](01_vectors): from words to vectors | Theory page, then [Exercise 1](exercises/01_warmup) |
| 0:35 | [Part 2](02_personality): the item pipeline | Theory page, then [Exercise 2](exercises/02_items) |
| 1:20 | A real application: decomposing the cognition scale of the Bayley-III | Slides |
| 1:30 | Where to go next | [References](references) |

[Part 3](03_features), embeddings as features for prediction, is take-home material: the same vectors become predictors in an ordinary statistical model.

## What you will be able to do afterwards

- Explain what an embedding is and why cosine similarity is the right comparison.
- Extract embeddings for a set of items with three lines of Python and compute all pairwise similarities.
- Compare model-predicted similarity against empirical item correlations, and test whether the agreement beats chance.
- Map items in two dimensions and read the map critically.
- Assign items to constructs from text alone, and say where and why that fails.
- Judge when a model fine-tuned on items is worth the effort, and what a fair evaluation of it needs.

## Credits

The exercises and most figures are adapted from the [LLM4BeSci course](https://github.com/dwulff/LLM4BeSci_2025MetaRep) by Zak Hussain, Taisiia Tikhomirova, Valentin Kriegmair and Dirk Wulff (MPIB Berlin, December 2025), released under CC BY-SA 4.0. The personality analysis follows Wulff and Mata (2025). See [References](references) for the full list and the license of this book.
