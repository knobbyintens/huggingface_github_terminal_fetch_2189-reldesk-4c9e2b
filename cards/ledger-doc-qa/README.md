# Provenance Sheet - ledger-doc-qa

- Owner: Document QA pod
- Build: 2026-10-23
- Release wave: Q4-2026

## Lineage

The pipeline reads two immediate data sources: `HuggingFaceH4/ultrachat_200k`
as the dialogue seed and `project-numina/NuminaMath-CoT` as the math seed.
Final answers are polished with the synthesis model
`Qwen/Qwen2.5-7B-Instruct`.

No upstream ancestry is declared for this artifact.
