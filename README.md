
# 🚚 DelayDetect - Real-Time Delivery Delay Detection System

A real-time streaming analytics system that detects and analyzes delivery delays using Apache Kafka and Apache Spark.

## 🎯 Overview
DelayDetect ingests delivery data in real-time, enriches it with weather and traffic conditions, and calculates driver fault percentages to identify delay causes.

## 🛠️ Tech Stack
- Apache Kafka - Streaming platform
- Apache Spark (PySpark) - Stream processing
- Python 3.x - Core language
- Pandas - Data manipulation

## ✨ Features
- ⚡ Real-time streaming with Kafka
- 🌦️ Weather-enriched analytics
- 🚦 Traffic-aware delay detection
- 📊 Driver fault scoring algorithm
- 💾 Parquet output for efficient analytics

## 🚀 Quick Start

### Prerequisites
- WSL2/Linux with Java 11+
- Python 3.8+
- Apache Kafka 3.6.1+
- Apache Spark 3.5.5+

### Installation
\`\`\`bash
# Clone repo
git clone https://github.com/YOUR_USERNAME/DelayDetect.git
cd DelayDetect

# Setup environment
python3 -m venv env
source env/bin/activate
pip install -r requirements.txt
\`\`\`

### Run
\`\`\`bash
# Terminal 1: Start Zookeeper
cd ~/kafka
bin/zookeeper-server-start.sh config/zookeeper.properties

# Terminal 2: Start Kafka
bin/kafka-server-start.sh config/server.properties

# Terminal 3: Run producer
python scripts/kafka_producer.py

# Terminal 4: Run analytics
spark-submit --packages org.apache.spark:spark-sql-kafka-0-10_2.12:3.5.5 scripts/analytics.py
\`\`\`

## 📁 Project Structure
\`\`\`
DelayDetect/
├── data/               # CSV datasets
├── scripts/            # Producer & analytics
├── output/             # Parquet results
└── checkpoints/        # Spark checkpoints
\`\`\`

## 📊 Algorithm
Driver fault = (delay_score × 0.5) + (traffic_score × 0.3) + (weather_score × 0.2)

## 🤝 Contributing
Pull requests welcome! Please open an issue first.

## 📄 License
MIT License
EOF
