# Multimodal Document Retrieval Baseline

A document-retrieval baseline that combines OCR text, layout labels, image captions, and metadata evidence.

Generated on 2026-10-01 as an independent production-AI architecture project.

## Real-World Problem

Business documents contain meaning in text, tables, layout, and imagery that text-only retrieval can miss.

## Hugging Face Tasks

- `visual-document-retrieval`
- `document-question-answering`
- `image-to-text`
- `feature-extraction`

## Recommended Production Stack

- FastAPI for ingestion and multimodal search
- Transformers with LayoutLMv3 or ColPali-style encoders
- OCR adapter plus image captioning
- PostgreSQL plus pgvector for fused embeddings
- Object storage for source documents
- OpenTelemetry plus retrieval ablation reports

## Included

- Runnable Python pipeline with no runtime dependencies
- Local JSON HTTP inference service
- Public-data API connector with explicit provenance
- Reproducible training script
- Held-out evaluation command
- Synthetic dataset with explicit provenance
- Trained transparent baseline model
- Architecture and production-boundary documentation
- Unit tests, CI workflow, and Dockerfile
- Hugging Face-ready model and dataset cards

## Architecture

1. Modality-aware document schema
1. OCR and caption feature fusion
1. Metadata-aware retrieval
1. Evidence presentation
1. Modality ablation evaluation

See [ARCHITECTURE.md](ARCHITECTURE.md) for the full flow and production
boundaries.

## Quick Start

```bash
python3 -m unittest discover -s tests
PYTHONPATH=src python3 -m multimodal_document_retrieval.cli "Find the invoice with a shipping surcharge table"
PYTHONPATH=src python3 evaluate.py
PYTHONPATH=src python3 -m multimodal_document_retrieval.service
```

The service exposes `GET /health` and `POST /predict`.

Rebuild the model:

```bash
python3 train.py
```

## Baseline Evaluation

- Held-out synthetic examples: 4
- Accuracy: 1
- Target metrics: retrieval_accuracy, modality_coverage, recall_at_3

This score verifies that the code and evaluation contract work. It does not
claim production performance.

## Hugging Face Artifacts

When the controller has a Hugging Face token and namespace configured, it
publishes:

- Dataset: `multimodal-document-retrieval-20261001-dataset`
- Model: `multimodal-document-retrieval-20261001-model`

## Portfolio Value

This repository maps to production AI engineering work in:

- Multimodal embeddings and document understanding
- OCR, layout, image, and text feature fusion
- Vector retrieval and modality-aware ranking
- Ablation testing and retrieval evaluation
- Scalable document ingestion and object storage

See [PORTFOLIO.md](PORTFOLIO.md) for resume-ready impact targets and interview
discussion areas.

## 1-3 Month Expansion

Follow [ROADMAP.md](ROADMAP.md) to add real-world APIs, a stronger open model,
durable orchestration, evaluation, observability, scalability testing, and a
public deployment.

## Safety

The starter dataset contains synthetic textual modality descriptors, not sensitive scanned documents.

Review [ARCHITECTURE.md](ARCHITECTURE.md),
[PRODUCTION.md](PRODUCTION.md), [SECURITY.md](SECURITY.md),
[MODEL_CARD.md](MODEL_CARD.md), and [DATASET_CARD.md](DATASET_CARD.md) before
adapting this project.
