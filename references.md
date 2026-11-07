# References and license

## Reading

- Hussain, Z., Binz, M., Mata, R., & Wulff, D. U. (2024). A tutorial on open-source large language models for behavioral science. *Behavior Research Methods*. https://doi.org/10.3758/s13428-024-02455-8
- Wulff, D. U., & Mata, R. (2025). Semantic embeddings reveal and address taxonomic incommensurability in psychological measurement. *Nature Human Behaviour*. https://doi.org/10.1038/s41562-024-02089-y
- Reimers, N., & Gurevych, I. (2019). Sentence-BERT: Sentence embeddings using Siamese BERT-networks. *EMNLP*. https://arxiv.org/abs/1908.10084
- Mikolov, T., Chen, K., Corrado, G., & Dean, J. (2013). Efficient estimation of word representations in vector space. https://arxiv.org/abs/1301.3781
- Landauer, T. K., & Dumais, S. T. (1997). A solution to Plato's problem: The latent semantic analysis theory of acquisition, induction, and representation of knowledge. *Psychological Review*, 104(2), 211-240.

## Tools

- [sentence-transformers](https://www.sbert.net/): the Python library used in every exercise.
- [MTEB leaderboard](https://huggingface.co/spaces/mteb/leaderboard): compare embedding models across tasks.
- [embedR](https://github.com/dwulff/embedR): the same workflow from R.
- [LLM4BeSci course repository](https://github.com/dwulff/LLM4BeSci_2025MetaRep): the full three-day course this tutorial was cut from. It adds text generation, zero-shot classification, LoRA fine-tuning and information extraction.

## Models

- [`all-MiniLM-L6-v2`](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2): 22M parameters, 384 dimensions. Fast enough for a CPU.
- [`all-mpnet-base-v2`](https://huggingface.co/sentence-transformers/all-mpnet-base-v2): 110M parameters, 768 dimensions. A common general-purpose default.
- [`dwulff/mpnet-personality`](https://huggingface.co/dwulff/mpnet-personality): MPNet fine-tuned on pairs of personality items to predict their empirical correlation.

## License and attribution

This book is released under the [Creative Commons Attribution-ShareAlike 4.0 International](https://creativecommons.org/licenses/by-sa/4.0/) license.

The exercises, data files and the slide figures in the theory sections are adapted from the LLM4BeSci course at MetaRep, MPIB Berlin, December 2025, by Zak Hussain, Taisiia Tikhomirova, Valentin Kriegmair and Dirk Wulff, released under CC BY-SA 4.0. Figures are reproduced from the course slide decks by Dirk Wulff (*Transformers and embeddings*, *LLMs for classification and regression*, *Applying open-source LLMs in social and behavioral sciences*) and by Dirk Wulff and Zak Hussain (*Qualitative data analysis with LLMs*). Changes: the material was reorganised into three theory-plus-exercise chapters, the slide footer was cropped from the figures, data loading was changed to read from GitHub, the warm-up gained a similarity matrix, and the ridge classifier example now standardises training and test features consistently.

The personality item data (300 IPIP-NEO items and their inter-item correlations) and the fine-tuned model are from Wulff and Mata (2025). The tweet data are from a public political-media dataset distributed with the course.
