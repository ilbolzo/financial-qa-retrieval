<a id="readme-top"></a>

<br />
<div align="center">
<h3 align="center">Financial QA Retrieval</h3>

  <p align="center">
    Statistical Expansion vs. Neural Understanding: Advancing Financial Information Retrieval
    <br />
  </p>
</div>

## About The Project

This repository contains a complete pipeline designed to tackle the complexities of Financial Question Answering. The project addresses the vocabulary mismatch between everyday user language and complex financial terminology.

The codebase explores and compares different retrieval strategies, moving from heavily pre-processed lexical baselines and statistical query expansion up to Hybrid Entity-Aware Expansion and state-of-the-art Neural Cross-Encoder Re-ranking.

### Built With

* Python
* Jupyter
* HuggingFace
* **PyTerrier** (Information Retrieval Framework)

## Dataset

The experiments are conducted on the official **FiQA (Financial Question Answering) test collection**. The dataset presents unique challenges, including a high degree of syntactic noise (HTML tags, URLs) and a significant vocabulary mismatch between the short user queries and the highly technical target documents.

## Methodology

The project implements a multi-stage retrieval pipeline, evaluating the following models:

1. **Baselines (BM25 & Cleaned BM25):** Establishing a robust lexical foundation through rigorous text pre-processing and Regex-based noise reduction.
2. **Statistical Query Expansion (RM3):** Pseudo-relevance feedback to bridge the vocabulary gap.
3. **Hybrid Entity Expansion (NER):** A custom pipeline combining a BERT-based Named Entity Recognition model with a financial dictionary to provide a controlled semantic boost to the queries.
4. **Neural Re-ranking (monoT5):** A state-of-the-art cross-encoder architecture deployed to interpret the underlying semantic intent of the queries beyond exact keyword matching.

## Key Results

Our experiments demonstrate that traditional expansion techniques can suffer from *query drift* in highly specialized and noisy domains like Finance. Simply increasing term frequency or appending related entities does not guarantee better retrieval.

Conversely, neural re-ranking provides a decisive advantage. The **monoT5 model** achieved a **21% improvement in MAP** and a **32% increase in Precision at Rank 1** compared to the strongest lexical baseline, proving that deep structural understanding is required to effectively match layperson questions with professional financial advice.
