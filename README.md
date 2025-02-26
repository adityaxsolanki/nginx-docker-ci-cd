# 🚀 Nginx Docker CI/CD Pipeline

## 📌 Overview
This project automates the deployment of an **Nginx web server** using **Docker** and **Jenkins**. The pipeline ensures that every code change is automatically tested, built, and deployed to a running containerized environment.

## 🔥 Features
- **Automated Docker Image Build**: Every commit triggers a new image build.
- **CI/CD with Jenkins**: Fully automated pipeline for testing and deployment.
- **Containerized Deployment**: Runs inside a **Docker container** for portability.
- **Version Control Integration**: Uses **GitHub Webhooks** to trigger builds.
- **Security Scanning**: Checks for vulnerabilities before deployment.
- **Rollback Mechanism**: Ensures quick rollback in case of failure.

---

## 🏗 Architecture
1. Developer pushes code to GitHub.
2. GitHub Webhook triggers **Jenkins** pipeline.
3. Jenkins pulls the latest code and builds a **Docker image**.
4. The image is pushed to **Docker Hub**.
5. Deployment is done using **Docker Compose / Kubernetes (optional)**.
6. If successful, the Nginx server is live.

---

## 📦 Tech Stack
- **CI/CD**: Jenkins, GitHub Actions (optional)
- **Containerization**: Docker, Docker Compose
- **Web Server**: Nginx
- **Scripting**: Shell, Bash
- **Monitoring**: Prometheus & Grafana (optional)

---

## 🚀 Installation & Setup

### **1️⃣ Clone the Repository**
```sh
git clone https://github.com/adityaxsolanki/nginx-docker-ci-cd.git
cd nginx-docker-ci-cd
```

### **2️⃣ Run Locally with Docker**
```sh
docker build -t nginx-ci-cd .
docker run -d -p 80:80 nginx-ci-cd
```

### **3️⃣ Deploy via Jenkins Pipeline**
1. Open Jenkins and create a **new pipeline**.
2. Connect it with your **GitHub repo**.
3. Configure the following steps:
   - **Build**: `docker build -t nginx-ci-cd .`
   - **Push** (Optional): `docker push your-dockerhub/nginx-ci-cd`
   - **Deploy**: `docker run -d -p 80:80 nginx-ci-cd`
4. Save and trigger the pipeline.

---

## 🛠 CI/CD Pipeline Breakdown
- **Code Push** → GitHub Webhook → Jenkins Trigger
- **Jenkins Stages:**
  - 🛠 **Build Image**
  - 🔍 **Run Security Scans**
  - 🚀 **Push to Docker Hub**
  - 🔄 **Deploy to Server**

---

## 🔥 Screenshots
| Jenkins Pipeline Execution | Deployed Nginx Web Page |
|-----------------|-----------------|
| ![Jenkins Pipeline](https://via.placeholder.com/400x250.png?text=Pipeline) | ![Nginx Deployed](https://via.placeholder.com/400x250.png?text=Nginx+Live) |

---

## 🛡 Security & Best Practices
- **Use environment variables** for sensitive data.
- **Scan images with Trivy** before pushing.
- **Enable logging & monitoring** using Grafana.

---

## 📜 License
This project is open-source and available under the **MIT License**.

---

## 🔗 Connect with Me
📧 **Email**: [adityasolanki51@gmail.com](mailto:adityasolanki51@gmail.com)  
💼 **LinkedIn**: [linkedin.com/in/adityaxsolanki](https://linkedin.com/in/adityaxsolanki)  
🐙 **GitHub**: [github.com/adityaxsolanki](https://github.com/adityaxsolanki)  

