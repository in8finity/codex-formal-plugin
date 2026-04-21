# Formal Methods Plugin for Codex

Codex-compatible packaging of the Formal Methods plugin originally authored for Claude Code.
It provides two skills:

- `formal-modeling`: write, run, and interpret Alloy 6 and Dafny models for state machines,
  invariants, API contracts, permission matrices, business rules, and workflow designs.
- `formal-debugger`: investigate bugs with a structured, evidence-first workflow that uses
  formal models to distinguish competing hypotheses.

## Layout

```text
.agents/plugins/marketplace.json
plugins/formal-methods/
  .codex-plugin/plugin.json
  skills/
    formal-modeling/
    formal-debugger/
  system-models/
  LICENSE
  COMMERCIAL.md
  NOTICE
  THIRD_PARTY_LICENSES.md
```

## Running the Bundled Verifiers

The modeling skill includes a unified runner:

```bash
bash plugins/formal-methods/skills/formal-modeling/scripts/verify.sh path/to/model.als
bash plugins/formal-methods/skills/formal-modeling/scripts/verify.sh path/to/model.dfy
```

Self-verification is available from the same runner:

```bash
bash plugins/formal-methods/skills/formal-modeling/scripts/verify.sh --self --dafny
bash plugins/formal-methods/skills/formal-modeling/scripts/verify.sh --self --alloy
```

Java 11+ is required for Alloy. Dafny is required for Dafny verification. The Alloy runner
downloads Alloy at runtime into its local script cache.

## License

The plugin content keeps the original `CC-BY-NC-SA-4.0` license. Commercial use requires a
separate commercial license; see `plugins/formal-methods/COMMERCIAL.md`.
