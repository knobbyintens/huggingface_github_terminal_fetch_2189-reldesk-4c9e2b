# Provenance Sheet - atlas-instruct-v3

- Owner: Instruction tuning pod
- Build: 2026-10-18
- Release wave: Q4-2026

## Lineage

The build pipeline reads parquet shards from the immediate parent corpus
`tiiuae/falcon-refinedweb` directly. The parent corpus is itself a
derivative of the upstream web corpus `EleutherAI/pile`, which is kept
in the release ledger for audit only. Retrieved passages are rewritten into
chat-style instructions with the synthesis model `internlm/internlm2_5-7b-chat`.

No other corpus is read by this pipeline. The per-document notices that
travel with the upstream corpus are not part of this release's terms.
