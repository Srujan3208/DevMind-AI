# DevMind AI

**A research and learning project to build a domain-specialized AI software debugging assistant.**

DevMind AI is designed to analyze programming errors, understand code and stack traces, identify likely root causes, explain fixes in beginner-friendly language, and help developers verify solutions.

> **Project status:** Early development. The initial goal is to build a reproducible data collection and training pipeline, then train a small Transformer from random initialization as an educational baseline. A stronger domain-adapted model may be explored later.

## Vision

Users should be able to submit:
- Error messages and stack traces
- Source-code snippets or files
- Screenshots of errors
- Logs and configuration files
- Descriptions of unexpected behavior

DevMind AI should return a structured analysis:
1. Error identification and classification
2. Likely root cause
3. Explanation in understandable language
4. Suggested correction
5. Corrected code/configuration
6. Verification steps or tests
7. Prevention tips

## Planned capabilities

- Programming-language and framework detection
- Error/stack-trace parsing
- Root-cause analysis
- Code explanation and correction
- Debugging examples for C, C++, Python, Java, JavaScript and TypeScript
- Dataset preprocessing and deduplication
- Tokenizer experimentation
- Transformer language-model training from scratch (small baseline)
- Domain instruction tuning experiments
- Evaluation on held-out examples
- Later: screenshot/OCR input, repository analysis, retrieval, and deployment API

## Development roadmap

### Phase 1 — Environment
- [ ] Set up Google Colab GPU runtime
- [ ] Mount Google Drive
- [ ] Create project directories
- [ ] Verify PyTorch and GPU

### Phase 2 — Data
- [ ] Identify suitable, license-compatible datasets
- [ ] Download and inspect dataset schemas
- [ ] Normalize examples into a common format
- [ ] Deduplicate and filter
- [ ] Create train/validation/test splits
- [ ] Save processed datasets to Google Drive

### Phase 3 — Model
- [ ] Train a tokenizer
- [ ] Implement a small Transformer/GPT-style model
- [ ] Train from random initialization
- [ ] Save resumable checkpoints
- [ ] Generate sample outputs

### Phase 4 — Debugging specialization
- [ ] Prepare instruction examples
- [ ] Experiment with debugging-focused training
- [ ] Build an error-analysis response format
- [ ] Evaluate on unseen examples
- [ ] Verify code fixes where practical

### Phase 5 — Product
- [ ] Build upload/paste interface
- [ ] Add screenshot and log analysis
- [ ] Add inference API
- [ ] Deploy demo

## Repository structure

```
DevMind-AI/
├── README.md
├── requirements.txt
├── .gitignore
├── notebooks/
│   ├── 01_environment_setup.ipynb
│   └── 02_dataset_collection.ipynb
├── docs/
│   ├── architecture.md
│   └── training_plan.md
├── src/
│   ├── data/
│   ├── tokenizer/
│   ├── model/
│   ├── training/
│   └── evaluation/
├── datasets/
│   └── README.md
└── evaluation/
    └── benchmark.md
```

Large datasets, checkpoints, and model weights should **not** be committed to Git. Store them in Google Drive or an appropriate model/dataset hosting service.

## Initial technology stack

- Python
- PyTorch
- Google Colab
- Google Drive
- Hugging Face Datasets
- Hugging Face Tokenizers / Transformers
- NumPy and pandas
- GitHub

## Responsible data use

Before using any dataset, review its license, terms, provenance, and permitted use. Avoid collecting private, sensitive, credential-bearing, or proprietary data. Publicly accessible data is not automatically unrestricted for training.

## Getting started

Open the notebooks in Google Colab:

1. `notebooks/01_environment_setup.ipynb`
2. `notebooks/02_dataset_collection.ipynb`

The notebooks are designed to be run sequentially. See [docs/training_plan.md](docs/training_plan.md) for the overall plan.

## Disclaimer

DevMind AI is an experimental research and educational project. Generated debugging suggestions may be incorrect. Code should be reviewed and tested before use.
