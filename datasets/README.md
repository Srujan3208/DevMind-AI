# Dataset Storage

Datasets are stored outside GitHub, preferably in Google Drive.

Recommended structure:

```
DevMindAI/
└── datasets/
    ├── raw/
    │   ├── source_1/
    │   └── source_2/
    ├── processed/
    │   ├── train/
    │   ├── validation/
    │   └── test/
    └── metadata/
        └── sources.csv
```

Keep a metadata record for each dataset:
- Name
- URL
- Version/download date
- License
- Terms
- Processing steps
- Fields/schema
- Known limitations

Do not commit datasets or large artifacts to this repository.
