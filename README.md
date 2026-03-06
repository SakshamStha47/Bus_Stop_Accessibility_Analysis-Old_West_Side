# Bus Stop Accessibility Analysis: Old West Side, Ann Arbor
An urban planning data science project exploring transit equity and pedestrian accessibility using OpenStreetMap (OSM) and Python.

---

## Project Overview
This project evaluates the "walkability" of public transit in the **Old West Side (OWS)** neighborhood of Ann Arbor, Michigan. Using a **400-meter buffer analysis** (the industry standard for a 5-minute walk), I mapped the service area of all existing bus stops to identify potential "transit deserts" or blind spots.

<p align="center">
   <img src="./snapshots/OWS location.png" height="400" title="Bus Stop Accessibility Map">
   <img src="./snapshots/OWS bus stops.png" height="400" title="Bus Stop Accessibility Map">
   <img src="./snapshots/OWS buffer zones.png" height="400" title="Bus Stop Accessibility Map">
   <img src="./snapshots/OWS blind spots.png" height="400" title="Bus Stop Accessibility Map">
</p>


## Tech Stack
* **Language:** Python 3
* **Data Source:** OpenStreetMap (via `OSMnx`)
* **Spatial Analysis:** `GeoPandas`, `Shapely`, `PyProj`
* **Visualization:** `Matplotlib`

## Methodology
1. **Data Acquisition:** Pulled the official administrative boundaries for Ann Arbor and filtered for the historic Old West Side neighborhood.
2. **Feature Extraction:** Queried OSM for all `highway=bus_stop` nodes and the local street network.
3. **Coordinate Transformation:** Reprojected WGS84 (Lat/Long) data into **EPSG:2252** (Michigan South State Plane) to ensure distance calculations were accurate in meters.
4. **Buffer Generation:** Created 400m circular buffers around each stop and used a `unary_union` (Dissolve) to calculate the total aggregate service area.
5. **Validation:** Performed distance-checks between adjacent stops to verify scale and projection accuracy.

## Key Findings
* **Total Coverage:** The Old West Side exhibits exceptionally high transit density. Nearly **100%** of the residential area falls within a 5-minute walk of a stop.
* **No Significant Blind Spots:** Unlike more suburban layouts, the historic grid of OWS allows for a highly efficient distribution of transit access.

## How to Run
1. Clone the repo:
   ```bash
   git clone [https://github.com/SakshamStha47/Bus_Stop_Accessibility_Analysis-Old_West_Side.git](https://github.com/SakshamStha47/Bus_Stop_Accessibility_Analysis-Old_West_Side.git)
