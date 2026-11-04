# Provenance Sheet - verdant-math-mix

- Owner: Math instruction pod
- Build: 2026-10-20
- Release wave: Q4-2026

## Lineage

The pipeline mixes two immediate data sources at a 70/30 ratio:
`openai/gsm8k` and `cais/mmlu`. Explanations are polished for style with the
synthesis model `Qwen/Qwen2.5-7B-Instruct`.

The vendor notes mention `monology/pile-uncopyrighted` as an earlier seed
corpus used before this pipeline existed. It is recorded as upstream
ancestry and is not read by the current build.
