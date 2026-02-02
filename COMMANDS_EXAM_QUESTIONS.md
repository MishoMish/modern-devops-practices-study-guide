# 🛠️ COMMANDS EXAM QUESTIONS

**Format**: Multiple-Choice Questions covering ALL commands mentioned in the learning materials  
**Exam Context**: ~50 minutes, approximately 1 minute per question  
**Difficulty**: Easy to Medium (Practical focus)  

---

## Table of Contents
1. [Git Commands](#git-commands)
2. [GitHub Actions](#github-actions)
3. [Docker Commands](#docker-commands)
4. [Kubernetes (kubectl) Commands](#kubernetes-kubectl-commands)
5. [Docker Compose Commands](#docker-compose-commands)
6. [Terraform Commands](#terraform-commands)
7. [Helm Commands](#helm-commands)
8. [Security & Scanning Commands](#security--scanning-commands)
9. [Flyway Commands](#flyway-commands)
10. [Mixed Command Questions](#mixed-command-questions)

---

## Git Commands

### Question 1
What does the `git clone` command do?

A) Creates a new local branch  
B) Copies a repository from remote to local  
C) Uploads code to a remote repository  
D) Commits changes to the repository  

**Correct Answer: B**

---

### Question 2
Which command stages changes for committing?

A) `git push`  
B) `git commit`  
C) `git add`  
D) `git merge`  

**Correct Answer: C**

---

### Question 3
What is the purpose of `git commit`?

A) Sends changes to remote repository  
B) Creates a snapshot of staged changes  
C) Merges branches  
D) Deletes a branch  

**Correct Answer: B**

---

### Question 4
What does `git push` do?

A) Downloads changes from remote  
B) Sends local commits to remote repository  
C) Merges current branch with another  
D) Creates a new branch  

**Correct Answer: B**

---

### Question 5
Which command fetches and merges changes from a remote branch?

A) `git fetch`  
B) `git merge`  
C) `git pull`  
D) `git rebase`  

**Correct Answer: C**

---

### Question 6
What does `git branch myfeature` do?

A) Deletes the myfeature branch  
B) Creates a new branch named myfeature  
C) Switches to the myfeature branch  
D) Merges myfeature into main  

**Correct Answer: B**

---

### Question 7
Which command switches to an existing branch?

A) `git branch newbranch`  
B) `git checkout mybranch`  
C) `git switch-to mybranch`  
D) `git select mybranch`  

**Correct Answer: B**

---

### Question 8
What does `git merge develop` do?

A) Creates a new branch called develop  
B) Pushes to a remote branch  
C) Combines the develop branch into the current branch  
D) Deletes the develop branch  

**Correct Answer: C**

---

### Question 9
Which command shows the history of commits?

A) `git history`  
B) `git log`  
C) `git show`  
D) `git status`  

**Correct Answer: B**

---

### Question 10
What does `git status` display?

A) The current branch  
B) The remote repository URL  
C) Modified files and staged changes  
D) The commit history  

**Correct Answer: C**

---

### Question 11
Which command initializes a new Git repository?

A) `git create`  
B) `git new`  
C) `git init`  
D) `git setup`  

**Correct Answer: C**

---

### Question 12
What is the correct syntax to set your Git username?

A) `git config username "John Doe"`  
B) `git config user.name "John Doe"`  
C) `git set-user "John Doe"`  
D) `git user.name "John Doe"`  

**Correct Answer: B**

---

## Docker Commands

### Question 13
What does `docker run hello-world` do?

A) Creates a Docker image  
B) Lists all containers  
C) Creates and runs a container from an image  
D) Removes a container  

**Correct Answer: C**

---

### Question 14
Which command maps port 8080 on the host to port 80 in the container?

A) `docker run -p 80:8080 nginx`  
B) `docker run -p 8080:80 nginx`  
C) `docker run --port 8080-80 nginx`  
D) `docker run -map 8080:80 nginx`  

**Correct Answer: B**

*Note: Remember host:container format*

---

