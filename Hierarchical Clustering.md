# 🛍️ Customer Segmentation Using Hierarchical Clustering

## 🧩 Problem Statement

A **shopping mall** has collected customer information, including:

- **Customer ID**
- **Gender**
- **Age**
- **Annual Income (USD)**
- **Spending Score** (assigned by the mall based on purchasing behavior)

The goal is to **group customers into distinct categories** based on their purchasing patterns and demographics.  
By using **Hierarchical Clustering**, the mall can better understand its customer base and create targeted marketing strategies.

---

## 🎯 Objective

> Use **Hierarchical Clustering** to segment mall customers into meaningful groups based on **Annual Income** and **Spending Score**, helping the marketing team personalize promotions.

---

## 📊 Dataset Example

| Customer ID | Gender | Age | Annual Income (k$) | Spending Score (1–100) |
|-------------|--------|-----|--------------------|------------------------|
| 1           | Male   | 19  | 15                 | 39                     |
| 2           | Male   | 21  | 15                 | 81                     |
| 3           | Female | 20  | 16                 | 6                      |
| 4           | Female | 23  | 16                 | 77                     |
| 5           | Female | 31  | 17                 | 40                     |

---

## 🔍 Why Hierarchical Clustering?

- Does not require **predefining the number of clusters**
- Produces a **dendrogram** that visually represents cluster merging
- Works well for **small to medium datasets**
- Can reveal **natural customer groupings**

---

## 🧪 Approach

1. **Import** libraries (`pandas`, `matplotlib`, `scipy`, `sklearn`)
2. **Select Features**: Annual Income and Spending Score
3. **Use Dendrogram** to determine the optimal number of clusters
4. **Fit Agglomerative Hierarchical Clustering**
5. **Visualize** the clusters

---

## 🖥️ Example Code

```python
import pandas as pd
import matplotlib.pyplot as plt
import scipy.cluster.hierarchy as sch
from sklearn.cluster import AgglomerativeClustering

# Load dataset
df = pd.read_csv("Mall_Customers.csv")
X = df.iloc[:, [3, 4]].values  # Annual Income & Spending Score

# Create dendrogram
plt.figure(figsize=(8, 5))
dendrogram = sch.dendrogram(sch.linkage(X, method='ward'))
plt.title('Dendrogram')
plt.xlabel('Customers')
plt.ylabel('Euclidean distances')
plt.show()

# Fit Hierarchical Clustering
hc = AgglomerativeClustering(n_clusters=5, affinity='euclidean', linkage='ward')
y_hc = hc.fit_predict(X)

# Plot clusters
plt.figure(figsize=(8, 5))
plt.scatter(X[y_hc == 0, 0], X[y_hc == 0, 1], label='Cluster 1')
plt.scatter(X[y_hc == 1, 0], X[y_hc == 1, 1], label='Cluster 2')
plt.scatter(X[y_hc == 2, 0], X[y_hc == 2, 1], label='Cluster 3')
plt.scatter(X[y_hc == 3, 0], X[y_hc == 3, 1], label='Cluster 4')
plt.scatter(X[y_hc == 4, 0], X[y_hc == 4, 1], label='Cluster 5')
plt.title('Customer Segments')
plt.xlabel('Annual Income (k$)')
plt.ylabel('Spending Score (1–100)')
plt.legend()
plt.show()
```

---

## ✅ Outcome

The mall will obtain **customer groups** such as:
- **High income, high spenders** → Premium customers
- **Low income, high spenders** → Budget-conscious but loyal
- **High income, low spenders** → Potential upsell targets
- **Low income, low spenders** → Low priority marketing

---

## 🧠 Summary

Hierarchical clustering allows the mall to:
- **Understand customer behavior**
- **Target marketing campaigns**
- **Improve customer retention and satisfaction**

By grouping customers into **natural clusters**, marketing becomes more data-driven and efficient.

