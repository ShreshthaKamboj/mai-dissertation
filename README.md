# Privacy-Preserving Outbreak Surveillance with Geospatially-Aware Machine Learning

This repository contains the MAI dissertation project notebook, exported figures, and supporting material for a privacy-preserving outbreak surveillance framework. The work studies how geospatial context can be integrated into a differentially private machine learning pipeline to better protect sensitive medical data while preserving the utility of outbreak signals.

The project is motivated by the challenge of sharing public-health surveillance data without exposing individuals, especially in sparsely populated regions where re-identification risk is higher. The notebook explores a post-processing framework for differentially private outbreak detection that incorporates population sensitivity, false-positive sensitivity, and a cost-sensitive penalty function to make outbreak signals more reliable for downstream analysis.

## Project Summary

This dissertation investigates whether a geospatially-aware mechanism can improve the privacy-utility trade-off in outbreak surveillance. The proposed method:

- applies differential privacy to COVID-19 case counts using the Laplace mechanism
- detects outbreak signals using rolling baselines, robust deviation measures, growth trends, and persistence checks
- introduces a geospatially-informed penalty function based on population exposure and recent false-positive behaviour
- trains a cost-sensitive machine learning post-processing model to recover utility from noisy surveillance signals
- evaluates performance across multiple privacy budgets using F1 score and ROC-based analysis

The results suggest that combining differential privacy with geospatially-aware machine learning can improve utility while maintaining stronger privacy protection, making the approach promising for future outbreak surveillance systems.

## Repository Contents

- `mairesearchfinal.ipynb`: main Kaggle notebook for the dissertation experiments
- `figures/`: exported plots and interactive visual output from the notebook
- `README.md`: project overview and setup guide

## Tools and Technologies

- Python
- Jupyter Notebook / Kaggle Notebook
- NumPy
- pandas
- scikit-learn
- SciPy
- Matplotlib
- Seaborn
- Plotly Express

## Dataset

The notebook expects the OWID COVID-19 dataset to be available at:

```text
/kaggle/input/covid19/owid-covid-data.csv
```

If you run the notebook outside Kaggle, update the dataset path in the data-loading cell to match your local environment.

## Setup

1. Clone this repository.
2. Create a Python environment with the required libraries installed.
3. Place the OWID COVID-19 dataset where the notebook can access it, or update the dataset path in the notebook.
4. Open `mairesearchfinal.ipynb` in Jupyter or Kaggle.
5. Run the notebook from top to bottom to reproduce the figures and evaluation outputs.

A typical local install would look like:

```bash
pip install numpy pandas scikit-learn scipy matplotlib seaborn plotly notebook
```

## Notes

- The notebook has been annotated with markdown explanations to make the experimental pipeline easier to follow.
- Existing code comments inside the notebook were preserved.
- Exported figures are included so the repository captures the main visual results even without rerunning the notebook.
