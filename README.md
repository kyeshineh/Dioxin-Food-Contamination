# Dioxin-Food-Contamination
# README – CFIA Dioxin Data Analysis

## 1. Project Description

This project analyzes data collected by the Canadian Food Inspection Agency (CFIA) on dioxins and dioxin-like compounds in selected food products between 2014 and 2019.

The purpose of this analysis is to examine the distribution of contaminant concentrations, identify relationships between food characteristics and measured concentrations, and prepare the dataset for machine-learning analysis.

The planned machine-learning component will compare Random Forest Regression with Linear Regression to determine which method provides more accurate predictions of contaminant concentrations.

## 2. Data Source

**Dataset:** Dioxins and Dioxin-like Compounds in Selected Foods (2014–2019)

**Organization:** Canadian Food Inspection Agency (CFIA)

**Source:** [Government of Canada Open Data Portal](https://open.canada.ca/data/en/dataset/ed3d3c4b-fed8-4f4f-8455-2507812676e9)

The dataset contains approximately 96,565 measurement records from 3,115 food samples. It includes information about food products, origin, fat content, chemical components, measured concentrations, and detection limits.

## 3. Software and Libraries

The data profiling and exploratory analysis are conducted using Python.

The following libraries are used:

- pandas – Data cleaning and descriptive statistics
- NumPy – Numerical operations
- Matplotlib – Data visualization
- Seaborn – Statistical visualizations
- SciPy – Statistical analysis

Scikit-learn will be used for the planned machine-learning models.

## 4. Data Profiling and Exploratory Analysis

The analysis includes:

1. Examining dataset dimensions, variable types, and missing values.
2. Identifying repeated measurements for individual food samples.
3. Calculating descriptive statistics for contaminant concentrations.
4. Creating histograms, bar charts, scatterplots, and boxplots.
5. Investigating relationships between fat content, food categories, origin, and contaminant concentrations.

The Total UB TEQ measurement is being considered as the prediction target because it provides a combined upper-bound toxic-equivalent concentration for each food sample.

## 5. Preliminary Observations

Initial data profiling indicates that contaminant concentrations are right-skewed, with some samples having substantially higher concentrations than others.

A positive association was observed between fat content and Total UB TEQ concentrations, although the relationship was not particularly strong.

The number of samples also differs between food categories, which may affect the reliability of comparisons and predictive model performance.

These observations will help guide data preparation and the selection of appropriate modelling techniques.

## 6. Data Limitations

The dataset was collected through targeted surveillance rather than random sampling. Therefore, the findings may not represent all foods available in Canada.

Other considerations include unequal sample sizes across food categories, concentrations below detection limits, and repeated chemical measurements for individual samples.

These limitations will be addressed during data cleaning and model evaluation.

## 7. Instructions for Running the Analysis

1. Download the dataset from the Government of Canada Open Data Portal.
2. Install Python and the required libraries.
3. Place the CSV dataset and Python analysis script in the same folder.
4. Run the Python script to generate descriptive statistics and visualizations.
5. Review the resulting tables and charts.

Required libraries can be installed using:

```bash
pip install pandas numpy matplotlib seaborn scipy
```

Run the analysis using:

```bash
python profile_cfia.py
```

## 8. Next Steps

The next stage will involve preparing the data for Random Forest Regression and Linear Regression.

The models will be evaluated using Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), and R² to compare their predictive performance.

The results will be used to assess which food characteristics contribute most to predicting measured contaminant concentrations.

## 9. Data Attribution

Canadian Food Inspection Agency. *Dioxins and dioxin-like compounds in selected foods (2014–2019).* Government of Canada Open Data Portal.

The data is available under the Open Government Licence – Canada.

flowchart TD
    A["1. Raw CFIA Data<br/>2014–2019 food measurements"]
    B["2. Data Profiling<br/>Types, missing values, duplicates"]
    C["3. Data Cleaning<br/>Numeric conversion, detection limits"]
    D["4. Data Restructuring<br/>One row per food sample"]
    E["5. Exploratory Data Analysis<br/>Histograms, boxplots, correlations"]
    F["6. Train-Test Split<br/>Separate samples"]
    G["7. Feature Preparation<br/>Imputation and one-hot encoding"]
    H["8. Model Training"]
    I["Random Forest Regression"]
    J["Linear Regression"]
    K["9. Model Evaluation<br/>MAE, RMSE, R²"]
    L["10. Interpretation<br/>Feature importance and limitations"]

    A --> B --> C --> D --> E --> F --> G --> H
    H --> I
    H --> J
    I --> K
    J --> K
    K --> L
