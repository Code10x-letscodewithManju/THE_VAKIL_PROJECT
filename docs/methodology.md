# Methodology

## Overview

VAKIL (Virtual Assistant for Knowledge in Indian Law) is a domain-specific legal AI assistant designed to provide context-aware answers to Indian legal queries. The system combines Large Language Model (LLM) fine-tuning with Retrieval-Augmented Generation (RAG) to improve legal understanding and reduce unsupported responses.

The project was developed through four major stages:

1. Dataset Preparation
2. Model Fine-Tuning
3. Retrieval System Development
4. Evaluation and Deployment

---

## 1. Dataset Preparation

The foundation of the project was a dataset containing approximately 76,000 Indian legal instruction-response pairs.

### Data Sources

The dataset included:

* Constitutional provisions
* Statutory sections
* Legal concepts
* Legal procedures
* Question-answer style legal instructions

### Preprocessing

Several preprocessing steps were performed:

* Removal of incomplete records
* Standardization of formatting
* Instruction-response structuring
* Tokenization preparation
* Dataset validation

The final dataset was converted into an instruction-tuning format suitable for supervised fine-tuning.

---

## 2. Model Fine-Tuning

The objective of fine-tuning was to improve the model's understanding of legal terminology, legal reasoning patterns, and domain-specific concepts.

### Fine-Tuning Strategy

The model was trained using:

* Parameter-Efficient Fine-Tuning (PEFT)
* LoRA (Low-Rank Adaptation)

This approach significantly reduced computational requirements while enabling domain adaptation.

### Training Environment

* GPU-based cloud environment
* Approximately 18 hours of training
* Multiple experimentation cycles involving hyperparameter tuning and validation

### Goal

The primary goal was not memorization of legal content but adaptation to legal language, reasoning patterns, and question-answer structures commonly encountered in Indian law.

---

## 3. Retrieval-Augmented Generation (RAG)

During experimentation, it became evident that fine-tuning alone was insufficient for answering all legal queries accurately.

To improve contextual grounding, a Retrieval-Augmented Generation pipeline was implemented.

### Retrieval Workflow

User Query
↓
Embedding Generation
↓
FAISS Vector Search
↓
Relevant Legal Context Retrieval
↓
Context Injection
↓
Response Generation

### Why RAG?

RAG was introduced to:

* Improve factual grounding
* Reduce hallucinations
* Provide relevant legal context
* Support broader legal coverage beyond training data

### Vector Store

FAISS was used as the retrieval engine due to its efficient similarity search capabilities and lightweight deployment requirements.

---

## 4. Evaluation

One of the most challenging aspects of the project was evaluation.

Unlike traditional machine learning tasks, legal question answering cannot be measured using a single accuracy metric.

### Evaluation Approach

The system was evaluated using:

* Response relevance
* Context utilization
* Legal consistency
* Completeness of answers
* Comparative testing across retrieval configurations

### Key Observation

A response that appears fluent is not necessarily legally correct.

This led to iterative refinement of both the retrieval strategy and prompting framework.

---

## 5. Deployment

The final model was deployed through an inference-serving framework optimized for low-latency responses.

### Deployment Objectives

* Efficient inference
* Reduced response time
* Scalability for future users
* Reproducible experimentation

The fine-tuned model was also published publicly to support reproducibility and future development.

---

## Challenges Encountered

### Evaluating Legal Correctness

The largest challenge was determining whether responses were legally reliable rather than merely well-written.

### Balancing Fine-Tuning and Retrieval

Extensive experimentation was required to determine how much information should come from the model versus retrieved context.

### Hallucinations

Early versions occasionally generated legally plausible but unsupported statements. This was partially mitigated through retrieval-based grounding and iterative prompt refinement.

---

## Lessons Learned

This project demonstrated that building a useful AI assistant requires much more than training a model.

The most important lesson was that successful AI systems depend on the interaction between:

* Data quality
* Fine-tuning
* Retrieval systems
* Evaluation methodology
* Deployment infrastructure

Fine-tuning improves domain understanding, but retrieval, evaluation, and system design are equally important in creating reliable AI applications.

---

## Future Improvements

Potential future work includes:

* Larger legal knowledge bases
* Advanced retrieval strategies
* Legal benchmark creation
* Citation-aware answer generation
* Human-in-the-loop validation workflows
* Multi-lingual legal support for Indian regional languages
