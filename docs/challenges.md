## Challenges Faced

### Evaluating Legal Accuracy

One of the hardest problems was evaluation.

Unlike classification tasks, legal responses cannot be measured using simple accuracy metrics.

A response may sound convincing while still being legally incorrect.

To address this:
- Multiple prompt strategies were tested
- Outputs were manually reviewed
- Different retrieval configurations were compared

### Hallucinations

The model occasionally generated legally plausible but unsupported statements.

This motivated the integration of the RAG pipeline to improve grounding.