### Question 15
What does the `-d` flag do in `docker run -d nginx`?

A) Enables debug mode  
B) Downloads the image  
C) Runs the container in detached (background) mode  
D) Deletes the container  

**Correct Answer: C**

---

### Question 16
Which command is used to execute a shell inside a running container?

A) `docker run -it alpine /bin/sh`  
B) `docker enter alpine /bin/sh`  
C) `docker exec -it <container> /bin/sh`  
D) `docker shell <container>`  

**Correct Answer: C**

---

### Question 17
What does `docker ps` display?

A) All images  
B) Running containers only  
C) All containers including stopped ones  
D) Persistent volumes  

**Correct Answer: B**

---

### Question 18
How do you list ALL containers (including stopped ones)?

A) `docker ps --all`  
B) `docker ps -a`  
C) Both A and B are correct  
D) `docker list containers`  

**Correct Answer: C**

---

### Question 19
Which command stops a running container?

A) `docker delete <container>`  
B) `docker stop <container>`  
C) `docker pause <container>`  
D) `docker kill <container>`  

**Correct Answer: B**

---

### Question 20
What does `docker rm <container>` do?

A) Stops a container  
B) Renames a container  
C) Removes a container  
D) Restarts a container  

**Correct Answer: C**

---

### Question 21
Which command views the logs of a container?

A) `docker log <container>`  
B) `docker logs <container>`  
C) `docker show-logs <container>`  
D) `docker tail <container>`  

**Correct Answer: B**

---

### Question 22
How do you follow container logs in real-time?

A) `docker logs <container> --real-time`  
B) `docker logs <container> -f`  
C) `docker logs <container> --tail`  
D) `docker stream-logs <container>`  

**Correct Answer: B**

---

### Question 23
What does `docker pull alpine` do?

A) Creates an Alpine Linux container  
B) Downloads the Alpine image  
C) Removes the Alpine image  
D) Lists all Alpine containers  

**Correct Answer: B**

---

### Question 24
Which command lists all Docker images?

A) `docker list images`  
B) `docker show images`  
C) `docker images`  
D) `docker image list`  

**Correct Answer: C**

*Note: `docker image ls` is also correct*

---

### Question 25
What does `docker build -t myapp .` do?

A) Downloads an image from Docker Hub  
B) Builds a Docker image from a Dockerfile in the current directory  
C) Creates and runs a container  
D) Lists all images with tag  

**Correct Answer: B**

---

### Question 26
Which command gets detailed information about a container?

A) `docker ps <container>`  
B) `docker describe <container>`  
C) `docker inspect <container>`  
D) `docker show <container>`  

**Correct Answer: C**

---

### Question 27
What does `docker image rm <image>` do?

A) Stops an image  
B) Removes an image  
C) Restarts an image  
D) Lists images  

**Correct Answer: B**

---

### Question 28
Which command removes all unused images?

A) `docker image cleanup`  
B) `docker image prune`  
C) `docker cleanup images`  
D) `docker remove unused`  

**Correct Answer: B**

---

### Question 29
What does `docker run -v /host:/container nginx` create?

A) A named volume  
B) A bind mount  
C) A network mount  
D) A temporary volume  

**Correct Answer: B**

---

### Question 30
How do you make a bind mount read-only?

A) `docker run -v /host:/container:ro nginx`  
B) `docker run -v /host:/container:readonly nginx`  
C) `docker run --readonly /host:/container nginx`  
D) `docker run -v /host:/container --ro nginx`  

**Correct Answer: A**

---

### Question 31
Which command creates a named volume?

A) `docker volume new data`  
B) `docker volume create data`  
C) `docker create-volume data`  
D) `docker storage create data`  

**Correct Answer: B**

---

### Question 32
What does `docker volume ls` do?

A) Lists containers  
B) Lists images  
C) Lists all volumes  
D) Lists networks  

**Correct Answer: C**

---

### Question 33
Which command creates a Docker network?

A) `docker network add mynet`  
B) `docker create network mynet`  
C) `docker network create mynet`  
D) `docker net create mynet`  

