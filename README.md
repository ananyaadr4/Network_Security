# 🔐 Network Security Threat Detection using Machine Learning

An end-to-end machine learning project for detecting potential threats or intrusions in network traffic data. This pipeline automates everything from data ingestion to model deployment using Python, FastAPI, MongoDB, MLflow, and more.

---

## 🚀 Project Overview

This project builds a **production-grade machine learning pipeline** that:

- Ingests and validates network traffic data
- Detects and handles data drift
- Trains multiple ML classifiers with hyperparameter tuning
- Tracks experiments and metrics using MLflow & Dagshub
- Deploys a prediction service via FastAPI with file upload support

---

## 📦 Tech Stack

| Area              | Technology                          |
|-------------------|--------------------------------------|
| Language          | Python                              |
| Data Handling     | Pandas, NumPy, MongoDB (PyMongo)    |
| Machine Learning  | Scikit-learn                        |
| Experiment Tracking | MLflow, Dagshub                   |
| API & Deployment  | FastAPI, Uvicorn, Docker-ready      |
| Logging & Config  | Custom Logger, dotenv, YAML reports |
| Templates         | Jinja2 HTML                         |

---

## 🧩 Pipeline Components

### 1. **Data Ingestion**
- Reads network data from MongoDB Atlas.
- Stores raw CSV data locally.
- Splits into train/test datasets.

### 2. **Data Validation**
- Validates schema.
- Checks for missing values.
- Detects **data drift** using Kolmogorov–Smirnov test.
- Saves a `drift_report.yaml` for monitoring.

### 3. **Data Transformation**
- Applies scaling, encoding, and preprocessing.
- Saves the preprocessor as a `.pkl` file for inference use.
- Converts data into NumPy arrays for ML.

### 4. **Model Training**
- Models: `RandomForest`, `DecisionTree`, `GradientBoosting`, `LogisticRegression`, `AdaBoost`
- Performs hyperparameter tuning using grid search.
- Logs metrics (F1, Precision, Recall) to MLflow.
- Saves final model & preprocessor to disk.

### 5. **Model Tracking**
- MLflow integration via Dagshub
- Model registration with experiment metrics
- Remote model visualization and versioning

### 6. **Model Inference API**
- REST API built with FastAPI.
- `/train`: Runs full training pipeline.
- `/predict`: Upload CSV, receive prediction as an HTML table.
- Saves prediction output as `prediction_output/output.csv`.

---

## 📁 Project Structure
networksecurity/
│
├── components/ # Core modules (ingestion, validation, transformation, training)
├── constant/ # Constants like DB and collection names
├── entity/ # Config and artifact dataclasses
├── logging/ # Centralized logger
├── utils/ # Utility functions and custom model class
├── templates/ # Jinja2 HTML template for result rendering
├── final_model/ # Stores final model and preprocessor
├── prediction_output/ # Output folder for predictions
├── main.py # Pipeline runner script
├── app.py # FastAPI application entry point
├── .env # Environment variables (e.g., MongoDB URI)
├── requirements.txt # Project dependencies



📌 MLflow Tracking via Dagshub
✅ Status
✅ End-to-end ML pipeline working
✅ FastAPI with Swagger UI
✅ MLflow & Dagshub integration
✅ Preprocessor and model serialization


Author
👩‍💻 Ananya Adarsh



