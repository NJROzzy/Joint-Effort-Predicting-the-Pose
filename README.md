# Joint Effort: Predicting Robot End-Effector Pose  
**Machine Learning for Robotics (RBE 577) – Project 1**

## 📌 Overview
This project focuses on **learning forward kinematics using machine learning** for a **6-DOF UR10 robotic manipulator**.  
Given joint angles as input, the goal is to **predict the end-effector pose** (position + orientation) using multiple regression techniques.

The project explores:
- Linear Regression (Analytical & Gradient-Based)
- Feature Engineering inspired by robot kinematics
- Neural Networks (Multi-Layer Perceptron)
- Performance evaluation using multiple regression metrics

This work was completed as part of **RBE 577: Machine Learning for Robotics** :contentReference[oaicite:0]{index=0}.

---

## 🎯 Problem Statement
Given joint angles  
\[
(\theta_1, \theta_2, \dots, \theta_6)
\]

Predict the end-effector pose  
\[
(x, y, z, r_x, r_y, r_z)
\]

using supervised learning on a dataset of **100,000 UR10 configurations**.

---

## 📂 Dataset
- **File:** `ur10dataset.csv`
- **Samples:** 100,000
- **Inputs (6):** Joint angles (θ₁ … θ₆)
- **Outputs (6):** End-effector pose (x, y, z, rx, ry, rz)

The dataset is split into **training and testing sets** with proper preprocessing and normalization.

---

## 🧠 Methods Implemented

### 1️⃣ Linear Regression – Analytical Solution
- Implemented **from scratch** using the closed-form normal equation  
- Trained on a **subset of data** due to matrix inversion constraints  
- Used to study:
  - Computational limitations
  - Numerical stability
  - Bias–variance trade-offs

### 2️⃣ Linear Regression – Stochastic Gradient Descent
- Fully **class-based implementation**
- No PyTorch shortcuts for:
  - Loss computation
  - Weight updates
  - Predictions
- Supports:
  - Batch training
  - Metric tracking
  - Training & validation curves

### 3️⃣ Feature Engineering
Inspired by forward kinematics equations:
- Trigonometric transformations (`sin(θ)`, `cos(θ)`)
- Joint angle interactions
- Non-linear feature mappings

Performance with engineered features is compared against raw joint angles.

### 4️⃣ Neural Network (MLP)
- Implemented using **PyTorch**
- Multi-Layer Perceptron with hidden layers
- Trained on engineered features
- Evaluated against linear models

---

## 📊 Evaluation Metrics
Implemented in `helpers/metrics.py`:
- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- Mean Absolute Error (MAE)
- R² Score

Training and test loss curves are plotted to analyze:
- Overfitting
- Underfitting
- Convergence behavior

---

## 🗂️ Project Structure
