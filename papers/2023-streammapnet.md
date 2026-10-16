# StreamMapNet: Streaming Mapping Network for Vectorized Online HD Map Construction

**Topic:** Temporal vector mapping  
**Primary paper:** https://arxiv.org/abs/2308.12570

## 1. Problem being solved
Per-frame vector predictions can flicker, fragment, or change identity as visibility and ego pose vary. Single-frame methods discard useful observations from immediately preceding frames.

## 2. Proposed solution / core idea
Fuse history into the online vector map predictor to increase stability and continuity over a stream. Its multi-point attention/temporal design captures cues that may not be observable in the current image.

## 3. Architecture and technical mechanism
Important distinction: temporal fusion is inside the learned map representation, rather than averaging already-decoded polylines after inference. Pose alignment and selection of historical information matter for stable results.

## 4. Main experimental results
The paper reports improved vectorized mapping performance and highlights the role of temporal context. Read benchmark tables with their frame history, backbone and evaluation setup before quantitative comparison.

## 5. Limitations and validation caveats
Past frame features may propagate errors and increase memory/latency. A temporally fused local map is not necessarily a persistent, globally optimized HD map.

## 6. Research lineage / connections
Precedes the map-element tracking and globally merged map branches exemplified by MapTracker and GlobalMapNet.

## 7. Questions for further study (researcher interpretation)
- Which ablation isolates the proposed contribution from extra training data or model capacity?
- How does the approach behave under pose noise, missing scene elements, and geographic distribution shift?
- What would be required for bounded-latency, long-running onboard deployment?

## References
- [Original paper](https://arxiv.org/abs/2308.12570)
- [Research roadmap](../ROADMAP.md) · [Full paper index](../PAPERS.md)

> **Evidence note:** Descriptions and any attributed results summarize the linked primary paper or, where explicitly stated, the SMERF paper's evaluation. Open questions and caveats include independent technical analysis. No cross-benchmark performance ranking is implied.
