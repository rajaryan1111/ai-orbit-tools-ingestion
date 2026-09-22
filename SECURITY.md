# Security Policy

## Scope

This repository contains a data-ingestion and verification pipeline. Do not submit credentials, private datasets, customer data, or production exports to the public repository.

## Reporting a vulnerability

Report security issues privately through the maintainer's GitHub profile instead of a public issue. Include the affected component, reproduction steps, and potential impact.

## Data and credentials

Keep API keys, tokens and private configuration in environment variables. The test suite should use deterministic local fixtures rather than real private source data.
