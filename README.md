# LLM embeddings in psychology: a 90-minute Jupyter Book tutorial

A three-chapter Jupyter Book cut from the [LLM4BeSci course](https://github.com/dwulff/LLM4BeSci_2025MetaRep). Each chapter is a theory section with figures followed by an exercise that runs on the free Google Colab CPU runtime. No Hugging Face account, API key, GPU or Google Drive mount is needed.

This folder is designed to become the root of its own public GitHub repository. It carries its own `.github/workflows/book.yml` that builds and publishes the book to GitHub Pages.

## Contents

| File | What it is |
|---|---|
| `intro.md`, `setup.md`, `references.md` | Landing page, Colab instructions, reading list and license |
| `01_vectors.ipynb` | Chapter 1: from words to vectors. Theory 15 min, exercise 10 min |
| `02_personality.ipynb` | Chapter 2: sentence embeddings and personality items. Theory 10 min, exercise 30 min |
| `03_features.ipynb` | Chapter 3: embeddings as features for prediction, plus the outlook. Theory 5 min, exercise 10 min, outlook 5 min |
| `images/` | Slide pages from the course decks, rasterised at 1920 px (CC BY-SA 4.0) |
| `_config.yml`, `_toc.yml`, `requirements.txt` | Jupyter Book 1.x configuration |
| `slide_picks.md` | Which course slides to use in the live talk and a run-of-show |

The chapter notebooks are committed **with their outputs**, and the book build does not re-execute them (`execute_notebooks: "off"`). That keeps the Pages build fast and free of torch. If you change a code cell, rerun the notebook before committing.

## Publishing

1. Create a new public repository on GitHub and copy the contents of this folder to its root.
2. `_config.yml` points at `leonardozaggia/PONS_material`; the Colab rocket button on every chapter is built from that URL, so change it if the repository moves.
3. In the repository settings, under Pages, set the source to **GitHub Actions**.
4. Push to `main`. The workflow builds the book and publishes it at `https://<owner>.github.io/<repo>/`.

To build locally instead:

```bash
pip install -r requirements.txt
jupyter-book build .
```

and open `_build/html/index.html`.

## Re-executing the chapters

```bash
pip install sentence-transformers pacmap
jupyter nbconvert --to notebook --execute --inplace 0*.ipynb
```

The first run downloads the embedding model (about 90 MB). Chapter 2, Task 3 asks participants to switch to `dwulff/mpnet-personality` (about 420 MB).

## Expected results

Measured locally on 2 Nov 2026 with a CPU; a Colab CPU runtime is comparable.

| Result | `all-MiniLM-L6-v2` | `dwulff/mpnet-personality` |
|---|---|---|
| r(predicted, observed item correlations) | .18 | .37 |
| r on absolute values | .33 | .95 |
| Item to facet assignment accuracy (chance .03) | .23 | .45 |
| Tweet bias test accuracy (chance .50) | .76 | .77 |

The jump to .95 is the fine-tuning punchline, and the moment to raise the caveat that the model was tuned on these very items. The tweet classifier barely moves: a model specialised on personality items does not help on political text.

## Known limitations

- Figures in the theory sections use relative paths, so they render in the book but not in the Colab copy. The Colab copy is for running the exercise; the theory is read in the book.
- The book has been built locally but not yet published, and the chapters have not been opened on Colab itself. Do a dry run on Colab before the session.

## Changes relative to the course notebooks

- Data loads from raw GitHub URLs instead of a mounted Google Drive.
- The warm-up shows the cosine similarity matrix, not only the raw vectors.
- Chapter 3 fixes a bug in `day_2/day_2_classification_b.ipynb`, where the ridge classifier was fitted on unscaled training features but scored on scaled test features.
- The model name is a single variable so the fine-tuned-model comparison is a one-line change.
- Text generation, zero-shot classification with Llama, LoRA fine-tuning and information extraction are left out: they need a GPU and a gated model license, and they are not about embeddings.

## License

CC BY-SA 4.0, inheriting from the LLM4BeSci course by Zak Hussain, Taisiia Tikhomirova, Valentin Kriegmair and Dirk Wulff. See `references.md` for attribution details.
