---
license: cc-by-4.0
language:
- en
pretty_name: Multimodal Document Retrieval Baseline Synthetic Evaluation Set
size_categories:
- n<1K
task_categories:
- visual-document-retrieval
tags:
- synthetic
- multimodal-ai
- evaluation
- visual-document-retrieval
- document-question-answering
- image-to-text
- feature-extraction
configs:
- config_name: default
  data_files:
  - split: train
    path: data/train.jsonl
  - split: test
    path: data/test.jsonl
---

# Multimodal Document Retrieval Baseline Synthetic Dataset

## Summary

This dataset contains 14 training examples and 4
held-out examples for **Business documents contain meaning in text, tables, layout, and imagery that text-only retrieval can miss.**

Every record is synthetic and includes:

- `input`: query, event, or feature description
- `label`: expected class, route, relation, or evidence category
- `context`: synthetic supporting context
- `source`: fictional source identifier
- `variant`: generation pattern
- `synthetic`: always `true`

## Uses

- Reproducible unit and integration tests
- Baseline model training
- Evaluation harness development
- Schema and architecture demonstrations

## Limitations

The starter dataset contains synthetic textual modality descriptors, not sensitive scanned documents.

This dataset does not represent real users, patients, customers, production
traffic, or licensed media. It must not be presented as real-world evidence.

## Related Model

[{{HF_NAMESPACE}}/multimodal-document-retrieval-20261001-model](https://huggingface.co/{{HF_NAMESPACE}}/multimodal-document-retrieval-20261001-model)
