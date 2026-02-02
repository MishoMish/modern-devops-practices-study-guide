# 📚 COMPREHENSIVE DevOps EXAM STUDY GUIDE

## Table of Contents
1. [Course Syllabus Overview](#course-syllabus-overview)
2. [Module 1: SDLC and Version Control](#module-1-sdlc-and-version-control)
3. [Module 2: Deployment Pipelines & CI](#module-2-deployment-pipelines--ci)
4. [Module 3: Docker & Containerization](#module-3-docker--containerization)
5. [Module 4: Kubernetes](#module-4-kubernetes)
6. [Module 5: DevSecOps & Continuous Delivery](#module-5-devsecops--continuous-delivery)
7. [Module 6: Microservices Architecture](#module-6-microservices-architecture)
8. [Module 7: AWS Cloud Services](#module-7-aws-cloud-services)
9. [Module 8: Infrastructure as Code (Terraform)](#module-8-infrastructure-as-code-terraform)
10. [Module 9: Flyway (Database Migrations)](#module-9-flyway-database-migrations)
11. [Exam-Style Multiple Choice Questions](#exam-style-multiple-choice-questions)

---

# Course Syllabus Overview

## What IS Covered in This Course

Based on the **lecture presentations** and provided materials, the following topics are **INCLUDED**:

### From Lecture Presentations:
1. **SDLC and Version Control** (S2) - DevOps history, Git workflows, SCM
2. **Deployment Pipelines and CI** (S4) - CI practices, toolchains, testing
3. **DevSecOps and CD** (S5) - Security testing types (SAST/DAST/SCA/IAST/RASP), CD practices
4. **Microservices and Docker** - Microservice principles, containers vs VMs
5. **Kubernetes** (S7 + CNCF Webinar) - Architecture, objects, services, Helm
6. **AWS Cloud Services** (S8, S9) - EC2, S3, VPC, Lambda, RDS, ECS/EKS
7. **Infrastructure as Code** (S10) - Terraform, declarative vs procedural
8. **Database Versioning** - Flyway migrations

### Key DevOps Concepts from Lectures:
- "Concept to Cash" - the journey from idea to revenue
- DevOps and Agile relationship
- Everything as Code philosophy
- Trunk-Based Development
- Deployment Pipeline as "the ONLY route to production"
- Six Advantages of Cloud Computing
- AWS Well-Architected Framework (6 Pillars)

---

# Module 1: SDLC and Version Control

## Software Development Life Cycle (SDLC)

### DevOps Definition
> **DevOps**: Set of practices for automation and unification of development, administration, and quality management processes.

### Key DevOps Quotes (From Lectures - Important!)
> "Having a dedicated DevOps team is organizational anti-pattern."
> "Buying DevOps is like buying Agile."

### Concept to Cash
The journey from idea to revenue - DevOps practices aim to shorten this cycle.

## Source Control Management (SCM)

### Definition
> **SCM (Source Control Management)**: Tracks running history of changes to a code base, helps resolve conflicts when multiple developers work on shared codebase.

### Everything as Code Philosophy
- Infrastructure as Code
- Configuration as Code
- Pipeline as Code
- Documentation as Code

## Git & Version Control

### What is Git?
**Definition**: Git is a distributed Version Control System (VCS) that allows users to track different versions of their code base.

### Why Use Git?
- Track changes to code over time
- Revert to previous working versions if problems occur
- Enable collaboration between multiple developers
- Maintain history of all changes

### Key Terminology

| Term | Definition |
|------|------------|
| Repository | A folder managed by Git |
| Clone | Copy a repository from remote to local |
| Commit | A snapshot of changes |
| Push | Send local commits to remote repository |
| Pull | Fetch and merge changes from remote |
| Branch | An independent line of development |
| Merge | Combine changes from different branches |

## Git Branching Workflows (Critical for Exam!)

| Workflow | Description |
|----------|-------------|
| **Basic Git Workflow** | Simple linear workflow |
| **Feature Branch Workflow** | Separate branch for each feature |
| **Feature Workflow + Stable Branches** | Feature branches + stable branches |
| **Git Flow** | Comprehensive: develop, release, hotfix branches |
| **Trunk-Based Development** | Continuous integration into main branch |

### GitHub
- A Git hosting website
- Stores repositories online
- Enables collaboration on projects
- Supports private and public repositories

---

# Module 2: Deployment Pipelines & CI

## Deployment Pipeline

### Key Definition
> **Deployment Pipeline**: Organizes ALL steps required to go from idea to releasable software; automates development process to produce software repeatably and reliably.

### Deployment Pipeline Characteristics (Critical!)
- Goes from **Commit to Releasable Outcome**
- **As quick as possible**
- **Repeatably**
- **Reliably**
- **Auditable**
- **The ONLY route to production**
- Includes: unit tests, acceptance tests, validation, integration, version control, sign-offs

## CI/CD Toolchain (Important for Exam!)

| Source Control | CI/CD Tool |
|----------------|------------|
| GitHub | GitHub Actions |
| BitBucket | BitBucket Pipelines |
| Azure DevOps repo | Azure DevOps Pipelines |
| GitLab | GitLab CI |
| (Any) | Jenkins |
| (Any) | Circle CI |

## Continuous Integration (CI)

### Key Definition
> **Continuous Integration (CI)**: Software development practice where developers regularly merge their code changes into a central repository, after which automated builds and tests are run.

### CI Components
1. **Automation component** (e.g., CI or build service)
2. **Cultural component** (learning to integrate frequently)

### Goals of CI
- Find and address bugs quicker
- Improve software quality
- Reduce time to validate and release new software updates

### CI Practices (Critical for Exam!)
1. Maintain a **single source repository** (Git)
2. **Automate the build**
3. Make your build **self-testing**
4. **Every commit** should build on an integration machine
5. **Keep the build fast**
6. **Test in a clone of production environment**
7. Make it easy for anyone to get the **latest executable version**
8. Everyone can **see what's happening**
9. **Automate deployment**

### Testing Practices in CI Process
1. Software build
2. Unit testing
3. Code quality
4. Integration testing
5. Security testing
6. Performance testing
7. UI testing
8. Accessibility testing
9. Test the infrastructure with the code
10. Data Migration

## GitHub Actions

### Workflow File Structure

```yaml
name: Main workflow        # Name of the workflow
on: push                   # Trigger event
jobs:                      # Collection of jobs
  Build:                   # Job name
    runs-on: ubuntu-latest # Runner type
    container: gradle:6-jdk11  # Optional container
    steps:                 # Sequence of tasks
      - name: Clone repository
        uses: actions/checkout@v4
      - name: Build
        run: ./build.sh
```

### Key Components

| Component | Description |
|-----------|-------------|
| `name` | Workflow name displayed in GitHub UI |
| `on` | Event that triggers the workflow |
| `jobs` | Collection of jobs to run |
| `runs-on` | Type of runner (e.g., `ubuntu-latest`) |
| `container` | Docker container to run the job in |
| `steps` | Sequence of tasks within a job |
| `uses` | Reference to an action |
| `run` | Shell command to execute |

### Trigger Events

```yaml
# Single event
on: push

# Multiple events
on: [push, pull_request]

# With branch filtering
on:
  push:
    branches: [main]
  pull_request:
    branches: [main]

# Manual trigger
on: workflow_dispatch
```

### Artifacts

**Upload Artifact:**
```yaml
- uses: actions/upload-artifact@v4
  with:
    name: my-artifact
    path: ./build/
```

**Download Artifact:**
```yaml
- uses: actions/download-artifact@v4
  with:
    name: my-artifact
    path: ./downloaded/
```

### Job Dependencies

```yaml
jobs:
  Build:
    runs-on: ubuntu-latest
    steps: [...]
  
  Docker-image:
    runs-on: ubuntu-latest
    needs: [Build]  # Runs after Build completes
    steps: [...]
```

### Matrix Builds

```yaml
strategy:
  matrix:
    container: ["gradle:6-jdk8", "gradle:6-jdk11", "gradle:6-jdk17"]
container:
  image: ${{ matrix.container }}
```

### Environment Variables

```yaml
env:
  github_username: ${{ github.actor }}
  github_password: ${{ secrets.GITHUB_TOKEN }}
  GIT_COMMIT: ${{ github.sha }}
```

### Permissions

```yaml
permissions:
  packages: write  # Required for pushing Docker images
```

### Branch Protection Rules
- Require status checks to pass before merging
- Require branches to be up to date before merging
- Prevent direct pushes to protected branches

---

# Module 3: Docker & Containerization

## Core Terminology

| Term | Definition |
|------|------------|
| Docker Container | An isolated, runnable environment that holds everything needed to run an application |
| Docker Image | A lightweight, standalone package containing code, libraries, and dependencies |
| Docker Daemon | Background service running on the host that manages containers |
| Docker Client | Command line tool to interact with the Docker daemon |
| Docker Hub | Public registry of Docker images |

## Essential Docker Commands

### Running Containers

```bash
# Basic run
docker run hello-world

# Run with port mapping (host:container)
docker run -p 8080:80 nginx

# Run in detached mode (background)
docker run -d nginx

# Run interactively with terminal
docker run -it alpine /bin/sh

# Run with auto-remove on exit
docker run --rm alpine

# Run with custom name
docker run --name my-container nginx

# Run with environment variable
docker run -e MYSQL_ROOT_PASSWORD=secret mysql
```

### Container Management

```bash
docker ps              # List running containers
docker ps -a           # List all containers
docker stop <name/id>  # Stop container
docker start <name/id> # Start container
docker rm <name/id>    # Remove container
docker logs <name/id>  # View logs
docker logs -f <name>  # Follow logs
docker exec -it <name> bash  # Execute command in container
docker inspect <name>  # Detailed container info
```

### Image Management

```bash
docker pull alpine           # Download image
docker image ls              # List images
docker images               # Alias for image ls
docker build -t myapp .      # Build image from Dockerfile
docker image rm <image>      # Remove image
docker rmi <image>           # Alias for image rm
docker image prune           # Remove unused images
```

### Volume Commands

```bash
# Bind mount
docker run -v /host/path:/container/path nginx

# Read-only bind mount
docker run -v /host/path:/container/path:ro nginx

# Named volume
docker volume create data
docker run -v data:/container/path nginx

# Volume management
docker volume ls
docker volume inspect data
docker volume rm data
docker volume prune
```

### Cleanup Commands

```bash
docker container prune  # Remove stopped containers
docker image prune      # Remove dangling images
docker network prune    # Remove unused networks
docker volume prune     # Remove unused volumes
docker system prune     # Remove all unused objects
```

## Dockerfile Instructions

| Instruction | Purpose | Example |
|-------------|---------|---------|
| `FROM` | Base image (REQUIRED first) | `FROM ubuntu:22.04` |
| `RUN` | Execute command during build | `RUN apt-get update` |
| `COPY` | Copy files from host to image | `COPY app.py /app/` |
| `ADD` | Copy with extraction (use for tar files) | `ADD app.tar.gz /app/` |
| `CMD` | Default command when container starts | `CMD ["python3", "app.py"]` |
| `ENTRYPOINT` | Command that always runs | `ENTRYPOINT ["./app"]` |
| `EXPOSE` | Document which port the app uses | `EXPOSE 5000` |
| `WORKDIR` | Set working directory | `WORKDIR /app` |
| `ENV` | Set environment variable | `ENV APP_ENV=prod` |

### Example Dockerfile

```dockerfile
FROM ubuntu:22.04

RUN apt-get update -y
RUN apt-get install -y python3 python3-pip

COPY requirements.txt /usr/src/app/
RUN pip3 install -r /usr/src/app/requirements.txt

COPY app.py /usr/src/app/

EXPOSE 5000

CMD ["python3", "/usr/src/app/app.py"]
```

## Multi-Stage Builds

**Purpose**: Create smaller production images by separating build and runtime stages.

```dockerfile
# Build stage
FROM golang:1.19 AS builder
WORKDIR /app
COPY . /app
RUN go build -o myapp

# Final stage (smaller)
FROM alpine
WORKDIR /app
COPY --from=builder /app/myapp /app/
ENTRYPOINT ["./myapp"]
```

**Key Points**:
- Use `AS <name>` to name build stages
- Use `COPY --from=<stage>` to copy from previous stage
- Final image only contains runtime dependencies
- Can dramatically reduce image size

## Docker Compose

**Purpose**: Define and run multi-container applications.

```yaml
services:
  wordpress:
    image: wordpress:5.7.2-apache
    ports:
      - 8080:80
    environment:
      WORDPRESS_DB_HOST: mysql
      WORDPRESS_DB_PASSWORD: secret

  mysql:
    image: mysql:5.7
    environment:
      MYSQL_ROOT_PASSWORD: secret
      MYSQL_DATABASE: wordpress
```

### Docker Compose Commands

```bash
docker compose up -d       # Start services in background
docker compose down        # Stop and remove services
docker compose ps          # List running services
docker compose logs        # View logs
docker compose restart     # Restart services
```

## Docker Networking

```bash
# Create network
docker network create mynetwork

# Run container on network
docker run --network mynetwork --name app nginx

# Inspect network
docker network inspect mynetwork
```

**Key Point**: Containers on the same network can communicate using container names as DNS hostnames.

---

# Module 4: Kubernetes

## Core Concepts

### What is Kubernetes?
A container orchestration platform for automating deployment, scaling, and management of containerized applications.

### Key Resources

| Resource | Purpose |
|----------|---------|
| Pod | Smallest deployable unit, contains one or more containers |
| Namespace | Virtual cluster for resource isolation |
| Deployment | Manages ReplicaSets and rolling updates |
| ReplicaSet | Ensures specified number of pod replicas |
| Service | Exposes pods to network traffic |
| ConfigMap | Store non-confidential configuration |
| Secret | Store sensitive data |
| PersistentVolume | Storage resource |
| PersistentVolumeClaim | Request for storage |

## kubectl Commands

### Basic Commands

```bash
# Get resources
kubectl get pods
kubectl get pods -A          # All namespaces
kubectl get pods -o wide     # More details
kubectl get pods --show-labels

# Describe resources
kubectl describe pod nginx

# Create from YAML
kubectl apply -f pod.yaml
kubectl create -f pod.yaml

# Delete resources
kubectl delete pod nginx
kubectl delete -f pod.yaml

# Execute commands
kubectl exec -it nginx -- /bin/sh

# View logs
kubectl logs nginx
kubectl logs nginx -f        # Follow logs
kubectl logs nginx -p        # Previous instance
```

### Generating YAML

```bash
# Generate YAML without creating
kubectl run nginx --image=nginx --dry-run=client -o yaml > pod.yaml

# Create namespace YAML
kubectl create namespace myns --dry-run=client -o yaml
```

## Pod Definition

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: nginx
  labels:
    app: nginx
spec:
  containers:
  - name: nginx
    image: nginx
    ports:
    - containerPort: 80
```

## Labels and Selectors

```bash
# Create pod with labels
kubectl run nginx --image=nginx --labels=app=v1,tier=web

# Filter by label
kubectl get pods -l app=v1
kubectl get pods -l 'app in (v1,v2)'
kubectl get pods -l app=v1,tier!=frontend

# Add/modify labels
kubectl label pod nginx app=v2 --overwrite

# Remove label
kubectl label pod nginx app-
```

## Annotations

```bash
# Add annotation
kubectl annotate pod nginx description="my description"

# View annotations
kubectl describe pod nginx | grep -i annotations

# Remove annotation
kubectl annotate pod nginx description-
```

## Deployments

```bash
# Create deployment
kubectl create deployment nginx --image=nginx --replicas=3

# Scale deployment
kubectl scale deployment nginx --replicas=5

# Update image
kubectl set image deployment/nginx nginx=nginx:1.19

# Rollout status
kubectl rollout status deployment nginx

# Rollout history
kubectl rollout history deployment nginx

# Undo rollout
kubectl rollout undo deployment nginx

# Undo to specific revision
kubectl rollout undo deployment nginx --to-revision=2

# Pause/resume rollout
kubectl rollout pause deployment nginx
kubectl rollout resume deployment nginx
```

### Deployment YAML

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:1.18.0
        ports:
        - containerPort: 80
```

## Services

```bash
# Create service exposing deployment
kubectl expose deployment nginx --port=80

# Create pod with service
kubectl run nginx --image=nginx --port=80 --expose
```

### Service Types

| Type | Description |
|------|-------------|
| ClusterIP | Internal IP, only accessible within cluster (default) |
| NodePort | Exposes on each node's IP at a static port |
| LoadBalancer | Exposes externally using cloud provider's load balancer |

### Service YAML

```yaml
apiVersion: v1
kind: Service
metadata:
  name: nginx-service
spec:
  selector:
    app: nginx
  ports:
  - port: 80
    targetPort: 80
  type: ClusterIP
```

## ConfigMaps

```bash
# Create from literal
kubectl create configmap myconfig --from-literal=key1=value1

# Create from file
kubectl create configmap myconfig --from-file=config.txt

# Create from env file
kubectl create configmap myconfig --from-env-file=config.env
```

### Using ConfigMap in Pod

```yaml
# As environment variable
env:
- name: MY_VAR
  valueFrom:
    configMapKeyRef:
      name: myconfig
      key: key1

# All values as environment variables
envFrom:
- configMapRef:
    name: myconfig

# As volume
volumes:
- name: config-volume
  configMap:
    name: myconfig
```

## Secrets

```bash
# Create secret
kubectl create secret generic mysecret --from-literal=password=mypass

# Create from file
kubectl create secret generic mysecret --from-file=username

# View secret (base64 encoded)
kubectl get secret mysecret -o yaml

# Decode secret
echo "YWRtaW4=" | base64 -d
```

### Using Secrets in Pod

```yaml
# As environment variable
env:
- name: PASSWORD
  valueFrom:
    secretKeyRef:
      name: mysecret
      key: password

# As volume
volumes:
- name: secret-volume
  secret:
    secretName: mysecret
```

## Resource Requests and Limits

```yaml
resources:
  requests:
    memory: "256Mi"
    cpu: "100m"
  limits:
    memory: "512Mi"
    cpu: "200m"
```

## Probes

### Liveness Probe
Determines if container is running. If fails, container is restarted.

```yaml
livenessProbe:
  exec:
    command:
    - ls
  initialDelaySeconds: 5
  periodSeconds: 5
```

### Readiness Probe
Determines if container can receive traffic.

```yaml
readinessProbe:
  httpGet:
    path: /
    port: 80
```

## Volumes

### emptyDir
Temporary storage shared between containers in a pod.

```yaml
volumes:
- name: shared-data
  emptyDir: {}
```

### PersistentVolume

```yaml
apiVersion: v1
kind: PersistentVolume
metadata:
  name: myvolume
spec:
  capacity:
    storage: 10Gi
  accessModes:
    - ReadWriteOnce
  hostPath:
    path: /data
```

### PersistentVolumeClaim

```yaml
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: mypvc
spec:
  accessModes:
    - ReadWriteOnce
  resources:
    requests:
      storage: 4Gi
```

## Node Scheduling

### nodeSelector

```yaml
spec:
  nodeSelector:
    accelerator: nvidia-tesla
```

### nodeName

```yaml
spec:
  nodeName: node01
```

### Tolerations

```yaml
tolerations:
- key: "tier"
  operator: "Equal"
  value: "frontend"
  effect: "NoSchedule"
```

## Init Containers

Containers that run before main containers start.

```yaml
initContainers:
- name: init
  image: busybox
  command: ['sh', '-c', 'echo init > /work-dir/index.html']
  volumeMounts:
  - name: workdir
    mountPath: /work-dir
```

## Jobs and CronJobs

### Job

```bash
kubectl create job pi --image=perl -- perl -Mbignum=bpi -wle 'print bpi(2000)'
```

### CronJob

```yaml
apiVersion: batch/v1
kind: CronJob
metadata:
  name: hello
spec:
  schedule: "*/1 * * * *"
  jobTemplate:
    spec:
      template:
        spec:
          containers:
          - name: hello
            image: busybox
            command: ["echo", "hello"]
          restartPolicy: OnFailure
```

## Helm

### Basic Commands

```bash
helm create mychart        # Create chart
helm install myrelease ./mychart  # Install chart
helm list                  # List releases
helm uninstall myrelease   # Uninstall release
helm upgrade myrelease ./mychart  # Upgrade release
helm repo add bitnami https://charts.bitnami.com/bitnami
helm show values bitnami/nginx    # Show chart values
helm install mynginx bitnami/nginx --set replicaCount=3
```

---

# Module 5: DevSecOps & Continuous Delivery

## DevSecOps Overview

### Security Testing in Deployment Pipeline
Security testing should be integrated into the deployment pipeline, not treated as an afterthought.

### OWASP (Open Web Application Security Project)
Non-profit foundation focused on software security. Provides:
- Security testing guidelines
- Top 10 security vulnerabilities list
- Best practices for secure development

## Security Testing Types (Critical for Exam!)

| Type | Full Name | Box Type | When Run | Description |
|------|-----------|----------|----------|-------------|
| **SAST** | Static Application Security Testing | **White Box** | Before runtime | Analyzes source code |
| **SCA** | Software Composition Analysis | - | Before runtime | Scans dependencies |
| **DAST** | Dynamic Application Security Testing | **Black Box** | At runtime | Tests running application |
| **IAST** | Interactive Application Security Testing | **Grey Box** | At runtime | Combines SAST+DAST |
| **RASP** | Runtime Application Self-Protection | - | At runtime | Real-time protection |

### SAST (Static Application Security Testing)
- **White Box Testing** - has access to source code
- Runs early in SDLC (before code compilation)
- Can analyze 100% of codebase
- Faster than manual code reviews
- Identifies vulnerabilities early

### DAST (Dynamic Application Security Testing)
- **Black Box Testing** - no access to source code
- Tests running application
- Simulates real-world attacks
- Finds runtime vulnerabilities

### IAST (Interactive Application Security Testing)
- **Grey Box Testing** - partial code access
- Combines SAST and DAST approaches
- Runs during application testing
- More accurate than SAST or DAST alone

### SCA (Software Composition Analysis)
- Scans third-party dependencies
- Identifies known vulnerabilities
- Checks for outdated libraries

### RASP (Runtime Application Self-Protection)
- Real-time protection during execution
- Detects and blocks attacks automatically
- Integrated into application runtime

## Continuous Delivery (CD)

### Key Definition
> **CD brings CI to the next step**: Not just an automated pipeline but also automated release process with a click of a button.

### CD Practices
- **Deployment Should Be Automated**
- **Test on a production clone**
- **Have a deployment plan** (and make sure to test it!)
- **Keep deployments small** (easier rollback)
- **Deploy to production frequently**
- **Shift Left Testing** (test earlier in pipeline)

## Security Testing Tools

### Trivy
Container vulnerability scanner.

```bash
# Scan container image
trivy image python:3.4-alpine

# Scan local image
trivy image myapp:1.0
```

### Snyk
Multi-purpose security scanner:
- **Snyk Code**: Scan source code (SAST)
- **Snyk Open Source**: Scan dependencies (SCA)
- **Snyk Container**: Scan container images
- **Snyk IaC**: Scan infrastructure code

### SonarQube
Code quality and security analysis platform.

---

# Module 6: Microservices Architecture

## Six Principles of Microservices (Critical for Exam!)

| # | Principle | Description |
|---|-----------|-------------|
| 1 | **Modeled around business domain** | Services align with business capabilities |
| 2 | **Culture of automation** | CI/CD, testing, deployment automation |
| 3 | **Hide implementation details** | Internal details not exposed |
| 4 | **Decentralize everything** | No central control point |
| 5 | **Deploy independently** | Each service deployable on its own |
| 6 | **Isolate failure** | Failures don't cascade |

## API Versioning Strategies

| Strategy | Description | Example |
|----------|-------------|---------|
| **URL Versioning** | Version in path | `/api/v1/resource` |
| **Header Versioning** | Version in header | `X-API-Version: 1` |
| **Query Parameter** | Version as parameter | `/api/resource?version=1` |
| **Content Negotiation** | Version in Accept header | `Accept: application/vnd.api.v1+json` |

## Containers vs Virtual Machines

| Feature | VMs | Containers |
|---------|-----|------------|
| OS | Full guest OS | Shares host OS kernel |
| Size | GBs | MBs |
| Boot time | Minutes | Seconds |
| Resource usage | High | Low |
| Isolation | Hardware-level | Process-level |

---

# Module 7: AWS Cloud Services

## Six Advantages of Cloud Computing (Critical for Exam!)

| # | Advantage | Description |
|---|-----------|-------------|
| 1 | **Trade CAPEX for variable expense** | Pay only for what you use |
| 2 | **Benefit from massive economies of scale** | Lower prices through aggregated usage |
| 3 | **Stop guessing capacity** | Scale on demand |
| 4 | **Increase speed and agility** | Deploy in minutes vs weeks |
| 5 | **Stop spending money on data centers** | Focus on customers, not infrastructure |
| 6 | **Go global in minutes** | Deploy worldwide easily |

## AWS Well-Architected Framework (6 Pillars)

| Pillar | Description |
|--------|-------------|
| **Operational Excellence** | Run and monitor systems |
| **Security** | Protect data and systems |
| **Reliability** | Recover from failures |
| **Performance Efficiency** | Use resources efficiently |
| **Cost Optimization** | Avoid unnecessary costs |
| **Sustainability** | Minimize environmental impact |

## AWS Global Infrastructure

| Concept | Description |
|---------|-------------|
| **Data Center** | Physical location with servers |
| **Availability Zone (AZ)** | One or more data centers (2-3+ per region) |
| **Region** | Geographic area with multiple AZs |

## Cloud Service Models

| Model | Description | User Manages | Example |
|-------|-------------|--------------|---------|
| **IaaS** | Infrastructure as a Service | OS, Runtime, App | EC2, Azure VMs |
| **PaaS** | Platform as a Service | App only | Heroku, Elastic Beanstalk |
| **SaaS** | Software as a Service | Nothing | Gmail, Salesforce |

## AWS Services Overview

| Service | Description |
|---------|-------------|
| **VPC** | Virtual Private Cloud - isolated network |
| **EC2** | Elastic Compute Cloud - virtual servers |
| **S3** | Simple Storage Service - object storage |
| **RDS** | Relational Database Service |
| **Lambda** | Serverless functions |
| **ECS** | Elastic Container Service |
| **EKS** | Elastic Kubernetes Service |
| **ALB** | Application Load Balancer |
| **ASG** | Auto Scaling Group |

### VPC
- Isolated network in AWS
- Contains subnets (public/private)
- Route tables control traffic flow
- Security Groups act as firewalls

### EC2 Instance Types

| Type | Use Case |
|------|----------|
| **General Purpose** | Balanced compute, memory, networking |
| **Compute Optimized** | High-performance computing |
| **Memory Optimized** | Large datasets in memory |
| **Storage Optimized** | High sequential read/write |
| **Accelerated Computing** | GPUs for ML/graphics |

### S3
- Object storage service
- **Can host static websites**
- Buckets contain objects
- 11 9's of durability

### Lambda
- Serverless compute service
- **Event-driven execution**
- Pay only for execution time
- Auto-scales automatically
- Multiple language support

### RDS
- Managed relational database
- Supports MySQL, PostgreSQL, Oracle, SQL Server
- Automatic backups and patching

### ECS/EKS
- **ECS**: AWS-native container orchestration
- **EKS**: Managed Kubernetes service

---

# Module 8: Infrastructure as Code (Terraform)

## What is Infrastructure as Code (IaC)?

> **IaC**: Version controlled, declarative, and automated infrastructure configuration.

### Key Definition
> **IaC enables teams to define infrastructure in code**, versioning, testing, and deploying it just like application code.

## Advantages of IaC (Critical for Exam!)

| Advantage | Description |
|-----------|-------------|
| **Speed** | Rapid infrastructure provisioning |
| **Accuracy** | Consistent, reproducible deployments |
| **Traceability** | Version controlled changes |
| **Cost efficiency** | Automated management reduces labor |
| **Reusability** | Templates and modules |

## IaC Tool Categories (Critical for Exam!)

| Category | Purpose | Tools |
|----------|---------|-------|
| **Configuration Management** | Configure existing servers | **Chef**, **Puppet**, **Ansible** |
| **Provisioning** | Create new infrastructure | **Terraform**, **CloudFormation**, **Pulumi** |

### Configuration Management vs Provisioning
- **Configuration Management**: Configures/manages software on existing servers
- **Provisioning**: Creates the infrastructure itself (servers, networks, etc.)

## Declarative vs Procedural (Critical for Exam!)

| Approach | Description | Example Tools |
|----------|-------------|---------------|
| **Declarative** | Define WHAT you want | Terraform, CloudFormation |
| **Procedural** | Define HOW to get there | Ansible (some), Scripts |

### Declarative (Functional)
- You describe the desired end state
- Tool figures out how to achieve it
- **Terraform uses this approach**

### Procedural (Imperative)
- You describe step-by-step instructions
- Order matters

## What is Terraform?

HashiCorp Terraform is an Infrastructure as Code (IaC) tool that lets you define cloud and on-prem resources in human-readable configuration files.

### Key Features
- **Declarative** configuration language (HCL)
- **Provider ecosystem** for multiple clouds
- **State management** tracks infrastructure
- **Plan before apply** shows changes

## Key Terraform Concepts

### State File
Terraform tracks real infrastructure in a state file, which serves as the source of truth.

### Providers
Enable Terraform to work with different platforms (AWS, Azure, GCP, etc.).

### Modules
Reusable, configurable Terraform configurations.

## Basic Terraform Workflow

```bash
terraform init      # Initialize working directory
terraform plan      # Preview changes
terraform apply     # Apply changes
terraform destroy   # Remove infrastructure
```

## Immutable Infrastructure
Terraform takes an immutable approach - instead of modifying existing resources, it replaces them.

---

# Module 9: Flyway (Database Migrations)

## What is Flyway?

Flyway is an open-source database migration tool that manages and tracks database changes.

## Key Features
- Versioned migrations
- Sequential application of changes
- Consistency and traceability
- Undo migrations (for rollback)
- Integration with build tools (Maven, Gradle)

## Migration File Naming

```
V0__Create_person_table.sql   # Version 0
V1__Add_email_column.sql      # Version 1
V2__Create_orders_table.sql   # Version 2
```

**Pattern**: `V<version>__<description>.sql`

## Flyway Commands

| Command | Description |
|---------|-------------|
| `migrate` | Apply pending migrations |
| `clean` | Remove all database objects |
| `info` | Show migration status |
| `validate` | Validate migrations |
| `baseline` | Create baseline for existing database |

## Configuration

```properties
flyway.url=jdbc:mysql://localhost:3306/mydb
flyway.user=root
flyway.password=secret
flyway.cleanDisabled=false
```

---

# Exam-Style Multiple Choice Questions

## Section 1: Git & Version Control

### Question 1
What is Git primarily used for?

A) Container orchestration  
B) Version control of code  
C) Database management  
D) Cloud infrastructure provisioning  

**Correct Answer: B**

*Explanation: Git is a Version Control System (VCS) that allows users to track different versions of their code base. Option A is Kubernetes, option C is unrelated, and option D describes Terraform.*

---

### Question 2
What is GitHub?

A) A Git command-line tool  
B) A local Git repository  
C) A Git hosting website  
D) A Docker registry  

**Correct Answer: C**

*Explanation: GitHub is a Git hosting website that allows you to store repositories online and collaborate on projects. It's not a command-line tool (that's git itself), not a local repository, and not a Docker registry (Docker Hub is a Docker registry).*

---

## Section 2: GitHub Actions

### Question 3
In a GitHub Actions workflow file, which keyword specifies when the workflow should run?

A) `jobs`  
B) `on`  
C) `runs-on`  
D) `steps`  

