# TransSinNorm: Production-Grade NLP Infrastructure for Transliterated Sinhala

[![Status: Exploratory Research](https://img.shields.io/badge/Status-Exploratory_Research-blue)]()
[![Started: 2026](https://img.shields.io/badge/Started-2026-brightgreen)]()
[![Target: 4th Year Thesis](https://img.shields.io/badge/Target-4th_Year_Thesis-orange)]()

> **Note:** This repository serves as the official academic workspace and timestamped electronic ledger for exploratory research beginning in Year 2, Semester 1 (2026). It is being actively developed in preparation for a 4th-year undergraduate computer science thesis.

## 📌 Abstract / The Problem Statement
Transliterated Sinhala (colloquially known as Romanized Sinhala or Singlish) is heavily utilized across digital platforms, customer service chats, and social media in Sri Lanka. However, it operates as a low-resource, code-mixed language with **no standardized orthography**. Users frequently omit vowels and heavily abbreviate words (e.g., typing `krl`, `krla`, or `karala` interchangeably for `කරලා`). 

Standard Large Language Model (LLM) subword tokenizers fail to process these non-standard abbreviations efficiently, resulting in extreme token fragmentation, high inference latency, and excessive compute costs. 

## 🎯 Core Research Question
*"How do we build reusable, production-grade NLP infrastructure for a low-resource code-mixed language with no standardized orthography?"*

## 🏗️ Project Scope & Architecture

This research proposes a multi-layered architectural approach to solve the latency and accuracy bottlenecks in processing Transliterated Sinhala:

*   **Layer 0: The TransSinNorm Architecture** 
    Development of a novel tokenization and normalization mapping strategy optimized for heavily compressed, non-standard text.
*   **Layer 1: The Dataset** 
    Construction and open-sourcing of a benchmark parallel dataset (Compressed Transliterated Sinhala $\rightarrow$ Standard Sinhala Script).
*   **Layer 2: Model Fine-Tuning** 
    Utilizing Parameter-Efficient Fine-Tuning (PEFT/LoRA) on lightweight foundational models (e.g., Llama-3/Mistral) to natively process the normalized outputs.
*   **Layer 3: Benchmarking & Evaluation** 
    Empirical evaluation of the fine-tuned model against generalized commercial LLMs (GPT-4/Claude) focusing on metrics such as Token Efficiency, Inference Latency, and Word Error Rate (WER).
*   **Layer 4: Deployment Prototype** 
    A local FastAPI wrapper serving as a proof-of-concept for enterprise API integration.

## 📂 Expected Repository Structure
```text
├── data/
│   ├── raw/                 # Scraped, raw social media comments (Embargoed)
│   ├── processed/           # Cleaned and normalized parallel dataset
│   └── synthetic/           # LLM-generated synthetic training data
├── src/
│   ├── scraper/             # Scripts for asynchronous data collection
│   ├── tokenizer/           # Custom tokenization algorithms (TransSinNorm)
│   ├── training/            # LoRA/PEFT training scripts
│   └── api/                 # FastAPI deployment code
├── notebooks/               # Jupyter notebooks for exploratory data analysis (EDA)
├── evaluation/              # Scripts for benchmarking latency and token costs
├── docs/                    # Literature review notes and thesis drafts
└── README.md
