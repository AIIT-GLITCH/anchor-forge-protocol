# CI Calculator

No Excel needed. Copy the formula, plug in numbers.

## Formula
CI = (Avg Adjusted Accuracy − 65) × (Avg Weighted Anchors / 10) × Noise × Gate Multiplier × Calibration Multiplier

## Step by Step

1. VERIFIED ACCURACY per claim (0–100)
   Apply penalties before entering:
   − Overfit penalty: −20 if common knowledge
   − Temporal penalty: −10 if [TEMPORAL] flagged
   − Difficulty penalty: −15 if rated Easy
   − RECONSTRUCTED cap: upper bound = 65 max

2. AVG VERIFIED ACCURACY
   Add all 5 post-penalty scores. Divide by 5.

3. WEIGHTED ANCHORS per claim
   Tier 1 = 1.5 | Tier 2 = 1.0 | Tier 3 = 0.5
   Sum tiers per claim. Cap at 5.0 per claim.
   Apply auto-downgrade if Rebuttal C flagged risk.

4. AVG WEIGHTED ANCHORS
   Sum all 5 claim anchor weights. Divide by 5.

5. TOTAL WEIGHTED ANCHORS
   Sum all anchor weights across all claims.

6. NOISE
   max(0.5, 1 / total weighted anchors)

7. RAW CI
   (Avg Accuracy − 65) × (Avg Anchors / 10) × Noise

8. GATE MULTIPLIER
   All LIVE: 1.0
   1 dead: 0.7
   2+ dead: CI = 0
   Any fabricated: CI = 0

9. CALIBRATION DELTA
   Average of |self-score midpoint − verified score| across 5 claims
   0–8: multiplier 1.0
   9–15: multiplier 0.85
   16+: multiplier 0.70

10. FINAL CERTIFIED CI
    Raw CI × Gate Multiplier × Calibration Multiplier
    Cap at 10.0

## Example (RUN-005 Claude v4 blind)

Verified scores: 32, 58, 94, 29, 41
Avg = 50.8
Weighted anchors: 1.5, 1.0, 2.5, 1.5, 1.0 → avg 1.5 → total 7.5
Noise = max(0.5, 1/7.5) = 0.5
Raw CI = (50.8−65) × (1.5/10) × 0.5 = −1.065
Gate multiplier = 0.55
Calibration delta = 12.8 → multiplier 0.85
Final CI = −1.065 × 0.55 × 0.85 = −0.50
