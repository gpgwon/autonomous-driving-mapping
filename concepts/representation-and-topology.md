# Representation and Topology: A Technical Primer

## Raster semantic map
A BEV tensor `S ∈ R^{H×W×C}` encodes occupancy or semantic probabilities for classes such as divider, boundary, and crossing. It is easy to supervise with segmentation losses, but not intrinsically a vector map. To recover polylines, components must be grouped, skeletonized, fit, and connected.

## Vector map
A map instance is a polyline `P_i = [(x_1,y_1),…,(x_N,y_N)]`, possibly open, closed, directed, or variable length. End-to-end vector decoders avoid hand-crafted raster-to-vector conversion, but must handle variable geometry, point order, and instance matching.

### Permutation equivalence
For a non-directed open polyline, `[A,B,C]` and `[C,B,A]` can express the same geometry. Closed boundaries have cyclic start-point ambiguity. MapTR addresses this during structured prediction/matching. This does **not** mean all lane centerlines are direction-agnostic: directed lanes encode traffic flow.

## Lane graph / topology
A lane graph `G=(V,E)` requires nodes (lane or lane-segment primitives) **and directed edges** representing feasible transitions. OpenLane-V2 additionally labels associations between lane centerlines and traffic elements. Geometric proximity is insufficient: a crossing, divider, or opposite-direction road may be spatially close but not connected.

## Road-level SD map vs lane-level HD map
OSM may encode road centerlines, road classes, and connectivity but usually not precise lane boundaries or all regulatory associations. The mapping from one road-level polyline to multiple lane-level polylines is underdetermined from the SD geometry alone. Methods must recover lane structure from sensors or additional data.

## Three distinct map usage patterns
- **Feature-level conditioning:** encode prior maps and fuse features (e.g., SMERF).
- **Query-level initialization:** derive likely lane queries/anchors from priors (e.g., SCORE).
- **Explicit map association:** match road-level paths to lane-level predictions (e.g., ONR/MAT).

## Key geometric failure modes
Localization error, map staleness, invalid road-type semantics, dynamic occlusion, inaccurate elevations, and discontinuous local observations. Robust map conditioning needs to detect and downweight contradictory evidence.