**Correct Answer: B**

*Explanation: The `on` keyword specifies the event that triggers the workflow (e.g., push, pull_request). `jobs` defines the collection of jobs, `runs-on` specifies the runner, and `steps` defines the sequence of tasks.*

---

### Question 4
What does `runs-on: ubuntu-latest` specify in a GitHub Actions workflow?

A) The Docker container to use  
B) The type of runner machine  
C) The operating system of the host  
D) The branch to run on  

**Correct Answer: B**

*Explanation: `runs-on` specifies the type of runner (virtual machine) that will execute the job. `ubuntu-latest` means a GitHub-hosted Ubuntu runner. The `container` keyword is used for Docker containers, not `runs-on`.*

---

### Question 5
Which action is used to clone the repository in a GitHub Actions workflow?

A) `actions/download-artifact@v4`  
B) `actions/checkout@v4`  
C) `actions/upload-artifact@v4`  
D) `actions/setup-node@v4`  

**Correct Answer: B**

*Explanation: `actions/checkout@v4` clones the repository's content to the runner. `download-artifact` and `upload-artifact` are for artifact management, and `setup-node` is for Node.js setup.*

---

### Question 6
What is the purpose of the `needs` keyword in a GitHub Actions job?

A) To specify required environment variables  
B) To define job dependencies  
C) To set required permissions  
D) To specify required inputs  

