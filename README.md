# Practical NLP with Python — Companion Code Repository

Chapter-by-chapter labs for *Practical NLP with Python: From Classical Methods to Transformers,
LLMs and RAG*. Every notebook is self-contained, runs on small public-domain or synthetic data
(no copyrighted third-party datasets, no vendored third-party repositories, no large binaries),
and can be run top to bottom without any manual data download beyond the pip/model downloads
listed in `requirements.txt`.

## Chapter map

| # | Chapter | Notebook | Core technique |
|---|---|---|---|
| 1 | Introduction and the History of NLP | `ch01/01_first_pipeline.ipynb` | Tokenization, word-frequency pipeline |
| 2 | NLP Methods and Data Acquisition | `ch02/02_data_acquisition.ipynb` | OCR, ASR, scraping, TF-IDF + PCA |
| 3 | From Morphology to Word Vectors | `ch03/03_morphology_and_vectors.ipynb` | Stemming/lemmatization, co-occurrence vectors, word2vec/GloVe |
| 4 | Syntax and Parsing | `ch04/04_dependency_parsing.ipynb` | spaCy dependency parsing, SVO extraction |
| 5 | Language Models: N-grams to GPT | `ch05/05_language_models.ipynb` | N-gram LM, char-LSTM, GPT-2 generation |
| 6 | Semantics and Discourse | `ch06/06_semantics_discourse.ipynb` | Distributional semantics, coreference resolution |
| 7 | The Transformer Architecture | `ch07/07_self_attention_from_scratch.ipynb` | Self-attention and multi-head attention from scratch |
| 8 | Pretrained LMs and Fine-Tuning | `ch08/08_pretrained_and_finetuning.ipynb` | Masked-LM probing, fine-tuning, extractive QA reader |
| 9 | Prompting and LLM Engineering | `ch09/09_prompting_and_llm_engineering.ipynb` | Zero/few-shot, chain-of-thought, local LLM serving |
| 10 | Automatic Text Correction | `ch10/10_text_correction.ipynb` | Levenshtein/Jaccard correction, masked-LM correction |
| 11 | Automatic Text Summarization | `ch11/11_summarization.ipynb` | TextRank, ROUGE, abstractive summarization |
| 12 | Machine Translation | `ch12/12_machine_translation.ipynb` | Encoder-decoder with attention, pretrained MT, BLEU |
| 13 | Dialogue Systems | `ch13/13_dialogue_systems.ipynb` | Eliza, retrieval bot, local LLM chatbot |
| 14 | Question Answering and Semantic Search | `ch14/14_qa_semantic_search.ipynb` | Sparse/dense retrieval, extractive QA |
| 15 | Retrieval-Augmented Generation | `ch15/15_rag_pipeline.ipynb` | Chunk → embed → FAISS index → retrieve → generate |
| 16 | Evaluation, Deployment, Monitoring | `ch16/16_evaluation_deployment.ipynb` | Recall@k, NLI faithfulness check, FastAPI serving, staleness register |

## Setup

```bash
python -m venv .venv
source .venv/bin/activate   # or .venv\Scripts\activate on Windows
pip install -r requirements.txt
python -m spacy download en_core_web_sm
```

Some notebooks (Ch. 2 OCR cell) additionally need the Tesseract OCR binary installed at the
system level — see https://tesseract-ocr.github.io/tessdoc/Installation.html. Cells that need it
are wrapped in `try/except` so the rest of the notebook still runs without it.

## A note on data and licensing

Every dataset used in this repository is either generated synthetically inside the notebook,
drawn from NLTK's bundled public-domain corpora (Gutenberg, Reuters sample, `words`), or a small
set of sentences written for this book. No notebook bundles or depends on:

- full copyrighted book texts,
- large scraped datasets of unclear license,
- vendored third-party application repositories,
- proprietary or client-identifying material of any kind.

Pretrained models are downloaded on demand from the Hugging Face Hub / gensim's model hub under
their own respective licenses (see each model's card); this repository does not redistribute
model weights.

## Staleness register

See `ch16/16_evaluation_deployment.ipynb` §4 for a starter template. As a rule, re-verify pinned
library and model versions quarterly, and re-run each notebook end to end after any dependency
bump before considering the chapter "verified" again.

## License

Code in this repository is released under the MIT License (see `LICENSE`). The accompanying book
manuscript is © the author; the license here applies to the code samples only.
