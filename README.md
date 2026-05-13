# Tailor

**A local-first MCP framework that lets any MCP-speaking AI work with your own data — without that data ever leaving your machine, with every action recorded in a durable audit log, and with results stamped for reproducibility.**

## What it is

Tailor curates a **Wardrobe** — the structured collection of your themes, moments, evidence, and source data that lives entirely on your machine. Any MCP-speaking AI (Claude Desktop, Cline, Goose, a local Ollama-fronted client) connects to Tailor over the standard MCP protocol; Tailor governs what the AI can see and what it can do, recording every call in a durable audit log scoped to optional subject identifiers.

The framework is built around three persistent surfaces:

- **The Wardrobe** — your data and prior analytical work, held in a local Obsidian-compatible markdown vault
- **The Ledger** — every action Tailor took on your behalf, recorded in SQLite with timestamps, parameters, and outcomes
- **Children** — extension points for new data sources (a Strava API client, a CSV directory ingest, a metadata-sidecar cohort grouper)

Across these surfaces Tailor enforces a three-tier access model server-side, not in the AI's prompt: most analytical questions resolve at Tier 1 (server-computed reports, zero raw data leaves the machine); the AI must request consent for Tier 2 (downsampled streams) and pre-approve cost for Tier 3 (raw streams).

## Install

```
uv tool install tailor-mcp
```

Tailor's CLI bootstraps your first project via `tailor pilot` (multi-subject CSV setup wizard) or `tailor tour` (a guided walkthrough using bundled synthetic fixtures from the HIP Lab realistic demo). No data leaves your machine at any point.

## Status

Tailor is a local-first MCP framework currently in invited evaluation. The source is on PyPI for any visitor to inspect; the project's full governance trail — ADRs, design notes, roadmap — is private until Tailor completes its first beachhead deployment with a research lab. If you're reading this with the intent to evaluate, you likely already have a back-channel to the maintainer.
