# headroom

**headroom** is "the context compression layer for AI agents." It is middleware
that sits in front of the LLM and compresses tool outputs, logs, files, and RAG
chunks *before* they reach the model — typically 60–95% fewer tokens with the
same answers. It ships six compression algorithms (SmartCrusher for JSON, an
AST-aware CodeCompressor, and more), cross-agent shared memory with auto-dedup,
and fully reversible compression (originals are cached). The `headroom learn`
command mines failed sessions to improve future runs. It is local-first and
ships as a library, a proxy, and an MCP server.

**Category:** `context_compression`

https://github.com/chopratejas/headroom

## How DriveEasy uses it
DriveEasy branch-management agents drown in bulky, repetitive data. headroom is
the bridge that keeps their context windows affordable:

- **Vehicle GPS / telematics streams** — every car continuously reports location,
  mileage, fuel, and diagnostics; headroom compresses these streams before they
  ever reach the branch agents.
- **Customer support transcripts** — long rental-support chat logs are crushed to
  their essentials without losing the facts an agent actually needs.
- **Maintenance logs** — verbose service histories are compressed before review.
- **Shared customer history** — headroom's cross-agent shared memory with
  auto-dedup means every branch agent sees the *same* deduplicated customer
  rental history instead of each one re-fetching and re-summarizing it.

Because compression is reversible, a branch agent can always expand a record back
to the original — a full telematics trace or a complete transcript — whenever a
dispute or audit requires it.
