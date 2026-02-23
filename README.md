

# MLOps Project - Vehicle Insurance End-to-End Data Pipeline

> Production-ready **MLOps pipeline** that covers the complete ML lifecycle — from data ingestion to CI/CD deployment on AWS.

---

## ✨ Project Overview

This project demonstrates a **full-stack MLOps implementation** designed for scalability, reproducibility, and automation.
It integrates **MongoDB, AWS, Docker, GitHub Actions, and FastAPI/Streamlit-style serving** to simulate a real-world ML production workflow.

💡 **Goal:** Build a robust pipeline that automatically:

* Ingests data from MongoDB
* Validates and transforms features
* Trains and evaluates models
* Pushes best model to AWS S3
* Deploys via Docker + CI/CD
* Serves predictions via web app

---

## 🏗️ Architecture

```
MongoDB → Data Ingestion → Data Validation → Data Transformation
        → Model Trainer → Model Evaluation → Model Pusher (AWS S3)
        → Prediction Pipeline → CI/CD → EC2 Deployment
```

---

## 🚀 Key Features

✅ Modular MLOps pipeline
✅ MongoDB Atlas integration
✅ Automated data validation with schema
✅ Feature engineering pipeline
✅ Model versioning on AWS S3
✅ Docker containerization
✅ GitHub Actions CI/CD
✅ Self-hosted runner on EC2
✅ Production deployment ready
✅ Environment-variable based security
✅ Custom logging & exception handling

---

## 🛠️ Tech Stack

### 👨‍💻 Programming & ML

* Python 3.10
* Scikit-learn
* Pandas, NumPy
* YAML

### ⚙️ MLOps & Backend

* FastAPI / App serving
* Docker
* GitHub Actions
* Self-Hosted Runner

### ☁️ Cloud & Storage

* MongoDB Atlas
* AWS S3
* AWS ECR
* AWS EC2
* AWS IAM

---

## 📂 Project Structure

```
.
├── src/
│   ├── components/
│   ├── configuration/
│   ├── entity/
│   ├── aws_storage/
│   ├── data_access/
│   ├── exception/
│   └── logger/
│
├── notebook/
├── templates/
├── static/
├── .github/workflows/
├── app.py
├── Dockerfile
├── requirements.txt
├── setup.py
└── pyproject.toml
```

---

# 🔧 Setup Guide

## 1️⃣ Project Initialization

```bash
python template.py
```

Configure local package imports:

* `setup.py`
* `pyproject.toml`

---

## 2️⃣ Environment Setup

```bash
conda create -n vehicle python=3.10 -y
conda activate vehicle
pip install -r requirements.txt
pip list
```

---

# 🍃 MongoDB Setup

### Steps

1. Create MongoDB Atlas project
2. Create **M0 free cluster**
3. Create DB user
4. Add IP: `0.0.0.0/0`
5. Copy Python connection string

### Environment Variable

**Bash**

```bash
export MONGODB_URL="your_connection_string"
```

**PowerShell**

```powershell
$env:MONGODB_URL="your_connection_string"
```

---

# 📊 Pipeline Components

## 🔹 Data Ingestion

* Connects to MongoDB
* Converts JSON → DataFrame
* Stores raw artifacts

## 🔹 Data Validation

* Schema-based validation
* Data drift checks
* Missing value checks

## 🔹 Data Transformation

* Feature engineering
* Train/test split
* Preprocessing pipeline

## 🔹 Model Trainer

* Model training
* Hyperparameter tuning
* Best model selection

## 🔹 Model Evaluation

* Compares with production model
* Threshold-based acceptance

## 🔹 Model Pusher

* Uploads model to AWS S3
* Maintains model registry

---

# ☁️ AWS Setup

## IAM

Create user:

```
firstproj
```

Attach:

```
AdministratorAccess
```

---

## Environment Variables

**Bash**

```bash
export AWS_ACCESS_KEY_ID="xxx"
export AWS_SECRET_ACCESS_KEY="xxx"
```

**PowerShell**

```powershell
$env:AWS_ACCESS_KEY_ID="xxx"
$env:AWS_SECRET_ACCESS_KEY="xxx"
```

---

## S3 Bucket

```
Bucket name: my-model-mlopsproj
Region: us-east-1
```

---

# 🐳 Docker Setup

### Build Image

```bash
docker build -t vehicleproj .
```

### Run Container

```bash
docker run -p 5080:5080 vehicleproj
```

---

# 🔄 CI/CD Pipeline

## GitHub Actions Workflow

Triggers on:

* push
* pull request

Pipeline:

```
Code Push → Build Docker → Push to ECR → Deploy on EC2
```

---

## Required GitHub Secrets

* `AWS_ACCESS_KEY_ID`
* `AWS_SECRET_ACCESS_KEY`
* `AWS_DEFAULT_REGION`
* `ECR_REPO`

---

# 🖥️ EC2 Deployment

### Instance Config

* Ubuntu Server 24.04
* t2.medium
* 30 GB storage

---

## Install Docker on EC2

```bash
sudo apt-get update -y
sudo apt-get upgrade
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo usermod -aG docker ubuntu
newgrp docker
```

---

## Activate App Port

Open inbound rule:

```
Custom TCP → Port 5080 → 0.0.0.0/0
```

---

# 🌐 Run the Application

```
http://<EC2-PUBLIC-IP>:5080
```

---

## 🧪 Training Endpoint

```
/training
```

Triggers full training pipeline.

---

# 📈 What Makes This Project Production-Ready

* ✔ Modular architecture
* ✔ Environment-based secrets
* ✔ Automated CI/CD
* ✔ Cloud model registry
* ✔ Containerized deployment
* ✔ Scalable design
* ✔ Industry-style folder structure

---

# 👨‍💻 Author

**Suyash Sharma**
Aspiring AI/ML & GenAI Engineer

---

---

