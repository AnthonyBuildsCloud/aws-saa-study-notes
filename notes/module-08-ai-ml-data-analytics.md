# Module 8 — AI/ML and Data Analytics (AWS Cloud Practitioner Essentials)

## What this module covered (high-level)
- AI/ML on AWS using fully managed services
- Generative AI concepts and AWS offerings
- Core data analytics services and common pipelines on AWS

## 5 key takeaways
1) **AWS focuses on managed AI/ML services**  
   Most AWS AI services (Comprehend, Rekognition, Transcribe, etc.) require *no* model training and are designed for quick integration into applications.

2) **AI/ML ≠ Data Analytics**  
   Data analytics analyzes historical data to find trends, while AI/ML is used to make predictions, classifications, or automate decisions.

3) **S3 is the foundation of analytics on AWS**  
   Data is typically stored in Amazon S3 first, then analyzed using Athena, Glue, Redshift, or visualized with QuickSight.

4) **Serverless analytics reduces operational overhead**  
   Services like Athena and QuickSight let you analyze and visualize data without managing servers or infrastructure.

5) **Generative AI on AWS is consumption-based**  
   Amazon Bedrock allows customers to use foundation models through APIs without building or training models themselves.

## Service selection cheat-sheet (when to use what)
- **Amazon Comprehend** → NLP on text (sentiment, entities, key phrases)
- **Amazon Rekognition** → image/video analysis
- **Amazon Lex** → chatbots + voice bots
- **Amazon Polly** → text-to-speech
- **Amazon Transcribe** → speech-to-text
- **Amazon Translate** → language translation
- **Amazon Kendra** → enterprise search
- **Amazon SageMaker** → build/train/deploy ML models
- **Amazon Bedrock** → access foundation models via API (generative AI)
- **Data lake on S3** → centralized storage for analytics data
- **AWS Glue** → ETL + data catalog
- **Amazon Athena** → SQL queries directly on S3 data
- **Amazon Redshift** → data warehouse analytics at scale
- **Amazon QuickSight** → BI dashboards/visuals
- **Amazon Kinesis** → real-time streaming ingestion

## Things I’m fuzzy on (review list)
- When to choose **Athena vs Redshift** in exam scenarios
- Difference between **Glue ETL jobs vs Glue Data Catalog**
- Where **SageMaker ends and Bedrock begins** for ML use cases

## Quick self-quiz (3 questions)
1) If I need to query CSV files in S3 using SQL without servers, I use:  
   **Amazon Athena** because it is serverless and queries data directly in S3.

2) If I need ETL + cataloging for analytics data, I use:  
   **AWS Glue** because it provides data discovery, schema management, and ETL.

3) If I need near real-time streaming ingestion, I use:  
   **Amazon Kinesis** because it processes streaming data in real time.
