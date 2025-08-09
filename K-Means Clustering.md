# 🛍️ Customer Segmentation Using K-Means Clustering

## 🧩 Problem Statement

A **shopping mall** has collected customer data including the following features:

- **Customer ID**
- **Gender**
- **Age**
- **Annual Income**
- **Spending Score**

The mall wants to **segment customers into distinct groups** based on their purchasing behavior and demographics to tailor marketing strategies and improve customer engagement.

---

## 🎯 Objective

> Use **K-Means Clustering** to group customers into different categories (clusters) based on their:
> - Annual Income  
> - Spending Score

These clusters will help the mall identify patterns and target specific customer groups with personalized promotions.

---

## 📊 Why K-Means Clustering?

- It is an **unsupervised learning** algorithm suitable for discovering natural groupings in data.
- Simple and efficient for segmenting customers.
- Helps in identifying distinct clusters such as **high-income low-spenders**, **young high-spenders**, etc.

---

## 🧪 Dataset Example

| Customer ID | Gender | Age | Annual Income (k$) | Spending Score (1-100) |
|-------------|---------|-----|--------------------|-----------------------|
| 1           | Male    | 19  | 15                 | 39                    |
| 2           | Female  | 21  | 16                 | 81                    |
| 3           | Female  | 20  | 17                 | 6                     |
| 4           | Male    | 23  | 35                 | 77                    |
| 5           | Female  | 31  | 45                 | 40                    |

---

## 🤖 Process Overview

1. **Data Preprocessing**  
   - Encode categorical variables (e.g., Gender) if needed  
   - Scale features for better clustering performance if needed

2. **Apply K-Means Algorithm**  
   - Choose the number of clusters (k) using methods like the Elbow Method  
   - Fit the model to the dataset  

3. **Analyze Clusters**  
   - Understand characteristics of each cluster  
   - Visualize clusters using scatter plots or dimensionality reduction  

4. **Business Application**  
   - Tailor marketing strategies for each customer segment  
   - Identify high-value customers or potential churn risks  

---

## ✅ Expected Outcome

- Clear customer segments that differ by spending behavior, income, and demographics  
- Improved targeted marketing and customer satisfaction  
- Data-driven insights for business growth  

---

## 📂 Notes

- Feature scaling (e.g., StandardScaler or MinMaxScaler) is important for K-Means  
- Consider multiple runs to ensure stable cluster assignment  

