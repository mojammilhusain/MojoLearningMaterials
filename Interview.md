# 🎯 DevOps Interview Preparation — Mojammil Husain

> **Role:** DevOps Engineer | **Experience:** 5+ Years | **Cloud:** Azure · AWS · GCP
> **Duration:** 2-Hour Technical Interview | **Difficulty:** Intermediate to Advanced

---

## 📋 Table of Contents

1. [🎤 Self Introduction](#-self-introduction)
2. [👤 Resume Deep-Dive Questions](#-resume-deep-dive-questions)
3. [☁️ Cloud & Infrastructure as Code](#️-cloud--infrastructure-as-code)
4. [🔄 CI/CD & Automation](#-cicd--automation)
5. [🐳 Docker & Containerization](#-docker--containerization)
6. [☸️ Kubernetes & Orchestration](#️-kubernetes--orchestration)
7. [📊 Monitoring & Observability](#-monitoring--observability)
8. [🔒 DevSecOps & Security](#-devsecops--security)
9. [🌐 Networking & DNS](#-networking--dns)
10. [🧠 Scenario-Based Questions](#-scenario-based-questions)
11. [💼 Behavioral & Situational Questions](#-behavioral--situational-questions)
12. [❓ Questions to Ask the Interviewer](#-questions-to-ask-the-interviewer)

---

## 🎤 Self Introduction

> **⏱️ Duration: 2.5 – 3 Minutes | This sets the tone for the entire interview.**

> Hi, I'm Mojammil. I'm a DevOps Engineer with over 5 years of experience specializing in managing cloud infrastructure, automation, and CI/CD pipelines. Throughout my career, I've been heavily focused on delivering secure, scalable, cloud-native platforms across multi-cloud environments — specifically Azure, AWS, and GCP.
>
> I started my career on the software engineering side as a full-stack developer working with Angular and .NET Core. That experience gave me a deep understanding of the software development lifecycle and the pain points developers face every day. It naturally led me to transition into DevOps, where my goal has always been to bridge the gap between development and operations to accelerate delivery cycles.
>
> I spent over three years at **Accenture** as a DevOps Engineer for their Identity and Access Management team. We followed a strict Agile methodology running 15-day sprints, and relied entirely on the Azure DevOps ecosystem — Azure Repos for source control, Azure Pipelines for CI/CD, Artifactory for package management, and Azure Boards for sprint planning and task tracking. In that role, I engineered foundational Infrastructure as Code modules using Terraform and Ansible, and led the automated deployments for passwordless and MFA authentication solutions. By driving CI/CD adoption and centralized monitoring, we were able to drastically cut down on authentication-related helpdesk tickets.
>
> Currently, I'm with **Infosys** managing DevOps and infrastructure operations for the **Haleon** account, where we track all our work through Jira. My team and I manage 8 critical servers hosting numerous IIS and Apache web applications, alongside Globalscape EFT for secure enterprise file transfers. We recently migrated all our core services to Azure, so I use Terraform extensively to provision and manage cloud resources — including Virtual Machines, Application Gateways, Key Vaults, MySQL databases, and networking components — while our DNS infrastructure still runs on GCP. Our CI/CD pipelines are built on Jenkins with code managed in GitHub.
>
> A major focus of mine at Infosys has been eliminating manual toil and improving reliability. I've built automated workflows for tasks like IIS site provisioning and SSL certificate generation and renewals — work that used to take significant manual effort. On the observability side, I manage our full monitoring stack using Datadog, OpsRamp, and Azure native alerting to ensure high availability across all our enterprise workloads.
>
> Moving forward, I'm passionate about Kubernetes orchestration, Infrastructure as Code, and building resilient, self-healing systems. I have a proven track record of driving operational efficiency, and I'm looking for my next challenge where I can bring this hands-on, multi-cloud expertise to make an immediate impact on your team.
>
> Thank you, and I'm really excited to be speaking with you today.

---

## 🛠️ Skill Set Introduction

> **⏱️ Duration: 1 – 1.5 Minutes | Use when asked "Walk me through your technical skills"**

> If I break down my skill set, I'd group it into four pillars:
>
> **First — Cloud & Infrastructure as Code.**
> I work across Azure, AWS, and GCP daily. At Infosys, we migrated our core workloads to Azure, so I manage resources like Virtual Machines, Application Gateways, Key Vaults, and MySQL databases — while our DNS still runs on GCP. I've also worked with AWS services like EC2 and RDS. Terraform is my primary IaC tool, alongside Ansible for configuration management.
>
> **Second — CI/CD & Automation.**
> I have deep experience building release pipelines. Currently I use Jenkins and GitHub, and at Accenture I worked entirely within Azure DevOps — Repos, Pipelines, Artifacts, and Boards. I also write PowerShell and Bash scripts to automate server tasks like SSL renewals and IIS site provisioning.
>
> **Third — Containerization & Orchestration.**
> I'm comfortable dockerizing applications and managing Kubernetes clusters — particularly AKS — for scalable, highly available microservices.
>
> **Fourth — Observability & Server Administration.**
> I manage servers hosting IIS and Apache sites, and use Datadog, OpsRamp, and Azure Monitor for centralized dashboards and alerting.
>
> My core strength is bringing all of these together to build infrastructure that is secure, reliable, and easy to maintain.

---

## 👤 Resume Deep-Dive Questions

> [!IMPORTANT]
> These are the first questions an interviewer will ask after your introduction. They come directly from your resume bullet points. **Be ready for these — they are guaranteed.**

---

### 🔹 Q1: Tell me about the Haleon account. What exactly do you manage?

> **Best Answer:**
>
> Haleon is a global consumer healthcare company, and at Infosys I manage the entire DevOps and infrastructure operations for their account. On a daily basis, my team and I are responsible for:
>
> - **8 critical servers** hosting multiple IIS and Apache web applications
> - **Globalscape EFT** servers for secure enterprise file transfers
> - **SSL certificate lifecycle management** — generation, renewal, and deployment
> - **Cloud infrastructure on Azure** — Virtual Machines, Application Gateways, Key Vaults, MySQL databases — all provisioned and managed through Terraform
> - **DNS management on GCP** — we migrated most services to Azure but DNS still runs on GCP Cloud DNS
> - **CI/CD pipelines** using Jenkins and GitHub
> - **Observability** using Datadog, OpsRamp, and Azure native alerts
> - **Task tracking** through Jira
>
> My primary contribution has been **automating manual toil** — I've built workflows to automate IIS site provisioning and SSL generation, which used to consume hours of manual effort per week.

---

### 🔹 Q2: You mentioned migrating services to Azure. Walk me through that migration.

> **Best Answer:**
>
> When I joined the Haleon account, many of our services were running across a mix of on-premises and multi-cloud setups. The goal was to consolidate core workloads onto Azure for better manageability, security, and cost optimization.
>
> My approach was:
> 1. **Assessment** — I catalogued all existing services, their dependencies, and traffic patterns
> 2. **IaC First** — Before migrating anything, I wrote Terraform modules for every Azure resource we'd need — VMs, Application Gateways, Key Vaults, MySQL databases, VNets, and NSGs
> 3. **Phased Migration** — We moved services in phases, starting with non-critical workloads and validating monitoring/alerting at each stage before moving production workloads
> 4. **DNS Exception** — We decided to keep DNS on GCP Cloud DNS because it was already well-configured and served as our global DNS resolution layer, avoiding unnecessary risk
> 5. **Validation** — Post-migration, we set up comprehensive Datadog dashboards and OpsRamp monitoring to ensure everything was performing at or above previous baselines
>
> The result was a more unified infrastructure with centralized management, improved security posture through Azure Key Vault, and reduced operational complexity.

---

### 🔹 Q3: Tell me about your work at Accenture. What was the IAM team responsible for?

> **Best Answer:**
>
> At Accenture, I was part of the Identity and Access Management team for over three years. Our team was responsible for building and deploying enterprise authentication solutions — specifically **Passwordless authentication, Windows Hello for Business, and Multi-Factor Authentication (MFA)**.
>
> My specific responsibilities included:
> - **Infrastructure as Code** — I engineered reusable Terraform and Ansible modules to standardize deployments across Azure and AWS
> - **CI/CD Pipelines** — I built and maintained automated release pipelines using Azure DevOps Pipelines with Artifactory for package management
> - **Agile Workflow** — We ran 15-day sprints using Azure Boards for sprint planning and task tracking
> - **Deployment Automation** — I led the automation of deploying passwordless and MFA solutions, which significantly reduced authentication-related helpdesk tickets
> - **Monitoring & Incident Response** — I implemented centralized monitoring and created operational runbooks that accelerated our Mean Time to Resolve (MTTR)
>
> The biggest win was driving CI/CD adoption across the team — moving from manual deployments to fully automated pipelines dramatically improved our deployment frequency and reliability.

---

### 🔹 Q4: You automated IIS site provisioning and SSL generation. How did you do that?

> **Best Answer:**
>
> Previously, setting up a new IIS site was a fully manual process — an engineer would RDP into the server, create the site in IIS Manager, configure bindings, set up the application pool, configure permissions, and then manually generate and bind the SSL certificate. This would take anywhere from 30 minutes to an hour per site, and it was error-prone.
>
> I automated this using **PowerShell scripts** that:
> 1. **Accept parameters** — site name, binding details, application pool settings, and certificate requirements
> 2. **Create the IIS site** programmatically using the `WebAdministration` PowerShell module
> 3. **Configure the application pool** with the correct .NET version and identity
> 4. **Generate or renew SSL certificates** — either through an internal CA or by automating the CSR generation and certificate installation process
> 5. **Bind the SSL certificate** to the site automatically
> 6. **Validate** the site is running and accessible
>
> I then integrated these scripts into our Jenkins pipeline so that a new site setup could be triggered through a parameterized Jenkins job with proper approvals. This reduced site provisioning time from ~1 hour of manual work to about 5 minutes of automated execution.

---

### 🔹 Q5: You have certifications in AZ-400, AZ-500, AZ-104, and Google ACE. Which one was the most challenging and why?

> **Best Answer:**
>
> The **AZ-500 (Azure Security Engineer Associate)** was the most challenging for me. While AZ-104 tests your ability to manage Azure resources and AZ-400 focuses on DevOps practices, AZ-500 goes deep into security concepts — network security groups, Azure Firewall, Azure AD Conditional Access, Key Vault advanced policies, and compliance frameworks.
>
> What made it challenging was the breadth of security topics — you need to understand identity security, platform security, data security, and security operations all at an expert level. But it also made me a much better DevOps engineer because I now approach every infrastructure decision with a security-first mindset. For example, when I set up Terraform modules, I always include Key Vault integration for secrets, NSG rules for network segmentation, and managed identities instead of storing credentials.
>
> The **Google ACE** was valuable for a different reason — it forced me to think in GCP terms (projects, VPCs, IAM bindings) which is useful because I manage DNS on GCP daily at Infosys.

---

## ☁️ Cloud & Infrastructure as Code

> [!NOTE]
> **⏱️ This section covers ~25-30 minutes of the interview.** Expect deep questions on Terraform, Azure services, and multi-cloud architecture.

---

### 🔹 Q6: What is Terraform and why do you prefer it over other IaC tools?

> **Best Answer:**
>
> Terraform is an open-source Infrastructure as Code tool by HashiCorp that allows you to define, provision, and manage infrastructure across multiple cloud providers using a declarative configuration language called HCL (HashiCorp Configuration Language).
>
> I prefer Terraform because:
> - **Multi-cloud support** — I work across Azure, AWS, and GCP, and Terraform lets me manage all three with a single tool and consistent workflow
> - **State management** — Terraform maintains a state file that tracks the real-world state of infrastructure, enabling accurate diffs and drift detection
> - **Modularity** — I can create reusable modules (e.g., a "VM module" or "AKS module") that standardize deployments across teams
> - **Plan before Apply** — `terraform plan` shows exactly what will change before anything is deployed, which is critical in production environments
> - **Large ecosystem** — The provider ecosystem is massive, covering everything from cloud resources to Datadog monitors to GitHub repositories
>
> Compared to **ARM Templates** (Azure-only, verbose JSON), **CloudFormation** (AWS-only), or **Pulumi** (code-based, less team adoption), Terraform hits the sweet spot of multi-cloud support, readability, and community adoption.

---

### 🔹 Q7: Explain the Terraform workflow. What happens when you run `terraform apply`?

> **Best Answer:**
>
> The Terraform workflow has four main stages:
>
> 1. **`terraform init`** — Initializes the working directory, downloads provider plugins (e.g., `azurerm`, `google`, `aws`), and configures the backend for state storage (e.g., Azure Storage Account, S3 bucket)
>
> 2. **`terraform plan`** — Reads the current state file, compares it with the desired state defined in `.tf` files, and generates an execution plan showing what will be created, modified, or destroyed. This is a dry run — nothing changes yet
>
> 3. **`terraform apply`** — Executes the plan. Terraform calls the cloud provider APIs in the correct dependency order (using its internal dependency graph) to create, update, or delete resources. After each resource is provisioned, Terraform updates the state file
>
> 4. **`terraform destroy`** — Tears down all resources managed by the configuration (used for cleanup)
>
> **Key concepts I always follow:**
> - **Remote state** — I store state in Azure Storage Account with state locking via blob lease to prevent concurrent modifications
> - **Workspaces or separate state files** — I use separate state files per environment (dev, staging, prod) to isolate blast radius
> - **Modules** — I create reusable modules for common patterns (VMs, AKS clusters, Key Vaults) so teams don't reinvent the wheel

---

### 🔹 Q8: What is Terraform state? What happens if the state file gets corrupted or lost?

> **Best Answer:**
>
> Terraform state (`terraform.tfstate`) is a JSON file that maps your Terraform configuration to real-world cloud resources. It stores resource IDs, metadata, and dependencies. Terraform uses this to determine what changes need to be made on the next `apply`.
>
> **If the state file is corrupted or lost:**
> - Terraform loses track of what it has already created — it may try to recreate resources that already exist, causing errors or duplicates
> - **Recovery options:**
>   1. **Restore from backup** — If using remote state (e.g., Azure Storage with versioning enabled), restore a previous version
>   2. **`terraform import`** — Manually import existing resources back into a new state file, one by one
>   3. **Prevent it in the first place** — Always use remote state with versioning and state locking
>
> **Best practices I follow:**
> - Store state in **Azure Storage Account** with soft delete and versioning enabled
> - Enable **state locking** to prevent concurrent writes
> - Never store state in Git — it may contain secrets
> - Use **`terraform state` commands** (`mv`, `rm`, `list`) carefully and always back up before manual state manipulation

---

### 🔹 Q9: What is the difference between Terraform and Ansible? When would you use each?

> **Best Answer:**
>
> | Feature | Terraform | Ansible |
> |---|---|---|
> | **Purpose** | Infrastructure provisioning (create VMs, networks, databases) | Configuration management (install software, configure OS) |
> | **Approach** | Declarative — you define the desired end state | Procedural — you define step-by-step tasks (though it can be declarative) |
> | **State** | Maintains a state file | Stateless — runs tasks each time |
> | **Idempotency** | Built-in through state comparison | Achieved through module design |
> | **Agent** | Agentless — uses cloud APIs | Agentless — uses SSH/WinRM |
> | **Best for** | Creating cloud resources | Configuring servers after creation |
>
> **In my workflow, I use both together:**
> - **Terraform** provisions the infrastructure — VMs, VNets, Key Vaults, AKS clusters
> - **Ansible** configures what's inside — installing packages, configuring IIS/Apache, deploying application configurations
>
> They complement each other perfectly. Terraform answers "What infrastructure exists?" and Ansible answers "How is that infrastructure configured?"

---

### 🔹 Q10: What Azure services have you worked with? Explain Application Gateway.

> **Best Answer:**
>
> I've worked extensively with:
> - **Azure Virtual Machines** — compute for hosting IIS/Apache sites
> - **Azure Application Gateway** — Layer 7 load balancer with WAF
> - **Azure Key Vault** — secrets, certificates, and key management
> - **Azure MySQL** — managed relational database
> - **Azure VNets, NSGs, Subnets** — networking and security
> - **Azure Monitor & Alerts** — native monitoring and alerting
> - **Azure Storage Accounts** — for Terraform state, file storage
> - **Azure DevOps** — repos, pipelines, boards, artifacts
>
> **Application Gateway** is a Layer 7 (HTTP/HTTPS) load balancer that provides:
> - **URL-based routing** — route `/api/*` to backend pool A, `/web/*` to backend pool B
> - **SSL termination** — offload SSL decryption from backend servers
> - **Web Application Firewall (WAF)** — protects against common attacks (SQL injection, XSS)
> - **Session affinity** — cookie-based session stickiness
> - **Health probes** — monitors backend health and removes unhealthy instances
>
> In my current role, I manage Application Gateways via Terraform to handle traffic routing and SSL termination for our IIS and Apache sites.

---

### 🔹 Q11: What is Azure Key Vault and how do you use it?

> **Best Answer:**
>
> Azure Key Vault is a managed service for securely storing and managing:
> - **Secrets** — API keys, connection strings, passwords
> - **Certificates** — SSL/TLS certificates with auto-renewal
> - **Encryption Keys** — for data encryption at rest
>
> **How I use it:**
> - **Terraform integration** — I reference Key Vault secrets in Terraform using `azurerm_key_vault_secret` data sources, so sensitive values never appear in code
> - **CI/CD pipelines** — Jenkins and Azure DevOps pull secrets from Key Vault at runtime instead of storing them in pipeline variables
> - **SSL management** — I store SSL certificates in Key Vault and configure Application Gateway to pull certificates directly from it
> - **Access policies** — I configure RBAC and access policies so only specific service principals and managed identities can read secrets
>
> The key principle is: **secrets should never live in code, config files, or pipeline variables — they should always come from a vault at runtime.**

---

### 🔹 Q12: Explain Terraform modules. How do you structure your Terraform code?

> **Best Answer:**
>
> A Terraform module is a reusable, self-contained package of Terraform configurations that encapsulates a set of resources. Think of it like a function in programming.
>
> **My typical project structure:**
> ```
> terraform/
> ├── environments/
> │   ├── dev/
> │   │   ├── main.tf          # Calls modules with dev-specific values
> │   │   ├── variables.tf
> │   │   ├── terraform.tfvars
> │   │   └── backend.tf       # Dev state backend
> │   ├── staging/
> │   └── prod/
> ├── modules/
> │   ├── vm/
> │   │   ├── main.tf
> │   │   ├── variables.tf
> │   │   └── outputs.tf
> │   ├── aks/
> │   ├── keyvault/
> │   ├── app-gateway/
> │   └── networking/
> └── README.md
> ```
>
> **Key principles:**
> - Each module has its own `main.tf`, `variables.tf`, and `outputs.tf`
> - Environment-specific values are passed via `terraform.tfvars`
> - Modules are versioned (via Git tags) when shared across teams
> - State is stored remotely with separate state files per environment

---

## 🔄 CI/CD & Automation

> [!NOTE]
> **⏱️ This section covers ~20-25 minutes of the interview.** Expect questions comparing Jenkins vs Azure DevOps, pipeline design, and GitOps.

---

### 🔹 Q13: Compare Jenkins and Azure DevOps Pipelines. When would you use each?

> **Best Answer:**
>
> | Feature | Jenkins | Azure DevOps Pipelines |
> |---|---|---|
> | **Type** | Self-hosted, open-source | Cloud-hosted SaaS (Microsoft) |
> | **Pipeline as Code** | Jenkinsfile (Groovy) | YAML-based pipelines |
> | **Plugins** | 1800+ plugins (massive ecosystem) | Built-in tasks + marketplace extensions |
> | **Scalability** | Requires managing agents/nodes yourself | Microsoft-hosted agents auto-scale |
> | **Integration** | Integrates with everything | Deep Azure/GitHub integration |
> | **Cost** | Free (but you pay for infrastructure) | Free tier + pay per parallel job |
>
> **My experience:**
> - **At Infosys (Haleon)** — I use **Jenkins** because the client's infrastructure is self-hosted, and Jenkins gives us full control over build agents and plugins. Our code lives in GitHub, and Jenkins triggers builds via webhooks.
> - **At Accenture** — I used **Azure DevOps** because everything was in the Microsoft ecosystem — Azure Repos, Azure Pipelines, Azure Boards, and Artifactory. The tight integration made it the natural choice.
>
> **My recommendation:** If you're deep in the Azure ecosystem, use Azure DevOps. If you need maximum flexibility and plugin support across diverse tech stacks, Jenkins is the better choice.

---

### 🔹 Q14: Design a CI/CD pipeline for a web application. Walk me through it.

> **Best Answer:**
>
> Here's how I'd design a production-grade CI/CD pipeline:
>
> ```
> Developer Push → GitHub → Webhook → Jenkins
>
> ┌─── CI (Continuous Integration) ──────────────────┐
> │  1. Checkout code from GitHub                     │
> │  2. Install dependencies                          │
> │  3. Run unit tests                                │
> │  4. Run SAST scan (SonarQube)                     │
> │  5. Build application artifact                    │
> │  6. Build Docker image                            │
> │  7. Push image to container registry (ACR/ECR)    │
> │  8. Run container vulnerability scan (Trivy)      │
> └──────────────────────────────────────────────────┘
>
> ┌─── CD (Continuous Delivery) ─────────────────────┐
> │  9.  Deploy to Dev environment (auto)             │
> │ 10.  Run integration/smoke tests                  │
> │ 11.  Deploy to Staging (auto after tests pass)    │
> │ 12.  Run automated E2E tests (Playwright)         │
> │ 13.  Manual approval gate for Production          │
> │ 14.  Deploy to Production (blue-green/canary)     │
> │ 15.  Post-deployment health checks                │
> │ 16.  Notify team via Slack/Teams                   │
> └──────────────────────────────────────────────────┘
> ```
>
> **Key design decisions:**
> - **Security scanning** is built into the pipeline, not bolted on after
> - **Automated tests** gate each environment promotion
> - **Manual approval** before production ensures human oversight
> - **Blue-green or canary deployment** minimizes production risk
> - **Health checks** after deployment catch issues early

---

### 🔹 Q15: What is GitOps? How does ArgoCD work?

> **Best Answer:**
>
> **GitOps** is a practice where Git is the single source of truth for both application code AND infrastructure/deployment configuration. Instead of running `kubectl apply` manually, you commit your desired state to Git, and an automated tool syncs it to the cluster.
>
> **ArgoCD** is a Kubernetes-native GitOps tool that:
> 1. **Watches** a Git repository containing Kubernetes manifests (YAML, Helm charts, or Kustomize)
> 2. **Compares** the desired state (in Git) with the actual state (in the cluster)
> 3. **Syncs** automatically or manually to bring the cluster in line with Git
> 4. **Self-heals** — if someone manually changes a resource in the cluster, ArgoCD reverts it to match Git
>
> **How I used it:**
> At Haleon, I migrated services to containerized microservices on AKS with GitOps via ArgoCD. The workflow was:
> - Developers merge code → CI pipeline builds and pushes Docker image → Updates image tag in the GitOps repo → ArgoCD detects the change → Syncs the new image to AKS → Automated rollback if health checks fail
>
> The biggest benefit: **no one has direct `kubectl` access to production. All changes go through Git, which gives us a full audit trail.**

---

### 🔹 Q16: What is the difference between Continuous Delivery and Continuous Deployment?

> **Best Answer:**
>
> - **Continuous Delivery** — Every code change is automatically built, tested, and *ready* to be deployed to production, but the actual deployment requires a **manual approval**. The code is always in a deployable state.
>
> - **Continuous Deployment** — Every code change that passes all automated tests is **automatically deployed** to production without any manual intervention.
>
> **In practice:** Most enterprise environments (including mine at Haleon and Accenture) use **Continuous Delivery** with a manual approval gate before production. This gives us the speed of automation with the safety net of human review for production deployments.

---

### 🔹 Q17: What is Artifactory and why is it important?

> **Best Answer:**
>
> JFrog Artifactory is a **universal artifact repository manager** that stores build artifacts — Docker images, npm packages, Maven JARs, NuGet packages, Python wheels, and more.
>
> **Why it's important:**
> - **Single source of truth** for all build artifacts — instead of scattering artifacts across different registries
> - **Dependency caching** — proxies and caches packages from public registries (npm, PyPI, Maven Central), speeding up builds and providing offline availability
> - **Security scanning** — integrates with Xray to scan artifacts for vulnerabilities
> - **Immutable artifacts** — ensures that a specific version of an artifact is never overwritten
>
> **At Accenture**, we used Artifactory alongside Azure DevOps Pipelines to store our build artifacts and Docker images. Every pipeline published artifacts to Artifactory, and downstream deployment pipelines pulled from there. This ensured that what we tested is exactly what we deployed.

---

## 🐳 Docker & Containerization

> [!NOTE]
> **⏱️ This section covers ~15-20 minutes.** Expect questions on Dockerfile best practices, multi-stage builds, and troubleshooting.

---

### 🔹 Q18: What is Docker? Explain the difference between a Docker image and a container.

> **Best Answer:**
>
> **Docker** is a platform for packaging, distributing, and running applications in isolated environments called containers.
>
> | Concept | Definition | Analogy |
> |---|---|---|
> | **Docker Image** | A read-only template containing the application code, runtime, libraries, and OS dependencies | Like a **class** in programming |
> | **Docker Container** | A running instance of an image — isolated, lightweight, and ephemeral | Like an **object** (instance of the class) |
>
> - An **image** is built from a `Dockerfile` and stored in a registry (Docker Hub, ACR, ECR)
> - A **container** is created from an image using `docker run` — it gets its own filesystem, network, and process space
> - Multiple containers can be created from the same image
> - Containers are **ephemeral** — when they stop, any data not in a volume is lost

---

### 🔹 Q19: Write and explain a production-grade Dockerfile.

> **Best Answer:**
>
> ```dockerfile
> # Stage 1: Build
> FROM node:18-alpine AS builder
> WORKDIR /app
> COPY package*.json ./
> RUN npm ci --only=production
> COPY . .
> RUN npm run build
>
> # Stage 2: Production
> FROM node:18-alpine
> RUN addgroup -S appgroup && adduser -S appuser -G appgroup
> WORKDIR /app
> COPY --from=builder /app/dist ./dist
> COPY --from=builder /app/node_modules ./node_modules
> USER appuser
> EXPOSE 3000
> HEALTHCHECK --interval=30s --timeout=3s CMD wget -qO- http://localhost:3000/health || exit 1
> CMD ["node", "dist/server.js"]
> ```
>
> **Key best practices demonstrated:**
> 1. **Multi-stage build** — Build stage installs dev dependencies and compiles; production stage only contains the compiled output. This reduces image size dramatically.
> 2. **Alpine base image** — Smaller image size (~5MB vs ~900MB for full OS)
> 3. **`npm ci`** — Deterministic installs from `package-lock.json` (not `npm install`)
> 4. **Non-root user** — Never run containers as root in production
> 5. **HEALTHCHECK** — Enables orchestrators (Kubernetes, Docker Swarm) to know if the app is healthy
> 6. **`.dockerignore`** — Always pair with a `.dockerignore` file to exclude `node_modules`, `.git`, etc.

---

### 🔹 Q20: What is the difference between `CMD` and `ENTRYPOINT` in a Dockerfile?

> **Best Answer:**
>
> | Feature | `CMD` | `ENTRYPOINT` |
> |---|---|---|
> | **Purpose** | Default command to run | Fixed executable for the container |
> | **Override** | Easily overridden by `docker run <args>` | Requires `--entrypoint` flag to override |
> | **Use case** | Default arguments that users may want to change | When the container should always run a specific binary |
>
> **Example:**
> ```dockerfile
> ENTRYPOINT ["python"]
> CMD ["app.py"]
> ```
> - `docker run myimage` → runs `python app.py`
> - `docker run myimage script.py` → runs `python script.py` (CMD overridden, ENTRYPOINT stays)
>
> **My rule of thumb:** Use `ENTRYPOINT` when the container is a specific tool (e.g., a Python script runner). Use `CMD` when you want flexible defaults.

---

### 🔹 Q21: How do you reduce Docker image size?

> **Best Answer:**
>
> 1. **Use multi-stage builds** — Build in one stage, copy only artifacts to the final stage
> 2. **Use Alpine or distroless base images** — Alpine is ~5MB vs Ubuntu's ~72MB
> 3. **Minimize layers** — Combine RUN commands with `&&` to reduce layers
> 4. **Use `.dockerignore`** — Exclude `.git`, `node_modules`, test files, documentation
> 5. **Don't install unnecessary packages** — Use `--no-install-recommends` with apt
> 6. **Clean up in the same layer** — `RUN apt-get install -y curl && apt-get clean && rm -rf /var/lib/apt/lists/*`
> 7. **Order layers by change frequency** — Put rarely changing layers (OS, dependencies) first for better caching

---

## ☸️ Kubernetes & Orchestration

> [!NOTE]
> **⏱️ This section covers ~20-25 minutes.** This is typically the heaviest section in a DevOps interview. Expect architecture, troubleshooting, and scenario questions.

---

### 🔹 Q22: Explain Kubernetes architecture. What are the main components?

> **Best Answer:**
>
> Kubernetes has two main planes:
>
> **Control Plane (Master):**
> | Component | Role |
> |---|---|
> | **kube-apiserver** | Front door to the cluster. All `kubectl` commands, CI/CD tools, and internal components talk to this |
> | **etcd** | Distributed key-value store that holds all cluster state and configuration |
> | **kube-scheduler** | Decides which node a new Pod should run on based on resource requirements and constraints |
> | **kube-controller-manager** | Runs controllers (ReplicaSet, Deployment, Node controllers) that maintain desired state |
> | **cloud-controller-manager** | Integrates with cloud APIs (Azure, AWS) for load balancers, storage, etc. |
>
> **Data Plane (Worker Nodes):**
> | Component | Role |
> |---|---|
> | **kubelet** | Agent on each node that ensures containers are running as specified by Pods |
> | **kube-proxy** | Manages network rules and service routing on each node |
> | **Container Runtime** | Runs containers (containerd, CRI-O) |
>
> **In my experience with AKS:** Azure manages the entire control plane for me. I focus on managing worker node pools, deploying workloads, configuring Ingress, and monitoring via Datadog.

---

### 🔹 Q23: What is the difference between a Deployment, StatefulSet, and DaemonSet?

> **Best Answer:**
>
> | Resource | Use Case | Key Feature |
> |---|---|---|
> | **Deployment** | Stateless applications (web servers, APIs) | Manages ReplicaSets; supports rolling updates and rollbacks |
> | **StatefulSet** | Stateful applications (databases, message queues) | Stable network identity, persistent storage, ordered startup/shutdown |
> | **DaemonSet** | Agents that must run on every node (monitoring, logging) | Ensures exactly one Pod runs on each node |
>
> **Real examples from my work:**
> - **Deployment** — Our web application containers running on AKS
> - **StatefulSet** — Would be used for something like a Redis cluster or Kafka brokers
> - **DaemonSet** — Datadog Agent runs as a DaemonSet on every node to collect metrics and logs

---

### 🔹 Q24: A Pod is stuck in CrashLoopBackOff. How do you troubleshoot it?

> **Best Answer:**
>
> `CrashLoopBackOff` means the container starts, crashes, and Kubernetes keeps restarting it with exponential backoff delays.
>
> **My troubleshooting steps:**
>
> ```bash
> # Step 1: Check Pod status and events
> kubectl describe pod <pod-name> -n <namespace>
> # Look at: Events section, Exit Code, Restart Count
>
> # Step 2: Check container logs
> kubectl logs <pod-name> -n <namespace>
> # For previous crashed instance:
> kubectl logs <pod-name> -n <namespace> --previous
>
> # Step 3: Check resource limits
> kubectl top pod <pod-name> -n <namespace>
> # Is it running out of memory (OOMKilled)?
>
> # Step 4: If logs aren't helpful, exec into a running instance
> kubectl exec -it <pod-name> -n <namespace> -- /bin/sh
>
> # Step 5: Check if ConfigMaps/Secrets are mounted correctly
> kubectl get configmap <name> -n <namespace> -o yaml
> ```
>
> **Common causes:**
> 1. **Application error** — bad config, missing env vars, wrong database connection string
> 2. **OOMKilled** — memory limit too low; container exceeds it and gets killed
> 3. **Missing dependencies** — can't reach a database, API, or service it depends on
> 4. **Wrong command** — `CMD` or `ENTRYPOINT` in the Dockerfile is incorrect
> 5. **Failed health checks** — liveness probe fails repeatedly

---

### 🔹 Q25: What is Helm? How do you use it?

> **Best Answer:**
>
> **Helm** is a package manager for Kubernetes — like `apt` for Ubuntu or `npm` for Node.js. It bundles Kubernetes manifests into reusable **charts** with templating support.
>
> **Key concepts:**
> - **Chart** — A package of templated Kubernetes YAML files
> - **Values** — A `values.yaml` file that provides environment-specific configuration
> - **Release** — A deployed instance of a chart (you can have multiple releases of the same chart)
>
> **How I use it:**
> ```bash
> # Install a chart
> helm install my-app ./my-chart -f values-prod.yaml -n production
>
> # Upgrade with new values
> helm upgrade my-app ./my-chart -f values-prod.yaml -n production
>
> # Rollback to previous version
> helm rollback my-app 1 -n production
>
> # List all releases
> helm list -n production
> ```
>
> **Benefits:**
> - **Templating** — One chart, multiple environments (dev, staging, prod) with different `values.yaml`
> - **Version control** — Each deployment is a versioned release; easy rollbacks
> - **Dependency management** — Charts can depend on other charts (e.g., your app chart depends on a Redis chart)

---

### 🔹 Q26: What is an Ingress Controller? How is it different from a Service?

> **Best Answer:**
>
> | Feature | Service | Ingress |
> |---|---|---|
> | **Layer** | Layer 4 (TCP/UDP) | Layer 7 (HTTP/HTTPS) |
> | **Routing** | IP:Port based | Host/path-based routing |
> | **SSL** | No SSL termination | Supports SSL termination |
> | **External Access** | LoadBalancer type exposes a single service | Single entry point routes to multiple services |
>
> **Ingress** is an API object that manages external HTTP/HTTPS access to services in a cluster. An **Ingress Controller** (like NGINX Ingress Controller or Azure Application Gateway Ingress Controller) is the actual component that implements the routing rules.
>
> **Example:**
> ```yaml
> apiVersion: networking.k8s.io/v1
> kind: Ingress
> metadata:
>   name: my-ingress
> spec:
>   rules:
>   - host: app.example.com
>     http:
>       paths:
>       - path: /api
>         pathType: Prefix
>         backend:
>           service:
>             name: api-service
>             port:
>               number: 80
>       - path: /
>         pathType: Prefix
>         backend:
>           service:
>             name: frontend-service
>             port:
>               number: 80
> ```
>
> This routes `app.example.com/api/*` to the API service and `app.example.com/*` to the frontend — through a single load balancer IP.

---

## 📊 Monitoring & Observability

> [!NOTE]
> **⏱️ This section covers ~10-15 minutes.** Your Datadog and OpsRamp experience is a strong differentiator.

---

### 🔹 Q27: What is observability? How is it different from monitoring?

> **Best Answer:**
>
> | Concept | Definition |
> |---|---|
> | **Monitoring** | Watching predefined metrics and alerting when thresholds are breached (e.g., CPU > 90%) |
> | **Observability** | The ability to understand the *internal state* of a system by examining its *external outputs* — logs, metrics, and traces |
>
> **The three pillars of observability:**
> 1. **Metrics** — Numerical measurements over time (CPU, memory, request rate, error rate)
> 2. **Logs** — Timestamped records of events (application logs, system logs)
> 3. **Traces** — End-to-end request flows across microservices (distributed tracing)
>
> **Monitoring tells you *something is wrong*. Observability helps you understand *why* it's wrong.**
>
> In my current role, I use **Datadog** for metrics and dashboards, **OpsRamp** for server-level monitoring, and **Azure native alerts** for cloud resource monitoring. Together, they give us full observability across our infrastructure.

---

### 🔹 Q28: How do you set up Datadog monitoring? What do you monitor?

> **Best Answer:**
>
> **Setup:**
> 1. Install the **Datadog Agent** on every server (or as a DaemonSet in Kubernetes)
> 2. Configure integrations — IIS, Apache, MySQL, Azure services
> 3. Set up **custom dashboards** for each application and environment
> 4. Create **monitors and alerts** with escalation policies
>
> **What I monitor at Haleon:**
>
> | Category | Metrics |
> |---|---|
> | **Server Health** | CPU utilization, memory usage, disk I/O, disk space |
> | **IIS/Apache** | Request rate, response time, HTTP error codes (4xx, 5xx), active connections |
> | **Application** | Custom application metrics, error rates, latency percentiles (p50, p95, p99) |
> | **SSL Certificates** | Expiration dates — alert 30 days before expiry |
> | **Azure Resources** | VM availability, Application Gateway health, Key Vault access |
>
> **Alerting strategy:**
> - **Warning** → Slack/Teams notification (e.g., CPU > 80% for 5 minutes)
> - **Critical** → PagerDuty/phone alert (e.g., site down, disk > 95%)
> - **Recovery** → Automatic notification when the issue resolves

---

### 🔹 Q29: What is MTTD and MTTR? How do you reduce them?

> **Best Answer:**
>
> - **MTTD (Mean Time to Detect)** — Average time between when an issue occurs and when it is detected
> - **MTTR (Mean Time to Resolve/Recover)** — Average time between detection and resolution
>
> **How I reduce MTTD:**
> - Comprehensive monitoring coverage — no blind spots
> - Proactive alerting with proper thresholds (not too noisy, not too silent)
> - Anomaly detection in Datadog that catches unusual patterns
> - Synthetic monitoring that simulates user traffic to detect issues before real users are affected
>
> **How I reduce MTTR:**
> - **Runbooks** — Documented step-by-step guides for common incidents (I created these at Accenture)
> - **Centralized dashboards** — One place to see all relevant metrics during an incident
> - **Automated remediation** — Self-healing scripts that trigger on specific alerts (e.g., restart a crashed IIS app pool automatically)
> - **Clear escalation paths** — Defined in our alerting policies so the right person gets paged immediately

---

## 🔒 DevSecOps & Security

> [!NOTE]
> **⏱️ This section covers ~10-15 minutes.** Your AZ-500 certification and IAM experience at Accenture make this a strong area for you.

---

### 🔹 Q30: What is DevSecOps? How do you implement it?

> **Best Answer:**
>
> **DevSecOps** is the practice of integrating security at every stage of the DevOps lifecycle — not as a separate gate at the end, but as a continuous, automated part of the pipeline.
>
> **How I implement it:**
>
> | Stage | Security Practice | Tool |
> |---|---|---|
> | **Code** | Static Application Security Testing (SAST) | SonarQube |
> | **Dependencies** | Dependency vulnerability scanning | Snyk, npm audit |
> | **Build** | Container image scanning | Trivy, Aqua |
> | **Secrets** | Secret management (never in code) | Azure Key Vault, HashiCorp Vault |
> | **Deploy** | RBAC, network policies, least privilege | Kubernetes RBAC, Azure AD |
> | **Runtime** | Dynamic Application Security Testing (DAST) | OWASP ZAP |
> | **Monitor** | Security incident alerting | Datadog Security Monitoring |
>
> **Key principle:** "Shift left" — find and fix security issues as early as possible in the pipeline, where they are cheapest and fastest to fix. A vulnerability caught in code review is infinitely cheaper than one found in production.

---

### 🔹 Q31: How do you manage SSL certificates at scale?

> **Best Answer:**
>
> At Haleon, I manage SSL certificates across numerous IIS and Apache sites. Here's my approach:
>
> 1. **Centralized storage** — All certificates are stored in **Azure Key Vault** with proper access policies
> 2. **Automated generation** — I built PowerShell scripts that generate CSRs, submit them to our internal CA, and install the issued certificates
> 3. **Automated renewal** — Scripts check certificate expiration dates and trigger renewal workflows 30 days before expiry
> 4. **Monitoring** — Datadog monitors check certificate expiration across all sites and alert the team if any certificate is within 30 days of expiry
> 5. **Binding** — After certificate installation, the script automatically binds the certificate to the correct IIS site or updates the Apache SSL configuration
>
> This end-to-end automation eliminated the risk of expired certificates causing outages — which is one of the most common and most embarrassing types of production incidents.

---

### 🔹 Q32: What is the difference between SAST and DAST?

> **Best Answer:**
>
> | Feature | SAST (Static) | DAST (Dynamic) |
> |---|---|---|
> | **When** | During development / code commit | After deployment (running application) |
> | **How** | Analyzes source code without executing it | Tests the running application from the outside |
> | **Finds** | Code-level vulnerabilities (SQL injection patterns, hardcoded secrets, buffer overflows) | Runtime vulnerabilities (authentication flaws, XSS, misconfigured headers) |
> | **Speed** | Fast — runs during CI | Slower — needs a running environment |
> | **False Positives** | Higher | Lower (tests real behavior) |
> | **Tool Example** | SonarQube | OWASP ZAP |
>
> **Best practice:** Use **both**. SAST catches issues early in the pipeline (shift left), and DAST validates the deployed application's security posture.

---

## 🌐 Networking & DNS

> [!NOTE]
> **⏱️ This section covers ~5-10 minutes.** Your GCP DNS and Azure networking experience is relevant here.

---

### 🔹 Q33: Explain DNS. Why do you still use GCP for DNS at Haleon?

> **Best Answer:**
>
> **DNS (Domain Name System)** translates human-readable domain names (e.g., `app.haleon.com`) into IP addresses that computers use to route traffic.
>
> **Key record types:**
> | Record | Purpose | Example |
> |---|---|---|
> | **A** | Maps domain to IPv4 address | `app.haleon.com → 20.30.40.50` |
> | **CNAME** | Alias for another domain | `www.haleon.com → app.haleon.com` |
> | **MX** | Mail server routing | `haleon.com → mail.haleon.com` |
> | **TXT** | Verification, SPF, DKIM | Used for domain ownership verification |
> | **NS** | Nameserver delegation | Points to authoritative DNS servers |
>
> **Why GCP for DNS?**
> When we migrated core services to Azure, we evaluated migrating DNS to Azure DNS as well. However, we decided to keep it on **GCP Cloud DNS** because:
> 1. It was already well-configured with all existing records, TTLs, and routing policies
> 2. GCP Cloud DNS has a 100% SLA — one of the highest in the industry
> 3. Migrating DNS carries risk — a misconfiguration could take down all services
> 4. Having DNS on a separate cloud provider from our primary infrastructure actually provides an extra layer of resilience

---

### 🔹 Q34: What is a reverse proxy? How does NGINX work as one?

> **Best Answer:**
>
> A **reverse proxy** sits in front of backend servers and forwards client requests to them. Clients only communicate with the proxy, never directly with the backend.
>
> **Benefits:**
> - **Load balancing** — distributes traffic across multiple backend servers
> - **SSL termination** — handles HTTPS decryption, reducing load on backends
> - **Caching** — caches static content to reduce backend load
> - **Security** — hides backend server details from clients
>
> **In my work:** I manage Apache servers that function as reverse proxies in front of our application servers. The Application Gateway in Azure also acts as a reverse proxy for our IIS-hosted sites, handling SSL termination and URL-based routing.

---

## 🧠 Scenario-Based Questions

> [!WARNING]
> **⏱️ This section covers ~15-20 minutes.** These are the "hard" questions where interviewers test your real-world problem-solving skills. Answer using the **STAR method** (Situation, Task, Action, Result).

---

### 🔹 Q35: Your production website is down. Walk me through your incident response.

> **Best Answer:**
>
> **Step 1: Acknowledge & Communicate** (First 2 minutes)
> - Acknowledge the alert in our monitoring tool (Datadog/OpsRamp)
> - Notify the team via Jira incident ticket and Teams/Slack
> - Start an incident bridge call if it's a high-severity issue
>
> **Step 2: Triage & Identify** (Next 5-10 minutes)
> - Check Datadog dashboards — is it a single server or all servers?
> - Check server health — CPU, memory, disk space
> - Check IIS/Apache logs — are there 5xx errors? Connection timeouts?
> - Check recent deployments — did we deploy anything in the last few hours?
> - Check SSL certificates — is a certificate expired?
> - Check Application Gateway health probes — are backends marked unhealthy?
> - Check DNS — is the domain resolving correctly?
>
> **Step 3: Mitigate** (Next 5-15 minutes)
> - If it's a bad deployment → **rollback** to the last known good version
> - If it's a crashed IIS app pool → **restart** the application pool
> - If it's a resource issue → **scale** the VM or add capacity
> - If it's an SSL issue → **install** a valid certificate
>
> **Step 4: Resolve & Document**
> - Confirm the site is back up via health checks and synthetic monitoring
> - Update the Jira incident ticket with timeline and resolution
> - Conduct a **blameless post-mortem** within 48 hours
> - Implement preventive measures (better monitoring, automated remediation)

---

### 🔹 Q36: You need to deploy a critical hotfix to production in 30 minutes. How do you do it?

> **Best Answer:**
>
> 1. **Create a hotfix branch** from the production branch in GitHub
> 2. **Apply the fix** and get a quick code review (even a verbal approval from a senior engineer)
> 3. **Push to GitHub** → Jenkins CI pipeline automatically triggers
> 4. **Fast-track testing** — run only the critical unit tests and smoke tests (skip full regression)
> 5. **Deploy to a staging server** first and verify the fix works
> 6. **Get emergency approval** — notify the team lead and get verbal/Jira approval to deploy to production
> 7. **Deploy to production** using our standard Jenkins CD pipeline
> 8. **Monitor closely** — watch Datadog dashboards for the next 30 minutes for any regression
> 9. **Document** — create a follow-up Jira ticket for proper testing and any technical debt
>
> **Key principle:** Speed is important, but never skip the staging validation step. Deploying an untested fix to production can make the situation worse.

---

### 🔹 Q37: A Terraform apply fails halfway through. Some resources were created, some weren't. What do you do?

> **Best Answer:**
>
> This is a common situation and one of the reasons Terraform's state management is so important.
>
> **What happens:** Terraform records successfully created resources in the state file, even if the overall apply fails. Resources that failed to create are NOT in the state.
>
> **My approach:**
> 1. **Don't panic** — Read the error message carefully. Common causes: permission issues, quota limits, naming conflicts, API rate limits
> 2. **Fix the root cause** — Update the Terraform code or fix the underlying issue (e.g., increase quota, fix permissions)
> 3. **Run `terraform plan`** — Terraform will show that already-created resources exist (no changes) and only the failed resources need to be created
> 4. **Run `terraform apply` again** — Terraform is idempotent; it will skip already-created resources and only create the remaining ones
> 5. **If state is inconsistent** — Use `terraform state list` and `terraform state show` to inspect, and `terraform import` if needed
>
> **Prevention:** Use `-target` flag for risky changes to limit the blast radius, and always run `terraform plan` before `apply`.

---

### 🔹 Q38: Your team wants to migrate from VMs to Kubernetes. How would you plan this?

> **Best Answer:**
>
> I'd approach this in phases:
>
> **Phase 1: Assessment (2-4 weeks)**
> - Inventory all applications running on VMs
> - Classify each app: stateless (easy to containerize) vs stateful (needs careful planning)
> - Identify dependencies — databases, file storage, inter-service communication
> - Estimate resource requirements (CPU, memory) for right-sizing containers
>
> **Phase 2: Foundation (2-4 weeks)**
> - Set up AKS cluster using Terraform (node pools, networking, RBAC)
> - Set up container registry (ACR)
> - Configure Ingress controller, DNS, SSL/TLS
> - Set up monitoring (Datadog DaemonSet) and logging
> - Establish GitOps workflow (ArgoCD)
>
> **Phase 3: Pilot Migration (2-4 weeks)**
> - Pick 1-2 non-critical, stateless applications
> - Write Dockerfiles, Kubernetes manifests, Helm charts
> - Deploy to AKS, validate functionality, performance, and monitoring
> - Document lessons learned and create templates for the team
>
> **Phase 4: Incremental Migration (ongoing)**
> - Migrate remaining applications one by one, starting with least critical
> - Run VMs and Kubernetes in parallel during transition
> - Gradually shift traffic using DNS or load balancer weight shifting
> - Decommission VMs only after full validation
>
> **Key principle:** Never do a "big bang" migration. Incremental, parallel migrations with easy rollback paths are the safest approach.

---

## 💼 Behavioral & Situational Questions

> [!TIP]
> **⏱️ This section covers ~10-15 minutes.** Use the **STAR method**: Situation → Task → Action → Result.

---

### 🔹 Q39: Why DevOps? What motivated your transition from development?

> **Best Answer:**
>
> I started as a full-stack developer building applications with Angular and .NET Core. While I enjoyed building features, I was constantly frustrated by the deployment process — it was slow, manual, and error-prone. I would spend days writing code, only to watch it sit in a deployment queue for weeks.
>
> That frustration led me to explore automation, CI/CD, and infrastructure. I realized that the real bottleneck wasn't in writing code — it was in getting code to production safely and quickly. DevOps was the perfect fit for me because it combines my development background with my passion for automation and system reliability.
>
> My developer experience is actually my biggest advantage as a DevOps engineer — I understand what developers need, I can read and debug application code, and I build tools that genuinely improve developer productivity.

---

### 🔹 Q40: Tell me about a time you automated something that saved significant time.

> **Best Answer (STAR Method):**
>
> **Situation:** At Infosys (Haleon), every time a new web application needed to be hosted, an engineer had to manually RDP into a server, create the IIS site, configure the application pool, generate an SSL certificate, and bind it. This process took approximately 45-60 minutes per site and was error-prone.
>
> **Task:** I was tasked with reducing this manual effort and standardizing the process.
>
> **Action:** I built a suite of PowerShell scripts that automated the entire process — from creating the IIS site and application pool to generating the SSL certificate and binding it. I then integrated these scripts into a parameterized Jenkins job so that anyone on the team could trigger a new site setup by simply filling in parameters and clicking "Build."
>
> **Result:** Site provisioning time dropped from ~60 minutes of manual work to ~5 minutes of automated execution. It also eliminated human errors in configuration, improved our security posture (every site got SSL by default), and freed up engineering time for higher-value work.

---

### 🔹 Q41: Describe a challenging production incident you resolved.

> **Best Answer (STAR Method):**
>
> **Situation:** One of our critical IIS-hosted web applications started returning intermittent 503 Service Unavailable errors during business hours. The issue wasn't consistent — some requests succeeded, others failed.
>
> **Task:** I needed to identify the root cause and restore full service as quickly as possible.
>
> **Action:**
> - First, I checked Datadog and noticed that the IIS application pool was recycling itself repeatedly
> - I dug into the Windows Event Logs and found that the app pool was crashing due to memory exhaustion — the application had a memory leak
> - As an immediate mitigation, I increased the memory limit for the app pool and configured a scheduled recycle during off-peak hours
> - I then worked with the development team to identify the memory leak in their code (an unclosed database connection in a high-traffic endpoint)
> - After the code fix was deployed, I set up a Datadog monitor specifically tracking application pool memory consumption with early warning thresholds
>
> **Result:** Service was fully restored within 30 minutes of detection. The long-term fix (code change) was deployed within 48 hours. The new monitoring rule has since caught similar patterns early, before they affect users.

---

### 🔹 Q42: Why are you looking for a change from Infosys?

> **Best Answer:**
>
> I've had a great experience at Infosys working on the Haleon account. I've grown significantly in infrastructure management, automation, and observability. However, I'm looking for an environment where I can:
>
> 1. **Work more deeply with Kubernetes at scale** — My current role is more VM and IIS-focused, and I want to work in a Kubernetes-native environment
> 2. **Take on more architectural ownership** — I want to be involved in platform design decisions, not just operations
> 3. **Work with modern cloud-native tools** — I'm passionate about GitOps, service mesh, and platform engineering, and I want a role where these are core to the work
>
> I'm not leaving because of any dissatisfaction — I'm leaving because I want to accelerate my growth and contribute at a higher level.

---

### 🔹 Q43: Where do you see yourself in 5 years?

> **Best Answer:**
>
> I see myself growing into a **Senior DevOps Engineer or Platform Engineering** role, where I'm not just maintaining infrastructure but **designing the entire developer platform** — the tools, pipelines, self-service systems, and golden paths that enable engineering teams to ship code faster and more securely.
>
> I'm also deeply interested in the **SRE (Site Reliability Engineering)** space — defining SLOs, error budgets, and building self-healing systems. Long term, I'd love to lead a platform or SRE team and mentor junior engineers.

---

### 🔹 Q44: What is your biggest strength and weakness?

> **Best Answer:**
>
> **Strength:** My ability to identify repetitive, manual processes and turn them into automated, reliable workflows. Whether it's IIS site provisioning, SSL management, or CI/CD pipelines — I instinctively look for automation opportunities. This mindset has consistently saved my teams hours of manual work every week.
>
> **Weakness:** I sometimes spend extra time perfecting an automation or script before shipping it. I've learned to balance this by shipping an "MVP automation" first, getting it into the team's hands, and then iterating on improvements based on real usage and feedback.

---

## ❓ Questions to Ask the Interviewer

> [!TIP]
> **Always ask 3-4 questions at the end.** This shows genuine interest and helps you evaluate if the company is the right fit.

---

### Strong Questions to Ask:

1. **"What does the current CI/CD pipeline look like, and what are the biggest pain points you're trying to solve?"**
   — Shows you're thinking about where you can add immediate value.

2. **"How does your team handle incident management and on-call rotations?"**
   — Shows you're serious about operational excellence.

3. **"What's the team's approach to Infrastructure as Code? Are you using Terraform, and is there a central module library?"**
   — Shows your depth in IaC best practices.

4. **"What does the tech stack look like — are you primarily on Kubernetes, VMs, or a mix? Any migration plans?"**
   — Helps you understand the technical environment.

5. **"How do you measure the success of the DevOps team? Is there a focus on metrics like deployment frequency, lead time, or MTTR?"**
   — Shows you understand DORA metrics and DevOps maturity.

6. **"What opportunities are there for professional development and certifications?"**
   — Shows you're growth-oriented (and you already have 8 certifications to prove it).

---

> [!IMPORTANT]
> ## 🎯 Final Interview Tips
>
> 1. **Practice out loud** — Read each answer aloud until the transitions feel natural
> 2. **Tailor the "Future" section** — Always change the last sentence of your intro to mention something specific about the company
> 3. **Use numbers** — "8 servers", "15-day sprints", "5+ years", "60 minutes to 5 minutes" — numbers make your answers memorable
> 4. **STAR method for behavioral questions** — Situation, Task, Action, Result
> 5. **Be honest** — If you don't know something, say "I haven't worked with that directly, but here's how I'd approach learning it"
> 6. **Show enthusiasm** — Smile, make eye contact, and let your passion for automation come through
> 7. **Bring examples** — Every technical answer should be backed by a real example from Haleon or Accenture
