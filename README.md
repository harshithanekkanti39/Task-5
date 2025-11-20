
# Decision Trees & Random Forests

## 1. Introduction

Decision Trees and Random Forests are popular **tree-based machine learning algorithms** used for **classification and regression**.

They are intuitive, require minimal preprocessing, and provide interpretability through tree structures and feature importance.

---

## 2. Decision Tree Classifier

A Decision Tree is a flowchart-like structure that splits the data based on feature values.

### **2.1 How a Decision Tree Works**

* Splits the data using **Gini Impurity** or **Entropy**
* Repeats splitting until leaf nodes are formed
* Each leaf node represents a class label

### **2.2 Advantages**

* Easy to visualize
* No need for feature scaling
* Handles both numerical and categorical data

### **2.3 Disadvantages**

* High risk of **overfitting**
* Unstable (small changes → different tree)

---

## 3. Visualizing Decision Trees

Trees can be visualized using:

* `sklearn.tree.plot_tree()` (recommended — no external setup)
* Graphviz (optional — requires installation)

Visualization helps interpret splits, thresholds, and structure.

---

## 4. Overfitting in Decision Trees

Decision Trees tend to memorize training data.

### **How to control overfitting:**

* `max_depth`
* `min_samples_split`
* `min_samples_leaf`
* `max_leaf_nodes`

### Example:

Limiting `max_depth = 4` often reduces overfitting significantly.

---

## 5. Random Forest Classifier

A Random Forest is an **ensemble** of multiple Decision Trees.

### **5.1 How it works**

* Builds many trees on random subsets of data & features
* Uses **Bootstrap Aggregation (Bagging)**
* Final output: Majority vote (classification)

### **5.2 Why Random Forest is better**

* More stable than single decision tree
* Reduces overfitting
* Works well on almost all tabular datasets

---

## 6. Feature Importance

Random Forests provide global feature importance scores.

### **Types of importance:**

1. **Gini-based importance (default)**
2. **Permutation importance (better for industry)**

High importance values indicate features strongly used in splits.

---

## 7. Model Evaluation (Classification)

Key metrics:

* Accuracy
* Precision
* Recall
* F1 score
* Confusion Matrix
* ROC-AUC

Random Forests generally outperform Decision Trees on all these metrics.

---

## 8. Cross-Validation

Cross-validation helps ensure model stability.

### Example:

```
from sklearn.model_selection import cross_val_score
scores = cross_val_score(model, X, y, cv=5, scoring='accuracy')
```

Use cases:

* Compare models
* Select hyperparameters
* Measure stability

---

## 9. Industry Best Practices

* Use Random Forests as a **baseline model** for tabular data
* Tune hyperparameters using GridSearch only when required
* Avoid deep trees unless dataset is small
* Evaluate using cross-validation
* Prefer permutation importance for explanation
* Use pipelines to avoid leakage

---

## 10. Summary

Decision Trees provide interpretability, while Random Forests provide stability and improved accuracy. Together, they are powerful tools for solving classification and regression problems in industry.

They perform well out-of-the-box and are widely used in:

* Risk scoring
* Credit card fraud detection
* Medical diagnosis
* Customer segmentation

Both models are essential for any data science or machine learning portfolio.