**Correct Answer: B**

*Explanation: The `needs` keyword creates a dependency between jobs, ensuring that one job runs after another completes. For example, `needs: [Build]` means the job waits for the Build job to complete.*

---

### Question 7
Which syntax correctly uploads an artifact named "code" in GitHub Actions?

A) `actions/upload-artifact@v4` with `name: code` and `path: .`  
B) `actions/artifact-upload@v4` with `artifact: code`  
C) `actions/checkout@v4` with `artifact: code`  
D) `actions/save-artifact@v4` with `name: code`  

**Correct Answer: A**

*Explanation: The correct action is `actions/upload-artifact@v4` with the `name` parameter for the artifact name and `path` for the source location.*

---

### Question 8
What does `${{ secrets.GITHUB_TOKEN }}` represent in a GitHub Actions workflow?

A) A user-provided secret  
B) An automatically generated token for authentication  
C) The GitHub username  
D) The repository name  

**Correct Answer: B**

*Explanation: `GITHUB_TOKEN` is an automatically generated token that GitHub provides for each workflow run. It's used for authentication when interacting with GitHub APIs, such as pushing Docker images to the GitHub Container Registry.*

---

### Question 9
In GitHub Actions, what is the purpose of a matrix build strategy?

A) To run the same job on multiple configurations  
B) To run jobs in parallel  
C) To create multiple artifacts  
D) To test different branches  

