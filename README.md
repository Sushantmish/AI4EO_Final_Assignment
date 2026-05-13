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
|Supervised Learning uses manual point sampling to train a Random Forest model which is verified by a confusion matrix |Unsupervised Learning applies K-Means Clustering to automatically segment burned areas after validating pixels|


**Important**: Check AI4EO_figure1.pdf and AI4EO_figure2.pdf versions of both figures in the Figures folder for better image quality. 

---
## 8. References and Acknowledgements

### Acknowledgements

I would like to thank Dr. Michel Tsamados and the course demonstraters for their constant support and guidance throughout the module. 

### References

Bonney, M.T., He, Y. and Myint, S.W., 2020. Contextualizing the 2019–2020 Kangaroo Island Bushfires: Quantifying landscape-level influences on past severity and recovery with Landsat and Google Earth Engine. Remote Sensing, 12(23), p.3942.

Tsamados, M. and Chen, W. (2022) GEOL0069: Artificial Intelligence for Earth Observation – course notebook. University College London. Available at: https://cpomucl.github.io/GEOL0069-AI4EO/intro.html

