# glossin

The glossdb skills: how a door-connected agent speaks glossql, writes
functions, takes a workspace to trusted metrics, and authors data
apps. Packaged as an [Agent Plugins] 1.0.0 plugin — the vendor-neutral
shape — with each skill in the [Agent Skills] format, so any client
that reads either standard can carry them.

[Agent Plugins]: https://agent-plugins.org/specification
[Agent Skills]: https://agentskills.io

## The skills

- `skills/glossql` — the statement set, the shipped reads, the
  outcome shape, and the substrate's sharp edges.
- `skills/glossql-functions` — measurements, check voices, and
  detectors; every body is one SQL query.
- `skills/glossql-metrics` — raw exports to metrics someone can
  trust, end to end.
- `skills/glossql-apps` — data apps on the app door.

## The sibling contract

These skills are gated by the [glossql] server's test suite: every
fenced example must parse and plan against a bootstrapped workspace.
That suite reads this repo from the sibling checkout (`../glossin`
beside `../glossql`), the same path contract the server already has
with its other siblings — a clone that can build glossql can gate the
skills. Edit skills here; `cargo test` there says whether the
examples still hold.

[glossql]: ../glossql

For development in Claude Code, load the working copy directly:

```
claude --plugin-dir ../glossin
```

and `/reload-plugins` picks up edits without restarting.
