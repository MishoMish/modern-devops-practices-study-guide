# 📝 ADDITIONAL EXAM QUESTIONS - PART 2

## More Exam-Style Multiple Choice Questions (Continued)

---

## Docker Advanced Questions

### Question 66
What is the default restart policy for Docker containers?

A) `always`  
B) `unless-stopped`  
C) `no`  
D) `on-failure`  

**Correct Answer: C**

*Explanation: By default, containers have restart policy `no`, meaning they won't restart automatically when they stop. Use `--restart=always` or similar to enable automatic restarts.*

---

### Question 67
What does `docker run --rm alpine` do differently than `docker run alpine`?

A) Runs with root permissions removed  
B) Automatically removes the container when it exits  
C) Runs in read-only mode  
D) Removes the image after use  

**Correct Answer: B**

*Explanation: The `--rm` flag tells Docker to automatically remove the container when it exits. This is useful for temporary containers where you don't need the container filesystem afterward.*

---

### Question 68
In Docker, what is a "dangling image"?

A) An image that is not tagged and not referenced by any container  
B) An image being downloaded  
C) A corrupted image  
D) An image shared between containers  

**Correct Answer: A**

*Explanation: A dangling image is one that is not tagged and is not referenced by any container. These often occur during rebuilds. Use `docker image prune` to remove them.*

---

### Question 69
What is the purpose of the `:ro` suffix in `-v /host/path:/container/path:ro`?

A) Read-only - container cannot modify the host files  
B) Root-only access  
C) Recursive option  
D) Remote origin  

**Correct Answer: A**

*Explanation: The `:ro` suffix makes the volume mount read-only, preventing the container from modifying files on the host. This is a security best practice when containers only need to read data.*

---

### Question 70
What command shows the disk space used by Docker images?

A) `docker disk usage`  
B) `docker image ls`  
C) `docker system df`  
D) `docker space`  

**Correct Answer: C** (but `docker image ls` also shows image sizes)

*Explanation: `docker system df` shows disk usage for images, containers, volumes, and build cache. `docker image ls` shows individual image sizes but not total disk usage.*

---

### Question 71
In Docker Compose, what does `docker compose down` do compared to `docker compose stop`?

A) They are identical  
B) `down` stops and removes containers and networks; `stop` only stops containers  
C) `down` only stops, `stop` removes  
D) `down` is for production, `stop` is for development  

**Correct Answer: B**

*Explanation: `docker compose stop` stops the containers but keeps them. `docker compose down` stops and removes containers, networks, and optionally volumes (`-v` flag).*

---

### Question 72
What happens if you try to build a Docker image without a Dockerfile in the current directory?

A) Docker creates a default Dockerfile  
B) Docker fails with an error  
C) Docker builds from the image cache  
D) Docker pulls a base image  

**Correct Answer: B**

*Explanation: Docker requires a Dockerfile to build an image. If not found, the build fails with an error. You can specify a different path with `-f`.*

---

### Question 73
In a Dockerfile, what does `WORKDIR /app` do?

A) Copies files to /app  
B) Creates /app directory and sets it as the working directory  
C) Only creates the directory  
D) Changes permissions of /app  

**Correct Answer: B**

*Explanation: `WORKDIR` creates the directory if it doesn't exist AND sets it as the current working directory for subsequent instructions like `RUN`, `CMD`, `COPY`, etc.*

---

### Question 74
What is the difference between shell form and exec form of CMD in a Dockerfile?

A) Shell form: `CMD command param1`; Exec form: `CMD ["command", "param1"]`  
B) They are identical  
C) Exec form uses shell, shell form doesn't  
D) Shell form is deprecated  

**Correct Answer: A**

*Explanation: Shell form (`CMD command`) runs the command in a shell (`/bin/sh -c`). Exec form (`CMD ["command"]`) runs the command directly without a shell. Exec form is preferred as it handles signals properly.*

---

### Question 75
When building a Docker image, layers are cached. Which action would invalidate the cache for a layer?

A) Using the same base image  
B) Changing the instruction or any files it depends on  
C) Running the build at a different time  
D) Using a different image name  

**Correct Answer: B**

*Explanation: Docker caches layers based on the instruction and its dependencies. If you change a RUN command or the files being COPYed, that layer and all subsequent layers are rebuilt.*

---

## Kubernetes Advanced Questions

### Question 76
What is the default Service type in Kubernetes if not specified?

A) NodePort  
B) LoadBalancer  
C) ClusterIP  
D) ExternalName  

