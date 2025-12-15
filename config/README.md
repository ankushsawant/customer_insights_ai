# Configuration Directory

This directory contains configuration files for the CustomerInsightsAI application.

## Files

- **`.env.example`**: Template for environment variables. Copy this to `.env` and fill in your actual values.
- **`service-account-key.json`**: (NOT COMMITTED) Your GCP service account credentials file.

## Setup Instructions

1. Copy `.env.example` to `.env`:
   ```bash
   cp config/.env.example config/.env
   ```

2. Fill in your actual GCP project details in the `.env` file.

3. Download your GCP service account key and place it in this directory as `service-account-key.json`.

4. Ensure the service account has the following permissions:
   - Cloud Storage Admin (for bucket operations)
   - BigQuery Data Editor (for writing to BigQuery)
   - BigQuery Job User (for running queries)
   - Cloud Functions Developer (for deploying functions)

## Security Notes

- **NEVER commit `.env` or `service-account-key.json` to version control**
- These files are already in `.gitignore`
- Use Google Cloud Secret Manager for production deployments
