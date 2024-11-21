# Healthcare Accessibility Analysis
Analyzed healthcare accessibility in Toronto using spatial analysis to identify optimal locations for new facilities and improve emergency response. Applied clustering, kernel density estimation (KDE), and Inverse Distance Weighting (IDW) to locate underserved areas. 

## Executive Summary

Healthcare accessibility is vital in a city like Toronto, where disparities in access to services can significantly affect health outcomes, particularly for vulnerable groups such as the elderly and low-income residents. This project aims to propose new locations for healthcare facilities and identify the shortest routes to existing facilities. Advanced spatial interpolation methods like Kriging and Inverse Distance Weighting (IDW) were used to identify underserved areas, with a focus on the northern and eastern parts of the city. This analysis offers insights that can aid city planners in improving healthcare accessibility and equity.

---

## Objectives
- **Identify Vulnerable Populations**: Analyze demographic data to locate areas with high concentrations of elderly and low-income residents.
- **Determine Optimal Locations for New Healthcare Facilities**: Use geospatial analysis to find underserved areas in Toronto.
- **Optimize Emergency Response Times**: Analyze road network data to determine the shortest routes to healthcare facilities.

---

## 1. Introduction

### 1.1 Background
Toronto, with a population of over 2.9 million, is home to diverse populations. Access to healthcare services varies, with certain neighborhoods facing significant challenges, especially among the elderly, immigrants, and low-income families. This project aims to address these disparities using data-driven approaches to propose new healthcare facilities where they are most needed.

### 1.2 Literature Review
Studies show that low-income and elderly populations face substantial barriers in accessing healthcare. Advanced geospatial tools, such as those applied in this project, are essential in identifying and addressing these inequalities.

### 1.3 Motivation
While prior research has identified underserved neighborhoods, the use of advanced mapping techniques like Kernel Density Estimation (KDE) and Multi-Criteria Decision Analysis (MCDA) provides a more detailed understanding of healthcare access in Toronto.

---

## 2. Data Sources

### 2.1 Healthcare Locations Data
Sourced from the Ministry of Health Service Provider Locations database (2024), this dataset includes geographic information on various healthcare facilities in Toronto.

### 2.2 Census Data
Demographic data was obtained from the City of Toronto’s Ward Profiles (2021), focusing on population distribution and income levels to identify vulnerable populations.

#### 2.2.1 Population Distribution
The population data shows higher densities in central Toronto, with lower densities in suburban areas.

#### 2.2.2 Income Distribution
Income disparities are evident across Toronto, with lower-income areas concentrated in the northern and central parts of the city.

### 2.3 Road Networks Data
Road network and traffic volume data were sourced from the City of Toronto’s open data portal. This dataset was essential for analyzing emergency response times.

---

## 3. Data Preprocessing

### 3.1 Healthcare Data Preprocessing
Non-essential healthcare services were excluded, and the dataset was transformed to the WGS 84 CRS for compatibility with other data sources.

### 3.2 Population and Income Data Preprocessing
Population and income data were aggregated and normalized. Missing values were handled to ensure clean and usable data.

### 3.3 Road Networks Data Preprocessing
The road network dataset was filtered to include only major roads, and distances between healthcare facilities and intersections were calculated.

---

## 4. Exploratory Data Analysis (EDA)

### 4.1 Income Analysis (KDE)
The KDE analysis identified regions with high concentrations of low-income households, particularly in the central and western parts of the city.

### 4.2 Elder Population Analysis (KDE)
KDE was used to visualize the density of elderly populations, highlighting central and southern areas with higher concentrations of elderly residents.

---

## 5. Methodology

### 5.1 Define Catchment Area and Calculate Supply-to-Demand Ratio
A 5-kilometer catchment area was created around each healthcare facility, and the supply-to-demand ratio was calculated based on the number of facilities and population within each catchment.

### 5.2 Calculate Accessibility Score
An accessibility score was calculated for each Census Tract, representing the ease of access to healthcare facilities across Toronto.

### 5.3 Identify Underserved Areas
Underserved areas were identified using accessibility scores below 0.2. New potential locations for healthcare facilities were generated.

### 5.4 Centroid as Potential Locations in Each Census Tract
Centroids of Census Tracts within 5 kilometers of the Toronto border were considered as potential locations for new healthcare facilities.

