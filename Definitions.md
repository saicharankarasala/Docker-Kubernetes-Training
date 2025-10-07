# Docker & Kubernetes Training - Comprehensive Definitions

## Table of Contents
- [Docker Fundamentals](#docker-fundamentals)
- [Docker Commands](#docker-commands)
- [Docker Networking](#docker-networking)
- [Docker Storage](#docker-storage)
- [Dockerfile Instructions](#dockerfile-instructions)
- [Kubernetes Fundamentals](#kubernetes-fundamentals)
- [Kubernetes Objects](#kubernetes-objects)
- [Kubernetes Services](#kubernetes-services)
- [Kubernetes Storage](#kubernetes-storage)
- [AWS EKS](#aws-eks)
- [Security & Access Control](#security--access-control)
- [Monitoring & Health Checks](#monitoring--health-checks)
- [Best Practices](#best-practices)

---

## Docker Fundamentals

### Q: What is Docker?
**A:** Docker is a platform to package applications and their dependencies into a single unit called a container. Containers run the same way across any environment, solving the "works on my machine" problem.

### Q: What is a Docker Container?
**A:** A Docker container is a running instance of a Docker image. It's an isolated, lightweight process that includes the application and all its dependencies.

### Q: What is a Docker Image?
**A:** A Docker image is a read-only, layered file system that contains everything needed to run a specific application inside a Docker container. It includes a minimal base operating system, language runtime, application source code, and all dependencies.

### Q: What is a Dockerfile?
**A:** A Dockerfile is a script with step-by-step instructions for building a Docker image. Each instruction tells Docker what to do and creates a layer in the final image.

### Q: What is Docker Hub?
**A:** Docker Hub is a cloud-based registry service where you can find and share Docker images. It's like GitHub for Docker images.

### Q: What is Container Orchestration?
**A:** Container orchestration is the automated process of managing, deploying, scaling, and monitoring containerized applications across multiple hosts.

---

## Docker Commands

### Q: What does `docker run` do?
**A:** `docker run` creates and starts a new container from an image. It can run in foreground or background mode with various options like port mapping and volume mounting.

### Q: What does `docker build` do?
**A:** `docker build` builds a Docker image from a Dockerfile in the current directory. It processes each instruction and creates layers.

### Q: What does `docker pull` do?
**A:** `docker pull` downloads an image from a registry (like Docker Hub) to your local system.

### Q: What does `docker ps` do?
**A:** `docker ps` shows running containers. Use `docker ps -a` to see all containers including stopped ones.

### Q: What does `docker exec` do?
**A:** `docker exec` runs a command inside a running container, commonly used to get a shell session with `docker exec -it <container> bash`.

### Q: What does `docker logs` do?
**A:** `docker logs` shows the output and logs of a container, useful for debugging and monitoring.

### Q: What does `docker stop` vs `docker kill` do?
**A:** `docker stop` gracefully stops a container (SIGTERM), while `docker kill` forcefully stops it (SIGKILL).

---

## Docker Networking

### Q: What is Docker Bridge Network?
**A:** Docker Bridge Network is the default network type that creates a private internal network. Containers get private IPs and can communicate using IP addresses or names (in user-defined bridges).

### Q: What is Docker Host Network?
**A:** Docker Host Network makes the container share the host's network stack directly. The container uses the host's IP and ports without port mapping.

### Q: What is Docker None Network?
**A:** Docker None Network provides no networking to the container. It's completely isolated with no internet, host, or container communication.

### Q: What is Docker Overlay Network?
**A:** Docker Overlay Network spans across multiple Docker hosts, enabling containers on different machines to communicate as if they were on the same LAN.

### Q: What is the difference between default bridge and user-defined bridge?
**A:** Default bridge only supports IP-based communication, while user-defined bridges include built-in DNS service allowing containers to communicate by name.

---

## Docker Storage

### Q: What is a Docker Volume?
**A:** A Docker Volume is a mechanism to store data outside the container's writable layer, providing persistent storage that survives container deletion.

### Q: What is an Anonymous Volume?
**A:** An Anonymous Volume is created when you specify only the container path without a name. Docker assigns a random hash-like ID, making it hard to identify or reuse.

### Q: What is a Named Volume?
**A:** A Named Volume is explicitly named and managed by Docker. It's easy to reference, inspect, and reuse across multiple containers.

### Q: What is a Bind Mount?
**A:** A Bind Mount maps a specific host folder to a path inside the container. Data is directly visible on the host machine, great for development.

### Q: What is the difference between volumes and bind mounts?
**A:** Volumes are managed by Docker and stored in Docker-managed locations, while bind mounts use actual host paths and are directly accessible from the host filesystem.

---

## Dockerfile Instructions

### Q: What does `FROM` do in a Dockerfile?
**A:** `FROM` sets the base image to use for building the Docker image. It's typically the first instruction in a Dockerfile.

### Q: What does `WORKDIR` do in a Dockerfile?
**A:** `WORKDIR` sets the working directory inside the image where subsequent instructions will be executed.

### Q: What does `COPY` do in a Dockerfile?
**A:** `COPY` copies files or folders from the local machine into the Docker image during the build process.

### Q: What does `RUN` do in a Dockerfile?
**A:** `RUN` executes a command while building the image. Docker creates a temporary container, runs the command, captures the changes, and commits them as a new layer.

### Q: What does `CMD` do in a Dockerfile?
**A:** `CMD` defines the default command to run when a container starts. It can be overridden when running the container.

### Q: What does `ENTRYPOINT` do in a Dockerfile?
**A:** `ENTRYPOINT` defines the primary executable that cannot be overridden. It's often used with CMD to create flexible command structures.

### Q: What does `EXPOSE` do in a Dockerfile?
**A:** `EXPOSE` documents the port used by the container. It doesn't actually publish the port - you still need `-p` flag when running.

### Q: What does `ENV` do in a Dockerfile?
**A:** `ENV` sets environment variables that will be available in the container at runtime.

### Q: What is the difference between CMD and ENTRYPOINT?
**A:** CMD provides default arguments that can be overridden, while ENTRYPOINT defines a fixed command. They work together: `ENTRYPOINT ["python"]` + `CMD ["app.py"]` = `python app.py`.

### Q: What is a Multi-Stage Dockerfile?
**A:** A Multi-Stage Dockerfile uses multiple `FROM` instructions to build in one stage and copy only artifacts to a smaller runtime image, reducing final image size and improving security.

---

## Kubernetes Fundamentals

### Q: What is Kubernetes?
**A:** Kubernetes is a container orchestration platform that manages the deployment, scaling, and lifecycle of containerized applications across clusters of machines.

### Q: What is a Kubernetes Cluster?
**A:** A Kubernetes cluster is a set of nodes (machines) that run containerized applications. It consists of a control plane and worker nodes.

### Q: What is the Kubernetes Control Plane?
**A:** The Control Plane is the brain of Kubernetes, consisting of API Server, etcd, Controller Manager, and Scheduler that manage the cluster state and make decisions.

### Q: What is the Kubernetes API Server?
**A:** The API Server is the front-end of the Kubernetes control plane. It exposes the Kubernetes API and processes all cluster requests.

### Q: What is etcd in Kubernetes?
**A:** etcd is a distributed key-value store that contains all cluster state and configuration data. It's the single source of truth for the cluster.

### Q: What is the Kubernetes Scheduler?
**A:** The Scheduler assigns pods to available nodes based on resource requirements, constraints, and policies.

### Q: What is the Controller Manager in Kubernetes?
**A:** The Controller Manager runs controllers that monitor and maintain the desired state of various Kubernetes objects like deployments, services, and nodes.

### Q: What is kubelet?
**A:** kubelet is an agent that runs on each node and ensures containers are running in pods as specified by the control plane.

### Q: What is kube-proxy?
**A:** kube-proxy is a network proxy that runs on each node and manages networking rules, enabling service discovery and load balancing.

### Q: What is Minikube?
**A:** Minikube is a tool that runs a single-node Kubernetes cluster locally for development and learning purposes.

---

## Kubernetes Objects

### Q: What is a Pod in Kubernetes?
**A:** A Pod is the smallest deployable unit in Kubernetes. It can contain one or more containers that share storage and network resources.

### Q: What is a Deployment in Kubernetes?
**A:** A Deployment manages ReplicaSets and provides declarative updates to applications. It handles rolling updates, rollbacks, and scaling.

### Q: What is a ReplicaSet in Kubernetes?
**A:** A ReplicaSet ensures a specified number of pod replicas are always running. It uses selectors to identify and manage pods.

### Q: What is a DaemonSet in Kubernetes?
**A:** A DaemonSet ensures that a copy of a pod runs on every node in the cluster, commonly used for logging, monitoring, or networking agents.

### Q: What is a StatefulSet in Kubernetes?
**A:** A StatefulSet manages stateful applications by providing stable network identities and persistent storage for pods.

### Q: What is a Job in Kubernetes?
**A:** A Job creates one or more pods and ensures they complete successfully. It's used for batch processing or one-time tasks.

### Q: What is a CronJob in Kubernetes?
**A:** A CronJob creates Jobs on a time-based schedule, similar to cron in Linux systems.

### Q: What is a Namespace in Kubernetes?
**A:** A Namespace provides a way to divide a cluster into smaller, logical sections, allowing multiple teams or projects to share a cluster.

### Q: What is a ServiceAccount in Kubernetes?
**A:** A ServiceAccount provides an identity for pods to access the Kubernetes API or external services.

---

## Kubernetes Services

### Q: What is a Service in Kubernetes?
**A:** A Service provides a stable network endpoint for pods. It gives a permanent IP and DNS name that doesn't change when pods are recreated.

### Q: What is a ClusterIP Service?
**A:** ClusterIP is the default Service type that provides an internal IP and DNS name accessible only within the cluster.

### Q: What is a NodePort Service?
**A:** NodePort Service exposes the service on each node's IP at a high port (30000-32767), making it accessible from outside the cluster.

### Q: What is a LoadBalancer Service?
**A:** LoadBalancer Service provisions an external load balancer (like AWS ELB) with a public IP or DNS for external access.

### Q: What is an ExternalName Service?
**A:** ExternalName Service maps a service to an external DNS name, allowing pods to access external services using internal service names.

### Q: What is the difference between port, targetPort, and nodePort?
**A:** port is the service's internal port, targetPort is the container's port, and nodePort is the external port on the node for NodePort services.

---

## Kubernetes Storage

### Q: What is a PersistentVolume (PV)?
**A:** A PersistentVolume is a storage resource in the cluster that can be provisioned statically or dynamically and is independent of pod lifecycle.

### Q: What is a PersistentVolumeClaim (PVC)?
**A:** A PersistentVolumeClaim is a request for storage by a user. It specifies size and access modes, and Kubernetes finds a suitable PV to bind to it.

### Q: What is a StorageClass?
**A:** A StorageClass defines different classes of storage available in the cluster and enables dynamic provisioning of persistent volumes.

### Q: What are Access Modes in Kubernetes storage?
**A:** Access Modes define how volumes can be mounted:
- ReadWriteOnce (RWO): Single node read/write
- ReadOnlyMany (ROX): Multiple nodes read-only
- ReadWriteMany (RWX): Multiple nodes read/write

### Q: What is Volume Binding Mode?
**A:** Volume Binding Mode determines when volume binding occurs:
- Immediate: Bind as soon as PVC is created
- WaitForFirstConsumer: Bind when pod using PVC is scheduled

---

## AWS EKS

### Q: What is Amazon EKS?
**A:** Amazon EKS (Elastic Kubernetes Service) is AWS's managed Kubernetes service where AWS manages the control plane and you manage worker nodes.

### Q: What is the difference between Kubernetes and EKS?
**A:** Kubernetes is the open-source container orchestration system, while EKS is AWS's managed service that runs Kubernetes with AWS-managed control plane.

### Q: What is OIDC in EKS?
**A:** OIDC (OpenID Connect) in EKS enables mapping Kubernetes Service Accounts to AWS IAM Roles through IAM Roles for Service Accounts (IRSA).

### Q: What is IRSA in EKS?
**A:** IRSA (IAM Roles for Service Accounts) allows pods to assume IAM roles without storing AWS credentials, providing secure access to AWS services.

### Q: What is EKS Pod Identity?
**A:** EKS Pod Identity is a newer method for pods to access AWS services without managing static credentials, using the EKS Pod Identity Agent.

### Q: What are EKS Add-ons?
**A:** EKS Add-ons are AWS-managed cluster components like CoreDNS, VPC CNI, kube-proxy, and EBS CSI Driver that are versioned and easy to update.

### Q: What is the EBS CSI Driver?
**A:** The EBS CSI Driver enables Kubernetes to use Amazon EBS volumes as persistent storage, allowing dynamic provisioning and management of EBS volumes.

---

## Security & Access Control

### Q: What is a ConfigMap in Kubernetes?
**A:** A ConfigMap is an API object used to store non-sensitive configuration data that can be consumed by pods as environment variables or mounted files.

### Q: What is a Secret in Kubernetes?
**A:** A Secret is an API object used to store sensitive data like passwords, tokens, and keys in base64 encoded format.

### Q: What is RBAC in Kubernetes?
**A:** RBAC (Role-Based Access Control) is a method of regulating access to computer or network resources based on the roles of individual users.

### Q: What is a Role in Kubernetes?
**A:** A Role defines permissions within a namespace, specifying what actions can be performed on which resources.

### Q: What is a ClusterRole in Kubernetes?
**A:** A ClusterRole defines permissions across the entire cluster, not limited to a specific namespace.

### Q: What is a RoleBinding in Kubernetes?
**A:** A RoleBinding grants the permissions defined in a Role to a user or set of users within a namespace.

### Q: What is a ClusterRoleBinding in Kubernetes?
**A:** A ClusterRoleBinding grants the permissions defined in a ClusterRole to a user or set of users across the entire cluster.

---

## Monitoring & Health Checks

### Q: What is a Liveness Probe in Kubernetes?
**A:** A Liveness Probe checks whether the container is still alive. If it fails, Kubernetes restarts the container automatically.

### Q: What is a Readiness Probe in Kubernetes?
**A:** A Readiness Probe checks whether the container is ready to serve traffic. If it fails, the pod is temporarily removed from service endpoints.

### Q: What is a Startup Probe in Kubernetes?
**A:** A Startup Probe indicates whether the application in the container has started. It's used for slow-starting containers and overrides liveness and readiness probes.

### Q: What is the difference between Liveness and Readiness Probes?
**A:** Liveness probes restart unhealthy containers, while readiness probes prevent traffic from reaching containers that aren't ready to serve requests.

### Q: What are Resource Requests in Kubernetes?
**A:** Resource Requests define the minimum resources (CPU/memory) a container needs to run. The scheduler uses this to find appropriate nodes.

### Q: What are Resource Limits in Kubernetes?
**A:** Resource Limits define the maximum resources a container can consume. If exceeded, the container is killed (memory) or throttled (CPU).

### Q: What is a ResourceQuota in Kubernetes?
**A:** A ResourceQuota restricts the amount of resources (CPU, memory, pods) that a namespace can consume, preventing resource hogging.

---

## Best Practices

### Q: What is the 12-Factor App methodology?
**A:** The 12-Factor App is a methodology for building software-as-a-service applications that emphasizes portability, scalability, and maintainability.

### Q: What is Infrastructure as Code (IaC)?
**A:** Infrastructure as Code is the practice of managing and provisioning infrastructure through machine-readable definition files rather than manual processes.

### Q: What is GitOps?
**A:** GitOps is a methodology that uses Git as the single source of truth for declarative infrastructure and applications, with automated deployment processes.

### Q: What is Blue-Green Deployment?
**A:** Blue-Green Deployment is a deployment strategy where two identical production environments (blue and green) are maintained, with traffic switched between them.

### Q: What is Canary Deployment?
**A:** Canary Deployment is a deployment strategy where a new version is gradually rolled out to a small subset of users before full deployment.

### Q: What is Rolling Update in Kubernetes?
**A:** Rolling Update is a deployment strategy where old pods are gradually replaced with new ones, ensuring zero downtime during updates.

### Q: What is Horizontal Pod Autoscaler (HPA)?
**A:** HPA automatically scales the number of pods in a deployment based on observed CPU utilization or custom metrics.

### Q: What is Vertical Pod Autoscaler (VPA)?
**A:** VPA automatically adjusts the CPU and memory requests and limits of containers based on historical usage data.

### Q: What is Cluster Autoscaler?
**A:** Cluster Autoscaler automatically adjusts the size of the Kubernetes cluster by adding or removing nodes based on resource demands.

### Q: What is the difference between Stateful and Stateless applications?
**A:** Stateful applications maintain data and state between requests, while stateless applications don't store client session data and treat each request independently.

---

## Additional Concepts

### Q: What is Container Runtime?
**A:** Container Runtime is the software responsible for running containers. Examples include Docker, containerd, and CRI-O.

### Q: What is CNI (Container Network Interface)?
**A:** CNI is a specification and libraries for writing plugins to configure network interfaces in Linux containers.

### Q: What is CSI (Container Storage Interface)?
**A:** CSI is a standard for exposing arbitrary block and file storage systems to containerized workloads on Container Orchestration systems.

### Q: What is Service Mesh?
**A:** Service Mesh is a dedicated infrastructure layer for handling service-to-service communication in microservices architectures.

### Q: What is Helm in Kubernetes?
**A:** Helm is a package manager for Kubernetes that simplifies the deployment and management of applications using charts.

### Q: What is a Helm Chart?
**A:** A Helm Chart is a collection of files that describe a related set of Kubernetes resources, packaged for easy deployment and management.

### Q: What is Operator Pattern in Kubernetes?
**A:** The Operator Pattern extends Kubernetes to manage complex applications by creating custom controllers that understand application-specific logic.

### Q: What is Custom Resource Definition (CRD)?
**A:** CRD allows you to define custom resources in Kubernetes, extending the API with domain-specific objects.

### Q: What is Admission Controller in Kubernetes?
**A:** Admission Controllers are plugins that govern and enforce how the API server processes requests, validating and mutating objects before they are stored.

### Q: What is Webhook in Kubernetes?
**A:** Webhooks are HTTP callbacks that allow external services to be notified of events in Kubernetes, enabling custom validation and mutation logic.

---

*This comprehensive definitions guide covers all major concepts from the Docker-Kubernetes Training repository. Each term is explained in a question-answer format for easy reference and learning.*
