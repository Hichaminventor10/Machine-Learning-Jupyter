# Machine-Learning-Labs

Practical machine-learning laboratories developed with Python and Jupyter
Notebooks. This repository documents introductory experiments in regression,
classification, feature engineering, model evaluation, and visualization.

The notebooks are educational exercises: some sections are complete
demonstrations, while others intentionally contain exercises or placeholders.
The documentation below reflects the current repository contents and recorded
notebook outputs.

## Contents

- [Repository structure](#repository-structure)
- [Algorithms and techniques](#algorithms-and-techniques)
- [Notebook guide](#notebook-guide)
- [Datasets](#datasets)
- [Technologies and libraries](#technologies-and-libraries)
- [Installation](#installation)
- [Running the notebooks](#running-the-notebooks)
- [Learning objectives](#learning-objectives)
- [Current limitations](#current-limitations)
- [Future learning roadmap](#future-learning-roadmap)

## Repository structure

```text
Machine-Learning-Labs/
├── datasets/
│   ├── data.csv
│   ├── fish (1).csv
│   └── iris.csv
├── notebooks/
│   ├── 02_knn_demo.ipynb
│   ├── Régression linéaire avec et sans régulariqation.ipynb
│   ├── Régression polynomial_TP.ipynb
│   ├── TP4 Logistic Regression sans Régularisation-Copy1.ipynb
│   └── reg_linear.ipynb
├── test.ipynb
├── .gitignore
└── README.md
```

The local `.venv/` directory is ignored and is not part of the project
content.

## Algorithms and techniques

| Area | Covered in the repository |
| --- | --- |
| Regression | `LinearRegression`, `KNeighborsRegressor`, manually constructed polynomial features, `PolynomialFeatures` |
| Regularization | Introduction to `Ridge`, alpha-parameter exercises, and an `SGDRegressor` exercise |
| Classification | `KNeighborsClassifier` and an unfinished logistic-regression exercise |
| Preprocessing | Min-max scaling, standardization, manual categorical encoding, label encoding |
| Data splitting | Training/test partitions with `train_test_split` |
| Evaluation | Mean squared error and R² for the completed linear-regression experiment; an accuracy exercise is present but unfinished |
| Visualization | Scatter plots, pair plots, regression curves, class distributions, and kNN decision boundaries |
| Mathematical concepts | Correlation, linear and polynomial functions, model coefficients, bias/intercept, feature scaling, neighborhood distance, and regularization strength |

## Notebook guide

| Notebook | Description | Data source | Status |
| --- | --- | --- | --- |
| [`02_knn_demo.ipynb`](./notebooks/02_knn_demo.ipynb) | Demonstrates kNN regression on a small synthetic apartment-price example, then kNN classification on Iris with train/test splitting and a 2D decision-boundary visualization. | [`iris.csv`](./datasets/iris.csv) and scikit-learn's built-in Iris dataset; the first regression example uses inline synthetic data. | Mostly complete; the first draft cell contains saved import/name errors, followed by a corrected regression example. |
| [`Régression linéaire avec et sans régulariqation.ipynb`](<./notebooks/Régression%20linéaire%20avec%20et%20sans%20régulariqation.ipynb>) | Explores fish measurements, pairwise relationships, correlations, simple linear regression from age to weight, and MSE/R² evaluation. | [`fish (1).csv`](<./datasets/fish%20%281%29.csv>) | Completed linear-regression workflow; regularization is named in the title but not implemented in the saved cells. |
| [`Régression polynomial_TP.ipynb`](<./notebooks/Régression%20polynomial_TP.ipynb>) | Generates noisy quadratic data, compares manual and `PolynomialFeatures` degree-2 feature construction, and creates a degree-300 feature matrix with scaling. | Inline synthetic data generated with NumPy. | Partial exercise; Ridge and SGD sections are placeholders, and the saved Ridge cell records a `NameError`. |
| [`TP4 Logistic Regression sans Régularisation-Copy1.ipynb`](<./notebooks/TP4%20Logistic%20Regression%20sans%20Régularisation-Copy1.ipynb>) | Inspects penguin measurements, encodes species labels, visualizes the classes, and prepares an 80/20 split for logistic regression. | [`data.csv`](./datasets/data.csv) | Preparation completed; model fitting, accuracy, decision boundaries, and interpretation remain placeholders. |
| [`reg_linear.ipynb`](<./notebooks/reg_linear.ipynb>) | No executable content is currently present. | None | Empty zero-byte file; not a valid Jupyter Notebook JSON document. |
| [`test.ipynb`](./test.ipynb) | Basic Python smoke test covering variables, formatted strings, arithmetic, a conditional, and a loop. | None | Complete introductory Python example; not a machine-learning experiment. |

### Recorded completed results

The fish regression notebook records the following results for predicting
weight from age:

- Training MSE: `1198.06`
- Training R²: `0.864`
- Test MSE: `1140.41`
- Test R²: `0.725`

The corrected kNN apartment example records a predicted price of
`493,333.33 DH` for the supplied example input. These values are the outputs
saved in the notebooks and are not claims about a production model.

## Datasets

| Dataset | Rows | Columns | Description | Used by |
| --- | ---: | --- | --- | --- |
| [`data.csv`](./datasets/data.csv) | 341 | `Culmen_Length_mm`, `Culmen_Depth_mm`, `Species` | Two penguin culmen measurements and three species: Adelie (150), Gentoo (123), and Chinstrap (68). | Logistic-regression exercise |
| [`fish (1).csv`](<./datasets/fish%20%281%29.csv>) | 44 | `age`, `temp`, `weight`, `length` | Fish measurements used for exploratory analysis, correlation, and regression. Temperature has four observed values: 25, 27, 29, and 31. | Linear-regression notebook |
| [`iris.csv`](./datasets/iris.csv) | 150 | `Id`, `SepalLength[cm]`, `SepalWidth[cm]`, `PetalLength[cm]`, `PetalWidth[cm]`, `Species` | Balanced Iris dataset with 50 observations each for Iris-setosa, Iris-versicolor, and Iris-virginica. | kNN notebook |

### Dataset path note

The notebooks currently load the CSV files using bare filenames such as
`pd.read_csv("iris.csv")` and `pd.read_csv("data.csv")`, while the files are
stored in `datasets/`. Run the notebooks from a working directory containing
the expected files, or update the notebook paths in a future maintenance
change. This README does not modify the notebooks.

The fish notebook's prose refers to `fish.csv`, but the repository contains
`fish (1).csv`. The filename shown in the notebook's executed loading cell is
`fish (1).csv`.

## Technologies and libraries

- **Python 3**
- **Jupyter Notebook**
- **NumPy** for numerical arrays and synthetic data generation
- **pandas** for tabular data loading and exploration
- **Matplotlib** for plotting
- **Seaborn** for statistical visualizations and pair plots
- **scikit-learn** for preprocessing, model fitting, splitting, and metrics

## Installation

1. Clone the repository and enter its directory:

   ```bash
   git clone https://github.com/Hichaminventor10/Machine-Learning-Jupyter.git
   cd Machine-Learning-Labs
   ```

2. Create and activate a virtual environment:

   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   ```

   On Windows PowerShell, use:

   ```powershell
   .venv\Scripts\Activate.ps1
   ```

3. Install the core dependencies:

   ```bash
   python -m pip install --upgrade pip
   python -m pip install jupyter numpy pandas matplotlib seaborn scikit-learn
   ```

   The kNN notebook also contains an optional `watermark` cell. Install
   `watermark` if you want to run that metadata cell:

   ```bash
   python -m pip install watermark
   ```

## Running the notebooks

Start Jupyter from the repository root:

```bash
jupyter notebook
```

Then open a notebook from the `notebooks/` directory and execute its cells in
order. For the CSV-loading notebooks, make sure the working directory allows
the bare filenames used by the existing code to resolve, or use the dataset
links above to locate the source files.

For reproducible execution, run cells from top to bottom and review the
placeholder and error notes in the [notebook guide](#notebook-guide).

## Learning objectives

This repository supports practice with:

- Loading and inspecting CSV data with pandas
- Separating features and target variables
- Creating training and test subsets
- Understanding regression versus classification
- Applying feature scaling before distance-based models
- Comparing linear and polynomial feature representations
- Reading coefficients, intercepts, correlations, MSE, and R²
- Visualizing class distributions, fitted models, and decision regions
- Recognizing incomplete experiments and debugging notebook execution issues



## Future learning roadmap

1. Normalize notebook and dataset filenames and use robust paths based on the
   repository layout.
2. Complete the logistic-regression model, accuracy calculation, confusion
   matrix, and decision-boundary visualizations.
3. Complete the Ridge experiments across the planned alpha values and compare
   them with the unregularized high-degree model.
4. Add a meaningful `SGDRegressor` comparison and document its important
   hyperparameters.
5. Add reusable preprocessing/model pipelines and cross-validation.
6. Report additional classification metrics such as precision, recall, and
   F1-score.
7. Add data-quality checks, missing-value handling, and clearer experiment
   conclusions.
8. Add requirements management and automated notebook validation for portfolio
   reproducibility.
