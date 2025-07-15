# Impacts of the 2024 Floods in Rio Grande do Sul, Brazil

This document focuses on assessing the spatial extent and environmental impacts of the catastrophic 2024 floods in Rio Grande do Sul, Brazil.

## Purpose

The primary objective of this project was to apply remote sensing techniques to:
* Assess the spatial extent and environmental impacts of the severe floods in Rio Grande do Sul between late April and mid-May 2024.
* Generate a detailed Land Cover Land Use (LCLU) map distinguishing water bodies, urban zones, vegetation and bare soil *before* and *after* the flood event.
* Demonstrate the effectiveness of satellite remote sensing as a cost-effective and timely tool for disaster monitoring.
* Provide critical insights to aid emergency response, recovery planning, and future risk mitigation efforts.

## Study Area

The project's study area is the state of **Rio Grande do Sul** in southern Brazil, which experienced severe and widespread flooding, affecting nearly 90% of its territory and approximately 2.3 million residents. The analysis includes the most impacted municipalities (e.g., Canoas, Eldorado do Sul) and their surrounding regions to capture the broader hydrological and environmental context.

## Technical Specifications

* **Minimum Mapping Unit (MMU):** 1 pixel (approximately 10 meters), based on Sentinel-2 data.
* **Map Classes:** Water, Urban, Vegetation, Bare Soil, Crops.
* **Satellite Imagery:** Multispectral Sentinel-2 Level-2A images.
* **Sentinel-2 Spatial Resolution:** 10m (some bands), 20m (others).

## Methodology

A systematic approach was followed for image acquisition, analysis, classification and accuracy assessment, primarily using ArcGIS Pro.

### 1. Image Acquisition
* **Satellite Mission:** Sentinel-2 (Copernicus Programme) L2A images.
* **Dates:** April 21st, 2024 (pre-flood) and May 6th, 2024 (post-flood).
* **Bands Used:** Visible (Blue, Green, Red), Near-Infrared (NIR), Short-Wave Infrared (SWIR 2).

### 2. Exploratory Analysis
* **Visual Inspection:** Initial visual inspection of individual spectral bands and true/false color composites (RGBN) to understand spatial extent and landscape changes.
* **Band Transformations:**
    * **Normalised Difference Water Index (NDWI):** Highly effective in distinguishing water bodies from land surfaces, crucial for flood mapping.
    * **Normalised Difference Vegetation Index (NDVI):** Indicates vegetation vigor and stress, detecting flood impacts on plant cover.

### 3. Information Extraction & Classification
* **Feature Selection:** Selected most relevant bands (Blue, Green, Red, NIR, SWIR 2, NDVI, NDWI) for classification.
* **Classification Methods:**
    * **Unsupervised Classification (ISO Cluster Classifier):** Grouped pixels into spectrally similar clusters (5 main land cover categories: Crops, Water, Vegetation, Bare Soil, Urban areas) without prior training.
    * **Supervised Classification (Maximum Likelihood Classifier - MLC):** Assigned pixels to classes based on statistical distributions derived from manually selected training samples (training areas selected from Blue, Green, Red, NIR, SWIR 2, NDVI, NDWI bands).

### 4. Post-classification Processing
* Minimal post-processing (filtering and smoothing) was applied to preserve essential spatial details, especially in urban areas, balancing noise reduction with feature preservation.

### 5. Thematic Accuracy Assessment
* **Reference Data:** A simple random sample of 100 points was manually gathered for each classification product and assigned to predefined land cover classes based on visual interpretation of high-resolution imagery.
* **Metrics:** Confusion matrices were created to compute Overall Accuracy (OA), Producer's Accuracy (PA), and User's Accuracy (UA) for both ISO and MLC.
* **Model Selection:** Supervised Classification (MLC) was chosen as the final land cover map due to its consistently superior overall accuracy (initial 85%, refined 76%) compared to ISO (initial 71%, refined 63%).

### 6. Map Comparison
* Compared pre- and post-flood maps to quantify changes using the Tabulate Area tool in ArcGIS Pro.
* Identified total flooded area (~540.07 km²) and land cover transitions (e.g., vegetation shifting to flooded areas).

## Limitations

* **Spatial Resolution:** 10-meter resolution of Sentinel-2 images may miss small-scale flood details.
* **Atmospheric Effects/Sensor Noise:** Residual effects could affect accuracy.
* **Minimal Smoothing:** Preserved features but left some noise in results.
* **Absence of Ground-Truth Data:** Accuracy assessment relied on visual interpretation, introducing uncertainty.

## Conclusion

Sentinel-2 imagery and GIS methods were effectively utilized to map the 2024 floods in Rio Grande do Sul, providing reliable results through supervised classification. The use of NDWI and NDVI indices significantly enhanced flood detection and vegetation analysis. These findings underscore the value of satellite remote sensing for timely flood monitoring and its support for future disaster management and planning.

## References

* America. Rio Grande do Sul (Brazil): State, Major Cities & Towns Population Statistics, Maps, Charts, Weather and Web Information.
* Copernicus: Sentinel-2. eoPortal.
* How iso cluster works. How Iso Cluster works-ArcGIS Pro Documentation.
* Sentinel-2. Documentation.
