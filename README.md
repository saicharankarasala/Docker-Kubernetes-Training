# 🐳☸️ Docker & Kubernetes Training Repository

A comprehensive, hands-on training repository covering Docker and Kubernetes fundamentals through advanced concepts. This repository provides a structured learning path from containerization basics to production-ready Kubernetes deployments on AWS EKS.

## 📋 Table of Contents

- [About This Repository](#about-this-repository)
- [Learning Path & Structure](#learning-path--structure)
- [Prerequisites](#prerequisites)
- [Quick Start Guide](#quick-start-guide)
- [Daily Training Modules](#daily-training-modules)
- [Additional Resources](#additional-resources)
- [Interview Preparation](#interview-preparation)
- [Contributing](#contributing)

---

## 🎯 About This Repository

This repository contains an **18-day comprehensive training program** that takes you from Docker basics to advanced Kubernetes concepts including:

- **Docker Fundamentals**: Images, containers, networking, volumes, and best practices
- **Kubernetes Core**: Pods, Deployments, Services, ConfigMaps, Secrets
- **AWS EKS**: Managed Kubernetes on AWS with real-world scenarios
- **Production Concepts**: Monitoring, security, storage, and scaling
- **Advanced Topics**: RDS integration, auto-scaling, ingress, and performance optimization
- **Hands-on Projects**: Real applications with step-by-step implementations

### 🏗️ Repository Structure

```
Docker-Kubernetes-Training/
├── Day-1/                    # Docker Introduction
├── Day-2/                    # Docker Commands & Images
├── Day-3/                    # Docker Networking & Volumes
├── Day-4/                    # Multi-container Applications
├── Day-5/                    # Docker Best Practices
├── Day-6/                    # Kubernetes Fundamentals
├── Day-7/                    # ReplicaSets & Auto-healing
├── Day-8/                    # Services & Networking
├── Day-9/                    # ConfigMaps & Secrets
├── Day-10/                   # AWS EKS Introduction
├── Day-11/                   # Namespaces & Context
├── Day-12/                   # EKS Pod Identity
├── Day-13/                   # Persistent Storage (PV/PVC)
├── Day-14/                   # EBS CSI Driver
├── Day-15/                   # EKS Storage with RDS Database
├── Day-16/                   # Advanced Applications (Ball App, Snake App)
├── Day-17/                   # Ingress & Annotations
├── Day-18/                   # Horizontal Pod Autoscaler (HPA)
├── Docker-Interview-Q&A/      # Docker interview questions
├── Kubernetes-Interview-Q&A/ # Kubernetes interview questions
├── iam_policy.json           # AWS IAM policies
└── Definitions.md            # Comprehensive term definitions
```

---

## 🚀 Learning Path & Structure

### **Phase 1: Docker Fundamentals (Days 1-5)**
- **Day 1**: Docker introduction and basic concepts
- **Day 2**: Docker commands, images, and Dockerfile instructions
- **Day 3**: Docker networking, volumes, and multi-stage builds
- **Day 4**: Multi-container applications and Docker Compose
- **Day 5**: Docker best practices and optimization

### **Phase 2: Kubernetes Core (Days 6-9)**
- **Day 6**: Kubernetes architecture, Pods, Deployments, ReplicaSets
- **Day 7**: Auto-healing mechanisms and YAML basics
- **Day 8**: Services (ClusterIP, NodePort, LoadBalancer)
- **Day 9**: ConfigMaps, Secrets, and environment management

### **Phase 3: AWS EKS & Advanced (Days 10-14)**
- **Day 10**: AWS EKS cluster creation and management
- **Day 11**: Namespaces, contexts, and multi-environment setups
- **Day 12**: EKS Pod Identity and IAM integration
- **Day 13**: Persistent Volumes and Persistent Volume Claims
- **Day 14**: EBS CSI Driver and production storage

### **Phase 4: Production & Advanced Topics (Days 15-18)**
- **Day 15**: EKS Storage with RDS Database integration
- **Day 16**: Advanced Applications (Ball App, Snake App with multiple services)
- **Day 17**: Ingress Controllers and Annotations
- **Day 18**: Horizontal Pod Autoscaler (HPA) and performance optimization

---

## 📚 Prerequisites

### **Required Knowledge**
- Basic understanding of Linux command line
- Familiarity with YAML syntax
- Basic networking concepts

### **Required Tools**
- **Docker Desktop** (for local development)
- **kubectl** (Kubernetes command-line tool)
- **AWS CLI** (for EKS modules)
- **eksctl** (for EKS cluster management)
- **Minikube** (for local Kubernetes testing)

### **Installation Commands**
```bash
# Install Docker Desktop
# Download from: https://www.docker.com/products/docker-desktop

# Install kubectl
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/darwin/amd64/kubectl"

# Install eksctl
curl --silent --location "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_$(uname -s)_amd64.tar.gz" | tar xz -C /tmp

# Install Minikube
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-darwin-amd64
```

---

## 🏃‍♂️ Quick Start Guide

### **1. Clone the Repository**
```bash
git clone https://github.com/saicharankarasala/Docker-Kubernetes-Training.git
cd Docker-Kubernetes-Training
```

### **2. Start with Docker Basics**
```bash
cd Day-2/python-application/snake-game
docker build -t snake-game .
docker run -p 5000:5000 snake-game
```

### **3. Set up Local Kubernetes**
```bash
# Start Minikube
minikube start --driver=docker

# Verify cluster
kubectl get nodes
```

### **4. Explore Training Materials**
- Start with **Day-1** for Docker introduction
- Follow the daily progression through **Day-14**
- Use **Definitions.md** as your reference guide
- Practice with **Interview Q&A** sections

---

## 📖 Daily Training Modules

### **🐳 Docker Phase (Days 1-5)**

| Day | Topic | Key Concepts | Hands-on Project |
|-----|-------|--------------|------------------|
| **Day 1** | Docker Introduction | Containers vs VMs, Docker basics | Snake Game setup |
| **Day 2** | Docker Commands & Images | docker run, build, push, pull | Python Flask app containerization |
| **Day 3** | Networking & Volumes | Bridge networks, named volumes, bind mounts | Multi-stage Dockerfile |
| **Day 4** | Multi-container Apps | Docker Compose, service communication | Voting app deployment |
| **Day 5** | Best Practices | Image optimization, security | Production-ready Dockerfile |

### **☸️ Kubernetes Phase (Days 6-9)**

| Day | Topic | Key Concepts | Hands-on Project |
|-----|-------|--------------|------------------|
| **Day 6** | K8s Fundamentals | Pods, Deployments, ReplicaSets | Basic pod deployment |
| **Day 7** | Auto-healing | Controllers, YAML structure | ReplicaSet management |
| **Day 8** | Services | ClusterIP, NodePort, LoadBalancer | Service networking |
| **Day 9** | Configuration | ConfigMaps, Secrets, env vars | Weather dashboard app |

### **☁️ AWS EKS Phase (Days 10-14)**

| Day | Topic | Key Concepts | Hands-on Project |
|-----|-------|--------------|------------------|
| **Day 10** | EKS Introduction | Managed K8s, cluster creation | EKS cluster setup |
| **Day 11** | Namespaces & Context | Multi-environment, RBAC | Namespace isolation |
| **Day 12** | Pod Identity | IAM roles, service accounts | S3 access from pods |
| **Day 13** | Persistent Storage | PV, PVC, EBS integration | Database with persistent storage |
| **Day 14** | CSI Driver | Dynamic provisioning, gp3 volumes | Production storage setup |

### **🚀 Production & Advanced Phase (Days 15-18)**

| Day | Topic | Key Concepts | Hands-on Project |
|-----|-------|--------------|------------------|
| **Day 15** | RDS Integration | External databases, MySQL service | User management with RDS |
| **Day 16** | Advanced Apps | Multi-service applications | Ball App & Snake App |
| **Day 17** | Ingress & Annotations | Load balancing, routing | Ingress controller setup |
| **Day 18** | Auto-scaling | HPA, performance monitoring | Auto-scaling demo |

---

## 🛠️ Additional Resources

### **📚 Documentation**
- **[Definitions.md](./Definitions.md)** - Comprehensive term definitions (100+ concepts)
- **Daily README files** - Detailed explanations for each module
- **YAML examples** - Production-ready Kubernetes manifests
- **Scripts** - Automation for EKS cluster management

### **🎯 Hands-on Projects**
- **Snake Game** (Day 2) - Python Flask application
- **Voting App** (Day 4) - Multi-tier application
- **Weather Dashboard** (Day 9) - React + Node.js with ConfigMaps/Secrets
- **EKS Storage Demo** (Day 14) - Production storage with EBS
- **User Management with RDS** (Day 15) - Database integration with MySQL
- **Ball App** (Day 16) - Interactive web application with Node.js
- **Enhanced Snake App** (Day 16) - Multi-service deployment
- **Ingress Demo** (Day 17) - Advanced networking and routing
- **HPA Demo** (Day 18) - Auto-scaling and performance optimization

### **🔧 Tools & Scripts**
- **EKS Cluster Scripts** - Automated cluster creation/deletion
- **Docker Build Scripts** - Image building automation
- **Kubernetes Manifests** - Ready-to-use YAML files
- **IAM Policies** - AWS permissions and policies configuration
- **Troubleshooting Guides** - Common issues and solutions

---

## 💼 Interview Preparation

### **🐳 Docker Interview Questions**
- Container vs VM concepts
- Dockerfile best practices
- Networking and storage
- Multi-stage builds
- Security considerations

### **☸️ Kubernetes Interview Questions**
- Pod lifecycle and management
- Service types and networking
- Storage and persistence
- Security and RBAC
- AWS EKS specifics

### **📋 Interview Topics Covered**
- **Fundamentals**: 50+ basic concepts
- **Architecture**: Control plane, worker nodes, components
- **Operations**: Deployment, scaling, monitoring
- **Security**: RBAC, secrets, network policies
- **Cloud**: AWS EKS, IAM, storage integration

---

## 🎓 Learning Outcomes

After completing this training, you will be able to:

### **Docker Skills**
- ✅ Containerize applications with Docker
- ✅ Create optimized Dockerfiles
- ✅ Manage multi-container applications
- ✅ Implement Docker networking and storage
- ✅ Apply Docker best practices

### **Kubernetes Skills**
- ✅ Deploy applications on Kubernetes
- ✅ Manage pods, deployments, and services
- ✅ Configure ConfigMaps and Secrets
- ✅ Implement health checks and monitoring
- ✅ Handle persistent storage

### **AWS EKS Skills**
- ✅ Create and manage EKS clusters
- ✅ Implement Pod Identity and IAM integration
- ✅ Configure persistent storage with EBS
- ✅ Integrate with RDS databases
- ✅ Set up production-ready environments
- ✅ Troubleshoot cluster issues

### **Production Readiness**
- ✅ Design scalable container architectures
- ✅ Implement security best practices
- ✅ Manage configuration and secrets
- ✅ Set up ingress controllers and load balancing
- ✅ Configure auto-scaling with HPA
- ✅ Integrate external databases and services
- ✅ Monitor and troubleshoot applications
- ✅ Prepare for technical interviews

---

## 🤝 Contributing

This repository is designed for learning and training purposes. Contributions are welcome:

1. **Report Issues**: Found a bug or unclear explanation?
2. **Suggest Improvements**: Better examples or clearer documentation?
3. **Add Examples**: More hands-on projects or use cases?
4. **Update Content**: Keep information current with latest versions

### **How to Contribute**
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

---

## 📞 Support & Community

- **Issues**: Use GitHub Issues for bug reports and questions
- **Discussions**: Join community discussions for help
- **Documentation**: Check daily README files for detailed explanations
- **Definitions**: Reference the comprehensive definitions guide

---

## 📄 License

This training repository is provided for educational purposes. Feel free to use, modify, and share the content for learning and training purposes.

---

## 🎉 Getting Started

Ready to begin your Docker and Kubernetes journey? Start here:

1. **📖 Read the [Definitions.md](./Definitions.md)** for comprehensive term explanations
2. **🐳 Begin with [Day-1](./Day-1/)** for Docker introduction
3. **☸️ Progress through [Day-6](./Day-6/)** for Kubernetes fundamentals
4. **☁️ Advance to [Day-10](./Day-10/)** for AWS EKS
5. **🚀 Master advanced topics with [Day-15](./Day-15/)** for production scenarios
6. **💼 Practice with [Interview Q&A](./Docker-Interview-Q&A/)** for job preparation

**Happy Learning! 🚀**

---

*This repository provides a complete 18-day learning path from Docker basics to production-ready Kubernetes deployments with advanced topics including RDS integration, auto-scaling, and ingress controllers. Each day builds upon the previous concepts, ensuring a solid foundation for container orchestration and cloud-native applications.*