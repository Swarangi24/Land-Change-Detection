# Land Change Detection using Multi-Band Raster Data from Sentinel-2 with XGBoost

## Overview

This project focuses on detecting and visualizing **land use and land cover (LULC) changes** using **Sentinel-2 satellite imagery** and the **XGBoost classification algorithm**. It applies a supervised machine learning pipeline to perform pixel-wise classification across two temporal datasets and generates interpretable **color-coded maps** to track changes such as urbanization, deforestation, and water body shifts.

## Objectives

- Build a robust and interpretable ML pipeline to classify LULC changes using multi-band satellite data.
- Compare land cover across two different time periods.
- Create visually intuitive maps for non-technical stakeholders such as policymakers and urban planners.

## Key Features

- Uses **11 bands** of Sentinel-2 imagery (excluding Band 10).
- Pixel-wise classification using **XGBoost** for both historical and current imagery.
- Outputs **color-coded maps** highlighting gain, loss, and unchanged regions.
- Demonstrates **urban expansion, forest cover change, and water body shifts**.
- Achieved **≥94% classification accuracy** with XGBoost.
  
## Technologies Used

- **Python**
- **XGBoost**
- **scikit-learn**
- **pandas**, **NumPy**
- **rasterio**
- **QGIS**
- **Matplotlib/Seaborn** (for visualizations)

## Dataset

- **Sentinel-2 Level-1C imagery** from Copernicus Data Space Ecosystem  
- Two time periods: **2018** and **2024**  
- Preprocessed to extract and align 11 bands: B01–B12 (excluding B10)


## Pipeline Workflow

1. **Image Loading & Preprocessing**  
   - Load `.jp2` bands using `rasterio`  
   - Resample and stack bands to align spatial dimensions

2. **Model Training (Supervised Learning)**  
   - Train XGBoost classifiers on labeled CSV datasets (one per time period)

3. **Pixel-wise Classification**  
   - Predict land class for each pixel and decode to human-readable classes

4. **Change Detection**  
   - Compare predictions across years on a per-pixel basis

5. **Visualization**  
   - Generate RGB maps:  
     - **Green:** Gain  
     - **Red:** Loss  
     - **Gray:** No change

## Results

- **XGBoost Accuracy (2018):** 94.12%  
- **XGBoost Accuracy (2024):** 97.04%  
- Detectable changes include:
  - Urban sprawl
  - Agricultural land conversion
  - Seasonal water body changes
  - Island submersion and reclamation

## Limitations

- Some misclassification in transition zones (e.g., semi-urban areas)
- Seasonal variations in imagery can affect change detection accuracy
- Class imbalance for rare LULC classes

## Future Work

- Integrate deep learning models (e.g., U-Net, LSTM-CNN) for better spatial context
- Incorporate elevation, soil, and socio-economic layers for holistic land change analysis
- Real-time or near-real-time monitoring with cloud automation

## References

- [ESA Sentinel-2 Data Hub](https://dataspace.copernicus.eu)

## License

This project is for academic and educational use only.