**Correct Answer: C**

*Explanation: If you don't specify a type, Kubernetes creates a ClusterIP service, which is only accessible within the cluster.*

---

### Question 77
In Kubernetes, what is an endpoint?

A) The URL of the Kubernetes API  
B) The IP and port of a pod backing a service  
C) The entry point of a container  
D) The DNS name of a service  

**Correct Answer: B**

*Explanation: Endpoints are the IP addresses and ports of the pods that match a service's selector. When you hit a service, traffic is routed to these endpoints.*

---

### Question 78
What command shows the IP address of a pod?

A) `kubectl get pod nginx -o wide`  
B) `kubectl get pod nginx --ip`  
C) `kubectl pod ip nginx`  
D) `kubectl network pod nginx`  

**Correct Answer: A**

*Explanation: The `-o wide` flag adds additional columns including the pod's IP address and the node it's running on.*

---

### Question 79
What happens to data in an `emptyDir` volume when a pod is deleted?

A) Data is preserved  
B) Data is deleted  
C) Data is moved to a PersistentVolume  
D) Data is backed up  

**Correct Answer: B**

*Explanation: An `emptyDir` volume's lifecycle is tied to the pod. When the pod is removed from a node for any reason, the data in the `emptyDir` is deleted permanently.*

---

### Question 80
What is the purpose of a ReplicaSet in Kubernetes?

A) To replicate data between pods  
B) To ensure a specified number of pod replicas are running  
C) To replicate nodes  
D) To backup deployments  

**Correct Answer: B**

*Explanation: A ReplicaSet ensures that a specified number of pod replicas are running at any given time. Deployments manage ReplicaSets, adding rolling update capabilities.*

---

### Question 81
What does `kubectl get events` show?

A) User login events  
B) Cluster events like pod scheduling, errors, and warnings  
C) Network traffic events  
D) API request logs  

**Correct Answer: B**

*Explanation: Events show what's happening in the cluster - pod scheduling, image pulls, container starts, errors, warnings, etc. Very useful for debugging.*

---

### Question 82
What is the purpose of `kubectl describe pod nginx`?

A) Shows the YAML definition  
B) Shows detailed information including events  
C) Describes how to use the pod  
D) Describes the container image  

**Correct Answer: B**

*Explanation: `describe` shows detailed information about a resource, including status, events, conditions, and configuration. Events at the bottom are particularly useful for debugging.*

---

### Question 83
In Kubernetes, what does "pending" pod status typically indicate?

A) The pod is running  
B) The pod cannot be scheduled (no available node, resource constraints, etc.)  
C) The pod is being deleted  
D) The pod image is being pulled  

**Correct Answer: B**

*Explanation: A "Pending" status usually means the scheduler cannot place the pod. Common reasons: insufficient resources, node selector mismatches, taints, or PVC binding issues.*

---

### Question 84
What is the purpose of `kubectl logs nginx -p`?

A) Shows logs in pod format  
B) Shows logs from the previous instance of the container  
C) Shows logs in parallel  
D) Shows logs with timestamps  

**Correct Answer: B**

*Explanation: The `-p` or `--previous` flag shows logs from the previous container instance. This is useful when a container has crashed and restarted, and you need to see what happened.*

---

### Question 85
What does `imagePullPolicy: Always` mean?

A) Always use cached images  
B) Always pull the image from the registry, even if present locally  
C) Always try local image first  
D) Always use the latest tag  

**Correct Answer: B**

*Explanation: `Always` means Kubernetes will always try to pull the image from the registry. `IfNotPresent` only pulls if not cached locally. `Never` never pulls (must be present).*

---

### Question 86
In a Kubernetes Job, what does `restartPolicy: Never` mean?

A) The job never runs  
B) Failed pods are not restarted; new pods are created instead  
C) The pod restarts on failure  
D) The job cannot be deleted  

**Correct Answer: B**

*Explanation: With `Never`, if a pod fails, it stays in Failed state and the Job creates a new pod. With `OnFailure`, the same pod is restarted. Jobs cannot use `Always`.*

---

### Question 87
What is the purpose of a HorizontalPodAutoscaler (HPA)?

A) To horizontally partition data  
B) To automatically scale the number of pods based on metrics  
C) To autoscale nodes  
D) To balance network traffic  

**Correct Answer: B**

*Explanation: HPA automatically adjusts the number of pod replicas based on observed CPU utilization or custom metrics. It requires metrics-server to be installed.*

---

### Question 88
In Kubernetes secrets, how is data stored?

