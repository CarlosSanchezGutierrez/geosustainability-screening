Roadmap
Phase 0 — Foundation
- [x] GIS Basics
- [x] ArcGIS Online Basics
- [x] ArcGIS Pro Basics
- [x] Data Management basics
- [x] Mapping and Visualization basics
- [x] Spatial Analysis basics
- [ ] Geographic Coordinate Systems
- [ ] Complete Spatial Data Science MOOC
Phase 1 — First Spatial Prototype
- [ ] create synthetic industrial assets;
- [ ] import locations into ArcGIS Pro;
- [ ] define and validate CRS;
- [ ] create environmental buffers;
- [ ] perform spatial joins;
- [ ] calculate distances;
- [ ] export screening table;
- [ ] create initial map.
Phase 2 — Environmental Layers
- [ ] protected areas;
- [ ] hydrology;
- [ ] land cover;
- [ ] administrative boundaries;
- [ ] optional biodiversity layers.
Phase 3 — Raster Analysis
- [ ] clip raster;
- [ ] extract by study area;
- [ ] calculate land-cover composition;
- [ ] generate site-level statistics.
Phase 4 — Automation
- [ ] ArcPy implementation;
- [ ] GeoPandas implementation;
- [ ] PyQGIS implementation;
- [ ] automated validation rules.
Phase 5 — Spatial Database
- [ ] PostgreSQL;
- [ ] PostGIS;
- [ ] spatial schema;
- [ ] spatial indexes;
- [ ] SQL analytical queries.
Phase 6 — Web GIS
- [ ] ArcGIS Online hosted layer;
- [ ] web map;
- [ ] dashboard or application;
- [ ] ArcGIS API for Python automation.
Phase 7 — Final Engineering Package
- [ ] reproducible execution;
- [ ] documented architecture;
- [ ] QA report;
- [ ] analytical outputs;
- [ ] methodology report;
- [ ] portfolio presentation.
  '@ | Set-Content docs\roadmap.md -Encoding UTF8
============================================================
ArcGIS README
============================================================
@'
ArcGIS Workspace
This directory will contain vendor-specific Esri project artifacts.
Planned contents:
arcgis/
|-- projects/
|   `-- geosustainability-screening.aprx
|
`-- layers/
    `-- reusable layer definitions

ArcGIS Pro will initially be used for:
- exploratory GIS;
- visual validation;
- geoprocessing;
- vector analysis;
- raster analysis;
- cartographic outputs.
Repeated workflows should eventually be reproduced using ArcPy.
