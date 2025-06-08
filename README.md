# 📸 Serverless Image Processing with AWS S3 and Lambda

A fully serverless image processing pipeline built with AWS services. This application allows users to upload images to an S3 bucket. When an image is uploaded, a Lambda function is triggered to resize (and optionally watermark) the image, then stores the processed image in another S3 bucket.

---

## 🏗️ Architecture

User Upload
│
└──▶ S3 Bucket (Source)
│
└──▶ Lambda Function (Resize + Watermark)
│
└──▶ S3 Bucket (Processed)



> Optional integrations:
> - **API Gateway**: Upload interface
> - **DynamoDB**: Store image metadata
> - **Step Functions**: Manage multi-step workflows

---

## ⚙️ AWS Services Used

| Service         | Purpose                                  |
|-----------------|-------------------------------------------|
| **S3**          | Store original and processed images       |
| **Lambda**      | Resize/watermark images on upload         |
| **IAM**         | Grant necessary permissions to Lambda     |
| **CloudWatch**  | Monitor Lambda logs                       |
| *(Optional)*    |                                           |
| API Gateway     | Secure upload endpoint                    |
| DynamoDB        | Metadata storage                          |
| Step Functions  | Workflow orchestration                    |

---

## 🚀 Features

- 🔁 Event-driven: triggered on S3 image upload
- 🪄 Resizing using `Pillow` (Python)
- 🔐 IAM Role and least-privilege policies
- 🌩️ Fully serverless and auto-scaling
- 💸 Cost-efficient pay-per-use model

---

## 📁 Project Structure

project/
├── main.tf # Infrastructure config
├── variables.tf # Input variables
├── outputs.tf # Outputs
├── lambda/
│ └── index.py # Lambda function logic
└── README.md # Project documentation


---

## 🧪 How It Works

1. Upload an image to the **source S3 bucket**
2. Lambda is automatically triggered
3. Image is resized and optionally watermarked
4. Result is saved to the **processed S3 bucket**

---

## 📦 Deployment

> Prerequisites:
> - AWS CLI configured
> - Terraform installed

```bash
# Initialize Terraform
terraform init

# Preview changes
terraform plan

# Apply infrastructure
terraform apply
