# AWS Machine Learning Services Cheat Sheet

## Amazon SageMaker
### What is SageMaker?
- A fully managed service for building, training, and deploying machine learning models.

### Key Features:
1. **Studio**:
   - Integrated development environment (IDE) for ML.
2. **Data Preparation**:
   - SageMaker Data Wrangler for data preparation.
   - Built-in support for Amazon S3 and data labeling.
3. **Training**:
   - Distributed training for large datasets.
   - Use built-in algorithms, custom code, or pre-trained models.
4. **Deployment**:
   - One-click deployment for real-time or batch predictions.
   - Support for A/B testing with endpoints.
5. **MLOps**:
   - Automate CI/CD pipelines with SageMaker Pipelines.
6. **Built-in Algorithms**:
   - Linear Learner, XGBoost, DeepAR, Image Classification, etc.

### Use Cases:
- Fraud detection, recommendation systems, computer vision, natural language processing.

### Example Workflow:
1. Prepare data in S3.
2. Train models using SageMaker’s managed infrastructure.
3. Deploy the model as an endpoint for inference.
4. Monitor and update the model as needed.

---

## Amazon ML Services Overview
AWS offers a variety of AI and ML services to cater to different use cases:

### 1. **AI Services (Pre-built APIs)**
#### a. **Amazon Rekognition**
- Image and video analysis (e.g., facial recognition, object detection).

#### b. **Amazon Polly**
- Text-to-speech service.

#### c. **Amazon Transcribe**
- Automatic speech-to-text transcription.

#### d. **Amazon Translate**
- Language translation.

#### e. **Amazon Comprehend**
- Natural language processing (e.g., sentiment analysis, entity recognition).

#### f. **Amazon Textract**
- Extract structured data from documents (e.g., tables, forms).

### 2. **ML Services (Custom Models)**
#### a. **Amazon SageMaker**
- Build, train, and deploy custom models.

#### b. **AWS Deep Learning AMIs (DLAMI)**
- Pre-configured EC2 instances for deep learning frameworks like TensorFlow, PyTorch, and MXNet.

#### c. **AWS DeepRacer**
- A 1/18th scale autonomous race car for reinforcement learning experiments.

#### d. **AWS Panorama**
- Computer vision for edge devices.

### 3. **Data and Analytics Services**
- **Amazon Redshift ML**: Integrate ML models into Redshift SQL queries.
- **AWS Glue**: Extract, transform, and load (ETL) for ML workflows.
- **Amazon EMR**: Big data processing for ML workflows.

---

## Amazon Quantum Ledger Database (QLDB) and Quantum Computing
### What is QLDB?
- A fully managed ledger database for recording immutable transaction history.

### Key Features:
1. **Immutable Data**:
   - Data cannot be altered or deleted.
2. **Cryptographically Verifiable**:
   - Ensures data integrity.
3. **Serverless**:
   - Scales automatically based on workload.

### Use Cases:
- Supply chain tracking, finance ledgers, compliance tracking.

---

## AWS ML Services for Developers
### Key Tools:
1. **AWS Lambda**:
   - Run serverless inference with SageMaker models.
2. **Amazon API Gateway**:
   - Create REST APIs to serve ML models.
3. **AWS IoT Greengrass**:
   - Deploy models to IoT devices.
4. **AWS Step Functions**:
   - Orchestrate workflows with SageMaker.

### Common Developer Workflows:
- Use pre-built APIs like Rekognition for fast prototyping.
- Train custom models in SageMaker for specific business problems.
- Deploy models to endpoints for real-time inference.

---

## Summary Table
| Service                   | Purpose                                           | Key Features                                   | Use Cases                                      |
|---------------------------|---------------------------------------------------|-----------------------------------------------|-----------------------------------------------|
| **Amazon SageMaker**      | Build, train, deploy ML models.                  | Studio, Pipelines, real-time endpoints.       | Custom ML workflows.                          |
| **Amazon Rekognition**    | Image and video analysis.                        | Facial recognition, object detection.         | Security, content moderation.                 |
| **Amazon Comprehend**     | Natural language processing.                     | Sentiment analysis, entity extraction.        | Social media analysis, customer insights.     |
| **Amazon Transcribe**     | Automatic speech-to-text transcription.          | Speaker identification, real-time transcription. | Call center analytics, media captions.       |
| **Amazon Polly**          | Text-to-speech.                                  | Neural TTS, multiple languages.               | Voice applications, accessibility.            |
| **Amazon Textract**       | Extract structured data from documents.          | Form and table data extraction.               | Invoice processing, document digitization.    |
| **QLDB**                  | Ledger database for immutable transaction logs.  | Immutable, cryptographically verifiable.      | Financial ledgers, supply chain tracking.     |

---

## Best Practices
1. Use **Amazon SageMaker Studio** for end-to-end ML workflows.
2. Leverage pre-built APIs like Rekognition and Comprehend for fast prototyping.
3. Use **AWS Glue** and **Redshift ML** for data preparation and integrated analytics.
4. Train and deploy models with **MLOps pipelines** using SageMaker Pipelines.
5. Optimize cost by using **Spot Instances** and **SageMaker Savings Plans**.
6. Secure data with **IAM roles**, **KMS encryption**, and **VPC endpoints** for ML workflows.
