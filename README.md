# 📦 Widgetario — Distributed Systems on Kubernetes

Widgetario is a gadget-selling company aiming to deploy its public-facing web application on Kubernetes. This project demonstrates how to configure, deploy, scale, and monitor microservices using Kubernetes with CI/CD and production-ready configurations.

---

## Part 1 - Welcome to Widgetario
Widgetario wants to host its public web application on Kubernetes. Below is an architectural overview of the services and their interactions.

![image](https://github.com/user-attachments/assets/8951d576-cb7a-4f2e-9dd6-87fe3a37fc4d)
![image](https://github.com/user-attachments/assets/80438922-822f-4e7f-85e0-3db9a1a0f832)

---

## Part 2 - Configuration
The project is set up with configurable deployments, services, and environment variables defined via Kubernetes manifests.
![image](https://github.com/user-attachments/assets/a51e5edd-ea9b-479a-a36a-768bf6dfb6ec)

---

## Part 3 - Storage
Persistent storage is implemented using PersistentVolume and PersistentVolumeClaim resources. This ensures that data is retained even if pods are deleted or rescheduled.
![Screenshot 2025-05-16 152611](https://github.com/user-attachments/assets/2c4754b0-ae47-4cdf-974f-d7d1b744d501)

## Part 4 - Ingress
To expose the services, ingress rules are defined using custom domain mappings.
- `widgetario.local` routes to the main web interface 

![image](https://github.com/user-attachments/assets/9ced8f39-2677-49fa-a0d2-7972655b88b7)

- `api.widgetario.local/products` routes to the API  

![Screenshot 2025-05-16 152713](https://github.com/user-attachments/assets/97bdcd8d-eb39-455f-bde1-f7ac4adfe410)

## Part 5 - Productionizing
The application is hardened for production by introducing:
- **Liveness and Readiness Probes**
- **Resource limits and requests**
- **Environment variable handling**
- **Error resilience and graceful degradation strategies**

---

## Part 6 - Observability
Observability is achieved using a combination of **Elastic** and **Grafana** dashboards, providing real-time insights into system performance and health.

Elastic dashboard 
![image](https://github.com/user-attachments/assets/bda0958e-e7c8-4c67-ba5a-c999303474aa)

Grafana
![image](https://github.com/user-attachments/assets/119906f2-e218-418f-8f79-37818d119e31)

## Part 7 - CI/CD
CI/CD pipelines are set up to automate the build, test, and deployment processes using GitHub Actions.

- `widgetario.uat` – User Acceptance Testing environment 
![image](https://github.com/user-attachments/assets/cdc98348-1782-4d0e-a9a5-00d5e96fe035)

- `widgetario.uat/products` – API endpoint in UAT 
![image](https://github.com/user-attachments/assets/040fb9d1-bdd7-4b8b-a728-9980a4da8c7d)

---

## 🧪 How to Run Locally

1. **Clone the repo**
   ```bash
   git clone https://github.com/joyyy-99/kubernetes_hackathon.git
   cd widgetario

2. Deploy to Minikube
   ```bash
    kubectl apply -f manifests/

3. Access the app
- Edit /etc/hosts to route local domains
   ```bash
    127.0.0.1 widgetario.local api.widgetario.local
- Open http://widgetario.local in your browser
