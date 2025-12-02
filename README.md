# Case–Control Sampling & Intercept Correction  
*Handling Imbalanced Financial Data in Credit Default Modelling*

---

##  Overview  
Financial datasets are almost always **imbalanced**.  
In real banking and fintech environments:

- Defaults occur in ~2% of customers  
- Fraud happens in ~0.1% of transactions  
- AML suspicious cases appear in ~0.01%  
- Churn events may be around 3–5%

A standard Logistic Regression model **cannot learn meaningful patterns** from such rare events.  
Instead, it tends to predict the majority class every time, resulting in:

✔ high accuracy  
✘ zero real predictive value  

This project demonstrates how to fix this using:

### * Case–Control Sampling  
### * Intercept Bias Correction (Stanford Statistical Learning)

Both techniques are widely used in **credit risk**, **fraud detection**, and **fintech analytics**.

---

##  Project Goals  

This mini project aims to:

- Show why imbalanced datasets break standard logistic regression  
- Demonstrate how to oversample the rare class *without destroying statistical validity*  
- Train a logistic regression model on a balanced sample  
- Apply **bias correction** to recover realistic probability estimates  
- Visualize how corrected probabilities behave with respect to a key risk feature  

This project is intentionally simple and educational —  
a beginner-friendly introduction to real-world financial modelling workflows.

---

##  Dataset Simulation  

We simulate a dataset of **5,000 customers** with features typically used in credit scoring:

- `age`  
- `income`  
- `late_payments`  

Only **2%** of the customers default — matching real credit risk data.

A synthetic logistic function determines the underlying “true” probability of default.  
Labels (`default = 1/0`) are generated using this function.

---

##  Methodology  

### **1️⃣ Case–Control Sampling**  
To allow the model to learn meaningful patterns:

- we take **all default cases**  
- and randomly sample an equal number of non-default customers  

This produces a **50/50 balanced dataset**, ideal for logistic regression training.

---

### **2️⃣ Train Logistic Regression on Sampled Data**  
The model learns appropriate coefficients:

- age → slightly lowers risk  
- income → lowers risk  
- late payments → strong positive effect  

However, the intercept becomes **biased**, because the sampled dataset no longer reflects the real-world event rate.

---

### **3️⃣ Intercept Bias Correction**  
Using the formula from *Stanford Statistical Learning*:

\[
\beta_0^\* = \beta_0 + \log\left(\frac{\pi}{1-\pi}\right)  
            - \log\left(\frac{q}{1-q}\right)
\]

Where:

- π = true positive rate in full data (2%)  
- q = positive rate in sampled data (50%)  

After this correction, the model outputs **realistic default probabilities** suitable for practical use.

---

### **4️⃣ Probability Curve Visualization**  
A corrected sigmoid curve is plotted to show how default probability changes with `late_payments`.

This mirrors how **credit scorecards** and **risk effect plots** are generated in the banking industry.

---

## Why This Matters in Banking & FinTech  

Rare events are the backbone of financial risk analytics.  
Understanding Case–Control Sampling is essential for roles involving:

- Credit Risk Modelling  
- Fraud Analytics  
- Collections Strategy  
- Regulatory Modelling (FCA / PRA / Basel)  
- Fintech Risk & Data Science  
- Customer Churn Prediction  

This project demonstrates foundational knowledge required for these areas:

- handling imbalanced datasets  
- logistic regression understanding  
- probability correction  
- feature risk interpretation  

---

## How to Run the Notebook  

1. Clone the repository:  
   ```bash
   git clone https://github.com/ebceran/case_control_sampling.git
Open the notebook in Google Colab or Jupyter Notebook

Run all cells from top to bottom

 *Tools & Technologies
Python

NumPy

Pandas

Scikit-Learn

Matplotlib


*Author
Emine Ceran
Learning Financial Data Science & Statistical Modelling
Inspired by Stanford’s Statistical Learning course


*** Future Improvements
Add ROC curves & AUC metrics

Compare logistic regression vs tree-based models

Create a full credit scorecard version

Add real-world dataset integration (open source credit datasets)

yaml
Copy code

Author
Emine Ceran
