# 🌿 NDVI Analysis Project Worksheet  

This worksheet will guide you through the process of designing and carrying out an NDVI-based analysis in R. Fill in the prompts for your chosen research question, location, time period, data sources, and methods.  

---Lehiwa W-F and Makaʻala

## 1. Framing the Question  

**What environmental or social issue will you explore?**  
Invasive plant species in Lehua forest, ROD.
CRB hotspots in Hawaiʻi.
Native or non-native vegetation.

---

**Why is NDVI an appropriate tool for this question?**  
NDVI can be used to track the spread of invasive plants over time by monitoring changes in the vegetation index. As ʻōhiʻa trees sicken and die from ROD, their leaf greenness (chlorophyll contnet) decreases, and canopy health declines. This change is detectable by NDVI, which would slow a corresponding decrease in the vegetation. 

---

**Who might find your results meaningful or useful?**  
Department Forestry and Wildlife
Daprtment of Natural Land Resource Management 
State legistration for policy and money efforts
Local communities and non-profit

---

## 2. Choosing a Place and Time  

**What geographic area will you focus on?**  
The Hawaiian Islands.  
Before ROD 2000 - 2008 - Present 2025

---

**What time frame makes sense for your question?**  
Multiple years 

---

**How will you define the scope of your analysis?**  
Focus on using time-series satellite data to track and interpret vegetation health changes, and to distinguish ROD-induced mortality from other environmental factors. Differentiate from other disturbances: isolate the NDVI signature of ROD-related mortality from other causes of vegetation stress, such as drought, fire, deforestation and other invasive species.  

---

## 3. Finding Data  

**Where could you get satellite imagery or NDVI data?**  
(https://dlnr.hawaii.gov/hisc/rapid-ohia-death-rod/)
https://earthexplorer.usgs.gov/
https://search.earthdata.nasa.gov/
NOAA website

---

**What resolution and frequency are appropriate?**  
Remote sensing of Rapid ʻŌhiʻa death (ROD) in Hawaiʻi.
High frequency monitoring.
Identify individual dying trees.
High spatial resolution.
Track diseaseʻs spead over time.
High frequency of data collection.

---

**Will you download data manually or use an R package? Which one?**  
Using R Package. 

---

## 4. Bringing Data into R  

**What R packages can help you work with spatial data?**  
Forest boundries
Plot locations
Spatial raster data (Satelite imagery)
Time series analysis
Visualization
terra, sf, RStoolbix, gglpot2, tidyterra, MODIStsp.

---

**How will you handle projections, boundaries, or missing data?**  
Projections:
Choose an appropriate projected coordinate system for Hawaii, as global systems may distort the area and distances of the islands.
Reproject all data layers, such as satellite imagery (like Landsat) and GIS data (like land boundaries), to a single, consistent coordinate system before analysis. 
Boundries:
Use a polygon of the Hawaiian islands to clip the NDVI raster data. This process removes data from the ocean, ensuring that calculations only include terrestrial vegetation.
For a study focused on a specific part of an island, like a national park or forest reserve, use a feature layer for that specific AOI to extract or clip the NDVI data. This creates a smaller, more manageable dataset.
To compare NDVI values across different management zones or land cover types, use a zonal statistics tool. This approach summarizes NDVI values within defined boundaries like land use districts or ROD-affected areas.
Missing Data:
Using the value from the previous observation (Last Observation Carried Forward, or LOCF) or interpolating between the dates before and after the gap.
Using machine learning algorithms, like a hybrid of multiple imputation and K-nearest neighbors, which has shown good performance in filling missing MODIS NDVI data in Hawaii. 

---

**What file formats will you be working with?**  
GeoTIFF(.tif)
NetCDF(.nc)
Zippedfiles
Jp2
Shape file

---

## 5. Calculating NDVI  

**What is the NDVI formula?**  
NDVI = (NIR - Red)/(NIR + Red)

---

**Which spectral bands are needed?**  
For sentinal near infer red Band 4 and 8.
4 and 5 landsat

---

**How will you apply this formula in R?**  
Install and import data
Visualize using terra and ggplot2

---

## 6. Exploring and Visualizing Data  

**How will you summarize NDVI values?**  
Combination of maps, plots, and tables to show the spatial patterns, termporal trends, and statistical distrubtion of vegetation health. This approach helps track the diseaseʻs progression, pinpoint affected areas, and identify long-term changes in forest health. 
hotspot time series, color gradient for NDVI health. 

---

**Will you compare locations, beofre and after events, look at seasonal patterns, or study long-term trends?**  
Before and after events.

---

**How will you make your visualizations clear and interpretable?**  
Spacial and temporal analysis
time series report

---

## 7. Interpreting Results  

**What patterns or relationships do you expect to see?**  
ROD and NDVI: Expect a negative correlation, ROD leads to lower NDVI values, signlaing the browning and death of native ʻōhiʻa trees.

---

**How do they relate to your research question?**  
*Write your thoughts here:*  

---

**What uncertainties or data limitations should you acknowledge?**  
Cloud cover and atmospheric effects
NDVI sensor and interpretation limitations
Geographic and ecological data limitations

---

## 8. Reflecting on Impact  


**Could your results inform decisions, policies, or further research?**  
Further research by identifying potential hotspots, prioritizing field validation, improving early detection methods, and developing more accurate monitoring tools.  

---

**What new questions emerge from your findings?**  
*Write your thoughts here:*  