**Correct Answer: C**

---

### Question 34
How do you connect a container to a specific network?

A) `docker run --connect mynet alpine`  
B) `docker run --network mynet alpine`  
C) `docker run --net mynet alpine`  
D) Both B and C  

**Correct Answer: D**

---

### Question 35
What does `docker container prune` do?

A) Removes unused images  
B) Removes all containers  
C) Removes stopped containers  
D) Removes container logs  

**Correct Answer: C**

---

### Question 36
Which command removes all unused Docker objects?

A) `docker cleanup`  
B) `docker prune`  
C) `docker system prune`  
D) `docker purge`  

**Correct Answer: C**

---

## Docker Compose Commands

### Question 37
What does `docker compose up -d` do?

A) Uploads services to Docker Hub  
B) Stops all services  
C) Starts services in background mode  
D) Updates Docker Compose  

**Correct Answer: C**

---

### Question 38
Which command stops and removes Docker Compose services?

A) `docker compose stop`  
B) `docker compose down`  
C) `docker compose delete`  
D) `docker compose remove`  

**Correct Answer: B**

---

### Question 39
What does `docker compose ps` display?

A) All images  
B) All containers on the system  
C) Running Docker Compose services  
D) Docker Compose configuration  

**Correct Answer: C**

---

### Question 40
Which command shows logs from Docker Compose services?

A) `docker compose show-logs`  
B) `docker compose log`  
C) `docker compose logs`  
D) `docker compose tail`  

**Correct Answer: C**

---

## Kubernetes (kubectl) Commands

### Question 41
Which command lists all pods in the current namespace?

A) `kubectl show pods`  
B) `kubectl list pods`  
C) `kubectl get pods`  
D) `kubectl describe pods`  

**Correct Answer: C**

---

### Question 42
How do you list pods across ALL namespaces?

A) `kubectl get pods --all`  
B) `kubectl get pods -A`  
C) `kubectl get pods --global`  
D) `kubectl get pods --everywhere`  

**Correct Answer: B**

---

### Question 43
Which command gets detailed information about a pod?

A) `kubectl show pod nginx`  
B) `kubectl info pod nginx`  
C) `kubectl describe pod nginx`  
D) `kubectl get pod nginx`  

**Correct Answer: C**

---

### Question 44
What does `kubectl apply -f pod.yaml` do?

A) Lists pod YAML  
B) Creates or updates resources from a YAML file  
C) Deletes a pod  
D) Shows pod status  

**Correct Answer: B**

---

### Question 45
Which command deletes a pod?

A) `kubectl stop pod nginx`  
B) `kubectl remove pod nginx`  
C) `kubectl delete pod nginx`  
D) `kubectl kill pod nginx`  

**Correct Answer: C**

---

### Question 46
What does `kubectl exec -it nginx -- /bin/sh` do?

A) Creates a new pod  
B) Executes a shell command in the pod  
C) Shows pod logs  
D) Deletes the pod  

**Correct Answer: B**

---

### Question 47
Which command shows pod logs?

A) `kubectl show logs nginx`  
B) `kubectl log nginx`  
C) `kubectl logs nginx`  
D) `kubectl tail nginx`  

**Correct Answer: C**

---

### Question 48
How do you follow logs in real-time?

A) `kubectl logs nginx --watch`  
B) `kubectl logs nginx -f`  
C) `kubectl logs nginx --follow`  
D) Both B and C  

**Correct Answer: D**

---

### Question 49
What does `kubectl logs nginx -p` do?

A) Shows logs from the previous instance  
B) Shows pod logs  
C) Shows logs in JSON format  
D) Shows logs from all pods  

**Correct Answer: A**

---

### Question 50
Which command generates YAML without creating the resource?

A) `kubectl run nginx --image=nginx --preview`  
B) `kubectl run nginx --image=nginx --dry-run=client -o yaml`  
C) `kubectl create nginx --dry-run`  
D) `kubectl generate nginx`  

**Correct Answer: B**

---

### Question 51
How do you create a pod with labels?

