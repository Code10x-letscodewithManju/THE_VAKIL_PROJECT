## Model Fine-Tuning

Approach:
- LoRA Fine-Tuning
- PEFT
- Hugging Face Transformers

Training Environment:
- RunPod RTX A6000
- Training Duration: ~18 Hours

Objective:
Improve domain-specific understanding of Indian legal concepts and terminology.


Model:
[https://huggingface.co/ManjunathCode10x/vakil-phi3-mini-4k-instruct-finetuned]

## Retrieval-Augmented Generation

To improve factual grounding, the system integrates:

- Text Chunking
- Embedding Generation
- FAISS Vector Search
- Context Injection

Instead of relying solely on model memory, relevant legal passages are retrieved and supplied during inference.