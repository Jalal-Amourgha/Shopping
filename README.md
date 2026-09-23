# CS50 AI — Shopping

An implementation of **Project 4: Shopping** from [CS50's Introduction to Artificial Intelligence with Python](https://cs50.harvard.edu/ai/).

The goal of this project is to build a machine learning model that predicts whether an online shopping session will result in a purchase. The project uses a **k-nearest-neighbor (KNN) classifier** from `scikit-learn`.

---

## 📌 Project Overview

Online shopping websites receive many visitors who browse products without completing a purchase. By analyzing information about a user's browsing session, it is possible to predict whether the user is likely to complete a purchase.

In this project, the AI uses information such as:

* Number of administrative pages visited
* Number of informational pages visited
* Number of product-related pages visited
* Time spent on different types of pages
* Bounce and exit rates
* Page values
* Month of the visit
* Operating system
* Browser
* Region
* Traffic type
* Visitor type
* Whether the visit occurred on a weekend

The target variable is `Revenue`, which indicates whether the user completed a purchase.

The model uses **K-Nearest Neighbors (KNN)** with `k = 1` to make its predictions.

---

## 🧠 Machine Learning Approach

The project consists of three main components:

### 1. Loading the Data

The `load_data` function reads the `shopping.csv` dataset and converts the categorical values into numerical representations suitable for machine learning.

It returns:

```text
(evidence, labels)
```

Where:

* `evidence` contains the features used to make predictions.
* `labels` contains the expected results (`0` or `1`).

### 2. Training the Model

The `train_model` function creates and trains a K-Nearest Neighbors classifier using:

```python
KNeighborsClassifier(n_neighbors=1)
```

The classifier is trained using the provided evidence and labels.

### 3. Evaluating Predictions

The `evaluate` function calculates two important metrics:

* **Sensitivity / True Positive Rate** — how accurately the model identifies users who completed a purchase.
* **Specificity / True Negative Rate** — how accurately the model identifies users who did not complete a purchase.

These metrics provide more useful information than accuracy alone because the dataset contains considerably more non-purchasing sessions than purchasing sessions.

---

## 📂 Project Structure

After downloading and extracting the project, your directory should look similar to:

```text
shopping/
├── shopping.py
├── shopping.csv
└── README.md
```

---

## 🛠️ Requirements

Before running the project, make sure you have:

* Python 3
* `pip3`
* `scikit-learn`

CS50 recommends using Python 3.12 for the course.

---

## 📥 Installation

### 1. Clone or download this repository

If you are using Git:

```bash
git clone https://github.com/Jalal-Amourgha/Shopping.git
cd shopping
```

Or simply download the project files manually.

### 2. Download the dataset

Download the official CS50 AI Shopping project distribution:

**Dataset / Project ZIP:**

https://cdn.cs50.net/ai/2023/x/projects/4/shopping.zip

You can also download it from the official CS50 project page.

After downloading, extract the ZIP file.

Make sure that `shopping.csv` is located in the same directory as `shopping.py`.

### 3. Install scikit-learn

Run:

```bash
pip3 install scikit-learn
```

This is the machine-learning library required by the project.

---

## ▶️ Running the Project

Once everything is installed, run:

```bash
python shopping.py shopping.csv
```

On some systems, you may need:

```bash
python3 shopping.py shopping.csv
```

The program will train the classifier, make predictions on the test data, and display the evaluation results.

Example output:

```text
Correct: 4088
Incorrect: 844
True Positive Rate: 41.02%
True Negative Rate: 90.55%
```

The exact results may depend on the implementation and environment.

---

## 📊 Evaluation Metrics

### Sensitivity

Sensitivity, also called the **True Positive Rate (TPR)**, measures the proportion of actual purchasing sessions that the model correctly identifies.

```text
Sensitivity = True Positives / (True Positives + False Negatives)
```

A higher sensitivity means the model is better at identifying users who actually completed a purchase.

### Specificity

Specificity, also called the **True Negative Rate (TNR)**, measures the proportion of non-purchasing sessions that the model correctly identifies.

```text
Specificity = True Negatives / (True Negatives + False Positives)
```

A higher specificity means the model is better at identifying users who did not complete a purchase.

CS50 uses these two metrics because accuracy by itself can be misleading when the classes are imbalanced.

---

## 📋 Dataset

The dataset contains approximately **12,000 user sessions** from an online shopping website.

Each row represents one user's session.

The final column, `Revenue`, is the label that the model attempts to predict:

```text
TRUE  → User completed a purchase
FALSE → User did not complete a purchase
```

The categorical values are converted into numerical values before being passed to the machine-learning model.

For example:

```text
VisitorType:
Returning_Visitor → 1
Other visitors    → 0
```

And:

```text
Weekend:
TRUE  → 1
FALSE → 0
```

Months are also converted to numerical values, beginning with January as `0` and December as `11`.

---

## 🧪 Testing

CS50 provides automated testing through `check50`.

You can test the project using:

```bash
check50 ai50/projects/2024/x/shopping
```

You can also check the style of your Python code with:

```bash
style50 shopping.py
```

These commands are documented in the official project specification.

> **Note:** Make sure you follow the version of the CS50 AI specification associated with your course session when submitting the assignment.

---

## 📚 Technologies Used

* **Python 3**
* **scikit-learn**
* **K-Nearest Neighbors (KNN)**
* **CSV data processing**
* **Supervised Machine Learning**

---

## 🎯 Learning Objectives

This project provides practical experience with:

* Supervised machine learning
* Classification
* K-nearest-neighbor algorithms
* Training and testing datasets
* Feature preprocessing
* Categorical data encoding
* Model evaluation
* Sensitivity and specificity

---

## 📖 CS50 AI

This project is part of **CS50's Introduction to Artificial Intelligence with Python**, Harvard University's introductory AI course.

Official course:

https://cs50.harvard.edu/ai/

Official Shopping project:

https://cs50.harvard.edu/ai/2023/projects/4/shopping/

---

## 📄 Academic Integrity

This repository is intended for **educational purposes**.

If you are currently completing the CS50 AI assignment, make sure your work follows the course's academic honesty and submission requirements. The purpose of the project is to understand and implement the machine-learning concepts yourself.

---

## 🙏 Acknowledgements

This project is based on the Shopping assignment from **CS50's Introduction to Artificial Intelligence with Python**.

The dataset is attributed by CS50 to:

> Sakar, C. O., Polat, S. O., Katircioglu, M. et al. *Neural Computing and Applications* (2018).

---

## ⭐ Project

**CS50 AI — Project 4: Shopping**

Built with Python and scikit-learn.

