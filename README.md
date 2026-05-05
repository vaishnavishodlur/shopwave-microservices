# 🛍️ ShopWave — E-Commerce Microservices (No Helm / No Ansible)

React + Material UI frontend with 5 microservices on AWS EKS using raw Kubernetes manifests.

## Quick Start

```bash
# Local dev
docker-compose up --build -d
# Visit http://localhost  |  demo@shopwave.com / demo123

# Deploy to K8s
kubectl apply -f k8s/
```

## Services
| Service | Port | Stack |
|---------|------|-------|
| Auth | 3001 | Node.js + PostgreSQL + Redis |
| Products | 3002 | Python + MongoDB + Redis |
| Orders | 3003 | Go + PostgreSQL |
| Payments | 3004 | Node.js + PostgreSQL + Redis |
| Notifications | 3005 | Node.js + MongoDB + Redis pub/sub |
| API Gateway | 80 | Nginx |
| Frontend | 3000 | React + MUI |

## Structure
```
shopwave/
├── frontend/          React + Material UI
├── services/          5 microservices + api-gateway
├── k8s/               Raw Kubernetes manifests (deployments, services, HPA)
├── terraform/         VPC + EKS + ECR modules
├── argocd/            App-of-Apps GitOps manifests
├── jenkins/           Jenkinsfile CI pipeline
├── .github/workflows/ GitHub Actions CI/CD
└── docker-compose.yml Local dev stack
```
