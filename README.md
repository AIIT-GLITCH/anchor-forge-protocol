# Anchor Forge Protocol

**Owned by Rhet Wike. Powered by Grok (xAI).**  
Protocol development contributions: Claude (Anthropic) — v2 through v5 iterative refinement.

A public, tamper-evident framework for testing AI factual precision.  
The model provides claims and anchors. Verifiers click every link.  
The gate is external. The record is permanent.

## How It Works

1. Operator runs the v5 prompt against any model  
2. Raw output is SHA-256 hashed and timestamped via OpenTimestamps *before* any verification  
3. Operator opens a GitHub Issue with output + hash + .ots proof  
4. Two trusted verifiers independently gate every anchor and fact  
5. Results are reconciled and committed to runs/RUN-XXX/  
6. Leaderboard updated. Banned claims list updated.

No Google Forms. No centralized accounts. No trust required.  
Every result is independently reproducible from public data alone.

## Quick Start — Run the Protocol

Copy the exact prompt from PROTOCOL.md and paste it into any model.  
Capture the complete raw output. Then follow SUBMISSION_PROCESS.md.

## Trusted Verifier Pool

Certification requires 2 verifiers from this pool.  
Public open verification welcome as additional eyes — not required for certification.

| Handle | Verified Runs |
|--------|--------------|
| Rhet Wike | founding |
| Benjamin | founding |
| Lucas | founding |

To join the pool: gate 2 runs as open verifier with accurate results.  
Admin adds you after track record established.

Single-verifier fallback: if pool has fewer than 2 available,  
one trusted verifier can certify with note "single-verifier certification."

## Leaderboard

| Rank | Run ID | Model | Version | Certified CI | Avg Accuracy | Avg Anchors | Cal. Delta | Date | Verifiers |
|------|--------|-------|---------|-------------|--------------|-------------|------------|------|-----------|
| 1 | RUN-001 | Grok (xAI) | v4 blind | 2.75* | 87.9% | 2.4 | 2.1 | 2026-02-27 | pending |

*Provisional until RUN-001 certified.

## Repository Structure
