# Mimosa Grove

Verification instruments for formal specifications. The repositories here are deterministic, CI-native tools that check specification artefacts 

| instrument | what | version |
|---|---|---|
| [quint-audit](https://github.com/Mimosa-Grove/quint-audit) | a deterministic linter for [Quint](https://github.com/quint-co/quint) specifications: decodes quint's parse IR, reports structural findings with spans, severities, suggestions and exit codes; runs at parse cost in CI | 0.1.0 |
| [quint-checktrace](https://github.com/Mimosa-Grove/quint-checktrace) | a deterministic checker for [Quint](https://github.com/quint-co/quint) specifications: it compares a recorded trace with the spec, evaluates your named invariants with quint's own evaluator at every recorded state, and reports pass, fail or error per invariant. It writes a human report and a JSON record for CI. | 0.1.0 |

## Verification discipline

Every instrument states its contract and proves what it can. quint-audit's check semantics are written as Quint specs and bounded-model-checked. A mutant counts as killed only when two independent instruments fail it. A 67-spec corpus of real Quint files doubles as a drift detector. Exit codes separate a finding from a could-not-run. An instrument that cannot run never passes a gate.

## CI

Repositories are CI-gated on GitLab and GitHub Actions, per push.

## Licence

Each repository carries its own `LICENSE`, generally AGPL-3.0.
