Technical Decisions
This file records important architectural and methodological decisions.
D-001 — Use ArcGIS Pro and QGIS
Status: Accepted
ArcGIS Pro will be the primary enterprise GIS environment.
QGIS will be used to reinforce vendor-neutral GIS knowledge and test conceptual portability.
D-002 — Separate GIS concepts from vendor implementation
Status: Accepted
Spatial methodology should be documented independently from ArcGIS, QGIS, or Python syntax.
D-003 — Public or synthetic data only
Status: Accepted
No proprietary employer information will be used.
D-004 — Do not version raw GIS datasets in Git
Status: Accepted
Large and externally sourced datasets will remain outside standard Git history.
Metadata describing those datasets will be versioned instead.
D-005 — Code-first reproducibility is the long-term objective
Status: Accepted
GUI workflows are useful for learning and visual validation.
Once understood, repeatable workflows should eventually be automated.
D-006 — CRS choice must be explicit
Status: Accepted
No project-wide CRS will be assumed to be universally appropriate.
Projected CRS selection should depend on geography and analytical purpose.
D-007 — GeoPackage for portable prototypes
Status: Accepted
GeoPackage will be preferred over Shapefile for portable open-source vector storage.
D-008 — PostGIS for scalable spatial relational analysis
Status: Planned
PostgreSQL/PostGIS will be introduced after the first local prototype is operational.
