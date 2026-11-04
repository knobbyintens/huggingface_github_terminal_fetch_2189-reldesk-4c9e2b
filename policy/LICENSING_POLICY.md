# Data Release Licensing Policy (DRP-2.1)

Effective: 2026-10-01
Applies to every release wave handled by the Release Governance Desk.

## 1. Inputs on a provenance sheet

Every artifact carries a provenance sheet that may name three kinds of input:

- **Direct data sources** - the immediate datasets consumed by the artifact's
  build pipeline.
- **Synthesis models** - generative models invoked by the pipeline to
  synthesize, rewrite, or polish content.
- **Upstream ancestry** - earlier datasets or corpora that sit behind a
  direct data source. Ancestry is recorded for audit; it is not an input to
  this release.

## 2. Deciding the license

- If the artifact declares at least one direct data source, the license is
  decided from the declared license of the direct data sources. Synthesis
  models are not consulted for the license value in that case.
- If the artifact declares no direct data sources (a fully synthetic release),
  the license is decided from the declared license of the synthesis models
  actually used.
- The declared license of a data source or model is the license shown on its
  own public dataset or model page. Do not replace it with the license of an
  ancestor, with per-file or per-repository distribution terms, or with any
  other term inherited from further upstream. Ancestry remains context only.
- When more than one in-scope candidate applies, take the most restrictive
  license according to Section 3.

## 3. Restrictive ordering

From most restrictive to least restrictive:

1. `other`
2. `cc-by-sa-4.0`
3. `cc-by-nc-4.0`
4. `cc-by-4.0`
5. `odc-by`
6. `apache-2.0`
7. `mit`
8. `bsd-3-clause`
9. `unknown`

Use the lower-case license identifier exactly as it appears on the public
dataset or model page.

## 4. Release channel and legal review

- `public`: the resolved license is one of `odc-by`, `apache-2.0`, `mit`,
  `bsd-3-clause`.
- `internal-only`: the resolved license is any other value. Such artifacts
  require legal review (`review_required = true`) and are excluded from the
  external publication window.

## 5. Wave status

- `cleared`: every artifact in the wave is `public`.
- `partially-cleared`: at least one artifact is `internal-only` and at least
  one is `public`.
- `blocked`: every artifact is `internal-only`.

## 6. Clearance record

Every artifact record must contain exactly these fields:

- `artifact_id` - the artifact identifier from the wave manifest.
- `license` - the resolved lower-case license identifier.
- `decisive_sources` - the in-scope inputs that determined the result:
  the declared direct data sources when present; otherwise all synthesis
  models that were used.
- `scope_excluded` - every provenance input deliberately not used in the
  decision. This always includes upstream ancestry, and also includes
  synthesis models whenever direct data sources are declared.
- `release_channel` - `public` or `internal-only`.
- `review_required` - boolean, true only for `internal-only` releases.

The wave clearance document is published at `registry/` and must carry the
wave id, the policy id, the wave status, and the artifact records.
