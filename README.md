# 🚀 Banking Application DevOps CI/CD Pipeline with Kubernetes Monitoring

This project demonstrates an **end-to-end DevOps implementation for a Banking/Finance application** using modern DevOps tools.

The pipeline automates **application build, containerization, deployment to Kubernetes, and infrastructure monitoring**.

The system integrates:

* Jenkins CI/CD Pipeline
* Docker containerization
* Kubernetes deployment
* DockerHub container registry
* Prometheus monitoring
* Grafana visualization

This architecture simulates a **real banking production deployment environment**.

---

# 🏗 Architecture Overview

Developer → GitHub Repository
↓
Jenkins CI/CD Pipeline
↓
Build Application Artifact (.war)
↓
Docker Image Creation
↓
Push Image to DockerHub
↓
Deploy to Kubernetes Cluster
↓
Prometheus Monitoring
↓
Grafana Dashboards

---

# ☁️ Infrastructure Architecture

The environment consists of **5 Virtual Machines (VMs)**.

| Server                   | VM  | Purpose                            |
| ------------------------ | --- | ---------------------------------- |
| Jenkins Master           | VM1 | Manage CI/CD pipeline              |
| Jenkins Build Node       | VM2 | Build application and Docker image |
| Kubernetes Master        | VM3 | Manage cluster + monitoring        |
| Kubernetes Worker Node 1 | VM4 | Run application containers         |
| Kubernetes Worker Node 2 | VM5 | Run application containers         |

---

# ⚙️ Infrastructure Components

## Jenkins Master (VM1)

Purpose:

* Create CI/CD pipelines
* Manage pipeline execution
* Schedule jobs on build server

Installed Tools:

* Git
* Jenkins
* JDK

---

## Jenkins Build Server (VM2)

Purpose:

* Checkout source code from GitHub
* Compile application
* Generate artifacts (.war)
* Build Docker image
* Push Docker image to DockerHub

Installed Tools:

* Git
* Maven
* Docker
* JDK

---

## Kubernetes Master Node (VM3)

Purpose:

* Manage Kubernetes cluster
* Schedule pods
* Deploy applications
* Run monitoring services

Installed Components:

* kube-apiserver
* kube-scheduler
* kube-controller-manager
* etcd
* kubectl
* Prometheus
* Grafana

---

## Kubernetes Worker Nodes (VM4, VM5)

Purpose:

* Execute application containers
* Run deployed pods

Installed Components:

* kubelet
* kube-proxy
* container runtime

---

# 🔁 CI/CD Pipeline Workflow

The Jenkins pipeline automates the following stages.

---

## 1️⃣ Source Code Checkout

Application code is pulled from GitHub repository.

---

## 2️⃣ Application Build

The application is compiled using Maven.

Artifact generated:

```
application.war
```

---

## 3️⃣ Docker Image Build

A Docker image is created from the application artifact.

Example:

```
docker build -t banking-app .
```

---

## 4️⃣ Login to DockerHub

Jenkins authenticates with DockerHub using stored credentials.

---

## 5️⃣ Push Docker Image

The Docker image is pushed to DockerHub container registry.

Example:

```
docker push dockerhub-username/banking-app
```

---

## 6️⃣ Deploy Application to Kubernetes

The application is deployed using Kubernetes manifest files.

Example:

```
kubectl apply -f deployment.yaml
```

Pods are scheduled on Kubernetes worker nodes.

---

# 🔗 Jenkins Integration with Kubernetes

Jenkins deploys applications to Kubernetes using **Publish Over SSH Plugin**.

Steps:

1. Create user **devopsadmin** on Kubernetes Master node.
2. Generate SSH keys for devopsadmin.
3. Provide kubectl access to devopsadmin user.
4. Configure Kubernetes master credentials in Jenkins.
5. Use **Publish Over SSH plugin** to run deployment commands.

Deployment command executed:

```
kubectl apply -f kubernetesdeploy.yaml
```

---

# 🔐 Jenkins Credential Management

Credentials configured in Jenkins include:

* DockerHub credentials
* GitHub repository access
* Jenkins slave SSH credentials
* Kubernetes SSH credentials

Location:

```
Jenkins → Manage Jenkins → Manage Credentials
```

---

# 📊 Monitoring Setup

Monitoring stack is installed on the **Kubernetes Master Node**.

Monitoring tools used:

* Prometheus
* Grafana

Prometheus collects metrics from:

* Kubernetes cluster
* Nodes
* Pods
* Containers

Grafana provides visualization dashboards.

Metrics monitored include:

* CPU usage
* Memory utilization
* Pod performance
* Node health
* Kubernetes cluster metrics

---

# 🛠 Tools Used

| Tool       | Purpose                   |
| ---------- | ------------------------- |
| GitHub     | Source code repository    |
| Jenkins    | CI/CD pipeline automation |
| Docker     | Containerization          |
| DockerHub  | Container registry        |
| Kubernetes | Container orchestration   |
| Prometheus | Infrastructure monitoring |
| Grafana    | Visualization dashboards  |
| Maven      | Application build         |

---

# 🎯 Project Outcome

This project demonstrates a **complete DevOps lifecycle for a banking application**:

✔ Automated CI/CD pipeline
✔ Containerized application deployment
✔ Kubernetes orchestration
✔ Secure image registry
✔ Real-time monitoring with Prometheus and Grafana

This architecture reflects a **production-ready DevOps environment used in enterprise banking systems**.

---

# 👨‍💻 Author

**Neeraj Kumar Verma**

Cloud & DevOps Engineer

Skills:
Linux • Docker • Kubernetes • Jenkins • Terraform • Prometheus • Grafana • AWS • Azure

Email: [neerajbhanu143@gmail.com](mailto:neerajbhanu143@gmail.com)


After Deployment
===========================================

Pipeline
===========================================
<img width="774" height="392" alt="image" src="https://github.com/user-attachments/assets/418a2611-4bb3-4e8f-bd04-c6290523ac13" />


Web Page
===========================================
<img width="955" height="518" alt="image" src="https://github.com/user-attachments/assets/948695e4-69b6-4cf2-8c1f-a127c73e3079" />

Monitoring
============================================
<img width="931" height="467" alt="image" src="https://github.com/user-attachments/assets/420995ba-85e9-433d-aad2-9247ee6dadc4" />
