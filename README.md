# Privacy-Preserving Outbreak Surveillance with Geospatially-Aware Machine Learning

This repository contains the dissertation project notebook, exported figures, and supporting material for a privacy-preserving outbreak surveillance framework. The work investigates how geospatial context can be integrated into a differentially private machine learning pipeline to improve the privacy–utility trade-off in epidemiological data sharing.

The project is motivated by the challenge of sharing public-health surveillance data without exposing individuals, particularly in sparsely populated regions where re-identification risk is disproportionately higher. The framework explores a post-processing approach for differentially private outbreak detection that incorporates population-density sensitivity, false-positive sensitivity, and a cost-sensitive penalty function to produce more reliable outbreak signals for downstream analysis.

## Project Summary

This dissertation investigates whether a geospatially-aware, cost-sensitive machine learning post-processing framework can improve the privacy–utility trade-off in differentially private outbreak surveillance data. The study is exploratory in nature, aiming to identify potentially suitable mechanisms and assess their appropriateness on a publicly available real-world dataset.

The proposed framework:

- Applies differential privacy to outbreak case counts using the Laplace mechanism across six privacy budgets (ε = 0.1, 0.5, 1.0, 2.0, 3.0, 4.0)
- Constructs a dataset-agnostic dynamic ground truth using rolling baselines, robust deviation measures, growth trends, and persistence checks — deliberately avoiding dependence on any single data provider's accuracy claims
- Introduces a geospatially-informed, cost-sensitive penalty function based on regional population exposure and false-positive behaviour
- Trains a cost-sensitive Gradient Boosting post-processing model to recover utility from differentially private surveillance signals
- Evaluates framework performance against a raw differentially private baseline using F1-score and ROC-based analysis

The framework is designed around disease-agnostic features and mechanisms, making it applicable beyond the evaluation dataset to broader outbreak surveillance contexts. The OWID COVID-19 dataset is used as a representative real-world evaluation case, given its richness and the acute privacy sensitivity of pandemic surveillance data.

The results provide preliminary evidence that combining differential privacy with geospatially-aware machine learning post-processing can improve data utility at moderate privacy budgets, and that ε = 0.5 represents a practical operating threshold for health authorities seeking to balance disclosure risk with surveillance reliability.

The results suggest that combining differential privacy with geospatially-aware machine learning can improve utility while maintaining stronger privacy protection, making the approach promising for future outbreak surveillance systems.

## Repository Contents

- `mairesearchfinal.ipynb`: main Kaggle notebook for the dissertation experiments
- `figures/`: exported plots and interactive visual output from the notebook
- `REFERENCES.md`: GitHub-friendly bibliography with clickable links
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

- The dynamic ground truth construction does not rely on externally confirmed case counts, making the evaluation methodology transferable to other outbreak datasets without modification.
- Exported figures are included so that the main visual results are accessible without needing to rerun the full notebook.
- The notebook markdown annotations are intended to make the experimental design and pipeline decisions transparent and reproducible.
