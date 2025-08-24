# 🚀 Linear Regression with Stochastic Gradient Descent (From Scratch!)

Welcome! 👋  
This project is all about understanding **Linear Regression** and building **Stochastic Gradient Descent (SGD)** from scratch – without relying on built-in optimizers.  

If you’ve ever wondered *"How does scikit-learn’s SGDRegressor actually work under the hood?"* 🤔 → this repo is for you.  

---

## 📌 Project Workflow

1. **Dataset**  
   - Used `load_diabetes` dataset from `sklearn.datasets`.

2. **Baseline Model (Linear Regression)**  
   - Performed a **train-test split**.  
   - Trained a Linear Regression model using scikit-learn.  
   - Got an **R² score = 0.4399** 🎯

3. **Custom SGD Regressor (From Scratch)**  
   - Implemented my own class `MySGDRegressor`.  
   - **Hyperparameters:** default `learning_rate = 0.01`, `epochs = 100` (user can override).  
   - **Initialization:**  
     - Coefficients = zeros (size = number of features).  
     - Intercept = 0.  
   - **Training Loop:**  
     - Outer loop runs for `epochs`.  
     - Inner loop runs over training rows.  
     - Randomly pick a training index (`idx`).  
     - Predict `y_hat` for that row.  
     - Compute gradients:  
       - Intercept derivative: `-2 * (y_train[idx] - y_hat)`  
       - Coefficient derivative: `-2 * np.dot((y_train[idx] - y_hat), X_train[idx])`  
     - Update intercept & coefficients using learning rate.  
   - **Predict Method:** Simple dot product with learned coefficients.  
   - **Result:** R² score ≈ **0.43**

4. **Comparison with scikit-learn’s SGDRegressor**  
   - Used `SGDRegressor` from `sklearn.linear_model`.  
   - With `lr = 0.02` and `epochs = 100` → R² ≈ **0.42**.  
   - Shows that with proper tuning, **our scratch implementation matches sklearn’s performance** ✅

---

## 📊 Results

| Model                         | R² Score |
|-------------------------------|----------|
| Linear Regression (sklearn)   | 0.4399   |
| Custom SGD Regressor (Scratch)| 0.43     |
| SGDRegressor (sklearn)        | 0.42     |

---

## ⚡ Key Learnings

- SGD updates **one row at a time** (faster & scalable).  
- Proper tuning of **learning rate** and **epochs** is crucial.  
- From-scratch implementation helps in **understanding the math behind ML models** instead of just using libraries.  

---

## 🛠️ How to Run

```bash
# Clone this repo
git clone https://github.com/yourusername/sgd-linear-regression.git

# Open the notebook or script
cd sgd-linear-regression
