# A Spatio-Temporal Machine Learning Benchmark for Forest-Habitat Disturbance Prediction around Salonga National Park

This repository contains the code, notebook workflow, generated figures, and experimental outputs associated with the paper:

**A Spatio-Temporal Machine Learning Benchmark for Forest-Habitat Disturbance Prediction around Salonga National Park**

The study develops a reproducible spatio-temporal machine learning benchmark for predicting one-year-ahead forest-habitat disturbance around Salonga National Park in the Democratic Republic of the Congo. The work is designed in the context of biodiversity management, where forest-cover loss is used as a spatially explicit proxy for potential habitat disturbance, not as a direct measurement of biodiversity loss.

---

## 1. Scientific Objective

The objective of this study is to evaluate whether open geospatial data and machine learning can predict forest-habitat disturbance risk around Salonga National Park at grid-cell level.

The prediction task is formulated as follows:

> Given a spatial cell and year `t`, predict whether the cell will experience significant forest-habitat disturbance in year `t+1`.

A cell is labelled as disturbed when it experiences at least **5 ha** of forest loss in the following year.

---

## 2. Research Question

Can machine learning models predict one-year-ahead forest-habitat disturbance risk around Salonga National Park using open spatio-temporal geospatial data?

---

## 3. Main Contribution

This repository supports three scientific contributions:

1. It formulates forest-cover loss around Salonga National Park as a one-year-ahead forest-habitat disturbance prediction problem at grid-cell level.

2. It constructs a reproducible spatio-temporal benchmark from open geospatial data, combining annual forest-loss history, forest-cover structure, protected-area context, and neighbourhood disturbance pressure.

3. It evaluates machine learning models against strong historical baselines, showing both the predictive value of tree-based models and the importance of disturbance persistence and spatial clustering.

---

## 4. Study Area

The study area includes:

- Salonga National Park;
- a 50 km surrounding buffer;
- a regular 10 km spatial analysis grid.

The final benchmark contains:

| Component | Value |
|---|---:|
| Spatial cells | 1,056 |
| Years | 2001–2024 |
| Cell-year observations | 25,344 |
| Prediction target | disturbance at `t+1` |
| Disturbance threshold | 5 ha |

---

## 5. Data Sources

The workflow uses open geospatial data sources:

| Data source | Role |
|---|---|
| Hansen Global Forest Change | Annual forest-cover loss and initial tree cover |
| WDPA / Protected Planet | Salonga National Park boundary |
| Google Earth Engine | Cloud-based geospatial extraction and zonal statistics |
| Derived 10 km grid | Spatial unit of prediction |

Large raw geospatial datasets are **not redistributed** in this repository. The notebook provides reproducible extraction steps to regenerate the processed benchmark from open sources.

---

## 6. Repository Structure

```text
salonga-forest-habitat-disturbance-ml/
│
├── README.md
├── requirements.txt
├── LICENSE
├── .gitignore
│
├── notebooks/
│   └── Salonga_Forest_Habitat_Disturbance_Complete_Study.ipynb
│
├── outputs/
│   ├── figures/
│   │   ├── fig_study_area_grid_10km.png
│   │   ├── fig_cumulative_loss_map_2001_2024_10km.png
│   │   ├── fig_model_comparison_pr_auc_10km.png
│   │   └── fig_predicted_risk_map_randomforest_2024_10km.png
│   │
│   └── tables/
│       ├── model_performance_10km.csv
│       └── class_balance_by_split_10km.csv
│
└── data/
    └── README.md
