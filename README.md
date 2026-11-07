# LLM embeddings in psychology

Material for a 90-minute hands-on seminar on using language-model embeddings in psychological research.

**Read the tutorial here: https://leonardozaggia.github.io/PONS_material/**

## What you need

- A Google account, to run the exercises on [Google Colab](https://colab.research.google.com) for free. Nothing is installed on your computer.
- No Python experience. Every cell is explained, and the tasks ask you to change a value or a line of text, not to write code from scratch.
- Some familiarity with questionnaires and correlation.

## How the session works

Each chapter starts with a short theory section and ends with an exercise you run yourself.

| Part | Theory page | Exercise notebook |
|---|---|---|
| 1. From words to vectors | Why a word is defined by its context, and how a model turns text into numbers | Three sentences become vectors; similarity heatmaps; what the model ignores |
| 2. Items as text (the core) | How a transformer builds a sentence embedding, and why items are text | The full pipeline on 300 personality items: embed, compare with observed correlations, permutation test, map, recover constructs, your own item, a fine-tuned model |
| 3. Beyond similarity (take-home) | Embeddings as features for prediction | A tweet classifier with permutation test, bootstrap and learning curve |

To run an exercise, open its notebook page in the tutorial, click the rocket icon at the top of the page and choose **Colab**. The notebook has no outputs yet; they appear as you run the cells from top to bottom. The first cell installs what is needed and takes about a minute. The [Setup](https://leonardozaggia.github.io/PONS_material/setup.html) page walks through this step by step and lists common problems.

If you prefer to open the notebooks directly:

- [Exercise 1: from sentences to vectors](https://colab.research.google.com/github/leonardozaggia/PONS_material/blob/main/exercises/01_warmup.ipynb)
- [Exercise 2: items as text](https://colab.research.google.com/github/leonardozaggia/PONS_material/blob/main/exercises/02_items.ipynb)
- [Exercise 3: embeddings as features](https://colab.research.google.com/github/leonardozaggia/PONS_material/blob/main/exercises/03_features.ipynb)

The `solutions/` folder holds the same notebooks with their outputs. They are published as unlisted pages linked from the book's References page.

## After the seminar

The notebooks keep working after the session, so you can rerun them with your own items or texts. The [References](https://leonardozaggia.github.io/PONS_material/references.html) page lists the papers behind the exercises, the tools, and where to find other embedding models.

## License

CC BY-SA 4.0. The exercises and figures are adapted from the [LLM4BeSci course](https://github.com/dwulff/LLM4BeSci_2025MetaRep) by Zak Hussain, Taisiia Tikhomirova, Valentin Kriegmair and Dirk Wulff. See the References page for details and the list of changes.

---

<details>
<summary>Notes for maintaining this repository</summary>

This repository is a [Jupyter Book](https://jupyterbook.org) (1.x). Pushing to `main` runs `.github/workflows/book.yml`, which builds the book and publishes it to GitHub Pages. Pages must be set to the **GitHub Actions** source in the repository settings.

The theory lives in `01_vectors.md`, `02_personality.md` and `03_features.md`. The exercise notebooks in `exercises/` are committed **without outputs** and are not executed at build time (`execute_notebooks: "off"`), so the book build needs neither torch nor a model download. The executed copies in `solutions/` are exported to static HTML by the workflow and copied into the site under `solutions/`, linked only from the References page. Regenerate them after changing an exercise:

```bash
pip install sentence-transformers pacmap
cp exercises/*.ipynb solutions/ && jupyter nbconvert --to notebook --execute --inplace solutions/*.ipynb
```

To build locally:

```bash
pip install -r requirements.txt
python -m nbconvert --to html solutions/*.ipynb --output-dir _solutions_html/solutions
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
