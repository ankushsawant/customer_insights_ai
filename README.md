## CustomerInsightsAI — AI-Powered Customer Feedback Analysis (GCP + Google ADK)

CustomerInsightsAI is an end-to-end, serverless customer feedback analysis pipeline built with Google ADK 
and Google Cloud Platform (GCP). The system automatically extracts sentiment, topics, summaries, and 
recommended actions from customer reviews, then stores the insights in BigQuery for visualization and 
analytics.

### Project Overview

CustomerInsightsAI processes raw customer review data using a fully automated AI pipeline:
1. Upload CSV → Cloud Storage
2. Cloud Function processes each row
3. AI model analyzes text via Google ADK
4. Insights stored in BigQuery
5. Dashboard built in Looker (or Looker Studio)

