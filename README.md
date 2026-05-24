# 🌆 Smart City – Real-Time Data Engineering Platform

## 📌 Project Overview

Smart City is an end-to-end real-time data engineering platform designed to simulate and process smart city data such as traffic, GPS, weather, cameras, and emergency events.

The project demonstrates how modern cities can collect massive streaming data, process it in real time, and store it in a cloud-based data lake for analytics and AI applications.

Built using **Apache Kafka**, **Apache Spark Structured Streaming**, and **Docker**.

---

## 🏗️ System Architecture

```
IoT Data Sources
(Vehicles, GPS, Cameras, Weather, Emergency)
        ↓
Apache Kafka (Streaming)
        ↓
Apache Spark Structured Streaming
        ↓
AWS S3 (Data Lake)
```

---

## ⚙️ Technologies Used

| Layer | Technology |
|---|---|
| Programming | Python 3 |
| Data Streaming | Apache Kafka, Apache Zookeeper |
| Data Processing | Apache Spark Structured Streaming |
| Storage | AWS S3 |
| Containerization | Docker, Docker Compose |

---

## 📂 Project Structure

```
SmartCity/
│
├── jobs/
│   ├── config.example.py   # Template for AWS credentials (copy → config.py)
│   ├── main.py             # Kafka producers & data simulation
│   └── spark-city.py       # Spark streaming processing job
│
├── ERD_Diagram.pdf         # Database entity relationship diagram
├── docker-compose.yml      # Kafka, Zookeeper, Spark cluster setup
├── requirements.txt        # Python dependencies
├── .gitignore
└── README.md
```

---

## 🔐 Setup Credentials

1. Copy `config.example.py` and rename it to `config.py`
2. Add your own AWS credentials inside it
3. **Never upload `config.py` to GitHub** — it is excluded via `.gitignore`

---

## 🚀 How to Run the Project

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/elattar10/smart-city.git
cd smart-city
```

### 2️⃣ Install Python Dependencies
```bash
pip install -r requirements.txt
```

### 3️⃣ Setup Config
```bash
cp jobs/config.example.py jobs/config.py
# Then open config.py and add your AWS keys
```

### 4️⃣ Start Services Using Docker
```bash
docker-compose up -d
```
This will start: Zookeeper, Kafka Broker, Spark Master, Spark Workers

### 5️⃣ Run Kafka Producers
```bash
python jobs/main.py
```

### 6️⃣ Run Spark Streaming Job
```bash
spark-submit jobs/spark-city.py
```

---

## 🔄 Data Flow

1. **Data Simulation** — Python scripts simulate smart city sensors (vehicle, GPS, weather, traffic, emergency)
2. **Kafka Streaming** — Each sensor type publishes to its own Kafka topic
3. **Spark Processing** — Spark consumes Kafka streams, applies schemas, and writes to AWS S3 in Parquet format

---

## 📊 Data Topics

| Topic | Description |
|---|---|
| `vehicle_data` | Vehicle info, speed, location |
| `gps_data` | GPS coordinates and direction |
| `traffic_data` | Camera snapshots and traffic events |
| `weather_data` | Temperature, wind, air quality |
| `emergency_data` | Accident, fire, medical alerts |

---

## 👨‍💻 Project Team

This project was built as part of the **DEPI Microsoft Data Engineer** program sponsored by the **Ministry of Communications & Information Technology of Egypt**.

| Name | Role |
|---|---|
| Mohamed Ebrahim | Team Lead |
| Mahmoud Ebrahim Elattar | Docker Setup & Container Orchestration |
| Mohamed Saadawy | Kafka Producer & Topic Design |
| Tarek Mohamed | Apache Spark Processing |
| Ghada Mohamed | Data Modeling & ERD |
| Eman Mahmoud | Documentation & Integration |

---

## 🧠 Future Improvements

- Real-time dashboard (Streamlit / Power BI)
- Machine learning: traffic prediction, accident risk, energy forecasting
- Integration with AWS Athena & Redshift
- Kubernetes orchestration for scaling

---

> 🚀 Built for learning, scalability, and real-time data engineering.
