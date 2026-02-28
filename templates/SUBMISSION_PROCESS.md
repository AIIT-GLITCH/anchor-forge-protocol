# Run Submission Process

## Step 1 — Run the Protocol
Paste the exact prompt from PROTOCOL.md into your model.
Capture the complete raw output. Do not edit it.

## Step 2 — Hash the Output
Generate a SHA-256 hash of the raw output before any verification.

Terminal:
  echo -n "PASTE RAW OUTPUT HERE" | sha256sum

Online: paste raw output into any SHA-256 generator.
Save the 64-character hash string.

## Step 3 — Timestamp the Hash
Go to opentimestamps.org
Paste your SHA-256 hash into the browser tool.
Download the .ots proof file.
This anchors your hash to the Bitcoin blockchain.
Takes under 2 minutes. Free. No account required.

## Step 4 — Open a GitHub Issue
Title format: [RUN SUBMISSION] [Model Name] [YYYY-MM-DD] [RUN-XXX]

Get your Run ID from the current highest number in runs/ + 1.

Issue body must contain:
- Complete raw model output (paste in full)
- SHA-256 hash
- .ots proof file (attach to Issue)
- Model name and version string if available
- Your operator handle
- Confirmation: "I have not begun verification. 
  Output is unchanged from model response."

## Step 5 — Wait for Verifiers
Two trusted verifiers will post independent gate reports 
as comments on your Issue using the template in 
templates/verifier_report_template.md

Do not contact verifiers about your results before both reports are posted.

## Step 6 — Reconciliation
Admin reconciles both reports and posts final certified CI as a comment.
Admin commits the run folder to runs/RUN-XXX/
Leaderboard and banned claims list updated in same commit.

## Checklist (copy this into your Issue)

- [ ] Raw output captured unedited
- [ ] SHA-256 hash generated
- [ ] OpenTimestamps .ots proof obtained
- [ ] No verification begun before Issue posted
- [ ] Banned claims checked against BANNED_CLAIMS.md
- [ ] Model version string included if available
- [ ] Run ID confirmed against current runs/ folder
