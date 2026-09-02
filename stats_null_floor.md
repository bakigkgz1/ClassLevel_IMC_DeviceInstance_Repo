# Paper IV — permutation / CI / excess-floor lock

## Ranking-regime analog maps n=9 (exclude collapse seed 99)
Kendall tau mean pairwise = 0.0905
  jackknife SE = 0.0228
  bootstrap unique-maps 95% CI = [0.0435, 0.1406]
  exchangeable-class permutation p (H0: tau >= obs) = 0.0000  (null mean 0.0002)
  pair tau min/median/max = -0.186/0.078/0.543
  single-pair analytic SE (n=100) ~ 0.067 — one pair at 0.087 is n.s.; the TESTED object is the 36-pair mean

Jaccard worst-10 mean = 0.1268
  jackknife SE = 0.0211
  bootstrap unique-maps 95% CI = [0.0905, 0.1685]
  exchangeable-class permutation p = 0.0000  (null mean 0.0552, random baseline ~0.053)

## Core recurrence
lawn_mower  7/9   crocodile 6/9   leopard 5/9   camel 3/9
uniform null p(count_lm >= 7) = 0.0000  — this null is TOO EASY (reviewer is right)
difficulty-preserving residual-shuffle p(lm >= 7) = 0.9390
difficulty-preserving residual-shuffle p(cr >= 6) = 0.6250
  null mean count lm=8.00  cr=5.87  max-class=8.07

## Excess floor (Section III said ~0.10 is noise)
worst-10 excess: mean=0.122  median=0.100  p10=0.060  p25=0.083  min=0.050  max=0.380
fraction of worst-10 slots with excess >= 0.1 = 56/90 = 0.622
mean excess by worst-10 rank (1=worst):
  rank  1: mean=0.196  median=0.140  min=0.100  frac>=0.1=1.00
  rank  2: mean=0.154  median=0.130  min=0.080  frac>=0.1=0.89
  rank  3: mean=0.130  median=0.110  min=0.060  frac>=0.1=0.89
  rank  4: mean=0.123  median=0.100  min=0.060  frac>=0.1=0.78
  rank  5: mean=0.119  median=0.100  min=0.060  frac>=0.1=0.56
  rank  6: mean=0.111  median=0.090  min=0.060  frac>=0.1=0.44
  rank  7: mean=0.104  median=0.090  min=0.050  frac>=0.1=0.44
  rank  8: mean=0.099  median=0.090  min=0.050  frac>=0.1=0.44
  rank  9: mean=0.096  median=0.080  min=0.050  frac>=0.1=0.44
  rank 10: mean=0.090  median=0.080  min=0.050  frac>=0.1=0.33

Core restricted to excess>=0.1 (class must beat the floor on that map):
  lawn_mower 6/9  crocodile 4/9  leopard 2/9  camel 3/9
Jaccard of floor-filtered sets (variable size) = 0.0825

## All 10 maps including collapse (for tau robustness, already in PROTOCOL)
tau all-10 = 0.0814

## Seed 33 digital (unmatched CV=0.15) — do NOT treat as analog-vs-digital core test
digital unmatched kangaroo 6/10 beetle 5/10 lawn_mower 1/10 crocodile 1/10
Matched-drop digital 10-map is NOT in this file. Run COLAB_GATED_FULLMATCH.py.

## How to read this for the paper
- Mean pairwise tau is distinguishable from the exchangeable-class null (report p and jackknife SE).
- Uniform 7/9 p-value is not a valid core test; use difficulty-preserving p.
- If difficulty-preserving p is large, the named core is a stuck-at FAMILY main effect,
  not an extra instance-recurrence beyond class fragility. Gate E still tests whether
  compression shares that main effect.
- Jaccard without a floor mixes noise-rank overlap; report both raw J10 and floor-filtered.

