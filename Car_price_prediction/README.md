# 🚗 Car Price Prediction using Ridge Regression & OLS  

This project demonstrates how to predict **car prices** using **multiple linear regression techniques**.  
Since the dataset contains **many correlated features**, we apply **Ridge Regression with Cross-Validation** to prevent overfitting, and then compare it with the **Ordinary Least Squares (OLS)** model.  

---

## 📂 Dataset
- **Source:** [Car Price Dataset](https://drive.google.com/file/d/1PhtFDhA5mawGhI3V-zLVDu42k2mAwXXT/view?usp=sharing)  
- **Target:** `price_k` (car price in thousands)  
- **Features Used:**
  - `mileage`  
  - `engine_size`  
  - `horsepower`  
  - `torque`  
  - `doors`  
  - `airbags`  
  - `weight`  
  - `fuel_efficiency`  
  - `brand_score`  
  - `luxury_index`  

---

## ⚙️ Methods
1. **OLS Regression** – Fits all features without regularization (can overfit when multicollinearity exists).  
2. **Ridge Regression with Cross-Validation** – Penalizes large coefficients, handles correlated features better, and selects best `alpha` (regularization strength).  

---

## 📊 Results

### 🔹 Ridge Regression (Cross-Validation)
- **Best Alpha:** `10.0`  
- **Intercept:** `46.42`  
- **R² Score:** `0.51`  

| Feature          | Ridge Coefficient |
|------------------|------------------:|
| mileage          | -1.588 |
| engine_size      |  3.410 |
| horsepower       |  1.725 |
| torque           |  1.208 |
| doors            |  1.415 |
| airbags          |  1.868 |
| weight           |  2.196 |
| fuel_efficiency  | -0.375 |
| brand_score      |  0.899 |
| luxury_index     |  1.844 |

---

### 🔹 OLS Regression
- **Intercept:** `46.42`  
- **R² Score:** `0.51`  

| Feature          | OLS Coefficient |
|------------------|----------------:|
| mileage          | -1.766 |
| engine_size      |  5.003 |
| horsepower       |  1.456 |
| torque           |  0.827 |
| doors            |  1.451 |
| airbags          |  2.029 |
| weight           |  1.895 |
| fuel_efficiency  |  0.229 |
| brand_score      |  0.840 |
| luxury_index     |  2.010 |

---

## ✅ Insights
- Both Ridge and OLS give **similar R² (0.51)** → moderate explanatory power.  
- Ridge **shrinks coefficients** (e.g., `engine_size` 5.0 → 3.4) to reduce overfitting.  
- Regularization helps balance correlated features (`engine_size`, `horsepower`, `weight`).  
- Ridge regression is more **stable** and generalizable compared to OLS.  

---

## 🛠️ Technologies Used
- Python 🐍  
- Pandas & NumPy (data handling)  
- Scikit-learn (RidgeCV, LinearRegression)  
- Statsmodels (OLS)  
- Matplotlib / Seaborn (visualization)  

---

## 🚀 How to Run
```bash
# Clone repo
git clone https://github.com/your-username/car-price-prediction.git
cd car-price-prediction

# Install dependencies
pip install -r requirements.txt

# Run notebook
jupyter notebook car_price_prediction.ipynb
