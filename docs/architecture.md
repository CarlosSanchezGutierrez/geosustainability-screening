Project Charter
Project
GeoSustainability Screening
Status
Planning / Prototype Design
Problem Statement
Environmental and sustainability teams may need to evaluate geographically distributed industrial assets using information coming from multiple spatial and non-spatial sources.
Without a structured methodology, these analyses may suffer from:
- inconsistent coordinate systems;
- invalid geometries;
- inconsistent site identifiers;
- duplicated records;
- undocumented spatial assumptions;
- manually repeated GIS operations;
- limited reproducibility;
- unclear data lineage.
The project proposes a reproducible geospatial screening framework.
Objective
Develop an auditable workflow for integrating industrial asset locations with environmental spatial datasets and generating standardized screening indicators.
Target Users
Potential users of such a framework include:
- sustainability analysts;
- ESG reporting teams;
- GIS analysts;
- environmental teams;
- data engineers;
- corporate risk teams;
- assurance reviewers;
- operational teams.
Initial Analytical Domains
Biodiversity
Protected areas and biodiversity-sensitive locations.
Land Cover
Forest, agricultural, urban, water, grassland, and other classes.
Hydrology
Water bodies, rivers, watersheds, and water-related context.
Industrial Assets
Plants, quarries, terminals, warehouses, and other facilities.
Data Quality
Geometry, CRS, identifiers, metadata, completeness, and consistency.
In Scope
- vector GIS;
- raster GIS;
- spatial joins;
- proximity analysis;
- buffers;
- intersections;
- land-cover analysis;
- spatial data validation;
- CRS management;
- GIS metadata;
- reproducible workflows;
- ArcGIS Pro;
- ArcGIS Online;
- QGIS;
- Python;
- PostGIS.
Out of Scope — Initial Phase
- regulatory compliance determinations;
- environmental-impact assessments;
- legal conclusions;
- production CEMEX data;
- proprietary datasets;
- operational deployment;
- real-time monitoring;
- final risk scoring methodology.
Success Criteria
The prototype should eventually demonstrate that:
1. source datasets are documented;
2. CRS decisions are explicit;
3. spatial operations are reproducible;
4. data-quality exceptions are visible;
5. results can be generated through code;
6. ArcGIS Pro and QGIS produce conceptually consistent results;
7. environmental indicators can be exported into analytical tables;
8. outputs can be clearly communicated to non-GIS users.
   '@ | Set-Content docs\project-charter.md -Encoding UTF8
