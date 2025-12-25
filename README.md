# End-to-End MLOps Pipeline | CI/CD, Docker, Flask, scikit-learn

## 📌 Project Overview

This repository demonstrates a **production-style MLOps workflow** covering **model training, evaluation, artifact management, containerization, and CI automation**.

The project trains a **Logistic Regression model on the Iris dataset**, saves the model and metrics as artifacts, exposes inference via a **Flask REST API**, and automates training using **GitHub Actions CI**.

This project is designed to showcase **real-world MLOps & DevOps skills** relevant for roles such as **MLOps Engineer, DevOps Engineer, ML Engineer, and Platform Engineer**.

---

## 🧠 Key Features (ATS-Optimized)

* ✅ Automated **CI/CD pipeline** using **GitHub Actions** for machine learning workflows
* ✅ **Model training automation** with reproducible environments
* ✅ **Python matrix builds** (Python 3.11, 3.12) for compatibility testing
* ✅ **Model artifact management** (model.pkl, metrics.json)
* ✅ **RESTful API** for ML inference using **Flask**
* ✅ **Docker containerization** for production deployment
* ✅ Separation of concerns: training, inference, serving

---

## 🏗️ Project Architecture

```
.
├── .github/workflows/
│   └── ci.yml                # CI pipeline for training & artifact upload
├── artifacts/
│   ├── model.pkl             # Trained ML model
│   └── metrics.json          # Model evaluation metrics
├── app.py                    # Flask inference API
├── train.py                  # Model training script
├── run_model.py              # CLI-based inference
├── requirements.txt          # Python dependencies
├── Dockerfile                # Container definition
└── README.md
```

---

## ⚙️ Tech Stack (Keywords for Recruiters & ATS)

* **Language:** Python 3.11 / 3.12
* **ML:** scikit-learn (Logistic Regression)
* **API:** Flask
* **CI/CD:** GitHub Actions
* **Containerization:** Docker
* **Artifact Handling:** GitHub Artifacts

---

## 🚀 CI/CD Pipeline – GitHub Actions

The CI pipeline automatically:

1. Runs on every push & pull request to `main`
2. Uses a **matrix strategy** for Python 3.11 and 3.12
3. Installs dependencies
4. Trains the ML model
5. Saves model & metrics to `artifacts/`
6. Uploads artifacts for traceability

**Sample metric output:**

```json
{
  "accuracy": 1.0
}
```

---

## 🧪 Model Training

Run locally:

```bash
python train.py
```

This will:

* Train a Logistic Regression model on the Iris dataset
* Save the model to `artifacts/model.pkl`
* Save evaluation metrics to `artifacts/metrics.json`

---

## 🔍 CLI-Based Inference

Run predictions directly from the command line:

```bash
python run_model.py --input "[5.1, 3.5, 1.4, 0.2]"
```

Output:

```json
{"prediction": [0]}
```

---

## 🌐 Flask REST API

Start the server:

```bash
python app.py
```

### Health Check

```bash
GET /health
```

Response:

```json
{"status": "ok"}
```

### Prediction Endpoint

```bash
POST /predict
```

Payload:

```json
{
  "features": [5.1, 3.5, 1.4, 0.2]
}
```

Response:

```json
{"prediction": 0}
```

---

## 🐳 Docker Support

### Build Image

```bash
docker build -t ml-flask-app .
```

### Run Container

```bash
docker run -p 5001:5001 ml-flask-app
```

The app will be available at:

```
http://localhost:5001
```

---

This repository demonstrates:

* Real CI/CD workflows for ML systems
* Reproducible ML pipelines
* Production-ready API design
* Artifact tracking and automation mindset
* Strong DevOps + MLOps fundamentals

It reflects how ML models are **trained, validated, packaged, and served in real production environments**.

---

## 🔮 Future Enhancements

* Add DVC for data & model versioning
* Add unit tests and model validation checks
* Push Docker image to Docker Hub / ECR
* Deploy on AWS / Azure / GCP
* Add monitoring & logging

---

## 👤 Author

**Anurag Patel**
MLOps / DevOps Engineer

---

⭐ If you find this project useful, feel free to star the repo!
