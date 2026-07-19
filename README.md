# # Land Cover Classification, Gilgit District, Pakistan
Assessing the Efficacy of Pixel-based and Object-based Classification Techniques and Classifiers for Land Cover Mapping Using Landsat-8 and Sentinel-2 Data in Complex Mountainous Terrain


> Pixel-based vs. Object-based Image Analysis (OBIA) using Random Forest, SVM, and k-NN on Landsat-8 and Sentinel-2 imagery in Google Earth Engine.
> **Published:** IJIST, vol. 7(9), pp. 42–56, July 2025


## Overview

This study compares two classification frameworks — pixel-based classification and Object-Based Image Analysis (OBIA) — using three machine learning classifiers (RF, SVM, k-NN) on two multispectral datasets (Landsat-8 OLI and Sentinel-2 MSI) for LULC mapping of Gilgit District, a complex mountainous terrain in Gilgit-Baltistan, Pakistan.

OBIA was performed in **eCognition Developer** using multiresolution segmentation. Pixel-based classification was implemented in **Google Earth Engine (GEE)** using the JavaScript API.

---

## Study Area

**Gilgit District**, Gilgit-Baltistan, Pakistan  
Coordinates: 35.8819° N, 74.4643° E  
Area: ~408,100 hectares  
Terrain: Complex mountainous — Karakoram Range

---

## Datasets Used

| Sensor | Product | Bands Used | Resolution | Date of Acquisition |
|---|---|---|---|---|
| Landsat-8 OLI | USGS L2 C2 T1 SR | B2, B3, B4, B5, B6, B7 | 30m | 12 & 21 September 2024 |
| Sentinel-2 MSI | L2A Surface Reflectance | B2, B3, B4, B8, B11, B12 | 10m / 20m | 21 September 2024 |

September was chosen to avoid monsoon cloud cover and fresh snow effects on classification.

---

## Land Cover Classes (7 Classes)

| Class | Description |
|---|---|
| Rock / Soil | Exposed bare land and bare mountains |
| Grass / Shrub | Grasses, forbs, shrubs |
| Forest | Dense and mixed tree cover |
| Cropland | Arable and horticultural land |
| Built-up Area | Urban and rural settlements |
| Snow / Glacier | Clean ice and debris cover |
| Water | Rivers, lakes, shallow water bodies |

---

## Methodology

### Pixel-based Classification (GEE)
- Platform: Google Earth Engine (JavaScript API)
- Classifiers: Random Forest (100 trees), SVM (RBF kernel, gamma=10, cost=20), k-NN (k=5)
- Training samples: 318 | Validation samples: 123 (stratified random sampling, 70/30 split)
- Accuracy metrics: Overall Accuracy (OA), Kappa Coefficient, Producer's Accuracy, User's Accuracy

### OBIA (eCognition Developer)
- Segmentation: Multiresolution segmentation
  - Sentinel-2: scale=50, shape=0.1, compactness=0.4
  - Landsat-8: scale=70, shape=0.1, compactness=0.4
- Same classifiers (RF, SVM, k-NN) applied on segmented objects
- Same accuracy assessment metrics



## Key Findings

- Pixel-based classification favors RF due to spectral strength in moderate-resolution data
- OBIA favors k-NN because multiresolution segmentation reduces within-class spectral variability, making neighborhood-based classification more coherent
- Sentinel-2 (10m) benefits OBIA more than pixel-based, while Landsat-8 (30m) suits pixel-based RF better
- Resolution-context compatibility is critical — classifier choice must align with both the dataset resolution and classification framework


## Publication

**Mati ur Rehman**, Syed Aun Abbas, Abdul Wahab Shah, Raja Tashfeen Muqarrab, Dur E Najaf Raza, Sawaid Abbas.  
*Assessing the Efficacy of Pixel-based and Object-based Classification Techniques and Classifiers for Land Cover Mapping Using Landsat-8 and Sentinel-2 Data in Complex Mountainous Terrain.*  
**International Journal of Innovations in Science & Technology**, vol. 7(9), pp. 42–56, July 2025.  
[Read Paper](https://www.researchgate.net/publication/408917607_Assessing_the_Efficacy_of_Pixel-based_and_Object-based_Classification_Techniques_and_Classifiers_for_Land_Cover_Mapping_Using_Landsat-8_and_Sentinel-2_Data_in_Complex_Mountainous_Terrain)

---

## Data Sources

- Landsat-8 OLI SR: [USGS Earth Explorer](https://earthexplorer.usgs.gov)
- Sentinel-2 MSI L2A: [Copernicus Open Access Hub](https://scihub.copernicus.eu)
- Reference samples: Google Earth Pro visual interpretation
- Processing: [Google Earth Engine](https://code.earthengine.google.com)
