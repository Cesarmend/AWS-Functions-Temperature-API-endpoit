# AWS S3 Bucket and Lambda Function

These two AWS services pair nicely to build lightweight, serverless workflows. **Amazon S3** provides durable, low-cost object storage for datasets, configs, and artifacts, while **AWS Lambda** runs code on demand (no servers to manage). Together, you can trigger code automatically when files land in a bucket (e.g., data ingestion → transform → export), expose simple APIs via API Gateway, or schedule recurring tasks—all with pay-for-what-you-use pricing.

---

## 🔧 Components

- **S3 Bucket** — stores input/output files (CSV, JSON, images, logs). Can emit events (PUT/DELETE) to trigger Lambda.
- **Lambda Function** — small, focused function packaged with dependencies. Invoked by S3 events, API Gateway, EventBridge, or directly.
- *(Optional)* **IAM Roles/Policies**, **CloudWatch Logs**, **EventBridge**, **API Gateway** for permissions, monitoring, scheduling, and HTTP access.

---

## 🗺️ Architecture (Event-Driven): 
- https://#####.amazonaws.com/weather?c={city}&download={} (full link shared upon request due to billing charges on the account)

## POSTMAN TEST
<img width="1394" height="428" alt="image" src="https://github.com/user-attachments/assets/b2a4fed5-a86f-4a09-b0ce-bf327f00c7a1" />

## API DEPLOY
<img width="434" height="560" alt="image" src="https://github.com/user-attachments/assets/f51868c1-5ebb-4b67-bb3e-666d248ae0bd" /><img width="411" height="651" alt="image" src="https://github.com/user-attachments/assets/c1c4648b-8372-4d34-ac0e-18e1b430762f" />

<img width="946" height="323" alt="image" src="https://github.com/user-attachments/assets/da2b9f45-6330-4775-8894-5058e45e6b3e" />

<img width="291" height="341" alt="image" src="https://github.com/user-attachments/assets/1d28ecf8-2c97-43e9-a970-72463e1d67a5" />





## 🚀 Road followed:

1. **Create an S3 bucket** (unique name, pick a region).  
2. **Write your Lambda** (`handler.py`) that reads/writes to S3.  
3. **Grant permissions** (Lambda execution role with S3 read/write, logs).  
4. **Wire S3 events** (ObjectCreated) to invoke the Lambda.  
5. **Deploy** (SAM/Terraform/Console) and **test** by uploading a file.  
6. **Observe logs** in CloudWatch; iterate on code as needed.

