# GeoSustainability Screening

> A reproducible geospatial framework for environmental screening of industrial assets, with emphasis on quarry and plant contexts, environmental indicators, spatial data quality, and sustainability decision support.

## Project Status

**Phase:** Planning / Learning / Prototype Design

No production implementation exists yet.

The current repository establishes:

- project architecture;
- analytical scope;
- GIS methodology;
- data governance principles;
- validation rules;
- ArcGIS Pro and QGIS workspaces;
- future Python and PostGIS integration;
- reproducibility standards.

The goal is to build the implementation incrementally while learning GIS through a real industrial sustainability use case.

---

## Motivation

Industrial sustainability analysis frequently requires combining operational information with geographic context.

A plant, quarry, mine, terminal, warehouse, or other industrial asset does not exist independently from its surroundings.

Its geographic location may need to be evaluated against:

- protected areas;
- biodiversity-sensitive areas;
- land-cover classes;
- water bodies;
- watersheds;
- administrative boundaries;
- nearby communities;
- environmental constraints;
- physical-risk layers;
- other spatial indicators.

This project explores how these datasets can be integrated into a reproducible geospatial analytical workflow.

The project is intentionally designed around use cases relevant to global industrial and cement-sector sustainability teams that combine:

**GIS + Data Integration + Data Quality + Environmental Analytics + Reporting + Assurance**

---

## Primary Objective

Design a reproducible geospatial workflow capable of screening industrial assets and producing traceable environmental indicators using both enterprise and open-source GIS technologies.

The same conceptual workflow should eventually be reproducible through:

1. ArcGIS Pro
2. ArcPy
3. ArcGIS Online / ArcGIS API for Python
4. QGIS
5. PyQGIS
6. GeoPandas / Shapely / Rasterio
7. PostgreSQL / PostGIS

The purpose is not to become dependent on a single GIS vendor, but to understand the underlying geospatial concepts and implement them through multiple technology stacks.

---

## Core Business Questions

The project is being designed to eventually answer questions such as:

### Asset Screening

- Which industrial assets are located near protected areas?
- Which assets intersect environmentally sensitive areas?
- What is the nearest protected area to each site?
- Which assets require additional environmental review?

### Land Cover

- What percentage of land within a defined radius is forest?
- What percentage is urban, agricultural, water, grassland, or other land-cover classes?
- How does land cover differ between sites?
- How does land cover change over time?

### Water and Hydrology

- How close is each site to relevant water bodies?
- Which assets are located within selected watersheds?
- Which assets may warrant additional water-related analysis?

### Biodiversity

- Which sites are located closest to biodiversity-sensitive areas?
- Which sites combine multiple environmental exposure indicators?
- How could spatial indicators support biodiversity action planning?

### Data Quality

- Are asset coordinates valid?
- Are geometries valid?
- Are coordinate reference systems correctly defined?
- Are there duplicated assets?
- Are required attributes missing?
- Can every calculated indicator be traced to its source and methodology?

---

## Planned Analytical Workflow

