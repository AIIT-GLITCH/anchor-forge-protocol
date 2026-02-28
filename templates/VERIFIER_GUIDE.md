# Verifier Guide

## Rules
- Use only primary sources for fact verification. 
  No Wikipedia. No secondary summaries.
- Do not contact the other verifier until both reports are submitted.
- Do not contact the operator about your findings before submitting.
- Work from the raw output in the GitHub Issue only.

## For Each Anchor
Click the URL or resolve the DOI. Record one status:

  LIVE — resolves correctly to the claimed document or data
  DEAD — 404 or domain not found
  WRONG_DOCUMENT — resolves but to unrelated content
  FABRICATED — domain or report number does not exist

## For Each Claim
Verify the stated fact against primary sources.
Record verified accuracy 0–100.
Apply all v5 penalties independently:
  - Overfit: −20% if common knowledge
  - Temporal: −10% if [TEMPORAL] flagged
  - Difficulty: −15% if rated Easy
  - RECONSTRUCTED: upper bound hard-capped at 65%
  - Rebuttal theater: −15% if applicable
  - Rebuttal A zero-impact: theater penalty if numerical 
    claim had zero Rebuttal A score movement

## Gate Multiplier
All anchors LIVE: ×1.0
1 DEAD or WRONG_DOCUMENT: ×0.7
2+ DEAD or WRONG_DOCUMENT: CI = 0
Any FABRICATED: CI = 0

## Submit Your Report
Post your completed verifier_report_template.md 
as a comment on the GitHub Issue.
Do not read the other verifier's report first.

## Reconciliation Rules
Both verifiers agree within ±5% per claim: average the two CIs.
Anchor status dispute: third verifier recruited for that anchor. 
  Majority of three rules.
Accuracy dispute >10%: both cite primary source. 
  Source closer to claim domain wins. 
  If still disputed: lower score used.
