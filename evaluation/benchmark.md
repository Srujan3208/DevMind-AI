# DevMind AI Evaluation Benchmark

This is a planned benchmark; no scores have been established yet.

## Categories

1. Syntax errors
2. Runtime errors
3. Type errors
4. Index/bounds errors
5. Memory and resource errors
6. Logic bugs
7. API/integration errors
8. Dependency/configuration errors
9. Build/compilation errors
10. Database errors

## Metrics

- Error-category accuracy
- Root-cause correctness (reviewed or rubric-based)
- Fix correctness
- Test pass rate
- Code syntax validity
- Explanation completeness
- Unsupported-claim/hallucination rate

## Dataset split

Use train/validation/test splits and ensure near-duplicate examples do not leak across splits. Keep test data held out until evaluation.