**Correct Answer: A**

*Explanation: Matrix builds allow you to run the same job across multiple configurations, such as different versions of a language or different operating systems. This avoids repeating the same YAML code.*

---

### Question 10
What trigger would you use to allow manual workflow execution?

A) `on: push`  
B) `on: manual`  
C) `on: workflow_dispatch`  
D) `on: trigger`  

**Correct Answer: C**

*Explanation: `workflow_dispatch` allows you to manually trigger a workflow from the GitHub Actions UI. There is no `manual` or `trigger` event.*

---

## Section 3: Docker

### Question 11
What is a Docker image?

A) A running instance of an application  
B) A lightweight, standalone package containing code and dependencies  
C) The Docker command-line tool  
D) A virtual machine  

**Correct Answer: B**

*Explanation: A Docker image is a lightweight, standalone package that contains all necessary code, libraries, and dependencies to run an application. A running instance of an image is called a container.*

---

### Question 12
What is a Docker container?

A) A file containing build instructions  
B) An isolated, runnable environment  
C) A storage volume  
D) A network bridge  

**Correct Answer: B**

*Explanation: A Docker container is an isolated, runnable environment that holds everything needed to run an application. It's created from an image.*

---

### Question 13
In the command `docker run -p 8080:80 nginx`, what does `8080:80` mean?

