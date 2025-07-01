
# 🚀 Deploy a Dockerized App to Azure Kubernetes Service (AKS) with CI/CD using Azure DevOps

This project demonstrates how to containerize an application using Docker, push it to Azure Container Registry (ACR), and deploy it to Azure Kubernetes Service (AKS) using a full CI/CD pipeline built with Azure DevOps.

## 🧰 Technologies Used

- **Azure DevOps** – For CI/CD pipelines
- **Azure Kubernetes Service (AKS)** – For container orchestration
- **Azure Container Registry (ACR)** – For storing Docker images
- **Docker** – For containerization
- **Kubernetes (kubectl, YAML)** – For managing deployments
- **Helm (optional)** – For Kubernetes packaging (if implemented)
- **Application Code** – Any web app (Node.js, Python, etc.)

---

## 📁 Project Structure

```
📦 root/
├── 📁 .azure-pipelines/ # Azure DevOps pipeline folder
│ └── 📄 azure-pipelines.yml # CI/CD pipeline definition
├── 📁 k8s/ # Kubernetes manifests
│ ├── 📄 deployment.yaml # Kubernetes Deployment manifest
│ ├── 📄 service.yaml # Kubernetes Service manifest
│ └── 📄 ingress.yaml # (Optional) Ingress manifest
├── 📄 Dockerfile # Docker image instructions
├── 📁 app/ # Application source code
│ └── 📄 index.js / app.py # Sample entry file
├── 📄 README.md # You're here
```