### 5.5 Calculate Distance to Nearest Existing Hospital
Dijkstra’s Algorithm was applied to calculate the shortest travel distance from potential new facility locations to existing hospitals.

### 5.6 Calculate Necessity Score Using MCDA
The MCDA approach was used to rank potential new locations based on factors such as distance to the nearest hospital, elderly population, income level, and accessibility score.

### 5.7 Apply Universal Kriging
Kriging was used to predict necessity scores for random points in underserved areas, providing a geostatistical approach to identifying key gaps in healthcare access.

### 5.8 Apply IDW
IDW was used as an alternative method, focusing on proximity to existing facilities to estimate accessibility scores.

---

## 6. Key Findings

### 6.1 Kriging Analysis
Kriging identified critical underserved areas in the northern and eastern parts of Toronto, particularly benefitting low-income and elderly populations.

### 6.2 IDW Analysis
IDW provided similar results but with a stronger focus on areas closer to existing healthcare facilities.

### 6.3 Comparison and Difference Analysis
A comparison between Kriging and IDW showed that Kriging better addressed the needs of more isolated populations, while IDW emphasized proximity to current facilities.

### 6.4 Shortest Route Point Analysis
Shortest route analysis confirmed that the new proposed healthcare locations were both strategically placed and accessible.

---

## 7. Limitations

### 7.1 Edge Location Considerations
The analysis did not account for healthcare facilities outside Toronto’s borders, potentially misrepresenting accessibility for border regions.

### 7.2 Generalizability
While the methods are broadly applicable, the findings are specific to Toronto’s urban landscape and may not be directly transferable to other cities.

### 7.3 Data Limitations
The accuracy of the results depends on the quality of census, healthcare, and road network data, and the assumption that all healthcare facilities provide equivalent services.

---

## 8. Future Scope

### 8.1 Real-Time Traffic Data Integration
Incorporating real-time traffic data could improve the accuracy of shortest route calculations.

### 8.2 Commercial Space Availability
Future research could analyze the availability of commercial properties for building new healthcare facilities.

### 8.3 Disability Population-Specific Analysis
Future studies could focus on healthcare accessibility for people with disabilities.

### 8.4 Incorporating Facility Capacity (Available Beds)
Considering the capacity of existing healthcare facilities could provide a more nuanced analysis of healthcare accessibility.

---

## 9. Conclusion

This project identified optimal locations for new healthcare facilities in Toronto, focusing on improving access for vulnerable populations. The Kriging and IDW methods, combined with shortest route analysis, provide actionable insights for improving healthcare accessibility in underserved areas.

---

## References

### Data sources
1. Ministry of Health Ontario (2024) Ministry of Health Service Provider Locations. GeoHub Ontario, 2024. [Link](https://geohub.lio.gov.on.ca/datasets/ministry-of-health-service-providerlocations/explore)
2. City of Toronto. Traffic Volumes at Intersections for All Modes. [Link](https://open.toronto.ca/dataset/traffic-volumes-at-intersections-for-all-modes)
3. City of Toronto. (2024). Ward Profiles 25 Ward Model. [Link](https://open.toronto.ca/dataset/ward-profiles-25-ward-model)

### Additional References
1. Shah, T. I., Bell, S., & Wilson, K. (2016). Spatial accessibility to healthcare services in Canadian urban areas. *PLoS ONE*, 11(12), e0168208. [Link](https://doi.org/10.1371/journal.pone.0168208)
2. Luo, W., & Wang, F. (2019). Understanding inequalities in healthcare access among vulnerable populations. *PLoS ONE*, 14(1), e0210113. [Link](https://doi.org/10.1371/journal.pone.0210113)
3. Laverty, M., & Dixon, J. (2021). Geographical disparities in access to hospital care in Ontario. *BMJ Open*, 11(1), e041474. [Link](https://doi.org/10.1136/bmjopen-2020-041474)
4. Ahmad, J., Nazir, M., & Shafiq, M. U. (2022). Enhanced two-step floating catchment area method for measuring spatial accessibility. *Recent Developments in Spatial Analysis and Decision Making*. [Link](https://doi.org/10.1007/978-3-031-06443-2_14)
5. Sun, M., Chao, G., Xue, C., & Li, C. (2021). A data-driven method for measuring accessibility to healthcare. *IEEE Access*, 9, 64972-64982. [Link](https://doi.org/10.1109/ACCESS.2021.3075494)

