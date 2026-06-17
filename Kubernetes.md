# ☸️ Kubernetes — Complete Mastery Guide
## Part 2 of 3 | From Absolute Beginner to Expert

> [!NOTE]
> 📘 **Series Navigation**
>
> 📕 [Part 1: Docker Guide](file:///C:/Users/Mojammil%20Husain/.gemini/antigravity/brain/810210d9-bd04-4967-a796-7552ae205906/part1_docker_guide.md)
> 📘 **You are here → Part 2: Kubernetes**
> 📗 [Part 3: Angular + Docker + K8s Project](file:///C:/Users/Mojammil%20Husain/.gemini/antigravity/brain/810210d9-bd04-4967-a796-7552ae205906/part3_angular_docker_k8s_project.md)

---

## 📚 What's Inside This Guide?

| # | Part | Topic | Level |
|---|------|-------|-------|
| ☸️ | **Part 1** | What is Kubernetes? Why K8s? | 🟢 Beginner |
| ☸️ | **Part 2** | Kubernetes Architecture | 🟢 Beginner |
| ☸️ | **Part 3** | Installing Kubernetes (Minikube) | 🟢 Beginner |
| ☸️ | **Part 4** | Kubectl — Essential Commands | 🟢 Beginner |
| ☸️ | **Part 5** | Pods — The Smallest Unit | 🟡 Intermediate |
| ☸️ | **Part 6** | Deployments & ReplicaSets | 🟡 Intermediate |
| ☸️ | **Part 7** | Services & Networking | 🟡 Intermediate |
| ☸️ | **Part 8** | ConfigMaps & Secrets | 🟡 Intermediate |
| ☸️ | **Part 9** | Persistent Volumes & Claims | 🟡 Intermediate |
| ☸️ | **Part 10** | Ingress Controller | 🔴 Advanced |
| ☸️ | **Part 11** | Helm — Package Manager | 🔴 Advanced |
| ☸️ | **Part 12** | Monitoring & Logging | 🔴 Advanced |
| ☸️ | **Part 13** | Best Practices | 🔴 Advanced |
| ☸️ | **Part 14** | StatefulSets, DaemonSets, Jobs | 🔴 Advanced |
| ☸️ | **Part 15** | Taints, Tolerations & Affinity | 🔴 Expert |
| ☸️ | **Part 16** | RBAC, Quotas, PDB, CRDs & Operators | 🔴 Expert |
| ☸️ | **Part 17** | Service Mesh, CI/CD, Strategies | 🔴 Expert |
| ☸️ | **Part 18** | Troubleshooting Guide | 🔴 Expert |
| ☸️ | **Part 19** | Interview Q&A (40 Questions) | 🎯 All Levels |
| 📋 | **Bonus** | Cheat Sheet + Learning Roadmap | ✅ All Levels |

---

# ☸️ PART 1 — What is Kubernetes? Why K8s?

> **🎯 Goal:** Understand why we need Kubernetes and what problems it solves.

---

### 🧩 Step 1: Understand the Problem

You've Dockerized your app. Great! But now you face new challenges:

```
🤔 "I have 50 containers running... how do I manage them all?"
🤔 "One container crashed at 3 AM... who restarts it?"
🤔 "My app is slow during peak hours... how to add more containers?"
🤔 "I need to update my app... can I do it without downtime?"
🤔 "My server is running out of memory... which server gets the next container?"
```

**Answer: Kubernetes handles ALL of this automatically! 🎉**

---

### 🧩 Step 2: The Restaurant Chain Analogy

> 🍔 You own a restaurant chain. Docker gives you the perfect recipe in a box (container). But now you have **100 boxes** across **10 restaurants**.
>
> - Who decides which restaurant gets which dish? → **Scheduler**
> - What if a dish goes bad? → **Self-healing**
> - Lunch rush! Need more dishes fast! → **Auto-scaling**
> - New recipe to roll out? → **Rolling updates**
>
> **Kubernetes is the OPERATIONS MANAGER** that handles all of this automatically! 👨‍💼

---

### 🧩 Step 3: What Kubernetes Does

| # | Capability | What It Does | Analogy |
|---|-----------|-------------|---------|
| 1 | 🚀 **Deployment** | Places containers on servers | Assigning staff to restaurants |
| 2 | 📈 **Scaling** | Adds/removes containers on demand | Hiring temp staff for rush |
| 3 | ❤️‍🩹 **Self-Healing** | Replaces crashed containers automatically | Calling a substitute when someone is sick |
| 4 | ⚖️ **Load Balancing** | Distributes traffic evenly | Splitting customers across counters |
| 5 | 🔄 **Rolling Updates** | Updates apps without downtime | Renovating while staying open |
| 6 | 🔍 **Service Discovery** | Containers find each other by name | Internal phone directory |
| 7 | 🔐 **Secret Management** | Stores passwords securely | Locked safe for keys |

---

### 🧩 Step 4: Docker Alone vs Docker + Kubernetes

```
╔═══════════════════════════╦════════════════════════════════════╗
║   🐳 Docker Alone          ║   🐳 Docker + ☸️ Kubernetes        ║
╠═══════════════════════════╬════════════════════════════════════╣
║  1 machine only            ║  Multi-machine cluster             ║
║  Manual container mgmt     ║  Automated orchestration           ║
║  No self-healing           ║  Auto-restarts crashed containers  ║
║  Manual scaling             ║  Auto-scaling based on load        ║
║  Downtime during updates   ║  Zero-downtime rolling updates     ║
║  Single point of failure   ║  High availability                 ║
║  Manual load balancing     ║  Built-in load balancing            ║
╚═══════════════════════════╩════════════════════════════════════╝
```

---

# ☸️ PART 2 — Kubernetes Architecture

> **🎯 Goal:** Understand every component in a Kubernetes cluster.

---

### 🏗️ Step 1: The Big Picture

```
╔══════════════════════════════════════════════════════════════════╗
║                     ☸️ KUBERNETES CLUSTER                         ║
║                                                                  ║
║  ┌──────────────── 🧠 CONTROL PLANE (The Brain) ─────────────┐  ║
║  │                                                            │  ║
║  │  ┌──────────────┐  ┌──────────────┐  ┌─────────────────┐  │  ║
║  │  │  📡 API      │  │  📋 Scheduler │  │  🔄 Controller  │  │  ║
║  │  │  Server      │  │  (who runs   │  │  Manager        │  │  ║
║  │  │  (front door)│  │   what where)│  │  (fix problems) │  │  ║
║  │  └──────────────┘  └──────────────┘  └─────────────────┘  │  ║
║  │  ┌──────────────┐  ┌────────────────────────────────────┐  │  ║
║  │  │  📒 etcd      │  │  ☁️ Cloud Controller Manager       │  │  ║
║  │  │  (database)  │  │  (talks to AWS/GCP/Azure)         │  │  ║
║  │  └──────────────┘  └────────────────────────────────────┘  │  ║
║  └────────────────────────────────────────────────────────────┘  ║
║                              │                                   ║
║  ┌─────── 💪 WORKER NODE 1 ───────┐ ┌──── 💪 WORKER NODE 2 ──┐  ║
║  │  ┌────────┐  ┌────────┐        │ │  ┌────────┐            │  ║
║  │  │ 📦 Pod │  │ 📦 Pod │        │ │  │ 📦 Pod │            │  ║
║  │  │┌──────┐│  │┌──────┐│        │ │  │┌──────┐│            │  ║
║  │  ││ 🐳 C1││  ││ 🐳 C3││        │ │  ││ 🐳 C5││            │  ║
║  │  │└──────┘│  │└──────┘│        │ │  │└──────┘│            │  ║
║  │  └────────┘  └────────┘        │ │  └────────┘            │  ║
║  │  ┌──────────┐ ┌─────────────┐  │ │  ┌──────────┐          │  ║
║  │  │👷 kubelet│ │🚦 kube-proxy│  │ │  │👷 kubelet│          │  ║
║  │  └──────────┘ └─────────────┘  │ │  └──────────┘          │  ║
║  └────────────────────────────────┘ └─────────────────────────┘  ║
╚══════════════════════════════════════════════════════════════════╝
```

---

### 🏗️ Step 2: Control Plane Components

| # | Component | Role | Analogy |
|---|-----------|------|---------|
| 1 | 📡 **API Server** | Front door for ALL commands. Every request goes through here. | Hotel reception desk 🏨 |
| 2 | 📋 **Scheduler** | Decides which worker node runs each pod based on resources. | Airport gate assignment ✈️ |
| 3 | 🔄 **Controller Manager** | Monitors cluster and ensures desired state = actual state. | Thermostat keeping temp at 72°F 🌡️ |
| 4 | 📒 **etcd** | Distributed key-value database storing ALL cluster state. | The cluster's notebook/diary 📓 |
| 5 | ☁️ **Cloud Controller** | Integrates with cloud providers (AWS, GCP, Azure). | Cloud services translator 🌐 |

---

### 🏗️ Step 3: Worker Node Components

| # | Component | Role | Analogy |
|---|-----------|------|---------|
| 1 | 👷 **kubelet** | Agent on each node. Manages pods, reports status. | Site supervisor 🏗️ |
| 2 | 🚦 **kube-proxy** | Handles networking rules and load balancing on each node. | Traffic officer at intersection |
| 3 | 🐳 **Container Runtime** | Runs containers (containerd, CRI-O). | The engine that runs Docker containers |

---

### 🏗️ Step 4: K8s Objects Hierarchy

```
☸️ Cluster
 └── 📁 Namespace (virtual sub-cluster)
      ├── 🚀 Deployment (manages desired state)
      │    └── 📦 ReplicaSet (ensures N pods running)
      │         └── 📦 Pod (runs containers)
      │              └── 🐳 Container
      ├── 🌐 Service (stable network endpoint)
      ├── 🔧 ConfigMap (non-sensitive config)
      ├── 🔐 Secret (sensitive config)
      ├── 💾 PersistentVolumeClaim (storage request)
      └── 🚪 Ingress (external HTTP routing)
```

---

# ☸️ PART 3 — Installing Kubernetes (Minikube)

> **🎯 Goal:** Set up a local Kubernetes cluster on your laptop using Minikube.

---

### ⚙️ Step 1: Install Minikube & kubectl

#### On Windows (PowerShell as Admin)

```powershell
# 1️⃣ Install Minikube
winget install Kubernetes.minikube

# 2️⃣ Install kubectl
winget install Kubernetes.kubectl

# 3️⃣ Start cluster
minikube start --driver=docker

# 4️⃣ Verify
kubectl cluster-info
kubectl get nodes
# ✅ NAME       STATUS   ROLES           AGE   VERSION
#    minikube   Ready    control-plane   30s   v1.28.0
```

#### On macOS

```bash
brew install minikube kubectl
minikube start --driver=docker
```

#### On Linux

```bash
# Minikube
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube

# kubectl
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl

minikube start --driver=docker
```

---

### ⚙️ Step 2: Essential Minikube Commands

```bash
minikube status                     # 📊 Check cluster status
minikube stop                       # ⏸️ Pause cluster
minikube start                      # ▶️ Resume cluster
minikube delete                     # 🗑️ Delete cluster entirely
minikube dashboard                  # 🖥️ Open beautiful web UI!
minikube ip                         # 🌐 Get cluster IP address
minikube ssh                        # 💻 SSH into the node
minikube addons list                # 📋 List available addons
minikube addons enable ingress      # 🚪 Enable Ingress
minikube addons enable metrics-server # 📊 Enable metrics
minikube service SVC_NAME --url     # 🔗 Get URL for a NodePort service
```

---

# ☸️ PART 4 — Kubectl: Essential Commands

> **🎯 Goal:** Master the kubectl command-line tool — your gateway to Kubernetes.

---

### 🔧 Step 1: Command Structure

```
kubectl  [VERB]     [RESOURCE]   [NAME]     [FLAGS]
         ────       ────────     ────       ─────
         get        pods         my-pod     -o wide
         describe   services     my-svc     -n my-namespace
         delete     deployments  my-app     --all
         apply      -f           file.yaml
```

---

### 🔧 Step 2: GET — View Resources

```bash
# 📋 List resources
kubectl get pods                    # All pods in current namespace
kubectl get pods -o wide            # More columns (IP, Node)
kubectl get pods -o yaml            # Full YAML output
kubectl get pods -o json            # Full JSON output
kubectl get pods --show-labels      # Show labels

kubectl get services                # or: kubectl get svc
kubectl get deployments             # or: kubectl get deploy
kubectl get all                     # Everything in namespace
kubectl get all -A                  # Everything in ALL namespaces

# 🔍 Detailed info + events
kubectl describe pod my-pod
kubectl describe svc my-service
kubectl describe deploy my-app
```

---

### 🔧 Step 3: CREATE / APPLY — Create Resources

```bash
# 📄 From YAML file (preferred method!)
kubectl apply -f pod.yaml           # Create/Update from file
kubectl apply -f ./k8s/             # Apply ALL YAML files in directory
kubectl apply -f https://url.com/manifest.yaml  # From URL

# ⚡ Quick creation (for testing)
kubectl run my-pod --image=nginx
kubectl create deployment my-app --image=nginx --replicas=3
```

---

### 🔧 Step 4: MODIFY — Update Resources

```bash
kubectl edit deployment my-app                    # Open in editor
kubectl scale deployment my-app --replicas=5      # Change replica count
kubectl set image deploy/my-app my-app=my-app:v2  # Update image
```

---

### 🔧 Step 5: DELETE — Remove Resources

```bash
kubectl delete pod my-pod
kubectl delete -f pod.yaml           # Delete using same YAML
kubectl delete deployment my-app
kubectl delete all --all -n my-ns    # Delete everything in namespace
```

---

### 🔧 Step 6: DEBUG — Troubleshoot Issues

```bash
# 📝 View logs
kubectl logs my-pod                  # Pod logs
kubectl logs -f my-pod               # Follow in real-time
kubectl logs my-pod -c my-container  # Specific container in pod
kubectl logs --previous my-pod       # Logs from crashed container

# 💻 Shell access
kubectl exec -it my-pod -- bash      # Open bash shell
kubectl exec -it my-pod -- sh        # If bash not available

# 🔗 Port forwarding
kubectl port-forward my-pod 8080:80
kubectl port-forward svc/my-svc 8080:80
# Now visit http://localhost:8080

# 📊 Resource usage
kubectl top pods                     # CPU & memory per pod
kubectl top nodes                    # CPU & memory per node
```

---

### 🔧 Step 7: Namespaces — Virtual Sub-clusters

```bash
kubectl get namespaces               # List namespaces
kubectl create namespace my-app      # Create new namespace
kubectl get pods -n my-app           # Pods in specific namespace
kubectl get pods -A                  # Pods in ALL namespaces
kubectl config set-context --current --namespace=my-app  # Set default
```

---

# ☸️ PART 5 — Pods: The Smallest Deployable Unit

> **🎯 Goal:** Understand Pods — the building blocks of Kubernetes.

---

### 📦 Step 1: What is a Pod?

```
╔══════════════════════════════════════════╗
║  📦 POD                                  ║
║  ┌──────────┐  ┌──────────┐             ║
║  │ 🐳 App   │  │ 🐳 Helper│ (optional)  ║
║  │ Container │  │ Container│             ║
║  └─────┬────┘  └────┬─────┘             ║
║        │             │                   ║
║  ┌─────┴─────────────┴─────┐             ║
║  │  🌐 Shared Network      │ Same IP!    ║
║  │  💾 Shared Volumes       │             ║
║  └─────────────────────────┘             ║
╚══════════════════════════════════════════╝
```

**Key facts:**
- A Pod wraps **1 or more containers** that share the same network and storage
- Containers in a pod communicate via `localhost`
- Pods are **ephemeral** — they can die and be replaced at any time
- You almost NEVER create pods directly — use Deployments instead!

---

### 📦 Step 2: Create a Simple Pod

```yaml
# pod.yaml
apiVersion: v1
kind: Pod
metadata:
  name: my-nginx-pod
  labels:
    app: nginx
    environment: dev
spec:
  containers:
    - name: nginx
      image: nginx:1.25
      ports:
        - containerPort: 80
      resources:
        requests:
          memory: "64Mi"
          cpu: "100m"      # 100 millicores = 0.1 CPU
        limits:
          memory: "128Mi"
          cpu: "250m"
```

```bash
# 1️⃣ Create the pod
kubectl apply -f pod.yaml

# 2️⃣ Check status
kubectl get pods
# NAME            READY   STATUS    RESTARTS   AGE
# my-nginx-pod    1/1     Running   0          30s

# 3️⃣ Access it
kubectl port-forward my-nginx-pod 8080:80
# 🌐 Visit http://localhost:8080

# 4️⃣ Delete it
kubectl delete pod my-nginx-pod
```

---

### 📦 Step 3: Multi-Container Pod (Sidecar Pattern)

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: multi-pod
spec:
  volumes:
    - name: shared-logs
      emptyDir: {}

  # 🔧 Init Container — runs BEFORE main containers
  initContainers:
    - name: init-setup
      image: busybox
      command: ["sh", "-c", "echo 'Initializing...' && sleep 2"]

  containers:
    # 🏠 Main App Container
    - name: app
      image: nginx:1.25
      ports:
        - containerPort: 80
      volumeMounts:
        - name: shared-logs
          mountPath: /var/log/nginx

    # 🔍 Sidecar — Log Collector
    - name: log-collector
      image: busybox
      command: ["sh", "-c", "tail -f /var/log/nginx/access.log"]
      volumeMounts:
        - name: shared-logs
          mountPath: /var/log/nginx
```

> [!TIP]
> 💡 **Common sidecar patterns:** log collectors, monitoring agents, proxy containers, config updaters.

---

### 📦 Step 4: Health Probes

```yaml
spec:
  containers:
    - name: app
      image: my-app:v1
      # 🟢 Startup Probe — "Has the app finished starting?"
      startupProbe:
        httpGet: { path: /healthz, port: 8080 }
        failureThreshold: 30
        periodSeconds: 10

      # 💓 Liveness Probe — "Is the app still alive?"
      livenessProbe:
        httpGet: { path: /healthz, port: 8080 }
        initialDelaySeconds: 15
        periodSeconds: 20
        # On failure → Container RESTARTED

      # ✅ Readiness Probe — "Is the app ready for traffic?"
      readinessProbe:
        httpGet: { path: /ready, port: 8080 }
        initialDelaySeconds: 5
        periodSeconds: 10
        # On failure → Removed from Service endpoints (no traffic)
```

| Probe | Question | On Failure |
|-------|---------|------------|
| 🟢 **Startup** | "Has it finished booting?" | Liveness/readiness paused until success |
| 💓 **Liveness** | "Is it alive?" | Container is **restarted** |
| ✅ **Readiness** | "Can it accept traffic?" | Removed from **Service** (no traffic) |

---

# ☸️ PART 6 — Deployments & ReplicaSets

> **🎯 Goal:** Master Deployments — the most important Kubernetes object for running applications.

---

### 🚀 Step 1: Why Deployments?

```
📦 Pod             → Single container, no self-healing, no scaling
📦📦 ReplicaSet    → Ensures N pods running, self-healing, BUT no rolling updates
🚀 Deployment      → ReplicaSet + rolling updates + rollback = PRODUCTION READY ✅
```

> [!IMPORTANT]
> 🔑 **Always use Deployments** in production. Never create Pods or ReplicaSets directly.

---

### 🚀 Step 2: Create a Deployment

```yaml
# deployment.yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
  labels:
    app: nginx
spec:
  replicas: 3                        # 📦 Run 3 copies

  selector:
    matchLabels:
      app: nginx                     # 🏷️ Match pods with this label

  strategy:
    type: RollingUpdate              # 🔄 Update strategy
    rollingUpdate:
      maxSurge: 1                    # Create 1 extra pod during update
      maxUnavailable: 1              # Allow 1 pod to be down during update

  template:                          # 📋 Pod template
    metadata:
      labels:
        app: nginx
    spec:
      containers:
        - name: nginx
          image: nginx:1.25
          ports:
            - containerPort: 80
          resources:
            requests: { memory: "64Mi", cpu: "100m" }
            limits:   { memory: "128Mi", cpu: "250m" }
          readinessProbe:
            httpGet: { path: /, port: 80 }
            initialDelaySeconds: 5
```

```bash
kubectl apply -f deployment.yaml
kubectl get deployments
# NAME               READY   UP-TO-DATE   AVAILABLE   AGE
# nginx-deployment   3/3     3            3           30s
```

---

### 🚀 Step 3: Rolling Update (Zero Downtime!)

```bash
# 1️⃣ Update the image
kubectl set image deployment/nginx-deployment nginx=nginx:1.26

# 2️⃣ Watch the rollout happen
kubectl rollout status deployment/nginx-deployment
# Waiting for deployment "nginx-deployment" rollout to finish:
# 1 out of 3 new replicas have been updated...
# 2 out of 3 new replicas have been updated...
# 3 out of 3 new replicas have been updated...
# ✅ deployment "nginx-deployment" successfully rolled out
```

```
🔄 What happens during Rolling Update:
┌────────────────────────────────────────────┐
│  Step 1: Old: [v1] [v1] [v1]              │
│  Step 2: Old: [v1] [v1]    New: [v2]      │  (1 new created)
│  Step 3: Old: [v1]         New: [v2] [v2] │  (1 old removed)
│  Step 4: Done!             New: [v2] [v2] [v2] │  
└────────────────────────────────────────────┘
🎯 At no point are zero pods available!
```

---

### 🚀 Step 4: Rollback

```bash
# 📜 View rollout history
kubectl rollout history deployment/nginx-deployment
# REVISION   CHANGE-CAUSE
# 1          <none>
# 2          <none>

# ⏪ Rollback to previous version
kubectl rollout undo deployment/nginx-deployment

# ⏪ Rollback to specific revision
kubectl rollout undo deployment/nginx-deployment --to-revision=1
```

---

### 🚀 Step 5: Scaling

```bash
# 📈 Manual scaling
kubectl scale deployment nginx-deployment --replicas=5

# 📈 Auto-scaling (HPA)
kubectl autoscale deployment nginx-deployment \
    --min=2 --max=10 --cpu-percent=80

# 📊 Check auto-scaler status
kubectl get hpa
```

---

# ☸️ PART 7 — Services & Networking

> **🎯 Goal:** Understand how to expose your pods and route traffic.

---

### 🌐 Step 1: Why Services?

```
❌ Problem: Pods get random IPs that change when they restart!
   Pod "web-abc" → IP: 10.1.0.5  → dies → new pod → IP: 10.1.0.12 😱

✅ Solution: Service gives a STABLE IP and DNS name!
   Service "web-service" → IP: 10.96.0.100 → Always reachable! 🎯
   DNS: web-service.my-namespace.svc.cluster.local
```

---

### 🌐 Step 2: Service Types

```
╔═══════════════╦════════════════════════════════════════════════════╗
║  Type         ║  What It Does                                     ║
╠═══════════════╬════════════════════════════════════════════════════╣
║  ClusterIP    ║  Internal only (default). Other pods can reach it.║
║  NodePort     ║  External via NodeIP:30000-32767. For dev/testing.║
║  LoadBalancer ║  Cloud LB with public IP. For production.         ║
║  ExternalName ║  Maps to external DNS (CNAME). For external svcs. ║
╚═══════════════╩════════════════════════════════════════════════════╝
```

```
🌐 Traffic flow:
Internet → LoadBalancer → NodePort → ClusterIP → Pod
                          (30080)    (80)        (3000)
```

---

### 🌐 Step 3: Create Services

```yaml
# ═══════════════════════════════════════
# 🔒 ClusterIP — Internal Only
# ═══════════════════════════════════════
apiVersion: v1
kind: Service
metadata:
  name: backend-service
spec:
  type: ClusterIP
  selector:
    app: backend                    # 🏷️ Routes to pods with this label
  ports:
    - port: 80                      # Service port (what callers use)
      targetPort: 3000              # Container port (where app listens)

---
# ═══════════════════════════════════════
# 🌍 NodePort — External Access
# ═══════════════════════════════════════
apiVersion: v1
kind: Service
metadata:
  name: frontend-service
spec:
  type: NodePort
  selector:
    app: frontend
  ports:
    - port: 80
      targetPort: 3000
      nodePort: 30080               # 🔗 Access via NodeIP:30080

---
# ═══════════════════════════════════════
# ☁️ LoadBalancer — Cloud Production
# ═══════════════════════════════════════
apiVersion: v1
kind: Service
metadata:
  name: web-service
spec:
  type: LoadBalancer
  selector:
    app: web
  ports:
    - port: 80
      targetPort: 8080
```

```bash
kubectl get svc
kubectl describe svc my-service
minikube service frontend-service --url   # 🔗 Get URL for Minikube
```

---

# ☸️ PART 8 — ConfigMaps & Secrets

> **🎯 Goal:** Separate configuration from application code.

---

### 🔧 Step 1: ConfigMap (Non-sensitive Configuration)

```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: app-config
data:
  DATABASE_HOST: "postgres-service"
  DATABASE_PORT: "5432"
  LOG_LEVEL: "info"
  APP_MODE: "production"
```

### 🔐 Step 2: Secret (Sensitive Configuration)

```yaml
apiVersion: v1
kind: Secret
metadata:
  name: app-secret
type: Opaque
stringData:                          # ← plain text (K8s base64-encodes it)
  DB_PASSWORD: mysecretpassword
  API_KEY: sk-abc123xyz789
  JWT_SECRET: my-jwt-signing-key
```

> [!WARNING]
> ⚠️ K8s Secrets are base64-encoded, **NOT encrypted** by default! For production, use **Sealed Secrets**, **HashiCorp Vault**, or **cloud KMS**.

### 🔧 Step 3: Using in Pods

```yaml
spec:
  containers:
    - name: app
      image: my-app:v1
      # Method 1: Load ALL keys as env vars
      envFrom:
        - configMapRef:
            name: app-config
        - secretRef:
            name: app-secret
      # Method 2: Load specific keys
      env:
        - name: DB_HOST
          valueFrom:
            configMapKeyRef:
              name: app-config
              key: DATABASE_HOST
```

```bash
# ⚡ Quick creation from CLI
kubectl create configmap app-config --from-literal=DB_HOST=postgres
kubectl create secret generic app-secret --from-literal=DB_PASSWORD=secret123
```

---

# ☸️ PART 9 — Persistent Volumes & Claims

> **🎯 Goal:** Persist data beyond pod lifecycles using PVs and PVCs.

---

### 💾 Step 1: Understand the Concept

```
👨‍💼 Admin creates:           👩‍💻 Developer requests:       K8s matches them:
┌──────────────┐            ┌──────────────┐           PVC ──────→ PV
│ PersistentVol│            │ PVC          │           (request)    (storage)
│ (PV)         │            │ "I need 5Gi" │
│ "I have 10Gi"│            └──────────────┘
└──────────────┘
```

---

### 💾 Step 2: Create PVC & Use in Pod

```yaml
# pvc.yaml — Storage request
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: my-storage
spec:
  accessModes: [ReadWriteOnce]    # One node read-write
  resources:
    requests:
      storage: 5Gi

---
# pod-with-storage.yaml — Pod using the PVC
apiVersion: v1
kind: Pod
metadata:
  name: db-pod
spec:
  containers:
    - name: postgres
      image: postgres:15-alpine
      envFrom:
        - secretRef: { name: db-secret }
      volumeMounts:
        - name: db-data
          mountPath: /var/lib/postgresql/data
  volumes:
    - name: db-data
      persistentVolumeClaim:
        claimName: my-storage
```

```bash
kubectl apply -f pvc.yaml
kubectl get pvc
# NAME         STATUS   VOLUME   CAPACITY   ACCESS MODES
# my-storage   Bound    pv-xxx   5Gi        RWO
```

---

# ☸️ PART 10 — Ingress Controller

> **🎯 Goal:** Route external HTTP traffic to multiple services through one entry point.

---

### 🚪 Step 1: Why Ingress?

```
❌ Without Ingress:                    ✅ With Ingress:
LoadBalancer ($$$)  → frontend        ONE Ingress ($)  → /       → frontend
LoadBalancer ($$$)  → backend                          → /api    → backend
LoadBalancer ($$$)  → admin                            → /admin  → admin
Total: 3 × cloud LB = Expensive! 💸   Total: 1 × entry point = Cheap! 🎉
```

---

### 🚪 Step 2: Enable & Create Ingress

```bash
# 1️⃣ Enable Ingress addon in Minikube
minikube addons enable ingress
```

```yaml
# ingress.yaml
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: my-ingress
  annotations:
    nginx.ingress.kubernetes.io/rewrite-target: /
spec:
  rules:
    - host: myapp.local
      http:
        paths:
          - path: /
            pathType: Prefix
            backend:
              service: { name: frontend-service, port: { number: 80 } }
          - path: /api
            pathType: Prefix
            backend:
              service: { name: backend-service, port: { number: 80 } }
  tls:                               # 🔒 Optional: HTTPS
    - hosts: [myapp.local]
      secretName: tls-secret
```

---

# ☸️ PART 11 — Helm: Kubernetes Package Manager

> **🎯 Goal:** Install, upgrade, and manage complex K8s applications with Helm.

---

### 📦 Step 1: What is Helm?

```
🐧 Ubuntu:    apt install nginx
🍎 macOS:     brew install nginx
☸️ Kubernetes: helm install my-nginx bitnami/nginx
```

**Helm = package manager for Kubernetes.** A "chart" is a package of K8s YAML templates.

---

### 📦 Step 2: Essential Helm Commands

```bash
# 1️⃣ Add a chart repository
helm repo add bitnami https://charts.bitnami.com/bitnami
helm repo update

# 2️⃣ Search for charts
helm search repo nginx
helm search repo postgresql

# 3️⃣ Install a chart
helm install my-nginx bitnami/nginx
helm install my-db bitnami/postgresql --set auth.postgresPassword=secret
helm install my-db bitnami/postgresql -f my-values.yaml

# 4️⃣ Manage releases
helm list                           # 📋 List installed releases
helm status my-nginx                # 📊 Status of release
helm upgrade my-nginx bitnami/nginx --set replicaCount=3  # 📈 Upgrade
helm rollback my-nginx 1            # ⏪ Rollback to revision 1
helm history my-nginx               # 📜 View revision history
helm uninstall my-nginx             # 🗑️ Uninstall

# 5️⃣ Create your own chart
helm create my-app                  # 📁 Scaffold a chart
helm template my-app ./my-app       # 👀 Preview rendered YAML
helm lint ./my-app                  # ✅ Validate chart
helm package ./my-app               # 📦 Package as .tgz
helm install my-release ./my-app    # 🚀 Install from local
```

---

# ☸️ PART 12 — Monitoring & Logging

> **🎯 Goal:** Monitor cluster and application health.

---

### 📊 Step 1: Metrics Server

```bash
minikube addons enable metrics-server
kubectl top nodes                   # Node CPU & memory
kubectl top pods                    # Pod CPU & memory
kubectl top pods --sort-by=cpu      # Sort by CPU usage
```

### 📊 Step 2: Prometheus + Grafana

```bash
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm install monitoring prometheus-community/kube-prometheus-stack \
    -n monitoring --create-namespace

# Access Grafana dashboard
kubectl port-forward -n monitoring svc/monitoring-grafana 3000:80
# 🌐 Visit http://localhost:3000
# 👤 Username: admin  |  🔑 Password: prom-operator
```

---

# ☸️ PART 13 — Kubernetes Best Practices

> **🎯 Goal:** Follow production-grade patterns.

---

### ✨ Practice 1: Always Set Resource Requests & Limits

```yaml
resources:
  requests: { memory: "128Mi", cpu: "100m" }   # Guaranteed minimum
  limits:   { memory: "256Mi", cpu: "500m" }   # Maximum allowed
```

### ✨ Practice 2: Always Define Health Probes

```yaml
livenessProbe:  { httpGet: { path: /healthz, port: 8080 } }
readinessProbe: { httpGet: { path: /ready,   port: 8080 } }
```

### ✨ Practice 3: Security Context

```yaml
spec:
  securityContext:
    runAsNonRoot: true
    runAsUser: 1000
  containers:
    - securityContext:
        allowPrivilegeEscalation: false
        readOnlyRootFilesystem: true
        capabilities: { drop: [ALL] }
```

### ✨ Practice 4: Use Namespaces, Labels & Annotations

```yaml
metadata:
  namespace: production
  labels:
    app: my-app
    team: backend
    version: v2.1
  annotations:
    description: "Main backend API"
```

---

# ☸️ PART 14 — StatefulSets, DaemonSets, Jobs

> **🎯 Goal:** Learn when to use each workload type.

---

### 📊 Quick Comparison

| | Deployment | StatefulSet | DaemonSet | Job | CronJob |
|---|---|---|---|---|---|
| **Use For** | Stateless apps | Databases | Node agents | One-time tasks | Scheduled tasks |
| **Pod Names** | Random | Ordered (0,1,2) | Per node | Random | Random |
| **Storage** | Shared | Each gets own PVC | Host path | None | None |
| **Scaling** | Any order | Ordered (0→1→2) | 1 per node | completions | schedule |
| **Example** | Web app, API | PostgreSQL, Kafka | Log collector | DB migration | DB backup |

---

### 🗄️ StatefulSet — Stable Identity

```yaml
apiVersion: apps/v1
kind: StatefulSet
metadata:
  name: postgres
spec:
  serviceName: postgres-headless     # Required!
  replicas: 3
  selector:
    matchLabels: { app: postgres }
  template:
    metadata:
      labels: { app: postgres }
    spec:
      containers:
        - name: postgres
          image: postgres:15-alpine
          ports: [{ containerPort: 5432 }]
          volumeMounts:
            - name: data
              mountPath: /var/lib/postgresql/data
  volumeClaimTemplates:              # Each pod gets its OWN PVC!
    - metadata: { name: data }
      spec:
        accessModes: ["ReadWriteOnce"]
        resources: { requests: { storage: 10Gi } }
---
apiVersion: v1
kind: Service
metadata: { name: postgres-headless }
spec:
  clusterIP: None                    # Headless!
  selector: { app: postgres }
  ports: [{ port: 5432 }]
# Pod DNS: postgres-0.postgres-headless.ns.svc.cluster.local
```

---

### 🖥️ DaemonSet — One Pod Per Node

```yaml
apiVersion: apps/v1
kind: DaemonSet
metadata: { name: log-collector }
spec:
  selector:
    matchLabels: { app: log-collector }
  template:
    metadata:
      labels: { app: log-collector }
    spec:
      containers:
        - name: fluentd
          image: fluent/fluentd:v1.16
          volumeMounts:
            - name: varlog
              mountPath: /var/log
      volumes:
        - name: varlog
          hostPath: { path: /var/log }
```

---

### ⏱️ Jobs & CronJobs

```yaml
# 🏃 One-time Job
apiVersion: batch/v1
kind: Job
metadata: { name: db-migration }
spec:
  completions: 1
  backoffLimit: 3
  ttlSecondsAfterFinished: 3600
  template:
    spec:
      restartPolicy: Never
      containers:
        - name: migrate
          image: my-app:v1
          command: ["node", "migrate.js"]

---
# ⏰ CronJob — Runs on schedule
apiVersion: batch/v1
kind: CronJob
metadata: { name: nightly-backup }
spec:
  schedule: "0 2 * * *"             # Daily at 2 AM
  concurrencyPolicy: Forbid
  jobTemplate:
    spec:
      template:
        spec:
          restartPolicy: OnFailure
          containers:
            - name: backup
              image: postgres:15-alpine
              command: ["/bin/sh", "-c", "pg_dump mydb > /backup/db.sql"]
```

---

# ☸️ PART 15 — Taints, Tolerations & Affinity

> **🎯 Goal:** Control WHERE pods get scheduled.

---

### 🚫 Taints & Tolerations — "Go Away!" / "I Can Handle It"

```bash
# 🚫 Taint a node (repels pods)
kubectl taint nodes node1 gpu=true:NoSchedule
# Effects: NoSchedule, PreferNoSchedule, NoExecute

# ✅ Remove taint
kubectl taint nodes node1 gpu=true:NoSchedule-
```

```yaml
# ✅ Pod toleration (allows scheduling on tainted node)
spec:
  tolerations:
    - key: "gpu"
      operator: "Equal"
      value: "true"
      effect: "NoSchedule"
```

### 🧲 Node Affinity & Pod Anti-Affinity

```yaml
spec:
  affinity:
    # "Schedule me on high-memory nodes"
    nodeAffinity:
      requiredDuringSchedulingIgnoredDuringExecution:
        nodeSelectorTerms:
          - matchExpressions:
              - key: node-type
                operator: In
                values: [high-memory, gpu]

    # "Don't put me on the same node as another web pod"
    podAntiAffinity:
      preferredDuringSchedulingIgnoredDuringExecution:
        - weight: 100
          podAffinityTerm:
            labelSelector:
              matchExpressions:
                - key: app
                  operator: In
                  values: [web]
            topologyKey: kubernetes.io/hostname
```

```
📋 Summary:
   Taints + Tolerations   → Node says: "Go away!" (repels pods)
   Node Affinity          → Pod says: "Put me HERE" (attracts to nodes)
   Pod Anti-Affinity      → Pod says: "Keep me AWAY from those" (spreads out)
```

---

# ☸️ PART 16 — RBAC, Quotas, PDB, CRDs & Operators

> **🎯 Goal:** Secure your cluster and extend Kubernetes.

---

### 🔐 RBAC — Role-Based Access Control

```yaml
# 1️⃣ Create a Role (what permissions?)
apiVersion: rbac.authorization.k8s.io/v1
kind: Role
metadata: { name: developer-role, namespace: dev }
rules:
  - apiGroups: [""]
    resources: [pods, services, configmaps]
    verbs: [get, list, watch, create, update, delete]

---
# 2️⃣ Bind Role to User (who gets permissions?)
apiVersion: rbac.authorization.k8s.io/v1
kind: RoleBinding
metadata: { name: developer-binding, namespace: dev }
subjects:
  - kind: User
    name: john@example.com
    apiGroup: rbac.authorization.k8s.io
roleRef:
  kind: Role
  name: developer-role
  apiGroup: rbac.authorization.k8s.io
```

```bash
# 🔍 Check permissions
kubectl auth can-i create deployments --as=john@example.com -n dev
# yes / no
```

---

### 📊 ResourceQuota & LimitRange

```yaml
# Namespace-level limits
apiVersion: v1
kind: ResourceQuota
metadata: { name: dev-quota, namespace: dev }
spec:
  hard:
    pods: "50"
    requests.cpu: "10"
    requests.memory: "20Gi"

---
# Per-container defaults
apiVersion: v1
kind: LimitRange
metadata: { name: dev-limits, namespace: dev }
spec:
  limits:
    - type: Container
      default: { cpu: "500m", memory: "256Mi" }
      defaultRequest: { cpu: "100m", memory: "128Mi" }
```

---

### 🛡️ PodDisruptionBudget

```yaml
apiVersion: policy/v1
kind: PodDisruptionBudget
metadata: { name: web-pdb }
spec:
  minAvailable: 2                   # At least 2 pods stay running
  selector:
    matchLabels: { app: web }
```

---

### 🧩 CRDs & Operators

```yaml
# Define a new custom resource type: "Database"
apiVersion: apiextensions.k8s.io/v1
kind: CustomResourceDefinition
metadata: { name: databases.example.com }
spec:
  group: example.com
  names: { plural: databases, singular: database, kind: Database, shortNames: [db] }
  scope: Namespaced
  versions:
    - name: v1
      served: true
      storage: true
      schema:
        openAPIV3Schema:
          type: object
          properties:
            spec:
              type: object
              properties:
                engine: { type: string, enum: [postgres, mysql] }
                replicas: { type: integer }
```

> **Operator** = CRD + Custom Controller that encodes human operational knowledge (backup, failover, scaling) into code. Examples: Prometheus Operator, PostgreSQL Operator, cert-manager.

---

# ☸️ PART 17 — Service Mesh, CI/CD, Deployment Strategies

> **🎯 Goal:** Production-grade patterns for advanced deployments.

---

### 🕸️ Service Mesh (Istio)

Adds sidecar proxy to every pod for: mTLS, traffic splitting, observability.

```yaml
# Canary: 90% → v1, 10% → v2
apiVersion: networking.istio.io/v1beta1
kind: VirtualService
spec:
  http:
    - route:
        - destination: { host: my-app, subset: v1 }
          weight: 90
        - destination: { host: my-app, subset: v2 }
          weight: 10
```

### 🚀 Deployment Strategies

```
📋 Rolling Update   → Gradual swap, zero downtime ✅ (Default)
📋 Recreate         → All down, then all up (has downtime ⚠️)
📋 Blue-Green       → Two environments, instant switch 🔄
📋 Canary           → Gradual traffic shift (90/10 → 50/50 → 0/100) 📊
```

```bash
# Blue-Green: instant traffic switch
kubectl patch service my-svc -p '{"spec":{"selector":{"version":"green"}}}'
# Rollback to blue
kubectl patch service my-svc -p '{"spec":{"selector":{"version":"blue"}}}'
```

### 🔄 GitOps with ArgoCD

```bash
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
kubectl port-forward svc/argocd-server -n argocd 8080:443

argocd app create my-app \
    --repo https://github.com/org/repo.git \
    --path k8s/ \
    --dest-server https://kubernetes.default.svc \
    --dest-namespace production \
    --sync-policy automated
```

---

# ☸️ PART 18 — Troubleshooting Guide

> **🎯 Goal:** Diagnose and fix the most common Kubernetes issues.

---

### 🔧 Debugging Flow

```
1️⃣  kubectl get pods -o wide          → Check STATUS
2️⃣  kubectl describe pod <name>       → Check EVENTS section
3️⃣  kubectl logs <pod>                → Check APPLICATION output
4️⃣  kubectl logs --previous <pod>     → Logs from CRASHED container
5️⃣  kubectl get events --sort-by='.lastTimestamp'  → Cluster events
6️⃣  kubectl top pods / nodes          → Resource usage
7️⃣  kubectl exec -it <pod> -- sh      → Debug from INSIDE
```

### 🚨 Common Issues

| Issue | Cause | Fix |
|-------|-------|-----|
| **CrashLoopBackOff** | App crashes on startup | Check `kubectl logs --previous`, fix app code |
| **ImagePullBackOff** | Wrong image name/tag or private registry | Verify image name, add `imagePullSecrets` |
| **Pending** | Not enough resources or PVC not bound | Check events, increase node resources |
| **OOMKilled** | Memory limit exceeded | Increase `resources.limits.memory` |
| **Evicted** | Node disk/memory pressure | Clean up, add resources |
| **No endpoints** | Service selector doesn't match pod labels | Check labels match `kubectl get endpoints` |
| **CreateContainerError** | ConfigMap/Secret not found | Create missing ConfigMap/Secret |

```bash
# 🔍 Quick diagnostic command
kubectl run debug --image=busybox --rm -it -- wget -qO- http://my-service:80
```

---

# 📝 PART 19 — Kubernetes Interview Q&A

> **🎯 Goal:** Prepare for Kubernetes interview questions from beginner to expert.

---

### 🟢 Beginner

**Q1: What is Kubernetes?** → Open-source container orchestration platform for automated deployment, scaling, self-healing, load balancing, and management.

**Q2: Explain K8s architecture.** → **Control Plane:** API Server, Scheduler, Controller Manager, etcd. **Worker Nodes:** kubelet, kube-proxy, container runtime.

**Q3: What is a Pod?** → Smallest unit. Wraps 1+ containers sharing network (same IP) and storage. Ephemeral.

**Q4: Deployment vs ReplicaSet vs Pod?** → Pod = single instance. ReplicaSet = ensures N pods. Deployment = ReplicaSet + rolling updates + rollback. **Always use Deployments.**

**Q5: What are Service types?** → ClusterIP (internal), NodePort (external 30000-32767), LoadBalancer (cloud), ExternalName (DNS CNAME).

**Q6: ConfigMap vs Secret?** → ConfigMap = non-sensitive config. Secret = sensitive, base64-encoded (not encrypted by default).

---

### 🟡 Intermediate

**Q7: What is a Namespace?** → Virtual sub-cluster for isolation, RBAC, quotas. Defaults: `default`, `kube-system`, `kube-public`.

**Q8: Liveness vs Readiness vs Startup Probe?** → Liveness: alive? (restart on fail). Readiness: ready for traffic? (remove from Service). Startup: finished booting? (pause other probes).

**Q9: What is Ingress?** → Layer 7 HTTP router. One entry point → multiple services via path/host rules. Cost-effective vs multiple LoadBalancers.

**Q10: What is HPA?** → Horizontal Pod Autoscaler. Scales replicas based on CPU/memory/custom metrics. Checks every 15s. Requires Metrics Server.

**Q11: StatefulSet vs Deployment?** → StatefulSet: ordered pods (0,1,2), stable DNS, individual PVCs. For databases. Deployment: random pods, shared storage. For stateless apps.

**Q12: How does rolling update work?** → New ReplicaSet created → new pods added gradually → old pods removed gradually → zero downtime. Requires readiness probes.

**Q13: What is a DaemonSet?** → Ensures exactly one pod per node. For log collection, monitoring agents, networking.

---

### 🔴 Advanced

**Q14: Pod lifecycle (creation to termination)?** → **Create:** API Server validates → etcd → Scheduler picks node → kubelet pulls image → init containers → main containers → probes → added to endpoints. **Terminate:** Terminating state → removed from endpoints → preStop hook → SIGTERM → grace period → SIGKILL → removed from etcd.

**Q15: What is etcd?** → Distributed key-value store for ALL cluster state. Uses Raft consensus. 3 or 5 members for HA. SSD storage, regular backups, encryption at rest.

**Q16: How does K8s DNS work?** → CoreDNS creates records: `<svc>.<ns>.svc.cluster.local`. Headless services: `<pod>.<svc>.<ns>.svc.cluster.local`.

**Q17: What is RBAC?** → Role (namespace perms) + ClusterRole (cluster perms) + RoleBinding + ClusterRoleBinding. Follow least privilege.

**Q18: Resource requests vs limits?** → Requests = guaranteed minimum (scheduler uses). Limits = maximum. CPU exceeded → throttled. Memory exceeded → OOMKilled. QoS: Guaranteed, Burstable, BestEffort.

**Q19: What happens when a node fails?** → kubelet stops heartbeating → 40s: NotReady → 5 min: pods evicted → Deployment pods rescheduled. StatefulSet pods NOT auto-rescheduled (split-brain prevention).

**Q20: What is a Network Policy?** → Firewall rules for pods. Controls ingress/egress by pod labels, namespace labels, IP blocks. Requires CNI support (Calico, Cilium).

**Q21: Explain kube-proxy modes.** → **iptables** (default): O(n) sequential, random LB. **IPVS**: O(1) hash-based, multiple LB algorithms. Use IPVS for 1000+ services.

**Q22: How to achieve zero-downtime deployment?** → RollingUpdate + maxUnavailable:0 + readiness probes + PDB + graceful shutdown (preStop hook) + multiple replicas + pod anti-affinity.

**Q23: What are Operators?** → CRD + Custom Controller encoding human operational knowledge. Manages complex stateful apps (backups, failover, upgrades). Examples: Prometheus, PostgreSQL, cert-manager.

**Q24: PodDisruptionBudget?** → Ensures minimum pods stay running during voluntary disruptions (drain, upgrade). `minAvailable: 2` means at least 2 must remain.

**Q25: Blue-Green vs Canary deployment?** → Blue-Green: two full environments, instant switch via Service selector. Canary: gradual traffic shift (90/10 → 50/50 → 0/100), uses Ingress or Service Mesh.

---

### ⚡ Rapid-Fire

| # | Question | Answer |
|---|----------|--------|
| 26 | NodePort range? | 30000–32767 |
| 27 | Default Service DNS? | `<svc>.<ns>.svc.cluster.local` |
| 28 | Default restart policy? | `Always` |
| 29 | Internal DNS? | CoreDNS |
| 30 | Smallest CPU unit? | 1 millicore (`1m`) |
| 31 | CPU limit exceeded? | Throttled (NOT killed) |
| 32 | Memory limit exceeded? | OOMKilled 💀 |
| 33 | Headless Service? | `clusterIP: None` → returns pod IPs |
| 34 | Default update strategy? | RollingUpdate |
| 35 | HA etcd nodes? | 3 or 5 (odd for Raft quorum) |
| 36 | `kubectl drain`? | Evict pods for node maintenance |
| 37 | `kubectl cordon`? | Mark node unschedulable |
| 38 | Cross-namespace communication? | Yes, via full DNS name |
| 39 | What is a sidecar? | Helper container alongside main |
| 40 | `terminationGracePeriodSeconds`? | Default: 30 seconds |

---

## 📋 Kubernetes & Helm Cheat Sheet

```
╔══════════════════════════════════════════════════════════════════╗
║                   ☸️ KUBECTL CHEAT SHEET                          ║
╠══════════════════════════════════════════════════════════════════╣
║                                                                  ║
║  📊 CLUSTER & NODES                                              ║
║  kubectl cluster-info              Cluster details               ║
║  kubectl get nodes [-o wide]       List nodes                    ║
║  kubectl top nodes/pods            Resource usage                ║
║  kubectl config view               View config                   ║
║  kubectl config use-context CTX    Switch context                ║
║                                                                  ║
║  📋 VIEW RESOURCES                                               ║
║  kubectl get pods/svc/deploy/cm/secrets/pv/pvc/ingress/all      ║
║  kubectl get all -A                All namespaces                ║
║  kubectl describe TYPE NAME        Detailed info + events        ║
║                                                                  ║
║  ➕ CREATE / APPLY                                                ║
║  kubectl apply -f FILE.yaml        Create/Update resource        ║
║  kubectl apply -f DIRECTORY/       Apply all in dir              ║
║                                                                  ║
║  ✏️ MODIFY                                                       ║
║  kubectl edit deploy NAME          Edit in editor                ║
║  kubectl scale deploy NAME --replicas=N                          ║
║  kubectl set image deploy/N C=IMG:TAG                            ║
║  kubectl rollout status/undo/history deploy/N                    ║
║  kubectl autoscale deploy/N --min=2 --max=10 --cpu-percent=80    ║
║                                                                  ║
║  🗑️ DELETE                                                       ║
║  kubectl delete TYPE NAME          Delete resource               ║
║  kubectl delete -f FILE.yaml       Delete from YAML              ║
║  kubectl delete ns NAME            Delete namespace              ║
║                                                                  ║
║  🔧 DEBUG                                                        ║
║  kubectl logs [-f] POD [-c CONT]   View/follow logs              ║
║  kubectl logs --previous POD       Logs from crashed container   ║
║  kubectl exec -it POD -- bash      Shell access                  ║
║  kubectl port-forward POD H:C      Port forwarding               ║
║  kubectl top pods                  Resource usage                ║
║  kubectl get events --sort-by='.lastTimestamp'                   ║
║                                                                  ║
║  📁 NAMESPACES                                                   ║
║  kubectl get/create/delete ns NAME                               ║
║  kubectl config set-context --current --namespace=NAME           ║
║                                                                  ║
║  📦 HELM                                                         ║
║  helm repo add/update/list                                       ║
║  helm search repo KEYWORD                                        ║
║  helm install RELEASE CHART [--set K=V] [-f values.yaml]         ║
║  helm upgrade/rollback/uninstall RELEASE                         ║
║  helm list/status/history RELEASE                                ║
║  helm create/template/lint/package CHART                         ║
║                                                                  ║
╚══════════════════════════════════════════════════════════════════╝
```

---

## 🗺️ Kubernetes Learning Roadmap

```
📅 WEEK 1-2: K8s Fundamentals
├── Day 1: ✅ Install Minikube, run kubectl get nodes
├── Day 2: ✅ kubectl get/describe/apply/delete
├── Day 3: ✅ Create Pods with YAML
├── Day 4: ✅ Deployments — create, scale, update
├── Day 5: ✅ Rolling updates & rollback
├── Day 6: ✅ Services — ClusterIP, NodePort
├── Day 7: ✅ Practice: Deploy nginx with 3 replicas + Service

📅 WEEK 3-4: K8s Intermediate
├── Day 1: ✅ ConfigMaps & Secrets
├── Day 2: ✅ PersistentVolumes & PVCs
├── Day 3: ✅ Ingress Controller setup
├── Day 4: ✅ Helm basics — install, upgrade, rollback
├── Day 5: ✅ Create your own Helm chart
├── Day 6: ✅ Monitoring with Metrics Server
├── Day 7: ✅ Practice: Deploy WordPress + MySQL on K8s

📅 WEEK 5-6: K8s Advanced
├── Day 1: ✅ StatefulSets & Headless Services
├── Day 2: ✅ DaemonSets, Jobs & CronJobs
├── Day 3: ✅ Taints, Tolerations & Affinity
├── Day 4: ✅ RBAC — Roles & RoleBindings
├── Day 5: ✅ ResourceQuotas, LimitRanges, PDB
├── Day 6: ✅ CRDs & Operators concept
├── Day 7: ✅ Network Policies

📅 WEEK 7+: Expert & Interview Prep
├── Day 1: ✅ Service Mesh (Istio) overview
├── Day 2: ✅ CI/CD with GitOps (ArgoCD)
├── Day 3: ✅ Deployment strategies (Blue-Green, Canary)
├── Day 4: ✅ Troubleshooting common issues
├── Day 5: ✅ Study interview questions (Q1-Q20)
├── Day 6: ✅ Study interview questions (Q21-Q40)
└── Day 7: ✅ Mock interview + CKA/CKAD practice!
```

---

> [!TIP]
> 🎉 **Congratulations!** You've completed the Kubernetes guide!
>
> 👉 Continue to [**Part 3: Angular + Docker + K8s Project**](file:///C:/Users/Mojammil%20Husain/.gemini/antigravity/brain/810210d9-bd04-4967-a796-7552ae205906/part3_angular_docker_k8s_project.md) to put everything into practice! 🚀