A) `kubectl run nginx --image=nginx --tag=app=v1`  
B) `kubectl run nginx --image=nginx --label=app=v1`  
C) `kubectl run nginx --image=nginx --labels=app=v1`  
D) `kubectl run nginx --image=nginx -l app=v1`  

**Correct Answer: C**

---

### Question 52
Which command gets pods filtered by label?

A) `kubectl get pods --label app=v1`  
B) `kubectl get pods -l app=v1`  
C) Both A and B  
D) `kubectl get pods app=v1`  

**Correct Answer: C**

---

### Question 53
How do you add a label to a pod?

A) `kubectl set label pod nginx app=v2`  
B) `kubectl add label pod nginx app=v2`  
C) `kubectl label pod nginx app=v2`  
D) `kubectl label pod nginx app=v2 --overwrite`  

**Correct Answer: C**

*Note: Use `--overwrite` if the label already exists*

---

### Question 54
What does `kubectl create deployment nginx --image=nginx --replicas=3` do?

A) Runs 3 containers  
B) Creates a deployment with 3 replicas  
C) Creates 3 pods manually  
D) Creates 3 namespaces  

**Correct Answer: B**

---

### Question 55
Which command scales a deployment?

A) `kubectl scale nginx --replicas=5`  
B) `kubectl scale deployment nginx --replicas=5`  
C) `kubectl update deployment nginx --replicas=5`  
D) `kubectl set replicas nginx 5`  

**Correct Answer: B**

---

### Question 56
What does `kubectl set image deployment/nginx nginx=nginx:1.19` do?

A) Creates a new image  
B) Updates the image used in a deployment  
C) Lists images used  
D) Removes an image  

**Correct Answer: B**

---

### Question 57
Which command shows rollout status?

A) `kubectl rollout status deployment nginx`  
B) `kubectl get rollout nginx`  
C) `kubectl status nginx`  
D) `kubectl describe rollout nginx`  

**Correct Answer: A**

---

### Question 58
How do you undo a deployment rollout?

A) `kubectl deployment nginx --undo`  
B) `kubectl rollback deployment nginx`  
C) `kubectl rollout undo deployment nginx`  
D) `kubectl undo deployment nginx`  

**Correct Answer: C**

---

### Question 59
What does `kubectl rollout undo deployment nginx --to-revision=2` do?

A) Rolls back to an older version  
B) Rolls back to revision 2 specifically  
C) Shows revision 2  
D) Upgrades to revision 2  

**Correct Answer: B**

---

### Question 60
Which command pauses a deployment rollout?

A) `kubectl deployment nginx --pause`  
B) `kubectl rollout pause deployment nginx`  
C) `kubectl pause deployment nginx`  
D) `kubectl stop-rollout nginx`  

**Correct Answer: B**

---

### Question 61
How do you resume a paused deployment?

A) `kubectl resume deployment nginx`  
B) `kubectl rollout resume deployment nginx`  
C) `kubectl unpause deployment nginx`  
D) `kubectl start rollout nginx`  

**Correct Answer: B**

---

### Question 62
What does `kubectl expose deployment nginx --port=80` do?

A) Opens firewall port 80  
B) Creates a Service to expose the deployment  
C) Exposes the pod to the internet  
D) Configures port forwarding  

**Correct Answer: B**

---

### Question 63
Which command creates a ConfigMap from a literal value?

A) `kubectl configmap create myconfig key1=value1`  
B) `kubectl create configmap myconfig --value key1=value1`  
C) `kubectl create configmap myconfig --from-literal=key1=value1`  
D) `kubectl apply configmap myconfig key1=value1`  

**Correct Answer: C**

---

### Question 64
How do you create a ConfigMap from a file?

A) `kubectl create configmap myconfig --file=config.txt`  
B) `kubectl create configmap myconfig --from-file=config.txt`  
C) `kubectl apply configmap --file config.txt`  
D) `kubectl add configmap myconfig config.txt`  

**Correct Answer: B**

---

### Question 65
Which command creates a secret?

