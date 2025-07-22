# 📊 Simple Data Pipeline

This is a simple data pipeline project built with Python and Docker to demonstrate how to extract, transform, and load (ETL) data using a clean and reproducible environment.

It processes a medical dataset in CSV format by:

- Extracting the raw data
- Cleaning and transforming it (removing nulls and standardizing column names)
- Saving the cleaned data to a new CSV file

---

## 🧰 Tech Stack

- Python 3.10
- pandas
- Docker & Docker Compose

---

## 📁 Project Structure

```
simple-data-pipeline/
├── app/
│   └── pipeline.py              # Main ETL script
├── data/
│   ├── Medicaldataset.csv       # Raw medical data (input)
│   └── CleanedMedicalData.csv   # Cleaned data (output)
├── Dockerfile                   # Docker image build definition
├── docker-compose.yml           # Runs the pipeline as a container
├── requirements.txt             # Python dependencies
└── README.md
```

---

## ⚙️ How to Run

### 🔹 Option 1: Docker (recommended)

Make sure you have Docker installed. Then run:

```bash
docker compose up --build
```

This will:

- Build the container image
- Mount the `data/` folder
- Run the `pipeline.py` script inside the container

When completed, you’ll see:

```bash
Data Extraction completed.
Data Transformation completed.
Data Loading completed.
Data pipeline completed successfully.
```

Check `data/CleanedMedicalData.csv` for the result.

---

### 🔸 Option 2: Run locally (Python only)

1. Create and activate a virtual environment (optional but recommended):

```bash
python -m venv venv
venv\Scripts\activate  # On Windows
```

2. Install the dependencies:

```bash
pip install -r requirements.txt
```

3. Run the pipeline:

```bash
python app/pipeline.py
```

---

## ✅ Sample Output (first rows)

```csv
age,gender,heart_rate,systolic_blood_pressure,diastolic_blood_pressure,blood_sugar,ck-mb,troponin,result
64,1,66,160,83,160,1.8,0.012,negative
21,1,94,98,46,296,6.75,1.06,positive
...
```

---

## 🧠 Ideas for Extensions

Here are a few ideas to evolve this project:

### 🔍 1. **Data Validation**

Use `pydantic` or `pandera` to validate input data types and ranges.

### 📊 2. **Data Visualization**

Add a Jupyter notebook or a Streamlit dashboard to show:

- Distribution of results
- Correlations between features
- Outliers

### 📁 3. **Database Integration**

Instead of writing to a CSV, send the cleaned data to:

- PostgreSQL
- SQLite
- Google BigQuery (for cloud-based pipeline)

### 🛆 4. **Scheduled Pipelines**

Use `Apache Airflow`, `Prefect` or a simple `cron job` to schedule regular runs.

### ☁️ 5. **Cloud Deployment**

Containerize it on AWS ECS, Lambda (with Layers), or GCP Cloud Run.

---

[📘 Source: KDnuggets](https://www.kdnuggets.com/2020/01/top-20-data-science-pipeline.html)


## 👤 Author

**Paulo Chernicharo**\
[GitHub](https://github.com/pchernic)\
[LinkedIn](https://www.linkedin.com/in/pchernic/)

