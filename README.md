# Kubernetes Prompt Engineering Portfolio

This repository contains a portfolio of professional prompts designed for generating Kubernetes manifests using AI tools such as **Google Cloud kubectl-ai**.  
Each prompt follows the principles of **Prompt Engineering by Google** (clarity, explicit constraints, reproducibility, and role assignment).

The table below includes:

| NAME | PROMPT | DESCRIPTION | EXAMPLE |
|------|--------|-------------|----------|
| app.yaml | Generate a Kubernetes Deployment and Service manifest for a Go demo application named `go-demo-app`. Include labels, selector, port 8080, and minimal configuration. Output only valid YAML. | Base Deployment + Service manifest | [app.yaml](./yaml/app.yaml) |
| app-livenessProbe.yaml | Create a Deployment manifest that includes an HTTP livenessProbe checking `/healthz` on port 8080. Ensure probe delay=5s and period=10s. Output only YAML. | Deployment with livenessProbe | [app-livenessProbe.yaml](./yaml/app-livenessProbe.yaml) |
| app-readinessProbe.yaml | Generate a Deployment manifest that contains an HTTP readinessProbe checking `/ready` on port 8080. Include initialDelaySeconds=3. Return only YAML. | Deployment with readinessProbe | [app-readinessProbe.yaml](./yaml/app-readinessProbe.yaml) |
| app-volumeMounts.yaml | Create a Deployment manifest with a persistentVolumeClaim named `app-pvc` mounted at `/data`. Output strictly YAML. | Deployment with PVC volumeMount | [app-volumeMounts.yaml](./yaml/app-volumeMounts.yaml) |
| app-cronjob.yaml | Generate a Kubernetes CronJob named `go-cronjob` that runs every 5 minutes and executes `go-demo-app --task cleanup`. Output only YAML. | CronJob example | [app-cronjob.yaml](./yaml/app-cronjob.yaml) |
| app-job.yaml | Create a Kubernetes Job manifest that runs a one-time task `go-demo-app --task migrate`. Ensure restartPolicy=Never. Output YAML only. | Job example | [app-job.yaml](./yaml/app-job.yaml) |
| app-multicontainer.yaml | Build a Pod manifest with 2 containers: main app and sidecar logger. Both must share the same volume `/var/log/app`. Output valid YAML only. | Multi-container Pod | [app-multicontainer.yaml](./yaml/app-multicontainer.yaml) |
| app-resources.yaml | Create a Deployment manifest with CPU/memory requests and limits: 100m/200Mi request, 200m/400Mi limit. Output only YAML. | Deployment with resources | [app-resources.yaml](./yaml/app-resources.yaml) |
| app-secret-env.yaml | Generate a Deployment that loads environment variable `APP_PASSWORD` from a Kubernetes Secret named `app-secret`. Output only YAML. | Deployment with secret env | [app-secret-env.yaml](./yaml/app-secret-env.yaml) |

---
## Tools Used

- 📘 **Prompt Engineering by Google** (whitepaper)
- 🤖 **kubectl-ai** (Google Cloud AI Kubernetes plugin)
- ☸️ Kubernetes 1.30+ YAML schema

---

## Author

This repository was created as part of a DevOps engineering portfolio demonstrating AI-assisted infrastructure automation skills.
