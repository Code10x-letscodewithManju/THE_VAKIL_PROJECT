# VAKIL – Virtual Assistant for Knowledge in Indian Law

VAKIL is a domain-specific Legal AI Assistant designed to make Indian legal knowledge more accessible through Large Language Models (LLMs), Retrieval-Augmented Generation (RAG), and legal-domain fine-tuning.

The project combines domain adaptation, semantic retrieval, and legal reasoning to provide context-aware responses for legal queries related to constitutional provisions, statutory sections, legal procedures, and case law.

This project was developed as part of our research work and was subsequently published in the International Journal of Scientific Research in Engineering and Management (IJSREM).

---

## Motivation

General-purpose LLMs often struggle with legal queries because they lack domain-specific knowledge and may generate legally incorrect or unsupported responses.

The objective of VAKIL was to explore whether a language model could be adapted specifically for the Indian legal domain and enhanced with retrieval mechanisms to improve factual grounding, contextual relevance, and educational value.

Rather than relying solely on prompting, the project explores the complete lifecycle of building a domain-specific AI system:

- Dataset Curation
- Data Preprocessing
- LLM Fine-Tuning
- Retrieval-Augmented Generation (RAG)
- Evaluation
- Deployment

---

## Project Architecture

```text
User Query
      │
      ▼
FAISS Semantic Retrieval
      │
      ▼
Relevant Legal Context
      │
      ▼
Fine-Tuned Legal LLM
      │
      ▼
Context-Aware Legal Response
```

The system combines:

- Fine-Tuned Legal Language Model
- Retrieval-Augmented Generation (RAG)
- FAISS Semantic Search
- Legal Document Processing Pipeline
- Legal Question Answering Interface

---

## Dataset

The model was trained on approximately **76,000 Indian legal instruction-response pairs** covering:

- Constitutional Provisions
- Indian Penal Code (IPC)
- Criminal Procedure Code (CrPC)
- Legal Concepts
- Judicial Summaries
- Legal Procedures
- Statutory Sections

### Dataset Link

The complete dataset is hosted on Hugging Face:

👉 **Dataset:** [Add Hugging Face Dataset Link Here]

Dataset link is also available in:

```text
data/dataset_link.md
```

---

## Fine-Tuning

The legal language model was fine-tuned using:

- LoRA (Low-Rank Adaptation)
- Hugging Face Transformers
- PEFT
- PyTorch

### Training Details

- Training Environment: RunPod RTX A6000
- Training Duration: ~18 Hours
- Epochs: 2
- Domain: Indian Legal Knowledge

The objective was to improve legal terminology understanding, domain-specific reasoning, and instruction-following capabilities.

### Fine-Tuned Model

The trained model is publicly available on Hugging Face:

👉 **Model:** [Add Hugging Face Model Link Here]

Model link is also available in:

```text
model/model_link.md
```

---

## Retrieval-Augmented Generation (RAG)

To improve factual grounding and reduce hallucinations, a Retrieval-Augmented Generation pipeline was implemented.

The pipeline includes:

- Legal Document Chunking
- Embedding Generation
- Semantic Search
- Context Injection
- Response Generation

### Important Note

The RAG knowledge base consists of a large collection of legal documents, judgments, statutes, and processed embeddings totaling approximately **20–30 GB**.

Due to repository size limitations, the complete RAG dataset, vector indexes, embeddings, and processed legal corpus are **not included in this repository**.

Only the implementation notebook and pipeline code are provided for reference.

The RAG implementation can be found in:

```text
notebooks/rag_pipeline.ipynb
```

---

## Repository Structure

```text
THE_VAKIL_PROJECT
│
├── data
│   └── dataset_link.md
│
├── docs
│   ├── challenges.md
│   ├── evaluation.md
│   └── methodology.md
│
├── model
│   └── model_link.md
│
├── notebooks
│   ├── rag_pipeline.ipynb
│   └── VAKIL_Phi3_FineTuning_From_Scratch.ipynb
│
└── README.md
```

---

## Evaluation Highlights

The system was evaluated using:

### Dataset Analysis

- Instruction Length Distribution
- Response Length Distribution

### Training Evaluation

- Training Loss Monitoring
- Validation Loss Monitoring
- Convergence Analysis

### Intrinsic Evaluation

- Perplexity
- Response Length
- Lexical Diversity
- Readability (Flesch Reading Ease)

Results demonstrated:

- Stable training convergence
- Improved legal-domain understanding
- Better contextual grounding
- Reduced hallucinations
- Improved educational usability

Detailed evaluation is available in:

```text
docs/evaluation.md
```

---

## Challenges Faced

Some of the major challenges encountered during development included:

- Evaluating legal correctness
- Managing hallucinations in legal responses
- Processing large legal corpora
- Designing effective retrieval strategies
- Balancing fine-tuning with retrieval

More details:

```text
docs/challenges.md
```

---
### Infrastructure & Deployment

- Training was performed on a **RunPod RTX A6000 GPU** using LoRA-based fine-tuning.
- The fine-tuned model was published to **Hugging Face Hub** for versioning and reproducibility.
- Inference was served using **vLLM** through a **RunPod Serverless Endpoint**, enabling efficient and low-latency API access for the legal assistant.

---

## Key Learnings

This project taught us that building a useful AI system requires much more than training a model.

The most important lessons came from:

- Data quality and preprocessing
- Retrieval system design
- Evaluation methodology
- Hallucination mitigation
- End-to-end system thinking

A reliable AI assistant is the result of multiple well-designed components working together rather than a single model.

---

## Future Work

Future improvements include:

- Citation-aware response generation
- Advanced legal retrieval strategies
- Improved evaluation benchmarks
- Multilingual support for Indian languages
- Graph-based legal reasoning
- Expanded legal knowledge base

---

## Disclaimer

VAKIL is intended for educational and research purposes only.

The system is not a substitute for professional legal advice, legal representation, or official legal interpretation. Users should consult qualified legal professionals for legal matters requiring expert guidance.

---

