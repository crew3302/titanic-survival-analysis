# Data Science Assignment 02

This project contains a complete exploratory data analysis and visualization study of the Titanic dataset using `pandas`, `numpy`, `matplotlib`, and `seaborn`.

The assignment is organized into five notebook-based parts:

1. `Part_1_EDA.ipynb`  
   Exploratory data analysis, missing-value inspection, cleaning, and feature engineering.
2. `Part_2_Univariate_Analysis.ipynb`  
   Univariate analysis of age, fare, and key categorical variables.
3. `Part_3_Bivariate_Multivariate_Analysis.ipynb`  
   Survival analysis by group, correlation study, scatter plots, and pair plots.
4. `Part_4_Advanced_Visualization_Storytelling.ipynb`  
   Advanced visualizations, faceting, and annotated narrative charts.
5. `Part_5_Reflection_Critical_Analysis.ipynb`  
   Misleading visualization critique, reflection, and hypothesis generation.

## Dataset

The analysis uses the Titanic dataset loaded directly from Seaborn:

```python
df = sns.load_dataset("titanic")
```

This dataset contains 891 passenger records and includes variables such as:

- `survived`
- `pclass`
- `sex`
- `age`
- `sibsp`
- `parch`
- `fare`
- `embarked`
- `class`
- `who`
- `deck`
- `embark_town`
- `alone`

## Project Goals

The main goals of this assignment are:

- inspect and understand the structure of the Titanic dataset
- clean missing and incomplete data appropriately
- engineer useful analysis features
- study distributions of important variables
- examine relationships between passenger characteristics and survival
- produce publication-quality visualizations
- reflect critically on what visualizations can and cannot show

## Cleaning and Feature Engineering

The notebooks use a consistent cleaned dataset built from the original Titanic data.

### Cleaning steps

- impute missing `age` values using group-based medians by `sex` and `pclass`
- drop `deck` because of very high missingness
- fill missing `embarked` values using the mode
- fill missing `embark_town` values consistently with the cleaned embarkation data

### Engineered features

- `family_size = sibsp + parch + 1`
- `travel_group`
  - `Solo` for `family_size == 1`
  - `Small` for `family_size` in `2-4`
  - `Large` for `family_size >= 5`
- `age_group`
  - `Child` for ages `0-12`
  - `Teen` for ages `13-17`
  - `Adult` for ages `18-59`
  - `Senior` for ages `60+`

## Notebook Overview

### Part 1: Exploratory Data Analysis

This notebook covers:

- first and last rows of the dataset
- shape, data types, and summary statistics
- missing-value analysis with explanations
- overall survival rate and survival by passenger class
- data cleaning and feature engineering
- final null-value verification

### Part 2: Univariate Analysis and Distributions

This notebook covers:

- age histograms with multiple bin sizes
- histogram plus KDE for age
- KDE comparison of survivors vs non-survivors
- fare distribution before and after log transformation
- fare outlier analysis
- fare box plots by passenger class
- count plots for `pclass`, `sex`, and `embarked`
- bar/count plots for `travel_group` and `age_group`
- side-by-side count plots for `sex` and `survived`

### Part 3: Bivariate and Multivariate Analysis

This notebook covers:

- survival rate by sex
- survival rate by passenger class
- survival rate by age group
- grouped survival rate by class and sex
- survival rate by `travel_group`
- Pearson correlation heatmap
- strongest and weakest correlation discussion
- scatter plot of `age` vs `fare` colored by survival
- pairplot of `age`, `fare`, `pclass`, `survived`, and `family_size`

### Part 4: Advanced Visualization and Storytelling

This notebook covers:

- violin plot of age by class and sex
- box plot plus strip plot of fare by embarkation port
- `FacetGrid` KDE panels by sex and class
- `catplot` of survival by age group, class, and sex
- publication-style annotated narrative chart
- data-journalism-style caption

### Part 5: Reflection and Critical Analysis

This notebook covers:

- a deliberately misleading chart and corrected version
- discussion of how one earlier chart could be misread
- three follow-up hypotheses for predictive modeling
- reflection on the most insightful visualization
- appendix material with plotting and annotation references

## Generated Output Files

When the notebooks are executed, they regenerate chart image files such as:

- `q3a_age_histograms.png`
- `q3b_age_kde.png`
- `q3c_age_survival_kde.png`
- `q4a_fare_distribution.png`
- `q4c_fare_boxplot.png`
- `q5a_categorical_distributions.png`
- `q5b_travel_group_distribution.png`
- `q5c_age_group_distribution.png`
- `q5d_sex_survived_countplots.png`
- `q6a_survival_by_sex.png`
- `q6b_survival_by_class_age.png`
- `q6d_survival_by_travel_group.png`
- `q7a_correlation_heatmap.png`
- `q8a_age_vs_fare_scatter.png`
- `q8b_pairplot.png`
- `q10a_facetgrid_kde_age_sex_pclass.png`
- `q10b_catplot_survival_agegroup_pclass_sex.png`
- `q11a_narrative_chart_survival_multidim.png`
- `q12a_misleading_vs_corrected.png`

## Requirements

Recommended Python packages:

```python
pandas
numpy
matplotlib
seaborn
```

If you want to install them manually:

```powershell
pip install pandas numpy matplotlib seaborn
```

## How To Run

Open the notebooks in Jupyter Notebook, JupyterLab, or VS Code and run cells from top to bottom.

Recommended order:

1. `Part_1_EDA.ipynb`
2. `Part_2_Univariate_Analysis.ipynb`
3. `Part_3_Bivariate_Multivariate_Analysis.ipynb`
4. `Part_4_Advanced_Visualization_Storytelling.ipynb`
5. `Part_5_Reflection_Critical_Analysis.ipynb`

Although each notebook contains its own cleaning pipeline so it can run independently, the project is conceptually designed to flow from Part 1 through Part 5.

## Reproducibility

Each notebook begins with:

```python
np.random.seed(42)
warnings.filterwarnings("ignore")
```

The dataset is loaded from Seaborn, so an environment with Seaborn access to the Titanic dataset is required.

## Verification Status

The notebooks were checked for both execution and assignment compliance.

Verified locally:

- `Part_1_EDA.ipynb` passes
- `Part_2_Univariate_Analysis.ipynb` passes
- `Part_3_Bivariate_Multivariate_Analysis.ipynb` passes
- `Part_4_Advanced_Visualization_Storytelling.ipynb` passes
- `Part_5_Reflection_Critical_Analysis.ipynb` passes

The notebooks were also reviewed against the assignment brief, and missing or inconsistent items were corrected.

## File List

- `README.md`  
  Project overview and usage instructions.
- `Part_1_EDA.ipynb`
- `Part_2_Univariate_Analysis.ipynb`
- `Part_3_Bivariate_Multivariate_Analysis.ipynb`
- `Part_4_Advanced_Visualization_Storytelling.ipynb`
- `Part_5_Reflection_Critical_Analysis.ipynb`
- generated `.png` chart files after notebook execution

## Notes

- Some notebook print outputs use symbols such as `✓`, `£`, and arrows. These display correctly in Jupyter environments and UTF-8 terminals.
- The project is submission-ready as a notebook-based assignment.

## Author

Prepared for Data Science Assignment 02 using Python-based exploratory data analysis and visualization workflows.
