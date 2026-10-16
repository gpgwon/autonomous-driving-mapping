# PriorDrive: Enhancing Online HD Mapping with Unified Vector Priors

**Topic:** Unified heterogeneous vector-map priors  
**Primary paper:** https://ojs.aaai.org/index.php/AAAI/article/view/38223

## 1. Problem being solved
Real systems may have OSM road skeletons, vendor HD maps, and past local maps with different topology, detail, and reliability. A separate encoder per format reduces scalability.

## 2. Proposed solution / core idea
Build a unified interface for diverse vector map priors, including a hybrid prior query representation and unified vector encoder with map-structure pretraining objectives.

## 3. Architecture and technical mechanism
Treat prior elements as structured objects with instance/point semantics rather than raw pixels. A unified encoder can map heterogeneous geometry into a shared representation that an online mapper consumes. It is a representational interface, not proof that all priors are equally reliable.

## 4. Main experimental results
The AAAI 2026 paper reports online vector map performance improvements when using several types of prior map data. For precise numerical claims, compare identical backbone, additional priors, and dataset protocols in the paper.

## 5. Limitations and validation caveats
Map source trust, coordinate frames, staleness, and resolution mismatch remain engineering constraints. Benefits of more available priors must be balanced against compute and complexity.

## 6. Research lineage / connections
A broadening of the SMERF/P-MapNet/SMART trajectory from a specific SD prior toward a reusable prior-encoding framework.

## 7. Questions for further study (researcher interpretation)
- Which ablation isolates the proposed method from extra supervision, training budget, or capacity?
- What changes when pose calibration, global alignment, map freshness, or geography differs?
- What is the compute/memory cost and does the reported latency translate to automotive hardware?

## References
- [Original publication](https://ojs.aaai.org/index.php/AAAI/article/view/38223)
- [Research roadmap](../ROADMAP.md) · [Full paper index](../PAPERS.md)

> **Evidence note:** Results are attributed to the original work when specified. Technical interpretations and research questions are not assertions of measured outcomes. Numerical benchmark claims are not presented as cross-paper rankings.
