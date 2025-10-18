
---

 📊 Dataset
The dataset contains detailed laptop specifications such as:
- **Company** – Brand name (e.g., Dell, Apple, Lenovo)
- **TypeName** – Laptop type (Notebook, Ultrabook, Gaming, etc.)
- **Inches** – Screen size  
- **Cpu / Gpu** – Processor and graphics information  
- **Ram / Memory** – System memory and storage capacity  
- **OpSys** – Operating system  
- **Price_euros** – Target variable (laptop price)

---
 🔍 Exploratory Data Analysis (EDA)
Performed EDA using **Seaborn** and **Matplotlib** to identify key insights:
- Laptops with higher **RAM** and **SSD storage** cost significantly more.  
- **MacBooks** and **Workstation** types are among the most expensive.  
- Price distribution lies mainly between **€500 – €1500**.

---

⚙️ Data Preprocessing
- Cleaned and formatted data columns (`Weight`, `Ram`, `Memory`, etc.)
- Handled outliers using IQR method  
- Scaled numeric features with **StandardScaler**  
- Encoded categorical variables with **LabelEncoder**  
- Combined all processed features into a single final dataset for modeling

---

 Model Building
Trained multiple regression algorithms:
| Model | Description | R² (Test) | Remarks |
|--------|--------------|-----------|----------|
| **Linear Regression** | Baseline model | ~0.70 | Simple and interpretable |
| **Decision Tree Regressor** | Non-linear model | ~0.85 | Captures feature interactions |
| **Random Forest Regressor** | Ensemble method | ~0.90 | Reduces overfitting |
| **AdaBoost & Gradient Boosting** | Boosted ensemble | ~0.92 | Improved accuracy |
| **XGBoost Regressor** | Final chosen model | **~0.95** | Best performing |
| **SVR** | Kernel-based model | ~0.88 | Decent generalization |

 **XGBoost** was selected as the final model for its **high accuracy and low RMSE**.

---

## 🧪 Model Evaluation
- Metrics used: **R² Score**, **RMSE**
- Performed **5-Fold Cross-Validation** to ensure model stability.
- Saved the trained model with **Joblib** for deployment.

---

🌍 Deployment (Streamlit)
A user-friendly **Streamlit app** was developed for real-time laptop price predictions.

 Features:
- Interactive UI for entering laptop specifications  
- Instant price predictions in **Euros, Indian Rupees, and USD**  
- Responsive layout and currency conversion  
- Integrated with **Ngrok** for live hosting

To run locally:
```bash
pip install -r requirements.txt
streamlit run app.py