A) Container port 8080 is mapped to host port 80  
B) Host port 8080 is mapped to container port 80  
C) Both ports 8080 and 80 are exposed  
D) Port 8080 is blocked, port 80 is open  

**Correct Answer: B**

*Explanation: The format is `host:container`. So `-p 8080:80` maps host port 8080 to container port 80. Remember: host port always goes on the left, container port on the right.*

---

### Question 14
What does the `-d` flag do in `docker run -d nginx`?

A) Deletes the container after it stops  
B) Downloads the image  
C) Runs the container in detached (background) mode  
D) Enables debug mode  

**Correct Answer: C**

*Explanation: The `-d` flag runs the container in detached mode (background). The container runs without blocking the terminal. Use `--rm` to auto-delete after stopping.*

---

### Question 15
What flags enable interactive mode with a terminal in Docker?

A) `-d`  
B) `-it`  
C) `-p`  
D) `-v`  

**Correct Answer: B**

*Explanation: `-it` is short for `-i -t`, meaning interactive (keep STDIN open) and tty (allocate a terminal). This is needed for shells like `/bin/sh`.*

---

### Question 16
Which command lists all Docker containers, including stopped ones?

A) `docker ps`  
B) `docker ps -a`  
C) `docker containers`  
D) `docker list --all`  

**Correct Answer: B**

*Explanation: `docker ps` shows only running containers. Adding `-a` shows all containers, including stopped ones.*

---

### Question 17
In a Dockerfile, which instruction MUST come first?

A) `RUN`  
B) `COPY`  
C) `FROM`  
D) `CMD`  

**Correct Answer: C**

*Explanation: The `FROM` instruction is required as the first instruction in a Dockerfile. It specifies the base image for the build.*

---

### Question 18
What is the difference between `COPY` and `ADD` in a Dockerfile?

A) `COPY` can extract tar files, `ADD` cannot  
B) `ADD` can extract tar files, `COPY` cannot  
C) They are identical  
D) `ADD` is deprecated  

**Correct Answer: B**

*Explanation: `ADD` can extract tar files and download from URLs. `COPY` only copies files. Best practice is to use `COPY` unless you specifically need `ADD`'s extra features.*

---

### Question 19
What is the difference between `CMD` and `ENTRYPOINT` in a Dockerfile?

A) `CMD` cannot be overridden, `ENTRYPOINT` can  
B) `CMD` can be overridden at runtime, `ENTRYPOINT` always runs  
C) They are identical  
D) `CMD` is for build, `ENTRYPOINT` is for runtime  

**Correct Answer: B**

*Explanation: `CMD` provides default arguments that can be overridden when running the container. `ENTRYPOINT` configures a command that will always run, regardless of user-specified commands.*

---

### Question 20
What does `EXPOSE 5000` do in a Dockerfile?

A) Opens port 5000 on the host  
B) Documents that the container listens on port 5000  
C) Maps container port 5000 to host port 5000  
D) Blocks port 5000  

**Correct Answer: B**

*Explanation: `EXPOSE` is documentation only. It indicates which ports the application uses but does NOT actually publish the port. You still need `-p` when running the container.*

---

### Question 21
What is the purpose of multi-stage builds in Docker?

