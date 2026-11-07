# Setup

You need a Google account and a browser. Nothing is installed on your computer.

## Opening an exercise in Colab

1. Go to the exercise page you want to run (for example [Exercise 1](exercises/01_warmup)). The theory pages have no rocket; the exercise pages do.
2. Hover over the rocket icon at the top of the page and click **Colab**.
3. Colab opens the notebook in *playground mode*. To keep your changes, choose **File -> Save a copy in Drive**.
4. Leave the runtime on the default CPU. **Runtime -> Change runtime type** should show *CPU*; a GPU is not needed and only burns your free quota.
5. Run the first code cell. It installs the packages; the model downloads when the first model cell runs. This takes about a minute, so do it as soon as you open the notebook. The notebook has no outputs until you run it.

## Using a notebook

- `Shift + Enter` runs the selected cell and moves to the next one.
- Cells can be run in any order and variables persist, so if things get confusing use **Runtime -> Restart session** and run from the top.
- The last expression of a cell is displayed automatically. Use `print()` for anything else.
- Text cells explain the idea; comments inside code cells (lines starting with `#`) explain the mechanics.

## Where the data comes from

The exercises read their data straight from the public course repository on GitHub, so there is nothing to upload or mount:

```
https://raw.githubusercontent.com/dwulff/LLM4BeSci_2025MetaRep/main/day_2/
```

## Running locally instead

If you prefer your own machine, you need Python 3.10 or newer and:

```bash
pip install sentence-transformers pacmap pandas scikit-learn seaborn matplotlib jupyter
```

Then download the notebooks in `exercises/` from the repository and open them with `jupyter notebook`. The first run downloads the embedding model (about 90 MB) into your Hugging Face cache.

## If something goes wrong

| Symptom | Fix |
|---|---|
| `ModuleNotFoundError: sentence_transformers` | The setup cell did not finish. Run it again and wait for the checkmark. |
| Model download hangs | Colab's network hiccup. **Runtime -> Restart session**, run the setup cell again. |
| A plot does not show | Run the cell again; the first call sometimes only configures the plotting backend. |
| Everything is slow | Check that no GPU runtime was selected and that nobody else is running a large notebook on the same account. |

## Useful material

**Python basics.** If `import`, variables, lists and function calls are new to you, the Python introduction of the psy111 book covers them in an afternoon. The chapters that matter here are [Setup and usage](https://leonardozaggia.github.io/psy111/book/introduction/setup/introduction), [Data structures](https://leonardozaggia.github.io/psy111/book/introduction/data-structures/introduction), [Objects, functions and imports](https://leonardozaggia.github.io/psy111/book/introduction/objects/introduction) and [Scientific computing with numpy, pandas and matplotlib](https://leonardozaggia.github.io/psy111/book/introduction/scientific-comp/introduction).

**Embeddings on a whole literature.** The same pipeline as Exercise 2 applies to paper abstracts: search, embed, map and cluster. [Review Buddy](https://github.com/leonardozaggia/review_buddy) searches Scopus, PubMed, arXiv and other databases with one query, screens abstracts with a local language model and retrieves the PDFs. The companion book [Automated systematic literature search](https://leonardozaggia.github.io/automated_systematic_literature_search/) walks through it.

**Psychometrics in Python.** The [psy126 book](https://leonardozaggia.github.io/psy126/) is a tutorial on item response theory, the classical counterpart of what this seminar does with text.

**Tools and models** used in the exercises are listed on the [References](references) page.
