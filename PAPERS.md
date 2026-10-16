# Annotated Paper Index

**Dates:** early-publication years are used when known; publication in a later conference may differ. **Tags overlap intentionally.**

| First release | Paper | Main tags | Review |
|---|---|---|---|
| 2021 | HDMapNet | raster, online HD map | [Review](papers/2021-hdmapnet.md) |
| 2022 | VectorMapNet | end-to-end vector, autoregressive | [Review](papers/2022-vectormapnet.md) |
| 2022 | MapTR | vector, hierarchical query | [Review](papers/2022-maptr.md) |
| 2023 | MapTRv2 | vector, efficient decoder | [Review](papers/2023-maptrv2.md) |
| 2023 | LaneGAP | lane graph, continuity | [Review](papers/2023-lanegap.md) |
| 2023 | TopoNet | lane topology, graph reasoning | [Review](papers/2023-toponet.md) |
| 2023 | Neural Map Prior (NMP) | learned global prior, fusion | [Review](papers/2023-nmp.md) |
| 2023 | SMERF | OSM SD priors, topology | [Review](papers/2023-smerf.md) |
| 2023 | StreamMapNet | temporal vector mapping | [Review](papers/2023-streammapnet.md) |
| 2024 | LaneSegNet | lane segment, topology | [Review](papers/2024-lanesegnet.md) |
| 2024 | TopoLogic | topology, geometric constraints | [Review](papers/2024-topologic.md) |
| 2024 | P-MapNet | SD and learned HD priors | [Review](papers/2024-pmapnet.md) |
| 2024 | SDHDMap | OSM raster/graph fusion | [Review](papers/2024-sdhdmap.md) |
| 2024 | TopoSD | SD map, topology enhancement | [Review](papers/2024-toposd.md) |
| 2024 | MapTracker | temporal map tracking | [Review](papers/2024-maptracker.md) |
| 2024 | GlobalMapNet | online global map assembly | [Review](papers/2024-globalmapnet.md) |
| 2025 | SMART | map-prior pretraining | [Review](papers/2025-smart.md) |
| 2025 | SCORE | SD query prior, temporal | [Review](papers/2025-score.md) |
| 2026 | PriorDrive | unified vector priors | [Review](papers/2026-priordrive.md) |
| 2026 | Online Navigation Refinement / MAT | map association, lane navigation | [Review](papers/2026-onr-mat.md) |

## Organizing by objective

**Local construction:** HDMapNet, VectorMapNet, MapTR, MapTRv2.

**Lane topology:** LaneGAP, TopoNet, LaneSegNet, TopoLogic, TopoSD, SCORE.

**Externally guided mapping:** SMERF, P-MapNet, SDHDMap, SMART, PriorDrive.

**Historical priors and temporal coherence:** NMP, StreamMapNet, MapTracker, GlobalMapNet.

**Cross-representation map association:** Online Navigation Refinement / MAT.

## How to compare papers responsibly

A higher metric in one publication need not indicate a superior algorithm. Confirm the benchmark, geographic split, input sensors, area of interest, backbone, training budget, matching thresholds, and use of extra map data. See [Evaluation](concepts/evaluation-and-generalization.md).