# HDMapNet: An Online HD Map Construction and Evaluation Framework

**Topic:** Raster-to-vector map construction  
**Primary paper:** https://arxiv.org/abs/2107.06307

## 1. Problem being solved
Prior to online prediction, HD maps required expensive manual survey/annotation and repeated update. A sensor-only local map predictor must recover road markings, dividers, boundaries, and crosswalks from onboard observations.

## 2. Proposed solution / core idea
A raster-first learned mapping pipeline: extract multi-view camera and/or LiDAR features, form a bird's-eye-view representation, infer semantic and instance-level map masks, then vectorize raster outputs with post-processing.

## 3. Architecture and technical mechanism
The distinction between semantic class masks and individual map instances is essential; a class mask cannot on its own identify which pixels belong to which continuous divider. Vector fitting must resolve breaks and intersections after the neural prediction.

## 4. Main experimental results
The original paper establishes a sensor-based local map construction and evaluation baseline across modalities. Its central empirical contribution is the feasibility of predicting high-definition map elements online; quantitative scores are protocol-specific and are not reproduced here without a table-level check.

## 5. Limitations and validation caveats
Post-processing introduces brittle heuristics and can break continuity. A local semantic mask alone does not define lane-to-lane directed topology.

## 6. Research lineage / connections
Provides the raster-based reference point from which VectorMapNet's direct vector output and MapTR's structured point-set modeling emerged.

## 7. Questions for further study (researcher interpretation)
- Which ablation isolates the proposed contribution from extra training data or model capacity?
- How does the approach behave under pose noise, missing scene elements, and geographic distribution shift?
- What would be required for bounded-latency, long-running onboard deployment?

## References
- [Original paper](https://arxiv.org/abs/2107.06307)
- [Research roadmap](../ROADMAP.md) · [Full paper index](../PAPERS.md)

> **Evidence note:** Descriptions and any attributed results summarize the linked primary paper or, where explicitly stated, the SMERF paper's evaluation. Open questions and caveats include independent technical analysis. No cross-benchmark performance ranking is implied.
