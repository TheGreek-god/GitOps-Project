# 🚀 Zomato Clone Deployment on Kubernetes with Argo CD, Prometheus & Grafana

This project demonstrates a **GitOps-driven continuous deployment pipeline** for a **Dockerized Zomato clone application**, orchestrated on **Kubernetes (Minikube)** and monitored with **Prometheus** and **Grafana**.

---

## 🧩 Project Overview

The main goal of this setup was to automate deployment, scaling, and monitoring of a containerized application using modern DevOps tools.  
The stack includes:

- 🐳 **Docker** – Containerized the Zomato app for consistent deployments  
- ☸️ **Kubernetes (Minikube)** – Local cluster for orchestration and service management  
- 🚀 **Argo CD** – Continuous delivery using a GitOps workflow  
- 📈 **Prometheus** – Metrics collection and node monitoring  
- 📊 **Grafana** – Visualization and performance dashboards  

---

## 🏗️ Architecture Flow

1. **Dockerization:**  
   The application was built into a Docker image and pushed to Docker Hub for portability.  

2. **Kubernetes Deployment:**  
   The app was deployed into the Minikube cluster using `Deployment` and `Service` YAML manifests.  
   A NodePort service was used to expose the application to external traffic.

3. **Accessing the App:**  
   Due to Minikube’s internal networking restrictions, direct access via the default Minikube IP and `nodePort` was not possible.  
   Instead, the app was accessed using a tunneled service via:

   ```bash
   minikube service zomato

This command automatically exposed the service through a dynamically assigned local port, opening the app in the default browser.

4. **Continuous Deployment with Argo CD:**

- Argo CD was configured to monitor the GitHub repository for changes.

- Each commit to the k8s folder triggered automatic synchronization and deployment in the cluster.

5. **Monitoring Setup:**

- Prometheus scraped metrics from the Node Exporter deployed in the cluster.

- Grafana visualized CPU, memory, and pod activity metrics using Prometheus as the data source.

## ⚙️ Technologies Used

| 🧩 **Tool / Platform**       | 🎯 **Purpose** |
|------------------------------|----------------|
| 🐳 **Docker**                | 🧱 Containerization |
| ☸️ **Kubernetes (Minikube)** | 🖥️ Local cluster orchestration |
| 🚀 **Argo CD**               | 🔁 Continuous deployment (GitOps) |
| 📊 **Prometheus**            | 📈 Metrics collection |
| 📉 **Grafana**               | 🧭 Data visualization |
| 🧠 **Node Exporter**         | ⚙️ Node-level metric exporter |

## 🧠 Key Learnings

- Implemented GitOps-based continuous delivery using Argo CD

- Gained experience in observability and monitoring with Prometheus + Grafana

- Learned how Minikube handles internal networking and how to tunnel access using minikube service

- Built a complete DevOps lifecycle: containerization → orchestration → monitoring

## 🖥️ Accessing the Application

After successful deployment, run the following command to access the frontend app:

```bash
minikube service zomato

```

## 🏁 Conclusion

This project highlights the **end-to-end automation** of application deployment and monitoring using modern **DevOps tools**.  
It demonstrates how **Docker**, **Kubernetes**, and **Argo CD** integrate seamlessly to enable **reliable**, **automated**, and **observable systems** — all running locally on **Minikube**.  

---

### 🧩 Key Achievements

✅ **GitOps-driven pipeline** for automatic Kubernetes deployments using Argo CD  
📊 **Full observability** and real-time monitoring with Prometheus & Grafana  
🌐 **Deep understanding** of networking nuances within local Kubernetes clusters (and how Minikube tunnels ports dynamically)  

---

💡 *This project encapsulates the full DevOps lifecycle — from containerization to continuous delivery and observability — bringing everything together in one cohesive workflow.*