A) Plain text  
B) Encrypted with AES  
C) Base64 encoded (not encrypted by default)  
D) Hashed with SHA256  

**Correct Answer: C**

*Explanation: Secrets are base64 encoded, NOT encrypted by default. Base64 is encoding, not encryption. You need to enable encryption at rest separately.*

---

### Question 89
What is the CronJob schedule `*/5 * * * *`?

A) Every 5 hours  
B) Every 5 minutes  
C) At 5 minutes past each hour  
D) 5 times per day  

**Correct Answer: B**

*Explanation: The format is `minute hour day-of-month month day-of-week`. `*/5` in the first position means every 5 minutes. The asterisks mean "every" for the other fields.*

---

### Question 90
What does `kubectl exec -it pod-name -c container-name -- /bin/sh` do?

A) Executes a shell in all containers  
B) Executes a shell in the specified container within a multi-container pod  
C) Creates a new container  
D) Copies files to the container  

**Correct Answer: B**

*Explanation: The `-c` flag specifies which container to execute the command in when a pod has multiple containers. Without `-c`, it defaults to the first container.*

---

## GitHub Actions Advanced Questions

### Question 91
What is the difference between `on: push` and `on: pull_request` triggers?

A) They are identical  
B) `push` runs on code push; `pull_request` runs when a PR is opened/updated  
C) `push` is for main branch only  
D) `pull_request` doesn't run tests  

**Correct Answer: B**

*Explanation: `push` triggers when commits are pushed to the repository. `pull_request` triggers when a PR is opened, synchronized (new commits pushed), or reopened.*

---

### Question 92
In GitHub Actions, what does `continue-on-error: true` do?

A) Skips the step  
B) Allows the workflow to continue even if this step fails  
C) Retries the step on error  
D) Logs errors but stops execution  

**Correct Answer: B**

*Explanation: `continue-on-error: true` allows subsequent steps and jobs to run even if this step fails. The step is marked as failed, but the workflow continues.*

---

### Question 93
What is the purpose of `actions/cache@v4` in GitHub Actions?

A) To cache Docker images  
B) To cache dependencies to speed up builds  
C) To cache secrets  
D) To cache workflow files  

**Correct Answer: B**

*Explanation: `actions/cache` caches directories like `node_modules` or Maven's `.m2` to speed up subsequent builds by avoiding repeated downloads.*

---

### Question 94
In GitHub Actions, what does `if: success()` mean?

A) Run if all previous steps succeeded  
B) Run if the current step succeeds  
C) Always run  
D) Run if the workflow succeeds  

**Correct Answer: A**

*Explanation: `success()` is true if all previous steps succeeded. Other conditions: `failure()` (previous step failed), `always()` (always run), `cancelled()` (workflow cancelled).*

---

### Question 95
What is a reusable workflow in GitHub Actions?

A) A workflow that can be called from other workflows  
B) A workflow that runs on schedule  
C) A workflow template  
D) A workflow that can be paused and resumed  

**Correct Answer: A**

*Explanation: Reusable workflows use `workflow_call` trigger and can be called from other workflows using the `uses` keyword at the job level. They help reduce duplication.*

---

### Question 96
What permissions are needed to push a Docker image to GitHub Container Registry?

A) `contents: read`  
B) `packages: write`  
C) `actions: write`  
D) `admin: true`  

**Correct Answer: B**

*Explanation: To push packages (including Docker images) to GitHub Container Registry, you need `packages: write` permission in your workflow.*

---

### Question 97
In GitHub Actions, what is Super-linter used for?

A) Checking code formatting and style across multiple languages  
B) Building applications  
C) Testing applications  
D) Deploying applications  

**Correct Answer: A**

*Explanation: Super-linter is a GitHub Action that runs multiple linters (for various languages) against your code to check for formatting, style, and potential issues.*

---

## Terraform Questions

### Question 98
What is the purpose of `terraform init`?

A) Creates infrastructure  
B) Initializes working directory, downloads providers  
C) Shows planned changes  
D) Deletes state file  

**Correct Answer: B**

*Explanation: `terraform init` initializes the working directory containing Terraform configuration files. It downloads providers and modules, and sets up the backend for state storage.*

---

### Question 99
What is Terraform's approach to infrastructure changes called?

A) Mutable infrastructure  
B) Immutable infrastructure  
C) Dynamic infrastructure  
D) Flexible infrastructure  

**Correct Answer: B**

*Explanation: Terraform takes an immutable approach - rather than modifying existing resources, it often replaces them. This reduces complexity and ensures consistent configurations.*

