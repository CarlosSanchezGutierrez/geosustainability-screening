Validation Rules
Spatial Data Quality Framework
Identity
- asset_id must not be null.
- asset_id must be unique.
- duplicated records must be investigated.
Geometry
- geometry must exist;
- geometry must be valid;
- geometry type must match expected feature type;
- coordinates must fall within plausible bounds;
- empty geometries are not accepted.
Coordinate Reference System
- CRS must be explicitly defined;
- CRS must be documented;
- transformations must be reproducible;
- area and distance calculations must use an appropriate CRS.
Attributes
Required attributes must not be null unless explicitly permitted.
Metadata
Every external source must record:
- publisher;
- version;
- access date;
- license;
- CRS.
Analytical Controls
Every analytical output should document:
- source layer;
- operation;
- parameters;
- units;
- output CRS;
- execution date;
- implementation.
Reconciliation
When the same analysis is implemented in multiple platforms, results should be compared within an explicitly defined tolerance.
