# Review Methodology and Evidence Standards

## Review format
1. **Bibliography & task.** Official link, date, primary objective, inputs and outputs.
2. **Problem and baseline limitations.** What fails in prior systems?
3. **Core insight.** What architectural or representational change is proposed?
4. **Detailed method.** Data flow, query/feature representation, training signal, inference.
5. **Results.** Quote concrete metrics only when the exact table, dataset, and evaluated model are verified. Otherwise report qualitative findings explicitly.
6. **Limitations.** Separate author-reported caveats from analytical hypotheses.
7. **Connections.** What ideas it builds upon and what later work explores a related question.
8. **Sources.** Original paper/conference/project links.

## Evidence labels
- **Paper-reported:** directly supported by the original paper or official publication.
- **Technical interpretation:** our explanation of why a design might work.
- **Open question:** not established by the cited experiments.
- **Not independently verified:** do not treat a number as canonical if benchmark or table provenance is unclear.

## Common traps
- Treating a map prior as ground truth.
- Conflating OSM centerlines with lane centerlines.
- Equating instance geometry with directed lane connectivity.
- Comparing nuScenes map mAP with OpenLane-V2 topology OLS.
- Reporting relative percentage gains as absolute metric points.
- Calling a temporal local BEV output a globally optimized HD map.
- Attributing direct architectural descent from a concept diagram without evidence.

## Scope
Coverage emphasizes the trajectory from online local map extraction to prior-guided lane topology and global association, not a comprehensive survey of every mapping or SLAM paper.