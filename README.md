# 🌿 Urban Farming Potential in Detroit

This repository presents a spatial analysis project titled **“Urban Farming Potential in Detroit”**, carried out as part of a GIS capstone track. The study identifies the most suitable zones for urban farming in Detroit using spatial data and geoprocessing tools in QGIS.

Objective
To determine the **zones most favorable for urban farming** in Detroit by analyzing vacant land parcels and soil quality through spatial overlay analysis.

Data Sources
- **Detroit shapefile**
- **Vacant land parcels:** [data.detroitmi.gov](https://data.detroitmi.gov/)
- **Soil data:** [USDA Web Soil Survey](https://websoilsurvey.sc.egov.usda.gov/App/WebSoilSurvey.aspx)

Tools & Techniques
Performed using **QGIS** with the following geoprocessing tools:
- **Buffer:** To define influence zones around vacant parcels (100 m radius)  
- **Intersection:** To combine buffered parcels with soil data  
- **Difference:** To extract “Good” soil zones suitable for farming  

Workflow
1. Download and load **Vacant Parcel** and **Soil** datasets into QGIS.  
2. Apply a **100 m buffer** around vacant parcels.  
3. Perform **intersection** between buffered parcels and soil data.  
4. Categorize soil based on suitability: **Good, Moderate, Poor.**  
5. Extract only “Good” soil zones using the **Difference** tool.  
6. Identify and map **vacant plots within suitable soil zones**.  

Results
| Soil Class | Area (Ha) |
|-------------|-----------|
| Good | 389.985 |
| Moderate | 58.505 |
| Poor | 13,360.458 |

- Only a **small fraction of land** is suitable for urban farming.  
- Approximately **700 vacant plots** (each >250 m²) were identified as **best suited** for urban farming initiatives.

Key Insights
- Soil quality is a limiting factor for large-scale urban farming.  
- The selected “Good” zones can support **community-based agricultural projects**.  
- Findings can help in **urban renewal and green city planning** in Detroit.  

Tools Used
- QGIS (Buffer, Intersection, Difference)
- Spatial Data from Detroit Open Data Portal & USDA Soil Survey



---

### 📝 Summary
A GIS-based assessment of Detroit’s vacant parcels revealed around 700 plots suitable for urban farming, primarily determined by soil quality and spatial proximity. The project highlights how spatial analysis supports sustainable land use and urban food security initiatives.
