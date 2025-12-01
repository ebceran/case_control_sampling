# case_control_sampling
Case Control Sampling

A mini but professional-level project demonstrating how to handle imbalanced data in financial modeling.

Case–Control Sampling & Intercept Correction

A practical demonstration of how banks and fintech companies deal with rare events such as credit defaults and fraud.


* Project Overview

In real-world financial datasets, positive cases are extremely rare:

credit defaults → ~2%

fraud → ~0.1%

AML suspicious activity → ~0.01%

customer churn → ~5%

A standard logistic regression model fails badly on such imbalanced data,
because it learns to always predict the majority class.

To solve this problem, banks use:

- Case–Control Sampling
- Intercept Bias Correction (as taught in Stanford Statistical Learning)

This project demonstrates both techniques clearly and practically.

** What This Project Teaches

1️⃣ Creating an imbalanced financial dataset

We synthetically simulate 5000 customers with:

age

income

number of late payments

Only 2% of these customers default — mimicking real credit risk datasets.


2️⃣ Applying Case–Control Sampling

We take:

all defaulting customers (cases)

an equal number of non-defaults (controls)

This creates a balanced dataset that allows logistic regression to actually learn the patterns instead of guessing “always 0”.


3️⃣ Training Logistic Regression

The model is trained on the sampled (balanced) dataset.

It learns the correct direction of effects:

older customers → lower risk

higher income → lower risk

late payments → strong risk factor

However, the intercept becomes biased, because the sample no longer reflects true population rates.


4️⃣ Correcting the Intercept

We apply the Stanford Statistical Learning correction:
<img width="446" height="108" alt="image" src="https://github.com/user-attachments/assets/2558326a-f147-4670-b9af-52a0ee3a4675" />

Where:

π = true default rate

q = sampled dataset default rate

This adjusts the model so it outputs realistic default probabilities.

This is exactly how banks fix models before deploying them.


5️⃣ Visualizing Probability with Corrected Intercept

A final sigmoid curve shows how default probability changes with the number of late payments — using the corrected intercept.

This represents a real-world credit scoring effect curve.

* Why This Project Matters in Banking & FinTech

Case–control sampling is essential in:

credit scoring

fraud detection

AML investigations

risk modelling

collections strategies

churn prediction

*Understanding this concept shows that you:

- know how rare events behave
- understand logistic regression deeply
- can work with imbalanced financial datasets
- can apply statistical corrections correctly
- can think like a real risk analyst / data scientist

This is exactly what hiring managers look for.

* Skills Demonstrated

Python (NumPy, Pandas, Scikit-Learn, Matplotlib)

Logistic Regression

Imbalanced Data Handling

Sampling vs Population Bias

Statistical Correction of Intercept

Probability Curve Interpretation

Data Science in Financial Risk

* Next Steps

This project is part of an ongoing series focused on financial data science:

- Basic Logistic Regression Project

- Case–Control Sampling Project (this one)

+ Scorecard-Style Credit Model

+ Fraud Detection Simulation

+ Customer Churn Modelling

+ Time-Series Forecasting (Monthly Revenue / Stock Data)

Each project builds a stronger foundation for working in:

credit risk

fraud analytics

fintech data science

financial machine learning

Author
Emine Ceran
