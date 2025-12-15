# Setup Guide for CustomerInsightsAI

## Project Structure

```
customer_insights_ai/
├── src/                        # Main application source code
│   ├── data_processing/        # CSV parsing and data transformation
│   ├── ai_analysis/           # AI/ML analysis logic
│   ├── gcp_services/          # GCP integrations (Storage, BigQuery)
│   └── utils/                 # Helper functions
├── cloud_functions/           # Google Cloud Functions code
├── tests/                     # Unit and integration tests
├── config/                    # Configuration files
│   ├── .env.example          # Environment variable template
│   └── README.md             # Config setup instructions
├── sample_data/              # Sample CSV files for testing
├── app.py                    # Main application entry point
├── requirements.txt          # Python dependencies
└── README.md                 # Project documentation
```

## Quick Start

### 1. Install Dependencies

```bash
# Activate virtual environment
source .venv/bin/activate  # On macOS/Linux
# or
.venv\Scripts\activate     # On Windows

# Install packages
pip install -r requirements.txt
```

### 2. Configure Environment

```bash
# Copy environment template
cp config/.env.example config/.env

# Edit config/.env with your actual GCP credentials
```

### 3. Set Up GCP

1. Create a GCP project
2. Enable required APIs:
   - Cloud Storage API
   - BigQuery API
   - Cloud Functions API
   - Generative AI API
3. Create a service account with appropriate permissions
4. Download service account key to `config/service-account-key.json`

### 4. Run the Application

```bash
python app.py
```

## Dependencies

Key packages installed:
- **google-cloud-storage**: Upload/download files from GCS
- **google-cloud-bigquery**: Store and query insights data
- **google-generativeai**: AI analysis using Gemini models
- **pandas**: Data manipulation and CSV processing
- **python-dotenv**: Environment variable management

See [requirements.txt](requirements.txt) for the complete list.

## Security

- **Never commit** `.env` or `service-account-key.json` files
- These are already in `.gitignore`
- Use Google Secret Manager for production deployments

## Next Steps

1. Implement data processing logic in `src/data_processing/`
2. Build AI analysis functions in `src/ai_analysis/`
3. Create GCP service clients in `src/gcp_services/`
4. Write Cloud Functions in `cloud_functions/`
5. Add tests in `tests/`
6. Update `app.py` with main application logic

## Testing

```bash
# Run tests
pytest

# Run tests with coverage
pytest --cov=src tests/
```

## Code Quality

```bash
# Format code
black src/ tests/

# Lint code
ruff check src/ tests/

# Type checking
mypy src/
```
