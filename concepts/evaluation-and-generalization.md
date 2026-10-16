# Evaluation, Topology Metrics, and Geographic Generalization

## Different benchmarks answer different questions
**nuScenes map vectorization:** typically geometry mAP over predicted map elements and matching tolerances; details vary by codebase and dataset protocol.

**OpenLane-V2:** lane centerline detection (DET_l), traffic element detection (DET_t), lane-to-lane topology (TOP_ll), lane-to-traffic topology (TOP_lt), and consolidated OpenLane-V2 Score (OLS).

A score in one suite must not be numerically compared to another suite.

## SMERF's published benchmark example
OpenLane-V2 subset A, from Luo et al. (2023), Table I:

| Model | DET_l | TOP_ll | DET_t | TOP_lt | OLS |
|---|---:|---:|---:|---:|---:|
| Baseline | 17.0 | 2.3 | 48.5 | 16.2 | 30.2 |
| Baseline + SMERF | 26.8 | 3.9 | 48.9 | 19.2 | 34.8 |
| TopoNet | 28.2 | 4.1 | 44.5 | 20.6 | 34.5 |
| TopoNet + SMERF | 33.4 | 7.5 | 48.6 | 23.4 | 39.4 |

**Source:** [SMERF, Table I](https://arxiv.org/abs/2311.04079). The relative boost in OLS for TopoNet is about 14.2%; the **absolute** gain is 4.9 OLS points. Lane topology TOP_ll rises 4.1 → 7.5, an absolute +3.4 points.

## Geographic overlap
If training and validation include nearby or overlapping roads, models may appear to generalize while benefiting from location-specific memorization. SMERF reports an additional geographically disjoint evaluation (Table V), where absolute scores drop but SD-map augmentation still helps.

## Evaluation checklist
- Dataset version/subset and geographic split
- Online input modalities, calibration and pose assumptions
- Detection representation and distance/IoU match thresholds
- Topology edge direction and association definitions
- Additional data sources, pretrained models, and map coverage
- Model size, latency, memory, and target hardware
- Sensor/map robustness and handling of incorrect priors
- Temporal continuity and global consistency (if claimed)

## Interpretations vs evidence
High benchmark mAP is not proof of safe vehicle planning. A paper's reported runtime may not transfer to an automotive SoC, and noisy pose experiments do not necessarily cover stale or topologically incorrect maps.