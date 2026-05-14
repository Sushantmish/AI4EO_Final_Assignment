# Application of Supervised and Unsupervised Learning Algorithms for Bushfire Mapping 

### Comparative Analysis of Sentinel-2 Satellite Data to assess the 2019-2020 Bushfires in Kangaroo Island, Australia

This project explores the impact of 2019-2020 Bushfires in Kangaroo Island. Using Supervised (Random Forests) and Unsupervised Learning (K-Means Clustering) Algorithms, it maps how the severly bushfires impacted vegetation across different locations on the Island. It also evaluates the accuracy of both methods, compare results with actual post-fire imagery and calculate the environmental impact of the bushfires as well as the emissions from operating the project. 


---

## Table of Contents
1.  [Introduction](#1-introduction)
2.  [Data Collection](#2-data-collection)
3.  [Methods](#3-methods)
4.  [Notebooks](#4-notebooks)
5.  [Video](#5-video)
6.  [Results](#6-results)
7.  [Environmental Cost](#7-environmental-cost)
8.  [References and Acknowledgements](#8-references-and-acknowledgements)

---

## 1. Introduction

### Context

The 2019-2020 bushfires in Kangaroo Island were amongst the worst wildfires seen in recent history. Nearly half of the island was impacted by these fires which involved the destruction of natural habitats of animals such as koalas, wallabies and kangaroos (Bonney, 2020). 

### Problem Statement

Despite the wide availability of satellite imagery, accurately mapping land cover change post bushfires remains a challenge. A single classification method might lead to inaccurate results as burnt vegetation can be confused with dark water bodies. Therefore, a comparative analysis of different classification methods is essential to validate results. 

### Project Aim

This project aims to assess the performance of Supervised (Random Forest) and Unsupervised (K-Means Clustering) Learning algorithms in mapping and evaluating the impact of bushfires. 

---

## 2. Data Collection

### Data Source: 

1. **Location**: Kangaroo Island, South Australia.
2. **Satellite Imagery**: Sentinel-2 Satellite Imagery accessed through Google Earth Engine
3. **Acquisition Dates**: One-month median of **November-2019** and **February-2020**

#### Note that GEOTIFF files of Pre-fire and Post-fire are extracted by the code in Notebook 1 but are too big to upload on Github,hence a different image has been used below: 

![Pre and Post-Fire Comparison](data/NDVI_Comparison_Figure.png)


### Spectral Bands Used: 

1. **Blue (B2)**, **Green (B3)**, **Red (B4)**: For True Color visualization.
2. **Near-Infrared (B8)**: Essential for vegetation health assessment (NDVI).
3. **Short-Wave Infrared (B12)**: Used for calculating burn ratios (dNBR).

---

## 3. Methods

The project followed 2 different methods (**Supervised (Random Forest)** and **Unsupervised (K-Means Clustering)**) to evaluate the impact of bushfires:

| Supervised Learning (Random Forest) | Unsupervised Learning (K-Means Clustering) |
| :--- | :--- |
| <img src="Figures/AI4EO_figure2.png" width="100%" /> | <img src="Figures/AI4EO_figure1.png" width="100%" /> |
|Supervised Learning uses manual point sampling to train a Random Forest model which is verified by a confusion matrix. |Unsupervised Learning applies K-Means Clustering to automatically segment burned areas after validating pixels.|

**Important**: Check AI4EO_figure1.pdf and AI4EO_figure2.pdf versions of both figures in the Figures folder for better image quality. 

---

## 4. Notebooks

| Notebook Name | Significance |
| :--- | :--- |
| [data_prep.ipynb](Notebooks/data_prep.ipynb) | Handles Google Earth Engine setup and the loading of Sentinel-2 images. |
| [data_analysis.ipynb](Notebooks/data_analysis.ipynb) | Compares Pre-Fire and Post-Fire Imagery: NDVI to quantify vegetation loss and burn severity. |
| [AI_training.ipynb](Notebooks/AI_training.ipynb) | Executes the Machine Learning workflows for both Random Forest (Supervised) and K-Means (Unsupervised) classification. |

---


## 5. Video Explanation 

The video below guides through jupyter notebook code mentioned above:  


---

## 6. Results

<table>
  <tr>
    <th width="10%">Figure Name</th>
    <th width="45%">Visual Output</th>
    <th width="45%">Description</th>
  </tr>
  <tr>
    <td><b>NDVI Change</b></td>
    <td><img src="data/NDVI_Comparison_Figure.png" alt="NDVI Change" width="100%"></td>
    <td><b>Normalized Difference Vegetation Index (NDVI):</b> Maps visualise change in vegetation by comparing Pre-Fire and Post-Fire spectral signatures.</td>
  </tr>
  <tr>
    <td><b>Burn Severity Map</b></td>
    <td><img src="data/Kangaroo_Island_Inferno_Final.png" alt="Burn Severity Map" width="100%"></td>
    <td><b>Burn Severity:</b> Represents the burn intensity derived from the Delta Normalized Burn Ratio (dNBR) to categorize damage levels.</td>
  </tr>
  <tr>
    <td><b>Time Lapse</b></td>
    <td><img src="data/timelapse.gif" alt="Time Lapse" width="100%"></td>
    <td><b>Time Lapse Video:</b> Visualises vegetation change in the study period by comparing Pre-Fire and Burn Severity images.</td>
  </tr>
  <tr>
    <td><b>Random Forest Image</b></td>
    <td><img src="Results/AI_Wildfire_Burn_Map.tif" alt="Random Forest Image" width="100%"></td>
    <td><b>Random Forest Image:</b> Classification map generated by the supervised model, distinguishing burned areas from healthy vegetation.</td>
  </tr>
  <tr>
    <td><b>Confusion Matrix</b></td>
    <td><img src="Figures/ai_confusion_matrix.png" alt="Confusion Matrix" width="100%"></td>
    <td><b>Confusion Matrix:</b> Reflects the accuracy of the Random Forest model by comparing predicted labels against AI training samples.</td>
  </tr>
  <tr>
    <td><b>Feature Importance</b></td>
    <td><img src="Figures/ai_feature_importance.png" alt="Feature Importance" width="100%"></td>
    <td><b>Feature Importance:</b> Ranks spectral bands B4(Red), B3(Green), B2(Blue), B8(NIR) based on their contribution to the model's predictive power.</td>
  </tr>
  <tr>
    <td><b>Final 2x2 Comparison</b></td>
    <td><img src="Figures/Final_2x2_Comparison.png" alt="Final 2x2 Comparison" width="100%"></td>
    <td><b>Final 2x2 Comparison:</b> Summary Figure of Pre-Fire and Post-Fire Satellite Imagery along with Random Forest and K-Means Clustering produced images. </td>
  </tr>
</table>

### Results Summary

Key results from the figures above include: 

1. 

### Limitations
1. **Spectral Confusion**: It is often difficult to distinguish between burnt vegetation and dark water bodies as well as shadows. These similar spectral signatures can cause wrong interpretations, making it important to test different methods. 
2. **Resolution Constraints**: Sentinel-2 has a high resolution of 10m for the B4, B3,B2 and B8 spectral bands used in this study, however, that still might not be enough to detect smaller burnt patches. 
3. **Manual Sampling**: There is a manual sampling bias involved in the training dataset, although it produces highly accurate results.  

---

## 7. Environmental Cost

To ensure this project aligns with sustainable AI practices, the computational carbon footprint was monitored using the **CodeCarbon** library. This allows for transparency regarding the environmental impact of data processing, analysis and AI training as it keeps track of emissions generated throughout the operation of the notebook. 

| Notebook | Energy Consumed (kWh) | CO₂ Emissions (kg) | Water Used (L) |
| :--- | :--- | :--- | :--- |
| **Data Preparation** | 0.000460 | 0.000161 | 0.000000 |
| **Data Analysis** | 0.006126 | 0.001339 | 0.000000 |
| **AI Training** | 0.011039 | 0.003152 | 0.000000 |
| **Total Project Impact** | **0.017625** | **0.004652** | **0.000000** |

**Important**: The total footprint of this analysis (~0.0047 kg CO₂) is equivalent to driving a typical passenger car for approximately 18 meters. Although this emission is negligible, monitoring these metrics is essential for responsible Earth Observation research that implements the use of AI. Some key measures that were taken to keep environmental impact minimal in this project include: 

1. **Efficient Data Collection**: The data preparation notebook extracts particular extents of the Kangaroo Island minimising environmental costs of handling higher bandwidth data. 
2. **Targetted Spatial Masking**: The collected data from Copernicus Data Space ecosystem focused on collecting clean data so irrelevant data points like clouds are not being handled in later stages of processing and training. 
3. **Utilising Significant Spectral Bands**:  The model only uses spectral bands with the most predictive nature, ensuring better and efficient results. 
4. **Efficient Pixel Processing**: The model operates on vectorised processing of pixels instead of pixel by pixel loops which are slow and less sustainable.

---
## 8. References and Acknowledgements

### Acknowledgements

I would like to thank Dr. Michel Tsamados and the course demonstraters for their constant support and guidance throughout the module. 

### References

Bonney, M.T., He, Y. and Myint, S.W., 2020. Contextualizing the 2019–2020 Kangaroo Island Bushfires: Quantifying landscape-level influences on past severity and recovery with Landsat and Google Earth Engine. Remote Sensing, 12(23), p.3942.

European Union (2026) Contains modified Copernicus Sentinel data [2026]. Processed by [AI4EO Final Assignment]. Available at: https://dataspace.copernicus.eu/ (Accessed: 14 May 2026).

Copernicus Data Space Ecosystem (2026) Sentinel-2 - Copernicus Sentinel Missions. Available at: https://dataspace.copernicus.eu/data-collections/copernicus-sentinel-missions/sentinel-2 (Accessed: 14 May 2026).

Google Earth Engine (2026) Earth Engine Data Catalog. Google. Available at: https://earthengine.google.com/ (Accessed: 14 May 2026).

Gorelick, N., Hancher, M., Dixon, M., Ilyushchenko, S., Thau, D. and Moore, R. (2017) 'Google Earth Engine: Planetary-scale geospatial analysis for everyone', Remote Sensing of Environment, 202, pp. 18-27. doi: 10.1016/j.rse.2017.05.010.

Tsamados, M. and Chen, W. (2022) GEOL0069: Artificial Intelligence for Earth Observation – course notebook. University College London. Available at: https://cpomucl.github.io/GEOL0069-AI4EO/intro.html