---

### Question 100
What is a Terraform provider?

A) A cloud platform  
B) A plugin that enables Terraform to work with specific platforms/services  
C) A configuration file  
D) A state storage backend  

**Correct Answer: B**

*Explanation: Providers are plugins that enable Terraform to interact with cloud platforms, SaaS providers, and other APIs. Examples: AWS, Azure, GCP, Kubernetes providers.*

---

## Flyway Questions

### Question 101
What does Flyway use to track which migrations have been applied?

A) A local file  
B) A database table (flyway_schema_history)  
C) Git commits  
D) Environment variables  

**Correct Answer: B**

*Explanation: Flyway maintains a `flyway_schema_history` table in the database to track which migrations have been applied, their checksums, and when they were run.*

---

### Question 102
What happens if you try to apply a migration that conflicts with an already applied migration?

A) The new migration overwrites the old one  
B) Flyway fails validation and stops  
C) The migrations are merged  
D) The old migration is rolled back  

**Correct Answer: B**

*Explanation: Flyway validates migrations by checking checksums. If a migration file has been modified after being applied, or versions conflict, Flyway will fail with a validation error.*

---

### Question 103
In Flyway, what is the purpose of `flyway validate`?

A) Validates SQL syntax  
B) Validates that local migrations match what's in the database  
C) Validates database connection  
D) Validates configuration files  

**Correct Answer: B**

*Explanation: `validate` checks that local migration files match what was applied to the database (checksums). This helps catch accidental modifications to migrations.*

---

## Security Questions

### Question 104
What is "white box testing" in the context of SAST?

A) Testing without knowing the internal code  
B) Testing with full knowledge/access to the source code  
C) Testing the user interface  
D) Performance testing  

**Correct Answer: B**

*Explanation: White box testing (what SAST performs) involves analyzing code with full knowledge of its internals. Black box testing has no access to source code.*

---

### Question 105
Why is SAST considered faster than manual code reviews?

A) It uses AI  
B) It can analyze 100% of the codebase automatically  
C) It skips complex code  
D) It only checks configuration files  

**Correct Answer: B**

*Explanation: SAST tools can automatically analyze the entire codebase quickly, finding patterns that would take humans much longer to identify manually.*

---

## Mixed/Integration Questions

### Question 106
In a CI/CD pipeline, what is the correct order of stages?

A) Deploy → Build → Test  
B) Build → Deploy → Test  
C) Test → Build → Deploy  
D) Build → Test → Deploy  

**Correct Answer: D**

*Explanation: The standard order is: Build (compile/package), Test (run tests), Deploy (release to environment). Testing before deploying ensures quality.*

---

### Question 107
What is the relationship between Docker images and Kubernetes pods?

A) They are the same thing  
B) Pods contain one or more containers created from images  
C) Images contain pods  
D) They are unrelated  

**Correct Answer: B**

*Explanation: A Kubernetes Pod is a wrapper around one or more containers. Containers are created from Docker images. The pod spec references images to create containers.*

---

### Question 108
In a microservices architecture, why is Docker useful?

A) It makes applications run faster  
B) It provides isolation and consistent environments for each service  
C) It eliminates the need for testing  
D) It automatically scales services  

**Correct Answer: B**

*Explanation: Docker provides isolated, consistent environments. Each microservice can have its own dependencies and runtime without conflicts, and will behave the same across development, testing, and production.*

---

### Question 109
What is the benefit of using infrastructure as code (Terraform) over manual provisioning?

A) It's faster for one-time setups  
B) Reproducibility, version control, and automation  
C) It doesn't require any technical knowledge  
D) It's only for cloud providers  

**Correct Answer: B**

*Explanation: IaC provides reproducible infrastructure, can be version controlled with Git, reviewed like code, and automated in CI/CD pipelines. Manual provisioning is error-prone and not reproducible.*

---

### Question 110
What does "shift left" mean in DevSecOps?

A) Deploying to the left region  
B) Moving security testing earlier in the development process  
C) Prioritizing left-aligned code  
D) Using left-hand navigation  

**Correct Answer: B**

*Explanation: "Shift left" means moving testing, especially security testing, earlier in the development lifecycle. This catches issues when they're cheaper to fix.*

---

## Quick Reference: Common Mistakes to Avoid

### Docker Mistakes

1. **Port mapping confusion**: Remember `host:container` - host port FIRST
2. **EXPOSE doesn't open ports**: You still need `-p` when running
3. **CMD vs ENTRYPOINT**: CMD can be overridden, ENTRYPOINT always runs
4. **Using ADD instead of COPY**: Use COPY unless you need tar extraction