```text
Public / Synthetic Data
        |
        v
Raw Spatial Sources
        |
        v
Schema + Metadata Validation
        |
        v
CRS Validation / Transformation
        |
        v
Geometry Quality Controls
        |
        v
Standardized Spatial Layers
        |
        +----------------------+
        |                      |
        v                      v
Vector Analysis           Raster Analysis
        |                      |
        |                      |
Buffers / Intersects      Land Cover
Spatial Joins             Zonal Statistics
Distances                 Environmental Layers
        |                      |
        +----------+-----------+
                   |
                   v
          Environmental Indicators
                   |
                   v
             Screening Table
                   |
          +--------+---------+
          |                  |
          v                  v
      ArcGIS Pro           QGIS
          |                  |
          v                  v
   ArcGIS Online        Open Outputs
          |
          v
 Dashboards / Web Maps

Technology Strategy
LayerEnterprise / EsriOpen Source
Desktop GISArcGIS ProQGIS
AutomationArcPyPyQGIS
Python analyticsArcPyGeoPandas / Shapely
Raster processingSpatial Analyst / Image AnalystRasterio / GDAL
CRSArcGIS coordinate systemsPyProj / PROJ
Geometry engineArcGIS geometry engineGEOS / Shapely
Local spatial storageFile GeodatabaseGeoPackage
Enterprise spatial DBEnterprise GeodatabasePostgreSQL / PostGIS
Web GISArcGIS OnlineTBD
Web automationArcGIS API for PythonREST / open-source tooling


Repository Structure
geosustainability-screening/
|
|-- arcgis/
|   |-- projects/
|   `-- layers/
|
|-- qgis/
|   |-- projects/
|   `-- styles/
|
|-- data/
|   |-- raw/
|   |-- external/
|   |-- interim/
|   `-- processed/
|
|-- docs/
|   |-- project-charter.md
|   |-- architecture.md
|   |-- methodology.md
|   |-- data-sources.md
|   |-- data-dictionary.md
|   |-- validation-rules.md
|   |-- decisions.md
|   |-- glossary.md
|   |-- learning-log.md
|   `-- roadmap.md
|
|-- src/
|   |-- arcpy/
|   |-- arcgis_api/
|   |-- pyqgis/
|   `-- open_source/
|
|-- sql/
|-- config/
|-- notebooks/
|-- tests/
|
|-- outputs/
|   |-- maps/
|   |-- tables/
|   `-- figures/
|
|-- .gitignore
|-- .gitattributes
|-- LICENSE
`-- README.md

GIS Design Principles
1. Reproducibility
Spatial results should be reproducible from documented source data, parameters, CRS decisions, and transformations.
2. Traceability
Every derived environmental indicator should be traceable to:
Source
  -> Version
  -> Transformation
  -> Spatial Operation
  -> Parameter
  -> Output

3. Data Quality Before Visualization
Maps are outputs, not substitutes for data validation.
Spatial data quality must be evaluated before analytical results are interpreted.
4. CRS Is an Analytical Decision
Coordinate reference systems should not be chosen only because they are convenient.
Distance and area calculations must use an appropriate projected CRS.
5. Vendor-Aware, Vendor-Neutral Design
The project intentionally uses both ArcGIS and open-source GIS tools.
The analytical methodology should remain understandable independently of the implementation platform.
6. Automation After Understanding
Each major workflow should first be understood conceptually and visually before being automated.
The long-term objective is code-first reproducibility.
Planned Deliverables
The project is expected to progressively produce:
- industrial asset spatial dataset;
- protected-area proximity indicators;
- environmental buffers;
- spatial-intersection results;
- land-cover summaries;
- hydrology proximity metrics;
- environmental screening table;
- GIS data-quality report;
- ArcGIS Pro project;
- QGIS project;
- ArcGIS Online web map;
- reproducible Python workflows;
- PostGIS implementation;
- methodology documentation;
- final technical report.
Current Learning Context
Current Esri learning activities include:
- GIS Basics — completed
- ArcGIS Online Basics — completed
- ArcGIS Pro Basics — completed
- Getting Started with Data Management — completed
- Getting Started with Mapping and Visualization — completed
- Getting Started with Spatial Analysis — completed
- GIS Fundamentals Learning Plan — in progress
- Spatial Data Science: The New Frontier in Analytics — in progress
The repository is intended to convert theoretical GIS learning into an applied and documented engineering project.
Data Policy
This repository must not contain proprietary, confidential, employer-owned, or restricted information.
Only the following should be used:
- open public datasets;
- properly licensed datasets;
- synthetic data;
- manually generated demonstration data.
Raw datasets are intentionally excluded from Git by default.
Every external dataset should eventually document:
- source;
- publisher;
- download date;
- dataset version;
- license;
- CRS;
- geographic coverage;
- limitations.
Disclaimer
This is an independent educational and portfolio project.
It is not an official CEMEX project and is not affiliated with, sponsored by, or endorsed by CEMEX or Esri.
Any industrial examples are conceptual, synthetic, or based on publicly available information.
Author
Carlos Sánchez Gutiérrez
B.S. Computer Science and Technology
Tecnológico de Monterrey
