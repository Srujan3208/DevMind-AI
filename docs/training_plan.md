# DevMind AI Training Plan

## Step 0 — Environment setup

- Use Google Colab.
- Check GPU availability and VRAM.
- Mount Google Drive.
- Create project folders.
- Install and verify dependencies.

## Step 1 — Dataset research and collection

Prioritize data with clear licenses and provenance.

Potential categories:
- Code and documentation
- Bug-fix pairs
- Error messages and stack traces
- Debugging instructions and explanations
- Programming Q&A
- Unit tests and verified code fixes

Do not assume a dataset is suitable simply because it is hosted publicly. Check its license, terms, language, quality, and data provenance.

## Step 2 — Dataset inspection

For each source, record:
- Dataset name and source URL
- License/terms
- Dataset version/date
- Fields and schema
- Number of examples
- Languages
- Quality limitations

## Step 3 — Normalization

A proposed common record:

```json
{
  "instruction": "Analyze the error and suggest a fix.",
  "language": "Python",
  "code": "example code",
  "error": "error message or stack trace",
  "root_cause": "verified or source-provided explanation",
  "solution": "corrected code or steps",
  "explanation": "why the fix works",
  "tests": [],
  "source": "dataset/source identifier",
  "license": "license identifier"
}
```

Fields may be missing. Do not fabricate labels during cleaning.

## Step 4 — Quality checks

- Remove exact duplicates.
- Detect near duplicates.
- Remove secrets and sensitive information.
- Filter corrupted or low-quality examples.
- Preserve source and license metadata.
- Split train/validation/test sets before model training.
- Avoid leakage between splits.

## Step 5 — Model experiments

Start with a small tokenizer and Transformer. Record:
- Architecture and parameter count
- Tokenizer vocabulary
- Dataset version and size
- Training configuration
- GPU type
- Training time
- Training/validation loss
- Checkpoint location

## Step 6 — Evaluation

Evaluate on examples not used during training:
- Error classification
- Root-cause explanation
- Fix correctness
- Code syntax
- Test pass rate where executable
- Explanation clarity
- Hallucination rate

## Storage

Store raw and processed datasets, checkpoints, and model weights in Google Drive. Do not commit large artifacts to GitHub.