### Kubernetes Mistakes

1. **Forgetting namespace**: Use `-n namespace` or `--all-namespaces`
2. **Labels vs Annotations**: Labels are for selection, annotations are metadata
3. **Secrets aren't encrypted**: They're only base64 encoded
4. **Confusing ClusterIP with NodePort**: ClusterIP is internal only

### GitHub Actions Mistakes

1. **YAML indentation**: Very strict, use consistent spacing
2. **Forgetting checkout**: Many jobs need `actions/checkout@v4` first
3. **Secret names case-sensitive**: `secrets.MY_SECRET` exactly as defined
4. **Job dependencies**: Use `needs` for sequential execution

---

## Study Tips for Maximum Score

### 1. Understand the WHY
Don't just memorize commands - understand WHY each option exists. Exams often test understanding, not just recall.

### 2. Focus on Differences
Many questions ask about differences between similar concepts:
- CMD vs ENTRYPOINT
- ConfigMap vs Secret
- ClusterIP vs NodePort
- `kubectl create` vs `kubectl apply`

### 3. Know the Defaults
Questions often test knowledge of default values:
- Default restart policy: `no`
- Default service type: `ClusterIP`
- Default imagePullPolicy depends on tag

### 4. Practice Reading YAML
Many questions will show YAML and ask about behavior. Be comfortable reading and understanding Kubernetes and Docker Compose YAML.

### 5. Remember Key Numbers
- Container port = right side of `-p` mapping
- Default HTTP port: 80
- Default HTTPS port: 443
- Kubernetes API server typically: 6443

### 6. Command Structure Patterns
- Docker: `docker <object> <command>` (e.g., `docker container ls`)
- Kubernetes: `kubectl <verb> <resource>` (e.g., `kubectl get pods`)
- Terraform: `terraform <command>` (e.g., `terraform apply`)
- Flyway: `flyway <command>` (e.g., `flyway migrate`)

---

**Good luck on your exam! 🎓**

*Remember: This guide covers ONLY what's in your course materials. Stick to these concepts and you'll be well-prepared.*
---

## CRITICAL LECTURE-SPECIFIC QUESTIONS (Questions 111-130)

These questions are derived directly from the lecture presentations and are HIGH PRIORITY for exam preparation.

---

### Question 111
According to the course, what does SCM stand for?

A) Software Configuration Manager  
B) Source Code Manager  
C) Source Control Management  
D) System Control Module  

**Correct Answer: C**

*Explanation: SCM stands for Source Control Management - it tracks running history of changes to a code base and helps resolve conflicts when multiple developers work on a shared codebase.*

---

### Question 112
Which of these is NOT a pillar of the AWS Well-Architected Framework?

A) Operational Excellence  
B) Scalability  
C) Security  
D) Sustainability  

**Correct Answer: B**

*Explanation: The 6 pillars are: Operational Excellence, Security, Reliability, Performance Efficiency, Cost Optimization, and Sustainability. Scalability is not a separate pillar.*

---

### Question 113
What philosophy does DevOps embrace for managing systems?

A) Manual configuration  
B) Everything as Code  
C) Point-and-click interfaces  
D) Verbal documentation  

**Correct Answer: B**

*Explanation: DevOps embraces "Everything as Code" - Infrastructure as Code, Configuration as Code, Pipeline as Code, and Documentation as Code.*

---

### Question 114
According to CI practices, what should be maintained?

A) Multiple source repositories  
B) A single source repository  
C) No version control  
D) Separate repos per developer  

**Correct Answer: B**

*Explanation: One of the key CI practices is to maintain a single source repository (Git) for the codebase.*

---

### Question 115
What characteristic is NOT associated with a Deployment Pipeline?

A) Goes from Commit to Releasable Outcome  
B) The ONLY route to production  
C) Can be bypassed for urgent fixes  
D) Auditable  

**Correct Answer: C**

*Explanation: The Deployment Pipeline should be the ONLY route to production - it should never be bypassed, even for urgent fixes.*

---

### Question 116
What does CD (in Continuous Delivery context) bring beyond CI?

A) Only automated testing  
B) Automated release process with click of a button  
C) Manual deployments  
D) Only security scanning  

**Correct Answer: B**

*Explanation: CD brings CI to the next step - not just an automated pipeline but also automated release process with a click of a button.*

---

### Question 117
According to CD practices, deployments should be:

A) Large and infrequent  
B) Small and frequent  
C) Only on weekends  
D) Done manually for safety  

**Correct Answer: B**

*Explanation: CD practices include keeping deployments small (easier rollback) and deploying to production frequently.*

---

### Question 118
What is "Shift Left Testing"?

A) Moving testing to the end of the pipeline  
B) Testing earlier in the pipeline  
C) Only testing on the left side of the architecture  
D) Testing in production  

**Correct Answer: B**

*Explanation: Shift Left Testing means testing earlier in the pipeline (moving "left" in the timeline), catching issues sooner and reducing costs.*

---

### Question 119
Which is a Microservice principle related to handling failures?

A) Cascade failures  
B) Isolate failure  
C) Ignore failures  
D) Centralize failure handling  

**Correct Answer: B**

*Explanation: One of the 6 Principles of Microservices is "Isolate failure" - failures in one service should not cascade to others.*

---

### Question 120
In the IaaS service model, what does the user manage?

A) Only the application  
B) Nothing  
C) OS, Runtime, and Application  
D) Only the hardware  

**Correct Answer: C**

*Explanation: In IaaS (Infrastructure as a Service), the user manages the OS, Runtime, and Application. The provider manages the hardware/infrastructure.*

---

### Question 121
What is URL Versioning in APIs?

A) Version in HTTP header  
B) Version in the URL path  
C) Version in query parameter  
D) Version in request body  

**Correct Answer: B**

*Explanation: URL Versioning puts the version in the path, e.g., `/api/v1/resource`.*

---

### Question 122
How many Availability Zones typically exist per AWS Region?

A) 1  
B) 2-3 or more  
C) Exactly 5  
D) Exactly 10  

**Correct Answer: B**

*Explanation: AWS Regions typically contain 2-3 or more Availability Zones for redundancy and high availability.*

---

### Question 123
What is the key difference between containers and VMs in terms of OS?

A) Containers include a full guest OS, VMs don't  
B) VMs include a full guest OS, containers share the host OS kernel  
C) Both include a full guest OS  
D) Neither includes an OS  

**Correct Answer: B**

*Explanation: VMs run a full guest operating system, while containers share the host OS kernel, making containers lighter and faster.*

---

### Question 124
What is AWS Lambda?

A) A virtual machine service  
B) A serverless compute service  
C) A database service  
D) A storage service  

**Correct Answer: B**

*Explanation: AWS Lambda is a serverless compute service that runs code in response to events without provisioning servers.*

---

### Question 125
What does "event-driven execution" mean in the context of Lambda?

A) Functions run continuously  
B) Functions run in response to events  
C) Functions require manual triggering  
D) Functions run on a schedule only  

**Correct Answer: B**

*Explanation: Lambda functions are triggered by events (API calls, file uploads, database changes, etc.) rather than running continuously.*

---

### Question 126
According to the declarative approach, you define:

A) HOW to achieve the desired state  
B) WHAT you want (the desired end state)  
C) WHEN to execute changes  
D) WHO should make changes  

**Correct Answer: B**

*Explanation: Declarative approach means you define WHAT you want (the desired end state), and the tool figures out HOW to achieve it. Terraform uses this approach.*

---

### Question 127
According to the procedural approach, you define:

A) WHAT you want  
B) HOW to achieve the state (step-by-step)  
C) Only the final state  
D) Nothing specific  

**Correct Answer: B**

*Explanation: Procedural (imperative) approach means you define step-by-step instructions on HOW to get to the desired state. The order of operations matters.*

---

### Question 128
What is the AWS service for managed Kubernetes?

A) ECS  
B) EKS  
C) EC2  
D) Lambda  

**Correct Answer: B**

*Explanation: EKS (Elastic Kubernetes Service) is AWS's managed Kubernetes service. ECS is AWS's native container orchestration service.*

---

### Question 129
According to the course, what is the relationship between DevOps and Agile?

A) They are completely unrelated  
B) DevOps is related to and extends Agile practices  
C) Agile replaces DevOps  
D) DevOps replaces Agile  

**Correct Answer: B**

*Explanation: DevOps is related to Agile and extends its practices to include operations, automation, and the full software delivery lifecycle.*

---

### Question 130
What does S3 durability of "11 9's" mean?

A) 99% uptime  
B) 99.999999999% durability  
C) 11 storage classes  
D) 11 regions  

**Correct Answer: B**

*Explanation: S3 provides 99.999999999% (11 nines) durability, meaning your data is extremely unlikely to be lost.*

---