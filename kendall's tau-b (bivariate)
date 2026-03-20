import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
from scipy.stats import kendalltau

sns.set(style="whitegrid")

assignment = pd.read_csv("voterdemo.csv")
assignment.head()

assignment.columns = assignment.columns.str.strip()

numeric_cols = ['Population', 'Year', 'Religiosity', 'Diversity', 'Income', "Bachelor's", 
                'Legislative', 'Election Year', 'Strengthening Economy',
                'Reducing Healthcare Costs(S)', 'Budget Deficit(S)',
                'Dealing with Climate Change(S)', 'Protecting Environment',
                'Gun Control(S)', 'Immigration', 'Reproductive Rights(S)']

assignment[numeric_cols] = assignment[numeric_cols].apply(pd.to_numeric, errors='coerce')

assignment.isnull().sum()

demographic_cols = ['Religiosity', 'Diversity', 'Income', "Bachelor's"]
target_col = 'Legislative'

print("Kendall Tau B Correlations:\n")
for col in demographic_cols:
    tau, p_value = kendalltau(assignment[col], assignment[target_col])
    print(f"{col} vs {target_col}: tau={tau:.3f}, p-value={p_value:.3f}")

corr_matrix = assignment[demographic_cols + [target_col]].corr(method='kendall')

plt.figure(figsize=(8,6))
sns.heatmap(corr_matrix, annot=True, cmap='PuRd', center=0)
plt.title("Kendall Tau B Correlation Heatmap")
plt.show()

demographic_cols = ['Religiosity', 'Diversity', 'Income', "Bachelor's", 'Legislative']
target_col = 'Reproductive Rights(S)'

print("Kendall Tau B Correlations:\n")
for col in demographic_cols:
    tau, p_value = kendalltau(assignment[col], assignment[target_col])
    print(f"{col} vs {target_col}: tau={tau:.3f}, p-value={p_value:.3f}")

corr_matrix = assignment[demographic_cols + [target_col]].corr(method='kendall')

plt.figure(figsize=(8,6))
sns.heatmap(corr_matrix, annot=True, cmap='OrRd', center=0)
plt.title("Kendall Tau B Correlation Heatmap")
plt.show()

demographic_cols = ['Religiosity', 'Diversity', 'Income', "Bachelor's", 'Legislative']
target_col = 'Immigration'

print("Kendall Tau B Correlations:\n")
for col in demographic_cols:
    tau, p_value = kendalltau(assignment[col], assignment[target_col])
    print(f"{col} vs {target_col}: tau={tau:.3f}, p-value={p_value:.3f}")

corr_matrix = assignment[demographic_cols + [target_col]].corr(method='kendall')

plt.figure(figsize=(8,6))
sns.heatmap(corr_matrix, annot=True, cmap='RdPu', center=0)
plt.title("Kendall Tau B Correlation Heatmap")
plt.show()

demographic_cols = ['Religiosity', 'Diversity', 'Income', "Bachelor's", 'Legislative']
target_col = 'Gun Control(S)'

print("Kendall Tau B Correlations:\n")
for col in demographic_cols:
    tau, p_value = kendalltau(assignment[col], assignment[target_col])
    print(f"{col} vs {target_col}: tau={tau:.3f}, p-value={p_value:.3f}")

corr_matrix = assignment[demographic_cols + [target_col]].corr(method='kendall')

plt.figure(figsize=(8,6))
sns.heatmap(corr_matrix, annot=True, cmap='BuPu', center=0)
plt.title("Kendall Tau B Correlation Heatmap")
plt.show()

demographic_cols = ['Religiosity', 'Diversity', 'Income', "Bachelor's", 'Legislative']
target_col = 'Protecting Environment'

print("Kendall Tau B Correlations:\n")
for col in demographic_cols:
    tau, p_value = kendalltau(assignment[col], assignment[target_col])
    print(f"{col} vs {target_col}: tau={tau:.3f}, p-value={p_value:.3f}")

corr_matrix = assignment[demographic_cols + [target_col]].corr(method='kendall')

plt.figure(figsize=(8,6))
sns.heatmap(corr_matrix, annot=True, cmap='GnBu', center=0)
plt.title("Kendall Tau B Correlation Heatmap")
plt.show()

demographic_cols = ['Religiosity', 'Diversity', 'Income', "Bachelor's", 'Legislative']
target_col = 'Dealing with Climate Change(S)'

print("Kendall Tau B Correlations:\n")
for col in demographic_cols:
    tau, p_value = kendalltau(assignment[col], assignment[target_col])
    print(f"{col} vs {target_col}: tau={tau:.3f}, p-value={p_value:.3f}")

corr_matrix = assignment[demographic_cols + [target_col]].corr(method='kendall')

plt.figure(figsize=(8,6))
sns.heatmap(corr_matrix, annot=True, cmap='PuBu', center=0)
plt.title("Kendall Tau B Correlation Heatmap")
plt.show()

demographic_cols = ['Religiosity', 'Diversity', 'Income', "Bachelor's", 'Legislative']
target_col = 'Budget Deficit(S)'

print("Kendall Tau B Correlations:\n")
for col in demographic_cols:
    tau, p_value = kendalltau(assignment[col], assignment[target_col])
    print(f"{col} vs {target_col}: tau={tau:.3f}, p-value={p_value:.3f}")

corr_matrix = assignment[demographic_cols + [target_col]].corr(method='kendall')

plt.figure(figsize=(8,6))
sns.heatmap(corr_matrix, annot=True, cmap='YlGnBu', center=0)
plt.title("Kendall Tau B Correlation Heatmap")
plt.show()

demographic_cols = ['Religiosity', 'Diversity', 'Income', "Bachelor's", 'Legislative']
target_col = 'Reducing Healthcare Costs(S)'

print("Kendall Tau B Correlations:\n")
for col in demographic_cols:
    tau, p_value = kendalltau(assignment[col], assignment[target_col])
    print(f"{col} vs {target_col}: tau={tau:.3f}, p-value={p_value:.3f}")

corr_matrix = assignment[demographic_cols + [target_col]].corr(method='kendall')

plt.figure(figsize=(8,6))
sns.heatmap(corr_matrix, annot=True, cmap='PuBuGn', center=0)
plt.title("Kendall Tau B Correlation Heatmap")
plt.show()

demographic_cols = ['Religiosity', 'Diversity', 'Income', "Bachelor's", 'Legislative']
target_col = 'Strengthening Economy'

print("Kendall Tau B Correlations:\n")
for col in demographic_cols:
    tau, p_value = kendalltau(assignment[col], assignment[target_col])
    print(f"{col} vs {target_col}: tau={tau:.3f}, p-value={p_value:.3f}")

corr_matrix = assignment[demographic_cols + [target_col]].corr(method='kendall')

plt.figure(figsize=(8,6))
sns.heatmap(corr_matrix, annot=True, cmap='BuGn', center=0)
plt.title("Kendall Tau B Correlation Heatmap")
plt.show()
