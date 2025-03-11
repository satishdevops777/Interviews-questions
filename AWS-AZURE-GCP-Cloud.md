## AWS Questions
1. What is EC2?
```
Answer:
Amazon EC2 (Elastic Compute Cloud) is a service that provides scalable virtual servers (instances) in the cloud. It allows users to run applications on demand with different OS configurations.
```
2. How do you store and retrieve data in S3?
```
Answer:
Store data:
aws s3 cp myfile.txt s3://my-bucket/
Retrieve data:
aws s3 cp s3://my-bucket/myfile.txt .
```
3. What is IAM, and why is it important?
```
Answer:
AWS Identity and Access Management (IAM) is a security service that manages users, roles, and permissions for AWS resources. It helps enforce least privilege access and multi-factor authentication (MFA).
```
4. What is an AWS Lambda function?
```
Answer:
AWS Lambda is a serverless compute service that automatically runs code in response to events without managing servers. Example use case: triggering functions from an S3 upload event.
```
5. How do you create a VPC?
```
Answer:
You can create a VPC using the AWS CLI:
aws ec2 create-vpc --cidr-block 10.0.0.0/16
Alternatively, use the AWS Management Console under VPC Dashboard → Create VPC.
```
## GCP Questions
1. What is Google Cloud Storage?
```
Answer:
Google Cloud Storage (GCS) is a scalable object storage service used to store unstructured data such as images, videos, and backups.
```
2. How does Google Compute Engine differ from Kubernetes Engine?
```
Answer:
Google Compute Engine (GCE) provides virtual machines (VMs).
Google Kubernetes Engine (GKE) manages and deploys containerized applications using Kubernetes.
```
3. What is a GCP Project?
```
Answer:
A GCP Project is a logical container for managing GCP resources, billing, and permissions. It is identified by a unique project ID.
```
4. How do you deploy an application in App Engine?
```
Answer:
Create an app.yaml file:
runtime: python39
entrypoint: gunicorn -b :$PORT main:app
Deploy using:
gcloud app deploy
```
5. What is Cloud Run?
```
Answer:
Google Cloud Run is a serverless platform that runs containerized applications without managing infrastructure.
```
## Azure Questions
1. What is Azure Virtual Machine (VM)?
```
Answer:
Azure VM is a cloud-based virtual server that provides scalable computing power, supporting Linux and Windows OS.
```
2. What is an Azure Resource Group?
```
Answer:
An Azure Resource Group is a container that holds related Azure resources (VMs, storage, databases) for easier management.
```
3. How does Azure Blob Storage work?
```
Answer:
Azure Blob Storage is an object storage solution for storing unstructured data (images, videos, backups). It supports hot, cool, and archive tiers.
```
4. What is Azure Kubernetes Service (AKS)?
```
Answer:
Azure Kubernetes Service (AKS) is a managed Kubernetes solution for deploying and managing containerized applications.
```
5. How do you monitor applications in Azure?
```
Answer:
Using Azure Monitor, Application Insights, and Log Analytics to track performance, logs, and alerts.
```
