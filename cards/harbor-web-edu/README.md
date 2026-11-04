# Provenance Sheet - harbor-web-edu

- Owner: Web data pod
- Build: 2026-10-19
- Release wave: Q4-2026

## Lineage

The pipeline consumes a filtered subset of the immediate data source
`HuggingFaceFW/fineweb-edu`. The filtering is deterministic; no synthesis
model is used.

`monology/pile-uncopyrighted` is recorded as upstream ancestry from an earlier
vendor seed and is not ingested by this pipeline.
