# Remaining runs (2026-08-31) — locked

## Gate A campaign path (`hardware=0`, stuck 0.001, map 11)
`n_cim=21`, `logits_equal=1`, `max_abs_diff=0`. Same batch twice is bit-identical on the ranking path.

## Layer L1 (stuck-at, one batch / map, 20 CIM weight modules)
Map 99 is **not** a single-layer event. Largest excess vs ranking-mean L1:
- `conv3_x.0.shortcut.0` +0.0412
- `conv2_x.0.residual_function.3` +0.0394
`fc` is the largest L1 layer on **every** map (including 99: 0.41 vs ranking fc 0.36–0.47). Map 66 has the highest fc L1 (0.47) but only −7.03 pp Acc, not collapse.

## Sparse-binary (same 8-bit/ADC5 path, stuck=0; p=0.001 zero + p=0.001 saturate)
Nominal 72.05%. Ten maps, N=10000:

| seed | Acc | drop_pp | analog core |
|------|-----|---------|-------------|
| 11 | 70.13 | 1.92 | — |
| 22 | 70.53 | 1.52 | — |
| 33 | 70.65 | 1.40 | — |
| 44 | 70.59 | 1.46 | crocodile |
| 55 | 70.44 | 1.61 | crocodile |
| 66 | 70.86 | 1.19 | crocodile |
| 77 | 69.16 | 2.89 | crocodile |
| 88 | 70.76 | 1.29 | crocodile |
| 99 | 69.58 | 2.47 | crocodile |
| 110 | 70.41 | 1.64 | — |

Mean drop **1.74 pp** (1.19–2.89). **n_collapse=0**. lawn_mower **0/10**. crocodile **6/10**. Map 99 is −2.47 pp (stuck-at map 99 was −30.04).
