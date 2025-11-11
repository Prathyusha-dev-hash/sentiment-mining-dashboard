# E-Consultation Feedback Analysis Dashboard

A comprehensive ML-based sentiment analysis solution for analyzing e-consultation feedback with Aspect-Based Sentiment Analysis (ABSA) and Urgency Detection.

## Tech Stack

- **Language**: Python 3.8+
- **ML/NLP**: Hugging Face Transformers (BERT), PyTorch
- **Message Queue**: Kafka/RabbitMQ
- **Database**: PostgreSQL (relational), MongoDB (NoSQL for raw comments)
- **Dashboard**: Streamlit with Plotly visualizations
- **Cloud**: AWS/Azure/GCP ready

## Project Structure

```
ML Project/
├── data/                    # Dataset storage
│   ├── raw/                # Raw input data
│   └── processed/          # Processed data
├── models/                 # Saved ML models
├── src/                    # Source code
│   ├── nlp/               # NLP pipeline
│   ├── database/          # Database utilities
│   ├── ingestion/         # Message queue integration
│   └── utils/             # Utility functions
├── dashboard/             # Streamlit dashboard
├── config/                # Configuration files
└── tests/                 # Unit tests
```

## Setup Instructions

1. **Clone and navigate to the project**:
   ```bash
   cd "ML Project"
   ```

2. **Create a virtual environment**:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up environment variables**:
   - Copy `env_template.txt` to `.env`
   - Fill in your database credentials, message queue settings, etc.

5. **Initialize the database**:
   ```bash
   python src/database/init_db.py
   ```

6. **Run the dashboard**:
   ```bash
   streamlit run dashboard/main.py
   ```

## Features

- **Aspect-Based Sentiment Analysis (ABSA)**: Identifies specific aspects in feedback and their sentiment
- **Urgency Detection**: Classifies feedback by urgency level
- **Real-time Processing**: Kafka/RabbitMQ integration for high-volume data ingestion
- **Interactive Dashboard**: Streamlit-based visualization with real-time insights
- **Scalable Architecture**: Cloud-ready with PostgreSQL and NoSQL storage

## Usage

### Processing Twitter Dataset

The project includes scripts to process the Twitter sentiment dataset:

**Quick Test (100 samples):**
```bash
python process_twitter_dataset_simple.py 100
```

**Full Processing (with options):**
```bash
# Test with 1000 samples first
python process_twitter_dataset.py --file "path/to/dataset.csv" --sample 1000 --batch-size 50

# Process full dataset (WARNING: Takes a long time!)
python process_twitter_dataset.py --file "path/to/dataset.csv" --batch-size 50
```

### General Usage

1. Place your dataset in `data/raw/` directory or specify path in script
2. Configure your database and message queue settings in `.env`
3. Process your dataset using the appropriate script
4. Start the ingestion service (if using message queue)
5. Run the dashboard to view insights

## Configuration

Edit `config/config.yaml` to customize:
- Model parameters
- Database connections
- Message queue settings
- Dashboard settings

# sentiment-mining-dashboard
# sentiment-mining-dashboard
# sentiment-mining-dashboard
