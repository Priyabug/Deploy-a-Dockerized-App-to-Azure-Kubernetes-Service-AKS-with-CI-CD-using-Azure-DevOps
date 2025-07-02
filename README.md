
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


---

## ⚙️ Prerequisites

- Azure subscription
- AKS cluster set up
- ACR set up and integrated with AKS
- Azure DevOps account with a project created
- Service connection to Azure (Azure Resource Manager)
- Basic understanding of Git, Docker, Kubernetes, and YAML

---

## 🔧 Setup Instructions

### 1. **Clone the Repository**

```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
```
### 🚢 2. Dockerize the Application

Create a `Dockerfile` at the root of your project if it doesn't already exist:

```Dockerfile
# Use Node.js base image
FROM node:18

# Set working directory
WORKDIR /app

# Copy project files into the container
COPY . .

# Install dependencies
RUN npm install

# Expose the app on port 3000
EXPOSE 3000

# Start the application
CMD ["node", "index.js"]
```
## ☸️ 3. Kubernetes deployment

Ensure your Kubernetes deployment YAML files (located in the `k8s/` directory) are properly configured to pull the container image from your **Azure Container Registry (ACR)**.

Key areas to check in `deployment.yaml`:
- ✅ Correct image path: `myregistry.azurecr.io/your-image-name:tag`
- ✅ ImagePullSecrets (if needed)
- ✅ Proper resource limits, labels, and selectors

```yaml
containers:
  - name: your-app
    image: <your-acr-name>.azurecr.io/<image>:<tag>
    ports:
      - containerPort: 3000
```





