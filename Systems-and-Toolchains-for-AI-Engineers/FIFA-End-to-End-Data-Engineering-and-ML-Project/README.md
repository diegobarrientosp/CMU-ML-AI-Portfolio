#  **FIFA End-to-End Data Engineering & Machine Learning Project**

---

## 🚀 **1. Introduction**

This project implements a **complete end-to-end data engineering and machine learning pipeline** using the FIFA-22 player dataset. It covers every major stage of a modern ML system, including:

* Data ingestion & transformation
* SQL database design and population
* Scalable feature engineering with PySpark
* Classical ML modeling (Linear Regression & Random Forest)
* Deep Learning with PyTorch (GPU-accelerated)
* Cloud-ready architecture and Kafka streaming integration

The objective is to demonstrate strong engineering practices for **reliable**, **scalable**, and **reproducible** machine learning systems.

---

## ⚙️ **2. Tools & Technologies Used**

### **🧱 Data Engineering**

* **PostgreSQL** — relational storage for structured FIFA data
* **SQL (DDL + queries)** — table creation, constraints, and ingestion
* **PySpark** — distributed processing & scalable feature engineering

### **🧠 Machine Learning**

* **PySpark MLlib** — baseline models (Linear Regression, Random Forest)
* **PyTorch** — GPU-accelerated neural networks with customized architectures

### **📊 Additional Libraries**

* Pandas
* Matplotlib
* Seaborn
* confluent_kafka
* google-api-python-client

Tools were selected to simulate a **real-world ML pipeline**, mixing big-data frameworks (Spark), SQL databases, and deep learning tooling.

---

## 📂 **3. Repository Structure**

```
FIFA-End-to-End-Data-Engineering-and-ML-Project/
│
├── notebooks/              # Main notebooks (local + cloud versions)
│   ├── Project_Final.ipynb
│   └── Project_Final_Cloud.ipynb
│
├── sql/                    # PostgreSQL schema + ingestion query
│   └── Create_fifa_table.sql
│
├── models/                 # Saved trained PyTorch model
│   └── best_model_shallow_4.pt
│
├── data/                   # Data link only (no CSVs stored)
│   └── README.md           # Dataset download link from Kaggle
│
├── README.md               # Project documentation
└── .gitignore
```

---

## 📥 **4. Dataset**

The dataset used in this project is publicly available on Kaggle:

🔗 **[https://www.kaggle.com/stefanoleone992/fifa-22-complete-player-dataset](https://www.kaggle.com/stefanoleone992/fifa-22-complete-player-dataset)**

**Note:**
CSV files are **not included** in the repository due to size limits.
Users should download the files from Kaggle and place them in the appropriate local directory.

---

## 🛠️ **5. How to Run the Project**

### **Local Execution**

1. Install dependencies from the notebook or your own environment
2. Load the dataset downloaded from Kaggle
3. Execute `Project_Final.ipynb`

### **Cloud Execution**

If running on Dataproc / Google Cloud:
Execute `Project_Final_Cloud.ipynb`, which is adapted for cloud-based Spark runtime.

---

## 🧪 **6. Machine Learning Models Implemented**

### **PySpark Baselines**

| Model             | RMSE  | MAE   | R²    | Notes                  |
| ----------------- | ----- | ----- | ----- | ---------------------- |
| Linear Regression | ~1.86 | ~1.43 | ~0.93 | Strong simple baseline |
| Random Forest     | ~1.15 | ~0.82 | ~0.97 | **Best overall model** |

### **PyTorch Neural Networks**

Four architectures were developed and tested:

* **NN-1:** Simple baseline
* **NN-2:** Increased regularization
* **NN-3:** Deeper model with dropout
* **NN-4:** *Best NN model* (balanced depth & regularization)

Final NN performance (best):

* RMSE ≈ 2.94
* MAE ≈ 2.32
* R² ≈ 0.82

**Conclusion:**
Random Forest generalizes best for this problem, outperforming neural networks.

---

## 🏗️ **7. Project Workflow Overview**

1. **Load raw FIFA CSVs**
2. **Create PostgreSQL table** using `Create_fifa_table.sql`
3. **Ingest data** into database
4. **Load into PySpark** for scalable feature engineering
5. **Train ML models**
6. **Evaluate performance** across models
7. **Train Deep Learning models** in PyTorch (GPU)
8. **Save best model** to `/models/`
9. *(Optional)* **Kafka streaming** to process YouTube comments in real-time
