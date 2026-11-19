# Healthcare Access Gap: North Gonja vs Tolon

## Question
North Gonja District has no hospital. How far must residents travel to reach the nearest one, and how many people are affected?

## Methodology

1. **Facility data:** Queried OpenStreetMap via Execute SQL for `amenity=hospital`, 
   clipped to district boundaries. CHPS compounds, pharmacies and private 
   laboratories were excluded. Candidate points were visually verified against 
   satellite imagery; mislabeled features were removed.

2. **Population data:** WorldPop 1km aggregated rasters were clipped to each 
   district boundary using Clip Raster by Mask Layer, then summed with Zonal 
   Statistics to produce total population estimates.

3. **Distance analysis:** Computed straight-line distance from North Gonja to 
   the nearest hospital using QGIS Distance to Nearest Hub, measured in 
   kilometres on an ellipsoidal model.

4. **Mapping:** CartoDB Positron basemap, graduated density symbology, 
   layout assembled in QGIS Print Layout at A4 landscape.

## Findings

- **North Gonja:** 71,185 residents. **Zero** hospitals within the district.
- **Tolon:** 141,018 residents. At least one functioning hospital (Tolon District Hospital).
- **Gap:** Residents of North Gonja must travel **72.72 km** to reach Tolon District Hospital.
- **Inequity:** A district with ~71k people has no local hospital, while its larger neighbor (141k) has one.

## Limitations

- **OSM Coverage:** OpenStreetMap is community-mapped and may under-represent rural health infrastructure in northern Ghana.
- **Population:** WorldPop 1km aggregated rasters are modeled estimates and may differ from Ghana Statistical Service census counts.
- **Distance:** Straight-line distance; actual travel time may be longer due to road network and terrain.

## Data Sources
- Facilities: OpenStreetMap contributors
- Population: WorldPop (worldpop.org)
- Base map: CARTO Positron