A) `kubectl create secret generic mysecret --from-literal=password=mypass`  
B) `kubectl create secret mysecret --password=mypass`  
C) `kubectl add secret mysecret password=mypass`  
D) `kubectl secret mysecret --from-literal password=mypass`  

**Correct Answer: A**

---

### Question 66
What does `kubectl get secret mysecret -o yaml` do?

A) Creates a secret  
B) Shows the secret in YAML format (base64 encoded)  
C) Deletes the secret  
D) Encrypts the secret  

**Correct Answer: B**

---

### Question 67
How do you create a namespace?

A) `kubectl namespace create myns`  
B) `kubectl create namespace myns`  
C) `kubectl add namespace myns`  
D) `kubectl init namespace myns`  

**Correct Answer: B**

---

## Terraform Commands

### Question 68
Which command initializes a Terraform working directory?

A) `terraform start`  
B) `terraform setup`  
C) `terraform init`  
D) `terraform new`  

**Correct Answer: C**

---

### Question 69
What does `terraform plan` do?

A) Creates a configuration file  
B) Shows a preview of changes  
C) Applies all changes  
D) Destroys infrastructure  

**Correct Answer: B**

---

### Question 70
Which command applies Terraform configuration?

A) `terraform execute`  
B) `terraform apply`  
C) `terraform run`  
D) `terraform deploy`  

**Correct Answer: B**

---

### Question 71
What does `terraform destroy` do?

A) Deletes all infrastructure managed by Terraform  
B) Removes the state file  
C) Destroys the working directory  
D) Resets the configuration  

**Correct Answer: A**

---

### Question 72
What is the correct order for a new Terraform project?

A) plan → init → apply  
B) init → apply → plan  
C) init → plan → apply  
D) apply → plan → init  

**Correct Answer: C**

---

### Question 73
Which command validates Terraform syntax?

A) `terraform check`  
B) `terraform validate`  
C) `terraform lint`  
D) `terraform verify`  

**Correct Answer: B**

---

### Question 74
What does `terraform fmt` do?

A) Formats Terraform code  
B) Creates a format file  
C) Checks the format  
D) Lists format options  

**Correct Answer: A**

---

## Helm Commands

### Question 75
Which command creates a new Helm chart?

A) `helm new mychart`  
B) `helm create mychart`  
C) `helm init mychart`  
D) `helm add mychart`  

**Correct Answer: B**

---

### Question 76
What does `helm install myrelease ./mychart` do?

A) Downloads a chart  
B) Creates a release from a local chart  
C) Updates an existing release  
D) Deletes a release  

**Correct Answer: B**

---

### Question 77
Which command lists all Helm releases?

A) `helm show releases`  
B) `helm releases`  
C) `helm list`  
D) `helm get list`  

**Correct Answer: C**

---

### Question 78
What does `helm uninstall myrelease` do?

A) Downloads a release  
B) Removes a release  
C) Pauses a release  
D) Creates a backup  

**Correct Answer: B**

---

### Question 79
How do you upgrade a Helm release?

A) `helm update myrelease ./mychart`  
B) `helm upgrade myrelease ./mychart`  
C) `helm modify myrelease ./mychart`  
D) `helm install myrelease ./mychart --upgrade`  

**Correct Answer: B**

---

### Question 80
Which command adds a Helm repository?

A) `helm add-repo bitnami https://charts.bitnami.com/bitnami`  
B) `helm repo add bitnami https://charts.bitnami.com/bitnami`  
C) `helm add bitnami https://charts.bitnami.com/bitnami`  
D) `helm repository add bitnami https://charts.bitnami.com/bitnami`  

**Correct Answer: B**

---

### Question 81
How do you show values for a Helm chart?

A) `helm show values bitnami/nginx`  
B) `helm get values bitnami/nginx`  
C) `helm values bitnami/nginx`  
D) `helm cat values bitnami/nginx`  

**Correct Answer: A**

---

### Question 82
What does `helm install mynginx bitnami/nginx --set replicaCount=3` do?

