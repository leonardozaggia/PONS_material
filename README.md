# LLM embeddings in psychology

Material for a 90-minute hands-on seminar on using language-model embeddings in psychological research.

**Read the tutorial here: https://leonardozaggia.github.io/PONS_material/**

## What you need

- A Google account, to run the exercises on [Google Colab](https://colab.research.google.com) for free. Nothing is installed on your computer.
- No Python experience. Every cell is explained, and the tasks ask you to change a value or a line of text, not to write code from scratch.
- Some familiarity with questionnaires and correlation.

## How the session works

Each chapter starts with a short theory section and ends with an exercise you run yourself.

| Chapter | Topic | What you do |
|---|---|---|
| 1. From words to vectors | Why a word is defined by its context, and how a model turns text into numbers | Guess which sentences are similar, then check; shuffle word order; test negation |
| 2. Sentence embeddings and personality items | How a transformer builds a sentence embedding | Embed 300 personality items, test their similarity against real correlations with a permutation test, map them, write your own item, switch to a fine-tuned model |
| 3. Embeddings as features | Using embeddings as input to a classical model | Train a classifier on tweets, compete against it, and evaluate it with permutation and bootstrap |

To run an exercise, open the chapter in the tutorial, click the rocket icon at the top of the page and choose **Colab**. Run the cells from top to bottom. The first cell installs what is needed and takes about a minute. The [Setup](https://leonardozaggia.github.io/PONS_material/setup.html) page walks through this step by step and lists common problems.

If you prefer to open the notebooks directly:

- [Chapter 1](https://colab.research.google.com/github/leonardozaggia/PONS_material/blob/main/01_vectors.ipynb)
- [Chapter 2](https://colab.research.google.com/github/leonardozaggia/PONS_material/blob/main/02_personality.ipynb)
- [Chapter 3](https://colab.research.google.com/github/leonardozaggia/PONS_material/blob/main/03_features.ipynb)

The figures in the theory sections only show in the tutorial, not in the Colab copy.

## After the seminar

The notebooks keep working after the session, so you can rerun them with your own items or texts. The [References](https://leonardozaggia.github.io/PONS_material/references.html) page lists the papers behind the exercises, the tools, and where to find other embedding models.

## License

CC BY-SA 4.0. The exercises and figures are adapted from the [LLM4BeSci course](https://github.com/dwulff/LLM4BeSci_2025MetaRep) by Zak Hussain, Taisiia Tikhomirova, Valentin Kriegmair and Dirk Wulff. See the References page for details and the list of changes.

---

<details>
<summary>Notes for maintaining this repository</summary>

This repository is a [Jupyter Book](https://jupyterbook.org) (1.x). Pushing to `main` runs `.github/workflows/book.yml`, which builds the book and publishes it to GitHub Pages. Pages must be set to the **GitHub Actions** source in the repository settings.

The chapter notebooks are committed with their outputs and are not re-executed at build time (`execute_notebooks: "off"`), so the build needs neither torch nor a model download. If you change a code cell, rerun the notebook before committing:

```bash
pip install sentence-transformers pacmap
jupyter nbconvert --to notebook --execute --inplace 0*.ipynb
```

To build locally:

```bash
pip install -r requirements.txt
jupyter-book build .
```

Expected results, measured on a CPU on 2 Nov 2026:

| Result | `all-MiniLM-L6-v2` | `dwulff/mpnet-personality` |
|---|---|---|
| r(predicted, observed item correlations) | .18 | .37 |
| r on absolute values | .33 | .95 |
| Item to facet assignment accuracy (chance .03) | .23 | .45 |
| Tweet bias test accuracy (chance .50) | .76 | .77 |

`slide_picks.md` lists which course slides to use in the live talk and a run-of-show. The Colab links are built from the repository URL in `_config.yml`; change it there if the repository moves.

</details>
