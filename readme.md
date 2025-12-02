# USDA Plant Hardiness Zones  
**Climate Change and Impacts on Agriculture in the Kentucky-West Virginia-Ohio Region**

---

## Table of Contents
- [Motivation](#motivation)
- [Key Questions](#key-questions)
- [Data Acquisition & Normalization](#data-acquisition--normalization)
- [Problems & Challenges](#problems--challenges)
- [Technologies Used](#technologies-used)
- [Data Sources](#data-sources)

---

## Motivation

Climate-related changes have become more noticeable in the tri-state region, especially in **West Virginia**, where I live. I grew up here, and today my husband and I are watching his small-scale vegetable garden evolve toward a local farm business. Seeing how changing weather patterns affect even a small garden made this project personal.

The USDA Growing Zone update from 2012 to 2023 revealed significant shifts — and I wanted to understand the *why* behind it.

---

## Key Questions

This project focuses on the following core questions:

1. How have temperatures, rainfall, and extreme events changed over the past several decades in the tri-state area?  
2. How do these shifts relate to USDA Growing Zone changes between 2012 and 2023?  
3. Are corn and soybean yields or condition ratings showing signs of climate-driven stress or adaptation? 
4. Has drought frequency or duration changed over time? 
5. What do projections suggest for future minimum temperatures through 2050?

---

## Data Acquisition & Normalization

All datasets — including NOAA weather records, USDA crop statistics, USDA zone shapefiles, drought monitor logs, and county geography — were collected from publicly available sources. After acquisition, the data went through extensive cleaning to ensure consistency across formats. This included standardizing identifiers (FIPS codes, station IDs, county names), converting raw climate data into annual and 5-year aggregates, merging shapefiles with tabular datasets, and restructuring drought start/end records into weekly entries. Crop yield and condition data were grouped into decades or annual summaries to align with climate trends. The end result was a fully integrated dataset that allowed for long-term regional comparisons and visualizations.

---

## Problems & Challenges

Working across multiple sources created several obstacles:

### **1. Identifier Mismatches**
NOAA stations, USDA records, and county shapefiles each used different ID systems (FIPS, station IDs, abbreviations), requiring extensive standardization.

### **2. Reconstructing Drought Time Series**
The Drought Monitor records only start and end dates — not individual weekly entries.  
I had to expand ranges into weekly rows, which required careful iteration and validation.

### **3. Geospatial Integration**
Shapefiles used different projections and often had missing or outdated FIPS codes, requiring manual correction.

### **4. Missing or Incomplete Data**
Some weather stations had large gaps.  
Crop condition data had partial early-year records.  
These required smoothing, interpolation, or exclusion.

### **5. Folium & Mapping**
Creating interactive zone-shift maps required converting shapefiles to GeoJSON, then merging climate and zone-change attributes.

Despite these issues, the final dataset is fully cleaned, validated, and capable of supporting long-term climate and agricultural analysis.

---

## Technologies Used

**Python / Pandas** – for data exploration, cleaning, aggregation, and analysis  
**Excel** - for additional data cleaning and organizing  
**PowerPoint** – for presenting findings and communicating results  
**Git / GitHub** – for version control and project organization   

## Data Sources

### **Climate & Weather**
- NOAA National Centers for Environmental Information  
  https://www.ncei.noaa.gov/

### **Drought**
- U.S. Drought Monitor  
  https://droughtmonitor.unl.edu/

### **Crop Data**
- USDA National Agricultural Statistics Service  
  https://www.nass.usda.gov/

### **USDA Growing Zones**
- USDA Plant Hardiness Zone Maps  
  https://planthardiness.ars.usda.gov/

### **Geographic / Shapefiles**
- U.S. Census Bureau TIGER/Line Shapefiles  
  https://www.census.gov/geographies/mapping-files/time-series/geo/tiger-line-file.html  

---