A) Creates a release with 3 nodes  
B) Creates a release setting replicaCount to 3  
C) Updates the chart  
D) Scales the deployment  

**Correct Answer: B**

---

## Security & Scanning Commands

### Question 83
Which command scans a Docker image with Trivy?

A) `trivy scan python:3.4-alpine`  
B) `trivy image python:3.4-alpine`  
C) `trivy check python:3.4-alpine`  
D) `trivy test python:3.4-alpine`  

**Correct Answer: B**

---

### Question 84
What does `trivy image myapp:1.0` do?

A) Analyzes source code  
B) Scans a Docker image for vulnerabilities  
C) Builds an image  
D) Uploads an image  

**Correct Answer: B**

---

## Flyway Commands

### Question 85
Which Flyway command applies pending migrations?

A) `flyway apply`  
B) `flyway run`  
C) `flyway migrate`  
D) `flyway execute`  

**Correct Answer: C**

---

### Question 86
What does `flyway clean` do?

A) Removes Flyway configuration  
B) Cleans old migration files  
C) Removes all database objects  
D) Cleans the logs  

**Correct Answer: C**

---

### Question 87
Which Flyway command shows migration status?

A) `flyway status`  
B) `flyway show`  
C) `flyway info`  
D) `flyway list`  

**Correct Answer: C**

---

### Question 88
What does `flyway validate` do?

A) Checks if database is accessible  
B) Validates migration files syntax  
C) Applies migrations  
D) Checks if all migrations are correct  

**Correct Answer: B**

---

### Question 89
Which Flyway command marks an existing database as baseline?

A) `flyway init`  
B) `flyway start`  
C) `flyway baseline`  
D) `flyway setup`  

**Correct Answer: C**

---

## Mixed Command Questions

### Question 90
Which of the following is NOT a valid Docker command?

A) `docker ps`  
B) `docker stop`  
C) `docker wait`  
D) `docker delay`  

**Correct Answer: D**

---

### Question 91
Which command runs a container with an environment variable?

A) `docker run -env APP=prod nginx`  
B) `docker run -e APP=prod nginx`  
C) `docker run --env APP=prod nginx`  
D) Both B and C  

**Correct Answer: D**

---

### Question 92
What is the difference between these two commands?  
`docker run ubuntu`  
`docker run -it ubuntu`

A) They are identical  
B) First runs interactively, second runs in background  
C) First is background, second is interactive with terminal  
D) No difference, aliases for same command  

**Correct Answer: C**

---

### Question 93
Which kubectl command is equivalent to `kubectl get pods`?

A) `kubectl list pods`  
B) `kubectl show pods`  
C) `kubectl get pod`  
D) `kubectl get pods` is unique  

**Correct Answer: C**

*Note: Singular and plural forms both work*

---

### Question 94
What does `docker run --rm alpine` do?

A) Runs and keeps the container  
B) Runs and removes the container automatically when it exits  
C) Removes the image  
D) Removes all stopped containers  

**Correct Answer: B**

---

### Question 95
Which command creates a pod with a custom name?

A) `kubectl run --name=mypod nginx --image=nginx`  
B) `kubectl run mypod --image=nginx`  
C) `kubectl create pod mypod --image=nginx`  
D) Both A and B  

**Correct Answer: B**

---

### Question 96
What does `docker logs -f mycontainer` do?

A) Shows logs and exits  
B) Shows logs and follows (real-time stream)  
C) Shows previous logs  
D) Filters logs  

**Correct Answer: B**

---

### Question 97
Which command checks if a port is already in use?

A) `docker port check 8080`  
B) `netstat -an | grep 8080`  
C) `docker check-port 8080`  
D) `docker ports`  

**Correct Answer: B**

*Note: This is a system command, not Docker-specific*

---

### Question 98
What does `kubectl get pods -o wide` show compared to `kubectl get pods`?

A) Shows wide format output with more details (IP, node, etc.)  
B) Shows all namespaces  
C) Shows all resource types  
D) Shows only wide deployments  

