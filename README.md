# Sales Volume Prediction with Linear Regression

This repository contains my **first end-to-end machine learning project** 🎉  

The goal is to **predict product sales volume** using historical sales data and product / merchandising features such as:

- Product position in the store (aisle vs end-cap, etc.)
- Whether the product is on promotion
- Product category, section (MAN/WOMAN/KIDS), season
- Brand, material, origin
- Price and other basic attributes

The project walks through the typical ML workflow:

1. Loading and inspecting the dataset  
2. Exploratory data analysis (EDA)  
3. Data cleaning & feature engineering  
4. Training a **Linear Regression** model  
5. Evaluating performance  
6. Visualizing results (correlations, residuals, feature effects)

---

## 1. Project Objectives

- Build a **supervised regression** model that predicts `Sales Volume`.
- Understand which product and merchandising features most influence sales.
- Practice the full ML pipeline in Python using:
  - `pandas` for data handling  
  - `matplotlib` / `seaborn` for visualization  
  - `scikit-learn` for modeling

This project is mainly educational: it is designed to help me learn the ML workflow on a realistic business dataset.

---

## 2. Dataset

The main dataset is:

- `Business_sales_EDA.csv`

**Format**

- Semicolon-separated (`;`) CSV file.
- Each row represents a product in a certain configuration (position, promotion, season, etc.).

**Key columns**

- **Target**
  - `Sales Volume` – numeric value representing how much of the product was sold.

- **Features**
  - `Product Position` – where the product is placed (e.g. Aisle, Endcap).
  - `Promotion` – whether the product is on promotion (Yes/No).
  - `Product Category` – category of the product (e.g. clothing type).
  - `Seasonal` – whether this is a seasonal product.
  - `brand` – brand name.
  - `price` – numeric price of the product.
  - `currency` – currency code.
  - `terms` – commercial terms (if available).
  - `section` – section of the store (MAN / WOMAN / KIDS / etc.).
  - `season` – Spring / Summer / Fall / Winter.
  - `material` – main material of the product.
  - `origin` – country or region of origin.
  - (Additional text columns such as `name`, `url`, `description` may be used later for NLP, but are not part of the first basic model.)

Some columns are identifiers or long text and are intentionally **not** used in the first version of the ML model.

---

## 3. Methods and Approach

### 3.1. Data Loading & Cleaning

- Read the raw CSV with:

  ```python
  df = pd.read_csv("Business_sales_EDA.csv", sep=";")

