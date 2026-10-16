# P-MapNet: Far-seeing Map Generator Enhanced by both SDMap and HDMap Priors

**Topic:** Weakly aligned SD maps and learned HD priors  
**Primary paper:** https://arxiv.org/abs/2403.10521

## 1. Problem being solved
Far-range local map geometry is poorly observable from onboard sensors, while external SD centerlines may be geographically inaccurate and too coarse for lane-detail reconstruction.

## 2. Proposed solution / core idea
Fuse a weakly aligned SD road skeleton with onboard features, and learn a complementary HD map prior through masked modeling of available HD map training examples. The method uses prior knowledge to guide and refine online output.

## 3. Architecture and technical mechanism
Two priors play different roles: an SD map gives location-specific road geometry; a learned HD prior summarizes common fine-grained map patterns. Because the SD prior is not assumed pixel-perfect, alignment-tolerant attention/fusion matters. The HD prior is not equivalent to assuming a pre-existing HD map at inference everywhere.

## 4. Main experimental results
The paper reports improvements in long-range and occluded map prediction and evaluates both raster and vector outputs. Reported gains include up to +18.73 mIoU (raster) and +8.50 mAP (vector) in particular paper settings; **these are not comparable to SMERF's OLS**.

## 5. Limitations and validation caveats
Prior quality and map-coverage dependence remain; learned map patterns might hallucinate plausible-but-wrong road geometry. Evaluate wrong topology as well as coordinate misalignment.

## 6. Research lineage / connections
Extends the prior-fusion question posed by SMERF toward weak alignment and complementary learned HD priors; compare with SMART's offline prior training.

## 7. Questions for further study (researcher interpretation)
- Which ablation isolates the proposed method from extra supervision, training budget, or capacity?
- What changes when pose calibration, global alignment, map freshness, or geography differs?
- What is the compute/memory cost and does the reported latency translate to automotive hardware?

## References
- [Original publication](https://arxiv.org/abs/2403.10521)
- [Research roadmap](../ROADMAP.md) · [Full paper index](../PAPERS.md)

> **Evidence note:** Results are attributed to the original work when specified. Technical interpretations and research questions are not assertions of measured outcomes. Numerical benchmark claims are not presented as cross-paper rankings.
