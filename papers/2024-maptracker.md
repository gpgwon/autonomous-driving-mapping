# MapTracker: Tracking with Strided Memory Fusion for Consistent Vector HD Mapping

**Topic:** Temporal map element tracking  
**Primary paper:** https://arxiv.org/abs/2403.15951

## 1. Problem being solved
Independent vector map predictions can change shape, location, or identity from frame to frame, making the local map unstable even when per-frame detection looks good.

## 2. Proposed solution / core idea
Treat persistent vector elements as trackable scene structures, carry map instance hypotheses over time, and fuse historical memory at selected strides for stable vector prediction.

## 3. Architecture and technical mechanism
A static-world feature observed from a moving ego vehicle must be ego-motion-compensated before temporal matching. Query/instance association allows reuse of prior hypotheses and can limit identity switches. Strided history introduces a longer temporal baseline than immediately adjacent-frame fusion alone.

## 4. Main experimental results
The official ECCV 2024 work reports improvements in consistent vector HD mapping relative to its evaluated baselines. Numerical ranking needs the same temporal context, map definition, and hardware assumptions.

## 5. Limitations and validation caveats
Temporal hypotheses may preserve false positives, and longer histories increase state management, pose-alignment, and memory costs.

## 6. Research lineage / connections
Builds on online vector-mapping but frames stability as a tracking problem; complements StreamMapNet and global stitching in GlobalMapNet.

## 7. Questions for further study (researcher interpretation)
- Which ablation isolates the proposed method from extra supervision, training budget, or capacity?
- What changes when pose calibration, global alignment, map freshness, or geography differs?
- What is the compute/memory cost and does the reported latency translate to automotive hardware?

## References
- [Original publication](https://arxiv.org/abs/2403.15951)
- [Research roadmap](../ROADMAP.md) · [Full paper index](../PAPERS.md)

> **Evidence note:** Results are attributed to the original work when specified. Technical interpretations and research questions are not assertions of measured outcomes. Numerical benchmark claims are not presented as cross-paper rankings.