A) To run multiple containers  
B) To create smaller production images by separating build and runtime  
C) To build for multiple architectures  
D) To run tests in parallel  

**Correct Answer: B**

*Explanation: Multi-stage builds allow you to use multiple FROM statements, copying only the necessary artifacts from build stages to the final image. This results in much smaller production images.*

---

### Question 22
In the command `docker run -v /host/path:/container/path nginx`, what type of mount is this?

A) Named volume  
B) Bind mount  
C) tmpfs mount  
D) Network mount  

**Correct Answer: B**

*Explanation: When the first argument starts with `/`, it's a bind mount that maps a host directory directly to the container. A named volume would just use a name like `myvolume:/container/path`.*

---

### Question 23
What command creates a Docker network?

A) `docker network add mynetwork`  
B) `docker network create mynetwork`  
C) `docker create network mynetwork`  
D) `docker net create mynetwork`  

**Correct Answer: B**

*Explanation: The correct command is `docker network create <name>`. This creates a network that containers can join to communicate with each other using container names as DNS.*

---

### Question 24
In Docker Compose, what section defines the containers?

A) `containers`  
B) `images`  
C) `services`  
D) `applications`  

**Correct Answer: C**

*Explanation: Docker Compose uses the `services` section to define containers. Each service has its own configuration (image, ports, environment, etc.).*

---

### Question 25
What command starts Docker Compose services in detached mode?

A) `docker compose start -d`  
B) `docker compose run -d`  
C) `docker compose up -d`  
D) `docker compose deploy -d`  

**Correct Answer: C**

*Explanation: `docker compose up -d` creates and starts all services defined in the docker-compose.yml file in detached (background) mode.*

---

## Section 4: Kubernetes

### Question 26
What is a Pod in Kubernetes?

A) A cluster of nodes  
B) The smallest deployable unit containing one or more containers  
C) A storage volume  
D) A network service  

**Correct Answer: B**

*Explanation: A Pod is the smallest deployable unit in Kubernetes. It can contain one or more containers that share storage and network.*

---

### Question 27
Which command generates YAML for a pod without creating it?

A) `kubectl run nginx --image=nginx --dry-run -o yaml`  
B) `kubectl run nginx --image=nginx --dry-run=client -o yaml`  
C) `kubectl create nginx --image=nginx --preview`  
D) `kubectl generate pod nginx --image=nginx`  

**Correct Answer: B**

*Explanation: The `--dry-run=client` flag prevents the resource from being created, and `-o yaml` outputs the resource definition in YAML format.*

---

### Question 28
What is the purpose of a Kubernetes Namespace?

A) To store secrets  
B) To provide virtual cluster isolation  
C) To manage volumes  
D) To configure networking  

**Correct Answer: B**

*Explanation: Namespaces provide virtual cluster isolation within a Kubernetes cluster. They allow you to divide cluster resources between multiple users or projects.*

---

### Question 29
Which command shows pods across all namespaces?

A) `kubectl get pods --all`  
B) `kubectl get pods -A`  
C) `kubectl get pods --namespaces`  
D) `kubectl get pods --global`  

**Correct Answer: B**

*Explanation: The `-A` flag (or `--all-namespaces`) shows resources across all namespaces.*

---

### Question 30
What is a Deployment in Kubernetes?

A) The process of adding nodes to a cluster  
B) A resource that manages ReplicaSets and provides rolling updates  
C) A type of storage  
D) A network configuration  

**Correct Answer: B**

*Explanation: A Deployment is a higher-level resource that manages ReplicaSets and provides declarative updates, rolling updates, and rollback capabilities for pods.*

---

### Question 31
Which command rolls back a deployment to the previous version?

A) `kubectl rollback deployment nginx`  
B) `kubectl undo deployment nginx`  
C) `kubectl rollout undo deployment nginx`  
D) `kubectl deployment nginx --rollback`  

**Correct Answer: C**

*Explanation: The correct command is `kubectl rollout undo deployment <name>`. You can also specify `--to-revision=<number>` to rollback to a specific revision.*

---

### Question 32
What is the difference between ClusterIP and NodePort service types?

A) ClusterIP is external, NodePort is internal  
B) ClusterIP is internal only, NodePort exposes on each node's IP  
C) They are identical  
D) ClusterIP is for pods, NodePort is for deployments  

**Correct Answer: B**

*Explanation: ClusterIP (default) is only accessible within the cluster. NodePort exposes the service on a static port on each node's IP, making it accessible externally.*

---

### Question 33
What is the purpose of a ConfigMap in Kubernetes?

A) To store sensitive data  
B) To store non-confidential configuration data  
C) To configure networking  
D) To manage storage  

**Correct Answer: B**

*Explanation: ConfigMaps store non-confidential configuration data as key-value pairs. Secrets are used for sensitive data. ConfigMaps can be consumed as environment variables or mounted as volumes.*

---

### Question 34
How do you create a ConfigMap from a literal value?

A) `kubectl create configmap myconfig --value=key1=value1`  
B) `kubectl create configmap myconfig --from-literal=key1=value1`  
C) `kubectl configmap create myconfig key1=value1`  
D) `kubectl apply configmap myconfig --data=key1=value1`  

**Correct Answer: B**

*Explanation: The correct syntax is `kubectl create configmap <name> --from-literal=<key>=<value>`. You can specify multiple `--from-literal` flags.*

---

### Question 35
What is the difference between `env` and `envFrom` when using ConfigMaps in a pod spec?

A) `env` loads all values, `envFrom` loads specific keys  
B) `env` loads specific keys, `envFrom` loads all values  
C) They are identical  
D) `env` is for ConfigMaps, `envFrom` is for Secrets  

**Correct Answer: B**

*Explanation: `env` with `configMapKeyRef` loads specific keys as environment variables. `envFrom` with `configMapRef` loads all key-value pairs from the ConfigMap as environment variables.*

---

### Question 36
What is the purpose of a liveness probe?

A) To determine if a container can receive traffic  
B) To determine if a container is running; restart if it fails  
C) To check if the application has started  
D) To monitor resource usage  

**Correct Answer: B**

*Explanation: A liveness probe determines if the container is running. If the probe fails, Kubernetes restarts the container. A readiness probe determines if the container can receive traffic.*

---

### Question 37
What type of volume is `emptyDir` in Kubernetes?

A) Permanent storage that survives pod restarts  
B) Temporary storage that exists for the pod's lifetime  
C) Network-attached storage  
D) Host filesystem storage  

**Correct Answer: B**

*Explanation: An `emptyDir` volume is created when a pod is assigned to a node and exists for the pod's lifetime. When the pod is removed, the data is deleted. It's useful for sharing data between containers in a pod.*

---

### Question 38
What must match for a PersistentVolumeClaim to bind to a PersistentVolume?

A) Only the name  
B) StorageClassName and accessModes  
C) Only the capacity  
D) The namespace  

**Correct Answer: B**

*Explanation: For a PVC to bind to a PV, the storageClassName and accessModes must match, and the PV must have enough capacity to satisfy the PVC's request.*

---

### Question 39
What is the purpose of resource requests in Kubernetes?

A) To set maximum resource usage  
B) To specify the minimum resources a container needs for scheduling  
C) To request external resources  
D) To define storage requirements  

**Correct Answer: B**

*Explanation: Resource requests specify the minimum resources a container needs. The scheduler uses requests to find a node with sufficient capacity. Limits specify the maximum resources a container can use.*

---

### Question 40
What does a ResourceQuota do?

A) Limits resources for a single pod  
B) Limits total resources that can be used in a namespace  
C) Limits resources per container  
D) Limits resources per node  

**Correct Answer: B**

*Explanation: A ResourceQuota limits the total amount of resources (CPU, memory, number of pods, etc.) that can be consumed in a namespace. LimitRange limits resources per pod or container.*

---

### Question 41
What is the purpose of an init container?

A) To initialize the cluster  
B) To run before main containers start, often for setup tasks  
C) To restart failed containers  
D) To initialize volumes  

