# Online Navigation Refinement: Achieving Lane-Level Guidance by Associating Standard-Definition and Online Perception Maps

**Topic:** SD road-to-online-lane association  
**Primary paper:** https://proceedings.iclr.cc/paper_files/paper/2026/hash/884baf65392170763b27c914087bde01-Abstract-Conference.html

## 1. Problem being solved
Even when an online perception model predicts accurate lane vectors, an SD navigation route is road-level. There is no automatic explicit correspondence telling a planner which observed lane segments realize the route.

## 2. Proposed solution / core idea
Define the online navigation refinement / map association task and use a Map Association Transformer (MAT) to match coarse road-network elements with online lane-level elements, incorporating spatial and path-topological context.

## 3. Architecture and technical mechanism
One SD road can correspond to several directed lane segments, so pure nearest-neighbor matching is insufficient. Spatial alignment, legal continuation, topology, and many-to-one correspondences must be evaluated jointly. This is an association task, not just map-feature conditioning.

## 4. Main experimental results
The ICLR 2026 work introduces the OMA benchmark (about 30,000 scenarios and 2.6 million lane vectors as reported) and reports a 34 ms model latency under its evaluated environment. Latency is not a guarantee on embedded automotive hardware.

## 5. Limitations and validation caveats
Association inherits localization errors and topology uncertainty from both SD and perceived online maps. Strong association metrics do not alone prove closed-loop navigation safety.

## 6. Research lineage / connections
Moves beyond SD-prior feature fusion toward explicit cross-resolution map correspondences. Related to PriorDrive/SMERF by data modality, but solves a different downstream task.

## 7. Questions for further study (researcher interpretation)
- Which ablation isolates the proposed method from extra supervision, training budget, or capacity?
- What changes when pose calibration, global alignment, map freshness, or geography differs?
- What is the compute/memory cost and does the reported latency translate to automotive hardware?

## References
- [Original publication](https://proceedings.iclr.cc/paper_files/paper/2026/hash/884baf65392170763b27c914087bde01-Abstract-Conference.html)
- [Research roadmap](../ROADMAP.md) · [Full paper index](../PAPERS.md)

> **Evidence note:** Results are attributed to the original work when specified. Technical interpretations and research questions are not assertions of measured outcomes. Numerical benchmark claims are not presented as cross-paper rankings.
