import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

import matplotlib
matplotlib.style.use('ggplot')
%matplotlib inline
import seaborn as sns

from sklearn.model_selection import train_test_split, cross_val_score, StratifiedKFold
from sklearn.preprocessing import StandardScaler, LabelEncoder

from sklearn.neighbors import KNeighborsClassifier
from sklearn.ensemble import RandomForestClassifier
from sklearn.svm import SVC
from sklearn.linear_model import LogisticRegression

from sklearn.metrics import accuracy_score, confusion_matrix, classification_report
from sklearn.metrics import precision_score, recall_score, f1_score

assignment = pd.read_csv("voterdemo.csv")
assignment.head()

X = assignment[['Strengthening Economy', 'Reducing Healthcare Costs(S)', 'Gun Control(S)', 'Immigration', 'Protecting Environment', 'Dealing with Climate Change(S)', 'Budget Deficit(S)', 'Reproductive Rights(S)']]
y = assignment['Legislative']

#Train/Test Split
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

scaler = StandardScaler()
X_train_scaled = scaler.fit_transform(X_train)
X_test_scaled = scaler.transform(X_test)

#K-Nearest Neighbors
classifier = KNeighborsClassifier(n_neighbors=5)
classifier.fit(X_train_scaled, y_train)
y_pred = classifier.predict(X_test_scaled)
y_pred

acc = accuracy_score(y_test, y_pred)
print("KNN Accuracy for 5 Neighbors:", acc)

cm = confusion_matrix(y_test, y_pred)
print(cm)
sns.heatmap(cm, annot=True, fmt="d", cmap="PuRd")
plt.title("Confusion Matrix")
plt.show()

classifier2 = KNeighborsClassifier(n_neighbors=10)
classifier2.fit(X_train_scaled, y_train)
y_pred2 = classifier2.predict(X_test_scaled)
y_pred2

acc2 = accuracy_score(y_test, y_pred2)
print("KNN Accuracy for 10 Neighbors:", acc2)

cm2 = confusion_matrix(y_test, y_pred2)
print(cm2)
sns.heatmap(cm2, annot=True, fmt="d", cmap="PuRd")
plt.title("Confusion Matrix")
plt.show()

print(classification_report(y_test, y_pred2))

#Support Vector Machine
svm = SVC(kernel="rbf", C=1.0, gamma="scale")
svm.fit(X_train_scaled, y_train)
svm_pred = svm.predict(X_test_scaled)

print("SVM Accuracy:", accuracy_score(y_test, svm_pred))

svm_conf = confusion_matrix(y_test,svm_pred)
print(svm_conf)
sns.heatmap(svm_conf, annot=True, fmt="d", cmap="PuRd")
plt.title("Confusion Matrix")
plt.show()

print(classification_report(y_test, svm_pred))

#Random Forest
rf = RandomForestClassifier(n_estimators=100, random_state=42)
rf.fit(X_train_scaled, y_train)
rf_pred = rf.predict(X_test_scaled)

print("Random Forest Accuracy:", accuracy_score(y_test, rf_pred))

rf_conf = confusion_matrix(y_test,rf_pred)
print(rf_conf)
sns.heatmap(rf_conf, annot=True, fmt="d", cmap="PuRd")
plt.title("Confusion Matrix")
plt.show()

print(classification_report(y_test, rf_pred))

#Logistic Regression
log_reg = LogisticRegression(max_iter=1000, solver='lbfgs')
log_reg.fit(X_train_scaled, y_train)
log_pred = log_reg.predict(X_test_scaled)

accuracy = accuracy_score(y_test, log_pred)
print("Logistic Regression Accuracy:", accuracy)

log_reg_tab = confusion_matrix(y_test, log_pred)
print(log_reg_tab)
sns.heatmap(log_reg_tab, annot=True, fmt="d", cmap="PuRd")
plt.title("Confusion Matrix")
plt.show()

print(classification_report(y_test, log_pred))

#Comparing Classification Methods
models = {
    "K-Nearest Neighbors": KNeighborsClassifier(n_neighbors = 10),
    "Support Vector Machine": SVC(kernel="rbf", C=1.0, gamma="scale"),
    "Random Forest": RandomForestClassifier(n_estimators=100, random_state=42),
    "Logistic Regression": LogisticRegression(max_iter=1000, solver='lbfgs')
}

for name, model in models.items():
    model.fit(X_train_scaled, y_train)
    y_eval = model.predict(X_test_scaled)

    acc_eval = accuracy_score(y_test, y_eval)
    prec_eval = precision_score(y_test, y_eval, average='macro')
    rec_eval = recall_score(y_test, y_eval, average='macro')
    f1_eval = f1_score(y_test, y_eval, average='macro')

    print(f"{name}:")
    print(f"Accuracy: {acc_eval:.3f}")
    print(f"Precision: {prec_eval:.3f}")
    print(f"Recall: {rec_eval:.3f}")
    print(f"F1 Score: {f1_eval:.3f}")
    print("-" * 40)

cv = StratifiedKFold(n_splits=5, shuffle=True, random_state=42)
le = LabelEncoder()
y_encoded = le.fit_transform(y)

for name, model in models.items():
    acc_scores = cross_val_score(model, scaler.fit_transform(X), y_encoded, cv=cv, scoring='accuracy')
    f1_scores = cross_val_score(model, scaler.fit_transform(X), y_encoded, cv=cv, scoring='f1_macro')

    print(f"{name}:")
    print(f"CV Accuracy: {acc_scores.mean():.3f} ± {acc_scores.std():.3f}")
    print(f"CV F1 Score: {f1_scores.mean():.3f} ± {f1_scores.std():.3f}")
    print("-" * 40)