**Correct Answer: A**

---

### Question 99
Which Terraform command would you use if you want to see what will happen before making changes?

A) `terraform init`  
B) `terraform plan`  
C) `terraform apply`  
D) `terraform destroy`  

**Correct Answer: B**

---

### Question 100
Which command combination would deploy a Helm chart and set a custom value?

A) `helm install myrelease ./mychart --set image.tag=v2`  
B) `helm install myrelease ./mychart --value image.tag=v2`  
C) `helm create mychart --set image.tag=v2`  
D) `helm deploy mychart --config image.tag=v2`  

**Correct Answer: A**

---

## Bonus: Command Combinations

### Question 101
What does this sequence do?

```bash
docker build -t myapp:1.0 .
docker run -d -p 8080:3000 myapp:1.0
```

A) Lists images and containers  
B) Builds an image and then runs a container from it  
C) Pulls an image and runs it  
D) Deletes an image and container  

**Correct Answer: B**

---

### Question 102
What does this sequence do?

```bash
kubectl create deployment myapp --image=myapp:1.0
kubectl scale deployment myapp --replicas=3
kubectl expose deployment myapp --port=80
```

A) Creates a deployment, scales it to 3 replicas, and exposes it as a service  
B) Deletes resources  
C) Only creates a deployment  
D) Creates a namespace  

**Correct Answer: A**

---

### Question 103
What does this sequence do?

```bash
terraform init
terraform plan
terraform apply
```

A) Starts a server  
B) Initializes, previews, and applies infrastructure changes  
C) Deletes infrastructure  
D) Validates Terraform  

**Correct Answer: B**

---

### Question 104
What does `kubectl logs myapp -f | grep error` do?

A) Shows all logs  
B) Shows logs and filters for lines containing "error"  
C) Removes error logs  
D) Follows logs forever  

**Correct Answer: B**

---

### Question 105
Which sequence is correct for Git workflow?

A) git add → git push → git commit → git pull  
B) git init → git add → git commit → git push  
C) git clone → git add → git commit → git push  
D) git commit → git add → git push  

**Correct Answer: C**

---

## Answer Summary

**Git Commands**: Questions 1-12  
**Docker Commands**: Questions 13-36  
**Docker Compose**: Questions 37-40  
**Kubernetes (kubectl)**: Questions 41-82  
**Terraform**: Questions 68-74  
**Helm**: Questions 75-82  
**Security & Scanning**: Questions 83-84  
**Flyway**: Questions 85-89  
**Mixed & Combinations**: Questions 90-105  

---

## Quick Command Reference

### Top 20 Most Important Commands for Exam:

| Priority | Command | Purpose |
|----------|---------|---------|
| ⭐⭐⭐ | `docker run` | Create and run container |
| ⭐⭐⭐ | `docker ps` | List containers |
| ⭐⭐⭐ | `kubectl get pods` | List pods |
| ⭐⭐⭐ | `kubectl apply -f` | Create/update resources |
| ⭐⭐⭐ | `git add/commit/push` | Git workflow |
| ⭐⭐ | `docker build` | Build Docker image |
| ⭐⭐ | `kubectl logs` | View pod logs |
| ⭐⭐ | `terraform plan` | Preview changes |
| ⭐⭐ | `helm install` | Install Helm chart |
| ⭐ | `docker compose up` | Run multi-container app |
| ⭐ | `kubectl exec` | Execute command in pod |
| ⭐ | `docker network create` | Create network |
| ⭐ | `flyway migrate` | Apply migrations |

---

## Tips for Exam:
1. **Memorize basic command format** - Most questions test understanding of command syntax
2. **Pay attention to flags** - `-d`, `-f`, `-it`, `-p` are critical
3. **Remember host:container order** - In port mapping, host always comes first
4. **Focus on the most common commands** - The ones marked with ⭐⭐⭐
5. **Understand command purpose** - Rather than just memorizing, understand WHAT each command does
6. **Eliminate options** - Many wrong options will be obviously incorrect

**Good luck with your exam! 🚀**