**Correct Answer: B**

*Explanation: Init containers run before the main application containers start. They're useful for setup tasks like downloading configuration or waiting for dependencies to be available.*

---

### Question 42
What does `nodeSelector` do in a pod spec?

A) Selects which containers run on the node  
B) Schedules the pod to nodes with matching labels  
C) Selects which services to use  
D) Selects the network interface  

**Correct Answer: B**

*Explanation: `nodeSelector` is the simplest form of node selection. It schedules pods only to nodes that have all the specified labels.*

---

### Question 43
What is the purpose of a taint on a node?

A) To attract specific pods  
B) To repel pods that don't tolerate the taint  
C) To mark the node as unhealthy  
D) To limit node resources  

**Correct Answer: B**

*Explanation: Taints allow nodes to repel pods. A pod must have a matching toleration to be scheduled on a tainted node. This is useful for dedicated nodes.*

---

### Question 44
What is a NetworkPolicy used for?

A) To configure load balancing  
B) To control network traffic to/from pods  
C) To set up DNS  
D) To manage ingress controllers  

**Correct Answer: B**

*Explanation: NetworkPolicy controls network traffic flow at the pod level. It specifies which pods can communicate with each other and with external endpoints.*

---

### Question 45
Which Helm command installs a chart?

A) `helm deploy mychart`  
B) `helm install myrelease ./mychart`  
C) `helm run mychart`  
D) `helm apply mychart`  

**Correct Answer: B**

*Explanation: The correct command is `helm install <release-name> <chart-path>`. The release name identifies the deployment, and the chart path points to the chart to install.*

---

## Section 5: Security (SAST)

### Question 46
What does SAST stand for?

A) Static Application Security Testing  
B) Standard Application Security Tools  
C) System Application Security Testing  
D) Software Application Security Tools  

**Correct Answer: A**

*Explanation: SAST stands for Static Application Security Testing. It analyzes source code to find security vulnerabilities without running the application.*

---

### Question 47
When does SAST occur in the software development lifecycle?

A) After deployment  
B) During runtime  
C) Very early, before code is compiled  
D) During user acceptance testing  

**Correct Answer: C**

*Explanation: SAST runs early in the SDLC, analyzing source code before compilation. This allows developers to fix vulnerabilities early, reducing cost and risk.*

---

### Question 48
What does Trivy scan?

A) Only source code  
B) Container images and filesystems  
C) Only databases  
D) Only network configurations  

**Correct Answer: B**

*Explanation: Trivy scans container images, filesystems, git repositories, and other targets for vulnerabilities. It's commonly used to scan Docker images before deployment.*

---

### Question 49
Which Snyk product scans container images?

A) Snyk Code  
B) Snyk Open Source  
C) Snyk Container  
D) Snyk IaC  

**Correct Answer: C**

*Explanation: Snyk Container is used to scan container images for vulnerabilities. Snyk Code scans source code, Snyk Open Source scans dependencies, and Snyk IaC scans infrastructure code.*

---

## Section 6: AWS

### Question 50
What is an AWS VPC?

A) Virtual Private Computer  
B) Virtual Private Cloud  
C) Virtual Public Cloud  
D) Virtual Protected Container  

**Correct Answer: B**

*Explanation: VPC stands for Virtual Private Cloud. It's an isolated network that you define in AWS where you can launch resources.*

---

### Question 51
What AWS service provides virtual servers?

A) S3  
B) RDS  
C) EC2  
D) Lambda  

**Correct Answer: C**

*Explanation: EC2 (Elastic Compute Cloud) provides virtual servers (instances) in AWS. S3 is object storage, RDS is managed databases, and Lambda is serverless functions.*

---

### Question 52
Which AWS service can host a static website?

A) EC2 only  
B) S3  
C) RDS  
D) ECS  

**Correct Answer: B**

*Explanation: S3 can host static websites by enabling static website hosting on a bucket. It serves HTML, CSS, JavaScript, and other static files directly.*

---

## Section 7: Terraform

### Question 53
What type of tool is Terraform?

A) Configuration management  
B) Infrastructure as Code  
C) Continuous Integration  
D) Container orchestration  

**Correct Answer: B**

*Explanation: Terraform is an Infrastructure as Code (IaC) tool that lets you define infrastructure in declarative configuration files that can be versioned and shared.*

---

### Question 54
What is the Terraform state file used for?

A) Storing configuration templates  
B) Tracking real infrastructure as a source of truth  
C) Logging changes  
D) Storing secrets  

**Correct Answer: B**

*Explanation: Terraform uses the state file to track your real infrastructure. It compares the state with your configuration to determine what changes need to be made.*

---

### Question 55
What does `terraform plan` do?

A) Applies changes to infrastructure  
B) Initializes the working directory  
C) Shows a preview of changes that will be made  
D) Destroys all infrastructure  

**Correct Answer: C**

*Explanation: `terraform plan` creates an execution plan, showing what actions Terraform will take to reach the desired state without actually making changes.*

---

### Question 56
What is the correct order of basic Terraform commands for a new project?

A) plan → init → apply  
B) init → apply → plan  
C) init → plan → apply  
D) apply → init → plan  

**Correct Answer: C**

*Explanation: First, `init` initializes the working directory and downloads providers. Then `plan` previews changes. Finally, `apply` makes the changes.*

---

## Section 8: Flyway

### Question 57
What is Flyway used for?

A) Container orchestration  
B) Database migration management  
C) CI/CD pipelines  
D) Infrastructure provisioning  

**Correct Answer: B**

*Explanation: Flyway is a database migration tool that manages and tracks incremental changes to database schemas. It ensures consistency and traceability of database changes.*

---

### Question 58
What is the correct naming convention for a Flyway migration file?

A) `Create_person_table_V0.sql`  
B) `V0__Create_person_table.sql`  
C) `0_Create_person_table.sql`  
D) `migration_0_Create_person.sql`  

**Correct Answer: B**

*Explanation: Flyway migration files must follow the pattern `V<version>__<description>.sql` (note the double underscore). The version determines the order of execution.*

---

### Question 59
What does the Flyway `clean` command do?

A) Removes Flyway configuration  
B) Removes all database objects  
C) Cleans up old migrations  
D) Removes the Flyway history table  

**Correct Answer: B**

*Explanation: The `clean` command removes all objects from the configured schema(s), including tables, views, procedures, etc. Use with caution, especially in production!*

---

### Question 60
What is the purpose of the Flyway `baseline` command?

A) To create the first migration  
B) To introduce Flyway to an existing database with data  
C) To reset the database  
D) To validate migrations  

**Correct Answer: B**

*Explanation: The `baseline` command marks an existing database as having a baseline. This allows Flyway to manage migrations starting from that point, ignoring prior history.*

---

## Section 9: SDLC, DevOps & Security (From Lectures)

### Question L1
What type of testing is SAST (Static Application Security Testing)?

A) Black Box Testing  
B) White Box Testing  
C) Grey Box Testing  
D) Runtime Testing  

**Correct Answer: B**

*Explanation: SAST is White Box Testing because it has full access to the source code and analyzes it before the application runs.*

---

### Question L2
What type of testing is DAST (Dynamic Application Security Testing)?

A) White Box Testing  
B) Grey Box Testing  
C) Black Box Testing  
D) Static Testing  

**Correct Answer: C**

*Explanation: DAST is Black Box Testing because it tests the running application without access to source code, simulating real-world attacks.*

---

### Question L3
What type of testing is IAST (Interactive Application Security Testing)?

A) White Box Testing  
B) Black Box Testing  
C) Grey Box Testing  
D) No Box Testing  

**Correct Answer: C**

*Explanation: IAST is Grey Box Testing because it combines elements of both SAST and DAST, having partial access to code while testing the running application.*

---

### Question L4
Which security testing tool scans third-party dependencies for known vulnerabilities?

