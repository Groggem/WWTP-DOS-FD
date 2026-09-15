# WWTP Dissolved Oxygen Sensor Fault Detection

An automated anomaly detection and evaluation pipeline built in Python for identifying precision degradation faults in Wastewater Treatment Plant (WWTP) dissolved oxygen telemetry streams.

## Features

- **Multi-Method Detection Engine**: Implements and evaluates several statistical and machine learning approaches:
  - **Threshold Detector**: Standard deviation bounds ($\pm 3\sigma$).
  - **Window Detector**: Rolling statistical moving average and standard deviation bounds.
  - **Isolation Forest**: Unsupervised tree-based anomaly detection via `scikit-learn`.
  - **PELT Change-Point Detector**: Structural break detection using the `ruptures` library.
  - **Hybrid Detector**: Rule-based logical combination of threshold and window checks.
- **Automated Evaluation & Validation**: Computes confusion matrices, classification reports, and Precision-Recall metrics across all models.
- **Visualization Suite**: Generates temporal multi-method comparison charts and saved PNG plots for downstream analysis.

## Tech Stack

- **Language**: Python 3
- **Data Manipulation**: `pandas`, `numpy`
- **Machine Learning & Stats**: `scikit-learn`, `ruptures`, `scipy`
- **Visualization**: `matplotlib`, `seaborn`
- **Model Persistence**: `joblib`

## Getting Started

### Prerequisites

Install the required dependencies:
  ```bash
    pip install pandas numpy scikit-learn ruptures scipy matplotlib seaborn joblib
Data Requirements
The script expects the following CSV files in the working directory:

-bias_fault.csv (Faulty sensor telemetry dataset)

-sensor_without_faults.csv (Baseline normal operating telemetry dataset)

Execution
Run the main analysis script:

  ```bash
  python Test.py
Outputs will include evaluation metrics printed to the console, generated visualization .png charts, processed predictions (all_predictions.csv), and the serialized Isolation Forest model (isolation_forest_model.pkl).
