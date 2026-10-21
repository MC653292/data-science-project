# Medical Insurance Cost Analysis

A reproducible data science project that explores the factors behind individual medical insurance charges and builds a linear regression model to predict them.

## Problem / Research Question

What demographic and lifestyle factors drive individual medical insurance charges, and how accurately can a multiple linear regression model predict charges from a person's age, sex, BMI, number of children, smoking status, and region?

## Dataset

- **File:** `insurance.csv` (1,338 records, 7 columns)
- **Source:** The dataset is taken from the public repository [Machine-Learning-with-R-datasets](https://github.com/stedy/Machine-Learning-with-R-datasets) (`insurance.csv`), which is distributed under the **MIT License** and is freely available for educational and analytical use.
- **Columns:** `age`, `sex`, `bmi`, `children`, `smoker`, `region`, and the target variable `charges` (annual medical costs billed by the insurance, in USD).
- The dataset contains no names, IDs, passwords, or other personal identifiers, and no restricted data is included in this repository.

## Methods and Tools

- **Python** with **Pandas** and **NumPy** for data loading, cleaning, and wrangling
- **Matplotlib** and **Seaborn** for exploratory visualizations
- **Scikit-learn** for train/test splitting, multiple linear regression, and evaluation (R², MAE, RMSE)
- **Jupyter Notebook** for a fully documented, end-to-end analysis

## Key Findings

1. **Smoking is the dominant driver of charges**: smokers are charged about 3.8 times more on average (about USD 32,050 per year versus USD 8,440 for non-smokers), and smoking has the strongest correlation (0.79) and the largest regression coefficient.
2. **Age and BMI** have positive effects, and the age-versus-charges plot reveals three parallel bands.
3. **Regional and gender differences are small** compared with smoking, age, and BMI.
4. The multiple linear regression model explains about **81% of the variation** in held-out charges (R² = 0.807), with a mean absolute error of about USD 4,180.

### Limitation

The model assumes a linear relationship and cannot reproduce the banded, nonlinear structure visible in the scatter plots. It also relies on a single year of US data with no information about pre-existing medical conditions, so the results should not be generalized to other populations or time periods without further validation.

## Repository Structure

```
data-science-project/
├── insurance.csv                    # dataset
├── insurance_cost_analysis.ipynb    # full analysis notebook
├── requirements.txt                 # Python dependencies
└── visualizations/
    ├── fig1_charges_by_smoker.png
    ├── fig2_age_vs_charges.png
    ├── fig3_charges_by_region.png
    └── fig4_predicted_vs_actual.png
```

## How to Run the Analysis

1. **Clone the repository**

   ```bash
   git clone https://github.com/mc653292/data-science-project.git
   cd data-science-project
   ```

2. **Create and activate a virtual environment (optional but recommended)**

   ```bash
   python -m venv venv
   source venv/bin/activate          # Windows: venv\Scripts\activate
   ```

3. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   ```

4. **Start the notebook**

   ```bash
   jupyter notebook insurance_cost_analysis.ipynb
   ```

5. Run all cells in order. The notebook reads `insurance.csv` from the repository root and regenerates every figure in the `visualizations/` folder.

## Project Status

**Completed** — future work includes a gradient-boosted tree model, interaction terms (e.g., `smoker × age`), and cross-validation.
