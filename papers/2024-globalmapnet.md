# GlobalMapNet: An Online Framework for Vectorized Global HD Map Construction

**Topic:** Global map fusion  
**Primary paper:** https://arxiv.org/abs/2409.10063

## 1. Problem being solved
High-quality frame-local maps do not automatically create one globally consistent map: overlapping elements need deduplication, alignment, and merging across poses and traversals.

## 2. Proposed solution / core idea
Accumulate local vector map predictions in a global map builder, associate overlapping structures, suppress duplicates, and fuse consistent map elements into a persistent larger-scale vector representation.

## 3. Architecture and technical mechanism
Separate the upstream local vector detector from map-level data association. Matching tests whether two local vectors correspond to the same world object; merging then updates a global representation. Errors in ego localization and wrong matches can propagate at map scale.

## 4. Main experimental results
The original paper reports global vectorized HD map construction and evaluates the proposed online merging/fusion pipeline. Use its global-map benchmark metrics rather than local vector mAP alone.

## 5. Limitations and validation caveats
A globally accumulated result need not be as accurate as survey-grade HD maps; localization drift, loops, dynamic changes and edit conflicts require attention.

## 6. Research lineage / connections
Natural extension of per-frame vector map prediction and temporal fusion. It is a different problem axis from adding static SD priors to current BEV features.

## 7. Questions for further study (researcher interpretation)
- Which ablation isolates the proposed method from extra supervision, training budget, or capacity?
- What changes when pose calibration, global alignment, map freshness, or geography differs?
- What is the compute/memory cost and does the reported latency translate to automotive hardware?

## References
- [Original publication](https://arxiv.org/abs/2409.10063)
- [Research roadmap](../ROADMAP.md) · [Full paper index](../PAPERS.md)

> **Evidence note:** Results are attributed to the original work when specified. Technical interpretations and research questions are not assertions of measured outcomes. Numerical benchmark claims are not presented as cross-paper rankings.
