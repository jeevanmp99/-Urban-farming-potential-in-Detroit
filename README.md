# Urban Farming Potential in Detroit

A spatial analysis project evaluating land suitability for urban agriculture across the City of Detroit, Michigan. This study cross-references municipal vacant land parcels with USDA soil quality ratings to delineate viable sites for community-driven agricultural interventions.

---

## 📌 Project Overview

Urban agriculture offers substantial opportunities for vacant land revitalization, local food sovereignty, and urban greening. However, urban soils are frequently degraded, compacted, or unsuitable for cultivation. This study applies vector geoprocessing workflows in **QGIS** to identify vacant parcels that coincide with high-quality, cultivable soil profiles across Detroit.

---

## 🗺️ Spatial Distribution & Results

### Soil Suitability Classification
The spatial overlay of Detroit's land area classified under the USDA soil survey yields a stark disparity in agricultural viability:

| Soil Class | Area (Hectares) | Percentage of Analyzed Area |
| :--- | :--- | :--- |
| **Good** | **389.985 ha** | **2.83%** |
| **Moderate** | 58.505 ha | 0.42% |
| **Poor** | 13,360.458 ha | 96.75% |
| **Total** | **13,808.948 ha** | **100.00%** |

![Urban Farming Potential in Detroit](assets/Urban%20Farming%20Potential%20in%20Detroit.jpeg)

### Key Findings
* **Severe Soil Constraints:** Less than **3% (389.99 ha)** of the evaluated urban area possesses soil ratings categorized as "Good" for farming operations. The overwhelming majority falls under "Poor" (frequently urban land complexes, heavily disturbed, compacted, or made land).
* **Targeted Opportunities:** Filtering for parcels located within the "Good" soil zones yielding an area greater than **250 m²** isolated approximately **700 high-potential vacant plots**.

![Suitable Vacant Parcels](assets/Suitable%20Vacant%20Parcels.jpeg)

---

## 🔍 Site-Level Verification

High-resolution orthophoto inspection confirms that the identified clusters are concentrated along low-density residential blocks in northwest Detroit (e.g., Brightmoor and Eliza Howell park areas), where large contiguous swathes of vacant parcels sit on viable soil:

| Site Cluster: Westbrook St / Outer Dr W | Site Cluster: Chalfonte Ave / Beaverland St |
| :---: | :---: |
| <img src="assets/Vacant%20plots1.png" alt="Vacant Plots Cluster 1" width="100%"> | <img src="assets/Vacant%20plots2.png" alt="Vacant Plots Cluster 2" width="100%"> |
| *Contiguous vacant parcels along Westbrook St adjacent to green space.* | *Clusters near Gwen's Edible Playscape and Eliza Howell Trailhead.* |
---

## 🛠️ Data Sources & Geoprocessing Workflow

### Datasets
* **Vacant Land Parcels:** [City of Detroit Open Data Portal](https://data.detroitmi.gov/) (Filtered by Property Class: `Residential Vacant`, `Commercial Vacant`).
* **Soil Survey Data:** [USDA NRCS Web Soil Survey](https://websoilsurvey.sc.egov.usda.gov/App/WebSoilSurvey.aspx) (SSURGO database for Wayne County, MI).
* **Administrative Boundary:** City of Detroit municipal boundary shapefile.

### Methodology in QGIS
1. **Data Preprocessing:** Reprojected parcel and soil vectors to a common projected coordinate reference system (`EPSG:32617 - WGS 84 / UTM Zone 17N` / `EPSG:3857`).
2. **Buffer Analysis:** Applied a **100 m buffer** around vacant parcels to capture immediate neighborhood soil influence zones.
3. **Overlay (Intersection):** Intersected parcel buffer geometries with USDA soil polygons to attach attributes (`soil_class`).
4. **Classification:** Categorized soil units into three ordinal tiers: `Good`, `Moderate`, and `Poor`.
5. **Spatial Extraction:** Isolated vacant parcels falling directly within `Good` soil boundaries using spatial selection/overlay operators.
6. **Dimensional Thresholding:** Filtered parcels using field calculator queries to isolate plots with $\text{Area} > 250\text{ m}^2$ suitable for urban agriculture and community gardens.

---

## 📂 Repository Structure

```text
├── assets/
│   ├── Urban Farming Potential.jpeg in Detroit
│   ├── Suitable Vacant Parcels.jpeg
│   ├── Vacant plots1.png
│   └── Vacant plots2.png
├── data/
│   └── README.md                  # Instructions to download source layers
└── README.md