A) SAST  
B) DAST  
C) SCA  
D) RASP  

**Correct Answer: C**

*Explanation: SCA (Software Composition Analysis) specifically scans third-party dependencies and libraries for known vulnerabilities.*

---

### Question L5
What does a Deployment Pipeline do?

A) Only compiles code  
B) Organizes ALL steps required to go from idea to releasable software  
C) Only runs unit tests  
D) Only deploys to production  

**Correct Answer: B**

*Explanation: A Deployment Pipeline organizes ALL steps required to go from idea to releasable software, automating the development process to produce software repeatably and reliably.*

---

### Question L6
Which Git branching workflow encourages continuous integration into the main branch?

A) Git Flow  
B) Feature Branch Workflow  
C) Trunk-Based Development  
D) Basic Git Workflow  

**Correct Answer: C**

*Explanation: Trunk-Based Development encourages developers to integrate changes frequently into the main (trunk) branch, supporting continuous integration.*

---

### Question L7
Which is NOT one of the 6 Principles of Microservices?

A) Modeled around business domain  
B) Culture of automation  
C) Centralize all logic  
D) Deploy independently  

**Correct Answer: C**

*Explanation: One of the 6 Principles is "Decentralize everything" - the opposite of centralizing logic. The other options are all valid principles.*

---

### Question L8
What is the correct CI/CD tool for GitHub repositories?

A) Jenkins  
B) GitLab CI  
C) GitHub Actions  
D) Azure DevOps Pipelines  

**Correct Answer: C**

*Explanation: While Jenkins works with any repository, GitHub Actions is the native CI/CD solution for GitHub repositories.*

---

### Question L9
Which CI/CD tool is native to BitBucket?

A) GitHub Actions  
B) BitBucket Pipelines  
C) GitLab CI  
D) Circle CI  

**Correct Answer: B**

*Explanation: BitBucket Pipelines is the native CI/CD tool for BitBucket repositories.*

---

### Question L10
How many pillars are in the AWS Well-Architected Framework?

A) 4  
B) 5  
C) 6  
D) 7  

**Correct Answer: C**

*Explanation: The AWS Well-Architected Framework has 6 pillars: Operational Excellence, Security, Reliability, Performance Efficiency, Cost Optimization, and Sustainability.*

---

### Question L11
Which is NOT one of the 6 advantages of cloud computing?

A) Trade CAPEX for variable expense  
B) Go global in minutes  
C) Guaranteed 100% uptime  
D) Stop guessing capacity  

**Correct Answer: C**

*Explanation: The cloud does not guarantee 100% uptime. The 6 advantages include trading CAPEX for variable expense, economies of scale, stop guessing capacity, speed and agility, stop spending on data centers, and go global in minutes.*

---

### Question L12
What is an AWS Availability Zone?

A) A single server  
B) One or more data centers with redundant power and networking  
C) A continent  
D) A country  

**Correct Answer: B**

*Explanation: An Availability Zone consists of one or more data centers with redundant power, networking, and connectivity in an AWS Region.*

---

### Question L13
Which tools are classified as Configuration Management (not Provisioning)?

A) Terraform, CloudFormation, Pulumi  
B) Chef, Puppet, Ansible  
C) Kubernetes, Docker, Helm  
D) Git, GitHub, GitLab  

**Correct Answer: B**

*Explanation: Chef, Puppet, and Ansible are Configuration Management tools that configure existing servers. Terraform, CloudFormation, and Pulumi are Provisioning tools that create infrastructure.*

---

### Question L14
Which tools are classified as Provisioning (not Configuration Management)?

A) Chef, Puppet, Ansible  
B) Git, GitHub, GitLab  
C) Terraform, CloudFormation, Pulumi  
D) Docker, Kubernetes, Helm  

**Correct Answer: C**

*Explanation: Terraform, CloudFormation, and Pulumi are Provisioning tools that create infrastructure. Chef, Puppet, and Ansible are Configuration Management tools.*

---

### Question L15
What approach does Terraform use?

A) Procedural  
B) Declarative  
C) Imperative  
D) Object-Oriented  

**Correct Answer: B**

*Explanation: Terraform uses a declarative approach where you define WHAT you want (the desired end state), and Terraform figures out HOW to achieve it.*

---

### Question L16
According to CI practices, commits should build on:

A) Developer's local machine only  
B) An integration machine  
C) Production server directly  
D) No need to build  

**Correct Answer: B**

*Explanation: One of the CI practices states that "Every commit should build on an integration machine" to ensure consistent builds across the team.*

---

### Question L17
What does RASP stand for in security testing?

A) Runtime Analysis Security Protocol  
B) Runtime Application Self-Protection  
C) Rapid Application Security Process  
D) Real-time Attack Security Prevention  

**Correct Answer: B**

*Explanation: RASP stands for Runtime Application Self-Protection - a technology that runs within the application to detect and block attacks in real-time.*

---

### Question L18
According to DevOps principles, what is described as organizational anti-pattern?

A) Using Git for version control  
B) Having a dedicated DevOps team  
C) Automating deployments  
D) Using containers  

**Correct Answer: B**

*Explanation: The lecture states "Having a dedicated DevOps team is organizational anti-pattern" - DevOps should be a shared responsibility, not siloed.*

---

### Question L19
In the Cloud Service Models, what does the user manage in PaaS?

A) Hardware, OS, Runtime, and Application  
B) Only the Application  
C) Nothing  
D) OS, Runtime, and Application  

**Correct Answer: B**

*Explanation: In PaaS (Platform as a Service), users only manage the Application. The provider manages hardware, OS, and runtime.*

---

### Question L20
What is the term for the journey from idea to revenue in DevOps?

A) Deployment Pipeline  
B) Concept to Cash  
C) Time to Market  
D) Feature Delivery  

**Correct Answer: B**

*Explanation: "Concept to Cash" is the term used in DevOps to describe the journey from idea to revenue - shortening this cycle is a key goal.*

---

## Bonus Advanced Questions

### Question 61
In Docker, what happens when you run `docker run -it alpine` and then type `exit`?

A) The container keeps running  
B) The container stops because the primary process exited  
C) The container restarts automatically  
D) Only the shell exits, container continues  

**Correct Answer: B**

*Explanation: When you exit an interactive shell, the primary process (`/bin/sh`) stops. Since containers run as long as their primary process runs, the container stops.*

---

### Question 62
What is the difference between `kubectl create` and `kubectl apply`?

A) They are identical  
B) `create` is for new resources, `apply` can create and update  
C) `apply` only updates, `create` only creates  
D) `create` uses YAML, `apply` uses JSON  

**Correct Answer: B**

*Explanation: `kubectl create` creates a new resource and fails if it exists. `kubectl apply` creates or updates resources based on the configuration file, making it better for declarative management.*

---

### Question 63
In GitHub Actions, what does `${{ github.sha }}` represent?

A) The repository name  
B) The commit SHA that triggered the workflow  
C) The branch name  
D) The workflow ID  

**Correct Answer: B**

*Explanation: `github.sha` is a context variable containing the commit SHA that triggered the workflow run. It's commonly used for tagging Docker images.*

---

### Question 64
When using multi-stage Docker builds, what does `COPY --from=builder` do?

A) Copies files from a volume named builder  
B) Copies files from a previous build stage named builder  
C) Copies files from an external builder service  
D) Copies files from the host system  

**Correct Answer: B**

*Explanation: `COPY --from=<stage>` copies files from a previous build stage. This allows you to build in one stage and copy only the necessary artifacts to the final, smaller image.*

---

### Question 65
What is a canary deployment in Kubernetes?

A) A deployment that only runs at night  
B) A deployment strategy that routes a small percentage of traffic to a new version  
C) A deployment that tests hardware  
D) A deployment that rolls back automatically  

**Correct Answer: B**

*Explanation: A canary deployment releases a new version to a small subset of users/traffic first. If successful, it's gradually rolled out to the rest. This minimizes risk.*

---

