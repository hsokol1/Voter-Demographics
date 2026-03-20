## 📊 State Demographics & Political Party Control Analysis
This repository contains a multi-part analysis of state demographics, political issue preferences, and legislative control in the U.S.  

## 🔗 Overview
1. **Classification - Demographic Characteristics**: Predictive modeling using state demographic features (income, education, diversity, religiosity).  
2. **Classification - Policy/Issue Preferences**: Predictive modeling using issue-specific variables (e.g., reproductive rights, gun control, climate policy).  
3. **Kendall Tau B Analysis**: Rank correlations between demographics, issues, and legislative control.  
> **Note:** Variables marked with `(S)` are **scale-reversed**, meaning their interpretation is inverted. For example, a Kendall Tau B of `-0.22` actually indicates a positive relationship. This approach allows consistent interpretation across variables without modifying the original dataset.

## 📖 Dataset Overview
- Data Source: Complied from various online sources
- Formal: CSV/Excel
- Observations: State-level data for all U.S. States for 2016, 2020, and 2023

## 🧮 Variable Scales
| Variable | Description | Scale / Notes |
|----------|-------------|---------------|
| State | State name |
| Population | Total population |
| Year | Year of observation |
| Religiosity | Aggregate measure of religious adherence |1 (low) – 5 (high) |
| Diversity | Diversity index | 1 (low) – 5 (high) |
| Income | Relative income ranking | 1 (low) – 5 (high) |
| Bachelor's | % of population with a bachelor’s degree | 1 (low) – 5 (high) |
| Legislative | State legislative party control | 1 (republican) – 3 (democrat) |
| Election Year | | 1 (yes) - 0 (no) |
| Strengthening Economy | Salex Tax Rates | 1 (lower tax rates) – 5 (higher tax rates) |
| Reducing Healthcare Costs (S) | Accessibility of healthcare (scale-reversed) | 1 (most accessible) – (least accessible)  |
| Budget Deficit (S) | Union Memberships (scale-reversed) | 1 (20% or more) – 5 (4.9% or less) |
| Dealing with Climate Change (S) | Support of climate-related regulations (scale-reversed) | 1 (more support) – 5 (less support) |
| Protecting Environment | ACEEE | 1 (efficient laws) – 5 (inefficient laws) |
| Gun Control (S) | Giffords Scale (scale-reversed) | 1 (strong gun laws) – 5 (weak gun laws)|
| Immigration | Immigration policies and strictness | 1 (anti-immigration) – 5 (pro-immigration) |
| Reproductive Rights (S) | Reproductive health policies (scale-reversed) | 1 (total access) – 6 (eliminated) |


> Variables with `(S)` are **reversed for interpretability** in analysis and visualizations.

## 🛠️ Tech Stack
- **Python 3.x**  
- Jupyter Notebook  
- pandas, numpy (data cleaning & manipulation)  
- seaborn, matplotlib, plotly (visualizations)  
- scikit-learn (classification & regression)  
- scipy.stats (Kendall Tau B analysis)

## 🧪 Research Hypotheses
The analysis in this repository is motivated by two primary hypotheses regarding state legislative party control and policy emphasis:

**Hypothesis 1:** If the state legislature is predominantly Republican, there will be a stronger emphasis on **economic cleavages** (e.g., budget priorities, reducing healthcare costs) than on identity-related issues.

**Hypothesis 2:** If the state legislature is predominantly Democratic, there will be a stronger emphasis on **identity cleavages** (e.g., reproductive rights, immigration, gun control) than on economic issues.

> These hypotheses guide both the classification tasks (predicting legislative control from demographics and issue priorities) and the Kendall Tau B correlation analysis. Variables marked `(S)` are scale-reversed to ensure consistent interpretation of directionality.

## 📊 Analysis Workflow
### 1. Classification - Demographics
- Uses state demographic features to predict party control.  
- Includes logistic regression, scaling, train/test split, and model evaluation.
- Visualizes feature importance and model performance.

### 2. Classification - Issues
- Uses issue-specific variables to predict party control and demographics. 
- Highlights relationships between policy priorities and legislative control.

### 3. Kendall Tau B Analysis
- Computes bivariate rank correlations between demographics/issues and legislative control. 
- Includes visualization of correlation heatmaps.
- Variables with `(S)` are **interpreted with scale reversal**

## 🚀 Future Research
Future research could build on this analysis by incorporating additional demographic and institutional factors to better understand their influence on legislative priorities and voter preferences.  

Key suggestions include:  
- **Income Tax Policy:** Examine state-level income tax rates and resolutions, accounting for federal income tax, to explore how economic priorities differ between Democratic and Republican states.  
- **Gender Diversity:** Consider gender representation within both the state population and legislative bodies, particularly the impact of women and women of color on issues such as reproductive rights and healthcare accessibility.  
- **Racial and Ethnic Diversity:** Explore how racial and ethnic composition in the legislature interacts with population demographics to influence policy decisions, including immigration and healthcare policy.  

Incorporating these factors could produce more precise models, refine hypotheses, and help identify both direct and indirect associations between demographics and policy outcomes in state legislatures.

## ⚠️ Disclaimer
This repository is for educational and portfolio purposes. Some variables are subjective and derived from surveys; interpretations should be made cautiously.
