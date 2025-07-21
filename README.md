Here’s a complete `README.md` file for your project:

---

```markdown
# 🚀 Amazon ECS + Docker + ECR Deployment Project

This project demonstrates how to containerize an application with Docker, push it to Amazon ECR (Elastic Container Registry), and deploy it using Amazon ECS (Elastic Container Service). The entire workflow is managed through AWS CLI and AWS Management Console.

---

## 📦 Features

- Dockerized Application Deployment
- Secure Image Hosting with Amazon ECR
- Deployment on ECS Cluster (Fargate or EC2)
- Full cleanup of ECS services, tasks, clusters, and images
- Simple and modular configuration for reusability

---

## 🛠️ Technologies Used

- **Amazon ECS** (Elastic Container Service)
- **Amazon ECR** (Elastic Container Registry)
- **Docker**
- **AWS CLI**
- **CloudShell** (for command-line operations)
- **IAM Roles & Permissions** (secure access control)

---

## 🧩 Project Structure

```
/aws-devops-zero-to-hero/day-21/
├── Dockerfile
├── README.md
├── app.py
├── commands.md
└── requirements.txt

````

---

## 📋 Steps to Run the Project

### 1️⃣ Authenticate with AWS
```bash
aws configure
````

### 2️⃣ Authenticate Docker with ECR

```bash
aws ecr get-login-password --region us-east-1 | \
docker login --username AWS --password-stdin 233693674445.dkr.ecr.us-east-1.amazonaws.com
```

### 3️⃣ Build Docker Image

```bash
docker build -t repo-eks .
```

### 4️⃣ Tag the Image

```bash
docker tag repo-eks:latest 233693674445.dkr.ecr.us-east-1.amazonaws.com/repo-eks:latest
```

### 5️⃣ Push to ECR

```bash
docker push 233693674445.dkr.ecr.us-east-1.amazonaws.com/repo-eks:latest
```

### 6️⃣ Deploy to ECS

* Go to AWS Console > ECS
* Create Cluster (`demo-EKS-clusters`)
* Define Task > Create Service > Deploy

---

## 🧹 Cleanup Resources (Optional)

```bash
# Delete ECS cluster
aws ecs delete-cluster --cluster demo-EKS-clusters

# Delete ECR repo
aws ecr delete-repository --repository-name repo-eks --force
```

---

## 📖 Learnings

* Deploying scalable containers using ECS
* Efficient Docker image tagging & ECR integration
* Full lifecycle: build → push → deploy → clean
* Handling ECS via AWS CLI and Console

---

## 🤝 Connect with Me

If you're working on cloud-native projects or want to collaborate on Docker + AWS integrations, feel free to connect!

**LinkedIn**: [anurag7654](https://www.linkedin.com/in/anurag850)
**GitHub**: [anurag7654](https://github.com/anurag7654)

---
