# AI Orbit Tools Ingestion

[![CI](https://github.com/rajaryan1111/ai-orbit-tools-ingestion/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/rajaryan1111/ai-orbit-tools-ingestion/actions/workflows/ci.yml)

A Python ingestion and verification pipeline for collecting, normalizing, validating and curating AI-tool metadata for downstream applications.

## What this project does

The pipeline is organized around a staged workflow:

1. discover candidate tool records from configured sources
2. extract and normalize metadata
3. deduplicate candidates using stable invariants
4. resolve and verify source URLs
5. score records against an explicit rubric
6. persist checkpoints so long-running work can resume safely
7. write structured outputs and execution logs

The repository includes deterministic local HTML fixtures so discovery and verification tests can run without depending on live websites.

## Repository structure

- **src/** — ingestion, discovery, extraction, verification and persistence modules
- **config/** — source and pipeline configuration
- **data/** — structured pipeline data and fixtures
- **tests/** — unit and integration-style tests using deterministic fixtures
- **scripts/** — operational helpers
- **run.py** — pipeline entry point
- **PROGRESS.md** — development and implementation notes

## Engineering characteristics

- provenance-aware source records
- explicit scoring and verification rules
- deduplication invariants
- checkpoint durability and resumability
- graceful handling of HTTP/robots failures
- deterministic tests for source-specific extraction
- separation between discovery, verification and persistence

## Development

Use Python 3.11+.

Install the test runner:

```bash
python -m pip install --upgrade pip pytest
```

Run the test suite:

```bash
pytest -q
```

The same test command is executed by GitHub Actions on pushes and pull requests to main.

## Project status

The repository is under active development. `PROGRESS.md` contains detailed implementation notes; this README intentionally focuses on the architecture and reproducible development path.

## Security

See [SECURITY.md](SECURITY.md) for reporting guidance and data-handling expectations.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for project-specific development conventions.
