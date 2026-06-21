# Evaluation

## Evaluation Overview

The evaluation of VAKIL focused on assessing both the training performance of the fine-tuned model and the quality of the generated legal responses. The analysis consisted of:

* Dataset Distribution Analysis
* Training and Validation Loss Monitoring
* Intrinsic Evaluation Metrics
* Qualitative Assessment of Legal Responses

The goal was to determine whether domain-specific fine-tuning and retrieval augmentation improved the model's ability to generate coherent, context-aware, and educationally useful legal explanations.

---

# Dataset Analysis

Before fine-tuning, the legal instruction dataset was analyzed to understand its structure and complexity.

## Instruction Length Distribution

Most instructions fell within the range of **80–200 characters**, representing short to moderately detailed legal queries. A long-tail distribution extending to approximately **1,400 characters** indicated the presence of more complex legal instructions and multi-sentence queries. This diversity helped improve the model's exposure to different query styles and legal contexts.

## Response Length Distribution

Most responses ranged between **500–2,000 characters**, corresponding to legal explanations, statutory summaries, and case descriptions. A smaller subset contained significantly longer responses derived from statute-heavy legal documents and extended case law excerpts. This distribution supported the development of a chunking strategy suitable for long-form legal content.

---

# Fine-Tuning Performance

The model was fine-tuned using a LoRA-based parameter-efficient training approach on an RTX A6000 GPU over approximately 18 hours and two training epochs.

## Training and Validation Loss

Training performance was monitored using both training loss and validation loss across more than 10,000 optimization steps.

### Observations

* Training loss decreased from approximately **1.14 to 1.02**
* Validation loss stabilized around **1.04**
* Both curves showed consistent downward trends
* Training and validation losses remained closely aligned

This behavior indicates stable convergence and suggests that the model adapted effectively to Indian legal text without exhibiting significant overfitting.

---

# Intrinsic Evaluation Metrics

To assess the linguistic quality and readability of generated responses, four intrinsic evaluation metrics were used:

## 1. Perplexity

Perplexity was used as an indicator of response fluency and coherence.

Lower values correspond to more predictable and linguistically consistent outputs.

Observed values ranged between:

* 1.59
* 2.17

These results indicate stable language generation across different categories of legal queries.

---

## 2. Response Length

Response length was measured to evaluate whether the generated answers were sufficiently detailed while remaining concise and understandable.

Observed outputs ranged from:

* 44 words
* 125 words

This balance allowed the system to provide meaningful legal explanations without overwhelming users.

---

## 3. Lexical Diversity

Lexical diversity was measured using the unique word ratio.

Observed values ranged between:

* 0.561
* 0.889

The results suggest that responses maintained a healthy vocabulary diversity while remaining focused on legal terminology and concepts.

---

## 4. Readability (Flesch Reading Ease)

Readability was evaluated using the Flesch Reading Ease score.

Observed scores ranged between:

* 14.67
* 57.49

These values indicate that VAKIL's responses remained accessible to students and learners while preserving the complexity required for legal explanations.

---

# Qualitative Observations

During testing, the system demonstrated improvements in several areas compared to a general-purpose language model:

### Improved Domain Understanding

The fine-tuned model showed stronger familiarity with:

* Constitutional provisions
* Indian statutory law
* Legal terminology
* Judicial reasoning patterns

### Better Contextual Grounding

The FAISS-based Retrieval-Augmented Generation (RAG) pipeline enabled the model to retrieve relevant legal passages before generation, improving factual consistency and reducing unsupported claims.

### Reduced Hallucinations

Conditioning the model on retrieved legal context helped mitigate hallucinated legal interpretations and unsupported legal references.

### Educational Usability

Generated responses were generally:

* Context-aware
* Interpretable
* Student-friendly
* Suitable for legal learning and research

The system consistently produced explanations that balanced technical correctness with readability.

---

# Limitations

Several limitations were identified during evaluation:

* Lack of standardized Indian legal QA benchmarks
* Limited expert legal validation
* Dependence on retrieval quality
* Challenges with extremely long statute-dense documents
* Limited support for comparative multi-case legal reasoning

These areas provide opportunities for future improvement and more rigorous evaluation.

---

# Conclusion

The evaluation demonstrates that VAKIL successfully adapts a general-purpose language model to the Indian legal domain through LoRA-based fine-tuning and Retrieval-Augmented Generation. The model achieved stable convergence during training, maintained strong linguistic quality across multiple intrinsic metrics, and generated contextually relevant legal responses. The results suggest that combining domain-specific fine-tuning with retrieval-based grounding is an effective approach for building educational legal AI assistants tailored to the Indian legal ecosystem.
