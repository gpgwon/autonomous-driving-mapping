# Coherent Online Road Topology Estimation and Reasoning with Standard-Definition Maps (SCORE)

**Topic:** SD-map-guided lane queries and temporal coherence  
**Primary paper:** https://arxiv.org/abs/2507.01397

## 1. Problem being solved
A map-aware BEV feature may still force a decoder to discover lane locations from weak or generic initial queries; temporal inconsistency makes network predictions unstable.

## 2. Proposed solution / core idea
Use SD map geometry to guide initial lane query/reference-point placement, combine camera observations with this coarse geometry, and include temporal fusion and topology-oriented refinement.

## 3. Architecture and technical mechanism
Contrast **feature-level priors** (SMERF: attention from BEV queries into map feature tokens) with **query-level priors** (SCORE: SD-informed lane starting hypotheses). A query anchor is a soft initial hypothesis, not a hard guarantee that the SD geometry is correct.

## 4. Main experimental results
The paper reports better coherent road/lane topology estimation against its chosen baselines, with contributions from SD query initialization and temporal processing. Numerical scores are not copied without matching its official evaluation tables.

## 5. Limitations and validation caveats
Pose error, changed road graphs, and query anchors biased by incorrect SD geometry remain important failure modes. Temporal methods can propagate earlier mistakes.

## 6. Research lineage / connections
Extends the SD map usage design space beyond BEV feature concatenation/attention; closely connected to topology/temporal mapping streams.

## 7. Questions for further study (researcher interpretation)
- Which ablation isolates the proposed method from extra supervision, training budget, or capacity?
- What changes when pose calibration, global alignment, map freshness, or geography differs?
- What is the compute/memory cost and does the reported latency translate to automotive hardware?

## References
- [Original publication](https://arxiv.org/abs/2507.01397)
- [Research roadmap](../ROADMAP.md) · [Full paper index](../PAPERS.md)

> **Evidence note:** Results are attributed to the original work when specified. Technical interpretations and research questions are not assertions of measured outcomes. Numerical benchmark claims are not presented as cross-paper rankings.
