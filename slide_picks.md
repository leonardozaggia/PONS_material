# Slide picks and run-of-show for a 90-minute seminar

The course decks are PDF exports, so "picking" a slide means extracting that page (for example with `pdftk`, Preview, or PowerPoint's *Insert -> Pictures* from a PDF page export). Page numbers below were identified from the text on each page; several decks build one figure up over consecutive pages, in which case only the finished page is listed. Eyeball each pick before you commit to it.

## Run of show

The book's chapters carry the same figures in their theory sections, so you can present from the book directly or from your own slides built from the picks below.

| Time | Block | Source | Participant does |
|---|---|---|---|
| 0:00 - 0:05 | Why embeddings, two uses of an LLM | `day_1/day_1a.pdf` p30, p33, p37 | Opens Chapter 1 in Colab, runs the Setup cell |
| 0:05 - 0:20 | What an embedding is | Chapter 1 theory, or `day_2/day_2_embeddings.pdf` picks below | Listens |
| 0:20 - 0:30 | Warm-up: sentences to vectors | Chapter 1 exercise | Runs cells, Tasks 1-2 |
| 0:30 - 0:40 | How a transformer produces a sentence embedding | Chapter 2 theory, or `day_2/day_2_embeddings.pdf` p28, p29, p31, p40, p45, p46 | Listens |
| 0:40 - 1:10 | Personality items | Chapter 2 exercise | Runs 2.1 to 2.5, Task 3 rerun with the fine-tuned model |
| 1:10 - 1:15 | Three ways to use an LLM for prediction | Chapter 3 theory, or `day_2/day_2_classification.pdf` p4, p5, p29 | Listens |
| 1:15 - 1:25 | Embeddings as features | Chapter 3 exercise | Runs cells, Task 1 if time |
| 1:25 - 1:30 | Applications in the field, wrap-up | Chapter 3 outlook, or `day_3/day_3b.pdf` picks below | Questions |

If you run short, drop the Chapter 3 exercise and just show its final confusion matrix. If you run long, Chapter 2 Tasks 1 and 2 are the safest things to skip.

## Picks from `day_1/day_1a.pdf` (Intro to LLMs, 37 pages)

| Page | Content | Use |
|---|---|---|
| 30 | "Two major applications": text generation vs feature extraction, the same input yielding a sentence or a vector | Opening slide. Frames the whole seminar as the right-hand branch |
| 31 | Closed vs open models: performance, safety, reproducibility, data security, interpretability | Optional, one line on why open models matter for research data |
| 33 | Model families by type (reasoning, assistant, embedding, foundation) and size | Shows embedding models are the small, fast corner of the landscape |
| 37 | Models used in the course: BERT-ish (MiniLM, MPNet, MPNet-personality) for feature extraction vs Llama for generation | Names the models participants will run |

## Picks from `day_2/day_2_embeddings.pdf` (Transformers and embeddings, 47 pages)

This is the core deck. Pages 4-9, 10-12, 13-15 and 19-23 each build up one figure; take the last page of each run.

| Page | Content | Use |
|---|---|---|
| 3 | Firth: "You'll know a word by the company it keeps" | The distributional hypothesis in one quote |
| 9 | Latent semantic analysis: a word by context count matrix | Embeddings existed before neural networks |
| 12 | word2vec: one-hot input, 300-D hidden layer, predict context | The neural version of the same idea |
| 15 | "A good language model encodes words with similar context similarly" | The key intuition |
| 18 | Embeddings are hidden activations, typically right before the output | What you actually extract |
| 23 | Embedding table built from trained model activations (Galaxy, Cosmos, Region, Switzerland) | Bridges to the notebook's DataFrame view |
| 25 | Comparing embeddings with cosine similarity | Defines the measure used in every notebook cell |
| 26 | Full cosine similarity matrix across the four example words | Matches the matrix participants see in Part 1 |
| 28 | Transformer architecture block diagram with "extract embedding" marked | Where in the network the vector comes from |
| 29 | Tokenization of a normal sentence | Text is split into sub-word tokens first |
| 31 | Tokenization of "you've won 202000 Eur" | Fun example of sub-word splitting on numbers |
| 40 | Attention: queries, keys, values, contextualized embeddings (end of the 34-40 build-up) | One slide of mechanism, do not go deeper |
| 44 | Masked language modeling head (end of the 42-44 build-up) | How the model is trained without labels |
| 45 | Feature extraction, CLS approach | Sentence embedding option 1 |
| 46 | Feature extraction, pooling approach | Sentence embedding option 2, the one sentence-transformers uses |
| 47 | Exercise slide: personality items with factor, construct, item | Hand-off into notebook Part 2 |

Skip: pages 16-17 (gradient descent and loss), 33-39 (attention build-up), 42-43.

## Picks from `day_2/day_2_classification.pdf` (Classification and regression, 30 pages)

| Page | Content | Use |
|---|---|---|
| 4 | Three approaches: feature extraction, changing the model head, text generation | Positions Part 3 against prompting and fine-tuning |
| 5 | Feature extraction for regression and classification: inputs, embedding dimensions, labels, step 1 and 2 | Exactly what notebook Part 3 does |
| 22 | Model sizes: BERTs vs open GPTs vs proprietary GPTs | Optional, why a 22M-parameter model is enough here |
| 29 | Comparison table: training data needs, computational needs, interpretability per approach | Closing argument for embeddings plus classical models |

Skip: pages 6-12 (model heads, adapters, LoRA), 13-21 (generation internals), 24-28 (prompting).

## Picks from `day_3/day_3b.pdf` (Research applications, 28 pages)

| Page | Content | Use |
|---|---|---|
| 2 | Four applications for qualitative data: map and cluster, label, summarize or paraphrase, search | Overview slide for the closing block |
| 4-5 | Mapping 5,692 reinforcement-learning articles, core vs peripheral topics | Embeddings plus clustering on a literature |
| 6-7 | Mapping free associations to "AI" | Closest to classic psych data |
| 8 | embedR R package | For R-heavy audiences |
| 15-16 | Labeling texts with Sustainable Development Goals (text2sdg) | Embedding-based labeling at scale |
| 23-26 | Searching 232,000 APA articles: sample sizes, gender, student samples over time | Embedding search enabling meta-science |

Skip: pages 9-14 (labeling with generative models and GPT-4), 17-19 (Centaur), 20-22 (paraphrasing proverbs).

## Not used

- `day_1/day_1b.pdf` (Hugging Face and Python intro): assumes participants will write Python over three days. For 90 minutes the notebook's comments are enough.
- `day_3/day_3a.pdf` (information extraction) and all Llama or Gemma notebooks: generation, not embeddings, and they need a GPU plus a gated model license.
- `day_3/llm_tutorial.pdf`: the Hussain et al. 2024 tutorial paper. Cite it in the last slide rather than showing it.