============================================================
ARCHITECTURE
============================================================
@'
Architecture
Conceptual Architecture
#chatgpt-mermaid-_r_140n_{font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",sans-serif;font-size:14px;fill:rgb(255, 255, 255);}@keyframes edge-animation-frame{from{stroke-dashoffset:0;}}@keyframes dash{to{stroke-dashoffset:0;}}#chatgpt-mermaid-_r_140n_ .edge-animation-slow{stroke-dasharray:9,5!important;stroke-dashoffset:900;animation:dash 50s linear infinite;stroke-linecap:round;}#chatgpt-mermaid-_r_140n_ .edge-animation-fast{stroke-dasharray:9,5!important;stroke-dashoffset:900;animation:dash 20s linear infinite;stroke-linecap:round;}#chatgpt-mermaid-_r_140n_ .error-icon{fill:rgba(54, 54, 54, 0.96);}#chatgpt-mermaid-_r_140n_ .error-text{fill:rgb(255, 255, 255);stroke:rgb(255, 255, 255);}#chatgpt-mermaid-_r_140n_ .edge-thickness-normal{stroke-width:1px;}#chatgpt-mermaid-_r_140n_ .edge-thickness-thick{stroke-width:3.5px;}#chatgpt-mermaid-_r_140n_ .edge-pattern-solid{stroke-dasharray:0;}#chatgpt-mermaid-_r_140n_ .edge-thickness-invisible{stroke-width:0;fill:none;}#chatgpt-mermaid-_r_140n_ .edge-pattern-dashed{stroke-dasharray:3;}#chatgpt-mermaid-_r_140n_ .edge-pattern-dotted{stroke-dasharray:2;}#chatgpt-mermaid-_r_140n_ .marker{fill:rgba(255, 255, 255, 0.498);stroke:rgba(255, 255, 255, 0.498);}#chatgpt-mermaid-_r_140n_ .marker.cross{stroke:rgba(255, 255, 255, 0.498);}#chatgpt-mermaid-_r_140n_ svg{font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",sans-serif;font-size:14px;}#chatgpt-mermaid-_r_140n_ p{margin:0;}#chatgpt-mermaid-_r_140n_ .label{font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",sans-serif;color:rgb(255, 255, 255);}#chatgpt-mermaid-_r_140n_ .cluster-label text{fill:rgb(255, 255, 255);}#chatgpt-mermaid-_r_140n_ .cluster-label span{color:rgb(255, 255, 255);}#chatgpt-mermaid-_r_140n_ .cluster-label span p{background-color:transparent;}#chatgpt-mermaid-_r_140n_ .label text,#chatgpt-mermaid-_r_140n_ span{fill:rgb(255, 255, 255);color:rgb(255, 255, 255);}#chatgpt-mermaid-_r_140n_ .node rect,#chatgpt-mermaid-_r_140n_ .node circle,#chatgpt-mermaid-_r_140n_ .node ellipse,#chatgpt-mermaid-_r_140n_ .node polygon,#chatgpt-mermaid-_r_140n_ .node path{fill:rgb(26, 40, 61);stroke:rgb(31, 78, 148);stroke-width:1px;}#chatgpt-mermaid-_r_140n_ .rough-node .label text,#chatgpt-mermaid-_r_140n_ .node .label text,#chatgpt-mermaid-_r_140n_ .image-shape .label,#chatgpt-mermaid-_r_140n_ .icon-shape .label{text-anchor:middle;}#chatgpt-mermaid-_r_140n_ .node .katex path{fill:#000;stroke:#000;stroke-width:1px;}#chatgpt-mermaid-_r_140n_ .rough-node .label,#chatgpt-mermaid-_r_140n_ .node .label,#chatgpt-mermaid-_r_140n_ .image-shape .label,#chatgpt-mermaid-_r_140n_ .icon-shape .label{text-align:center;}#chatgpt-mermaid-_r_140n_ .node.clickable{cursor:pointer;}#chatgpt-mermaid-_r_140n_ .root .anchor path{fill:rgba(255, 255, 255, 0.498)!important;stroke-width:0;stroke:rgba(255, 255, 255, 0.498);}#chatgpt-mermaid-_r_140n_ .arrowheadPath{fill:rgba(255, 255, 255, 0.498);}#chatgpt-mermaid-_r_140n_ .edgePath .path{stroke:rgba(255, 255, 255, 0.498);stroke-width:1px;}#chatgpt-mermaid-_r_140n_ .flowchart-link{stroke:rgba(255, 255, 255, 0.498);fill:none;}#chatgpt-mermaid-_r_140n_ .edgeLabel{background-color:rgb(24, 24, 24);text-align:center;}#chatgpt-mermaid-_r_140n_ .edgeLabel p{background-color:rgb(24, 24, 24);}#chatgpt-mermaid-_r_140n_ .edgeLabel rect{opacity:0.5;background-color:rgb(24, 24, 24);fill:rgb(24, 24, 24);}#chatgpt-mermaid-_r_140n_ .labelBkg{background-color:rgba(24, 24, 24, 0.5);}#chatgpt-mermaid-_r_140n_ .cluster rect{fill:rgba(54, 54, 54, 0.96);stroke:rgba(255, 255, 255, 0.082);stroke-width:1px;}#chatgpt-mermaid-_r_140n_ .cluster text{fill:rgb(255, 255, 255);}#chatgpt-mermaid-_r_140n_ .cluster span{color:rgb(255, 255, 255);}#chatgpt-mermaid-_r_140n_ div.mermaidTooltip{position:absolute;text-align:center;max-width:200px;padding:2px;font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",sans-serif;font-size:12px;background:rgba(54, 54, 54, 0.96);border:1px solid rgba(255, 255, 255, 0.082);border-radius:2px;pointer-events:none;z-index:100;}#chatgpt-mermaid-_r_140n_ .flowchartTitleText{text-anchor:middle;font-size:18px;fill:rgb(255, 255, 255);}#chatgpt-mermaid-_r_140n_ rect.text{fill:none;stroke-width:0;}#chatgpt-mermaid-_r_140n_ .icon-shape,#chatgpt-mermaid-_r_140n_ .image-shape{background-color:rgb(24, 24, 24);text-align:center;}#chatgpt-mermaid-_r_140n_ .icon-shape p,#chatgpt-mermaid-_r_140n_ .image-shape p{background-color:rgb(24, 24, 24);padding:2px;}#chatgpt-mermaid-_r_140n_ .icon-shape .label rect,#chatgpt-mermaid-_r_140n_ .image-shape .label rect{opacity:0.5;background-color:rgb(24, 24, 24);fill:rgb(24, 24, 24);}#chatgpt-mermaid-_r_140n_ .label-icon{display:inline-block;height:1em;overflow:visible;vertical-align:-0.125em;}#chatgpt-mermaid-_r_140n_ .node .label-icon path{fill:currentColor;stroke:revert;stroke-width:revert;}#chatgpt-mermaid-_r_140n_ .node .neo-node{stroke:rgb(31, 78, 148);}#chatgpt-mermaid-_r_140n_ [data-look="neo"].node rect,#chatgpt-mermaid-_r_140n_ [data-look="neo"].cluster rect,#chatgpt-mermaid-_r_140n_ [data-look="neo"].node polygon{stroke:url(#chatgpt-mermaid-_r_140n_-gradient);filter:drop-shadow( 1px 2px 2px rgba(185,185,185,1));}#chatgpt-mermaid-_r_140n_ [data-look="neo"].swimlane.cluster rect{filter:none;}#chatgpt-mermaid-_r_140n_ [data-look="neo"].node path{stroke:url(#chatgpt-mermaid-_r_140n_-gradient);stroke-width:1px;}#chatgpt-mermaid-_r_140n_ [data-look="neo"].node .outer-path{filter:drop-shadow( 1px 2px 2px rgba(185,185,185,1));}#chatgpt-mermaid-_r_140n_ [data-look="neo"].node .neo-line path{stroke:rgb(31, 78, 148);filter:none;}#chatgpt-mermaid-_r_140n_ [data-look="neo"].node circle{stroke:url(#chatgpt-mermaid-_r_140n_-gradient);filter:drop-shadow( 1px 2px 2px rgba(185,185,185,1));}#chatgpt-mermaid-_r_140n_ [data-look="neo"].node circle .state-start{fill:#000000;}#chatgpt-mermaid-_r_140n_ [data-look="neo"].icon-shape .icon{fill:url(#chatgpt-mermaid-_r_140n_-gradient);filter:drop-shadow( 1px 2px 2px rgba(185,185,185,1));}#chatgpt-mermaid-_r_140n_ [data-look="neo"].icon-shape .icon-neo path{stroke:url(#chatgpt-mermaid-_r_140n_-gradient);filter:drop-shadow( 1px 2px 2px rgba(185,185,185,1));}#chatgpt-mermaid-_r_140n_ .node text{font-size:14px;font-weight:600;letter-spacing:normal;fill:rgb(153, 206, 255);}#chatgpt-mermaid-_r_140n_ .edgeLabels text{font-size:13px;font-weight:600;letter-spacing:-0.08px;fill:rgb(153, 206, 255);}#chatgpt-mermaid-_r_140n_ .node tspan[font-weight="normal"],#chatgpt-mermaid-_r_140n_ .edgeLabels tspan[font-weight="normal"]{font-weight:600;}#chatgpt-mermaid-_r_140n_ .edgeLabel .label rect{opacity:1;rx:13px;ry:13px;fill:rgb(0, 14, 26);stroke:rgb(26, 62, 95);stroke-width:1px;}#chatgpt-mermaid-_r_140n_ .node rect,#chatgpt-mermaid-_r_140n_ .node circle,#chatgpt-mermaid-_r_140n_ .node ellipse,#chatgpt-mermaid-_r_140n_ .node polygon,#chatgpt-mermaid-_r_140n_ .node path{fill:rgb(0, 40, 77);stroke:rgba(255, 255, 255, 0.1);stroke-width:1px;}#chatgpt-mermaid-_r_140n_ .node rect{rx:16px;ry:16px;}#chatgpt-mermaid-_r_140n_ .node.mermaid-decision .label-container{fill:rgb(0, 14, 26);stroke:rgb(26, 62, 95);stroke-dasharray:2,2;}#chatgpt-mermaid-_r_140n_ .edgePaths .flowchart-link{stroke:rgba(255, 255, 255, 0.498);stroke-width:1px;stroke-linecap:round;stroke-linejoin:round;}#chatgpt-mermaid-_r_140n_ .marker{fill:rgba(255, 255, 255, 0.498);stroke:rgba(255, 255, 255, 0.498);}#chatgpt-mermaid-_r_140n_ :root{--mermaid-font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",sans-serif;}Public / Synthetic SourcesRaw DataValidation LayerCRS StandardizationGeometry ValidationAttribute ValidationProcessed Spatial DataVector AnalysisRaster AnalysisEnvironmental IndicatorsPostgreSQL / PostGISArcGIS ProQGISArcGIS OnlineTables / Reports




Implementation Layers
Layer 1 — Data Sources
Public or synthetic datasets.
Layer 2 — Raw Storage
Immutable source datasets.
Layer 3 — Standardization
Schema normalization, identifiers, CRS, geometry validation.
Layer 4 — Spatial Analysis
Vector and raster analysis.
Layer 5 — Analytical Storage
GeoPackage during local prototyping.
PostgreSQL/PostGIS for relational and scalable spatial analysis.
Layer 6 — GIS Clients
ArcGIS Pro and QGIS.
Layer 7 — Automation
ArcPy, PyQGIS, GeoPandas, Shapely, Rasterio, GDAL, PyProj.
Layer 8 — Presentation
ArcGIS Online, maps, tables, figures, and reports.
Architectural Principle
Business logic should be separated from vendor-specific implementation whenever possible.
For example:
Business rule:
Find assets within 5 km of a protected area.

Possible implementations:

ArcGIS Pro
-> Buffer + Spatial Join

ArcPy
-> arcpy.analysis.Buffer + SpatialJoin

QGIS
-> native:buffer + join attributes by location

PostGIS
-> ST_DWithin()

GeoPandas
-> buffer() + sjoin()

The spatial concept is the same even when the implementation changes.
