# 🐳 Docker — Complete Mastery Guide
## Part 1 of 3 | From Absolute Beginner to Expert

> [!NOTE]
> 📘 **Series Navigation**
>
> 📕 **You are here → Part 1: Docker**
> 📘 [Part 2: Kubernetes Guide](file:///C:/Users/Mojammil%20Husain/.gemini/antigravity/brain/810210d9-bd04-4967-a796-7552ae205906/part2_kubernetes_guide.md)
> 📗 [Part 3: Angular + Docker + K8s Project](file:///C:/Users/Mojammil%20Husain/.gemini/antigravity/brain/810210d9-bd04-4967-a796-7552ae205906/part3_angular_docker_k8s_project.md)

---

## 📚 What's Inside This Guide?

| # | Part | Topic | Level |
|---|------|-------|-------|
| 📦 | **Part 1** | What is Docker? Why Docker? | 🟢 Beginner |
| 📦 | **Part 2** | Installing Docker | 🟢 Beginner |
| 📦 | **Part 3** | Docker Basic Commands | 🟢 Beginner |
| 📦 | **Part 4** | Docker Images Deep Dive | 🟡 Intermediate |
| 📦 | **Part 5** | Dockerfile — Build Custom Images | 🟡 Intermediate |
| 📦 | **Part 6** | Practical Project — Flask App | 🟡 Intermediate |
| 📦 | **Part 7** | Docker Volumes & Persistence | 🟡 Intermediate |
| 📦 | **Part 8** | Docker Networking | 🟡 Intermediate |
| 📦 | **Part 9** | Docker Compose | 🟡 Intermediate |
| 📦 | **Part 10** | Docker Best Practices | 🔴 Advanced |
| 📦 | **Part 11** | Docker Internals — Under the Hood | 🔴 Expert |
| 📦 | **Part 12** | Docker Interview Q&A (20 Questions) | 🎯 All Levels |
| 📋 | **Bonus** | Complete Cheat Sheet + Learning Path | ✅ All Levels |

---

# 📦 PART 1 — What is Docker? Why Docker?

> **🎯 Goal:** Understand what Docker is, why it exists, and how it's different from virtual machines.

---

### 🧩 Step 1: Understand the Problem Docker Solves

Imagine this situation:

```
👨‍💻 Developer: "The app works perfectly on my machine!"
👩‍💼 DevOps:    "Well, it's crashing on the server..."
👨‍💻 Developer: "But... it works on MY machine! 🤷"
```

**Why does this happen?**
- Different operating systems (Windows vs Linux)
- Different versions of Python, Node.js, Java, etc.
- Missing libraries or dependencies
- Different configuration files
- Different environment variables

**This is called the "Works on My Machine" problem.** Docker eliminates it completely.

---

### 🧩 Step 2: Understand Docker with a Simple Analogy

> 🍽️ **The Restaurant Analogy**
>
> You're a chef 👨‍🍳. You create an amazing recipe at home. When you try to cook the same dish in a different kitchen, the oven is different, the ingredients are slightly different, and the dish doesn't turn out the same.
>
> **Docker is like a portable kitchen** — it packages your recipe, ingredients, oven, pots, and everything into a shipping container 📦. No matter where you open that container (your home, a restaurant, another country), your dish will taste **exactly the same!**

---

### 🧩 Step 3: Learn the Core Concepts

| # | Concept | What It Is | Analogy |
|---|---------|-----------|---------|
| 1 | 📝 **Image** | A read-only blueprint/template for creating containers | A recipe |
| 2 | 🍽️ **Container** | A running instance of an image | The cooked dish |
| 3 | 📄 **Dockerfile** | A text file with instructions to build an image | Step-by-step cooking instructions |
| 4 | 🌐 **Docker Hub** | Online marketplace for Docker images | A cookbook library |
| 5 | 🏭 **Registry** | A server that stores Docker images | A warehouse for recipes |
| 6 | 🐳 **Docker Engine** | The runtime that creates & manages containers | The kitchen itself |

---

### 🧩 Step 4: Docker vs Virtual Machines

```
╔══════════════════════════╦══════════════════════════╗
║    🖥️ VIRTUAL MACHINE     ║    🐳 DOCKER CONTAINER    ║
╠══════════════════════════╬══════════════════════════╣
║  ┌──────────────────┐   ║  ┌──────────────────┐    ║
║  │    Your App       │   ║  │    Your App       │    ║
║  ├──────────────────┤   ║  ├──────────────────┤    ║
║  │   Guest OS        │   ║  │   Container       │    ║
║  │  (Full OS! 💾)     │   ║  │   Engine (tiny!)  │    ║
║  ├──────────────────┤   ║  ├──────────────────┤    ║
║  │   Hypervisor      │   ║  │   Host OS         │    ║
║  ├──────────────────┤   ║  ├──────────────────┤    ║
║  │   Host OS         │   ║  │   Hardware        │    ║
║  ├──────────────────┤   ║  └──────────────────┘    ║
║  │   Hardware        │   ║                          ║
║  └──────────────────┘   ║                          ║
╠══════════════════════════╬══════════════════════════╣
║  Size: ~GBs              ║  Size: ~MBs               ║
║  Boot: ~minutes           ║  Boot: ~seconds            ║
║  Performance: Slower     ║  Performance: Near-native  ║
║  Isolation: Full OS       ║  Isolation: Process-level  ║
╚══════════════════════════╩══════════════════════════╝
```

> [!TIP]
> 💡 **Think of it this way:** VMs are like renting an entire apartment (with kitchen, bathroom, bedroom) for each app. Containers are like renting just a desk in a co-working space — much cheaper and faster!

---

# 📦 PART 2 — Installing Docker

> **🎯 Goal:** Get Docker installed and running on your computer.

---

### ⚙️ Option A: Windows Installation

```
📋 Prerequisites:
   ✅ Windows 10/11 (64-bit)
   ✅ WSL 2 enabled (Docker Desktop does this for you)
   ✅ Virtualization enabled in BIOS
```

**Step 1:** Download Docker Desktop

```
🌐 Go to: https://www.docker.com/products/docker-desktop
📥 Click "Download for Windows"
```

**Step 2:** Run the Installer

```
🖱️ Double-click "Docker Desktop Installer.exe"
☑️ Check "Use WSL 2" when prompted
🔄 Click "OK" and wait for installation
```

**Step 3:** Restart your computer

**Step 4:** Verify installation

```powershell
# Open PowerShell and run:
docker --version
# ✅ Output: Docker version 24.x.x, build xxxxxxx

docker run hello-world
# ✅ If you see "Hello from Docker!" — you're all set! 🎉
```

---

### ⚙️ Option B: macOS Installation

**Step 1:** Install via Homebrew (recommended)

```bash
brew install --cask docker
```

**Step 2:** Open Docker Desktop from Applications

**Step 3:** Verify

```bash
docker --version
docker run hello-world
```

---

### ⚙️ Option C: Linux (Ubuntu/Debian) Installation

**Step 1:** Update packages & install prerequisites

```bash
sudo apt-get update
sudo apt-get install -y ca-certificates curl gnupg lsb-release
```

**Step 2:** Add Docker's GPG key and repository

```bash
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | \
    sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

echo "deb [arch=$(dpkg --print-architecture) \
  signed-by=/etc/apt/keyrings/docker.gpg] \
  https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

**Step 3:** Install Docker Engine

```bash
sudo apt-get update
sudo apt-get install -y docker-ce docker-ce-cli containerd.io docker-compose-plugin
```

**Step 4:** Allow running Docker without `sudo`

```bash
sudo usermod -aG docker $USER
# ⚠️ Log out and log back in for this to take effect!
```

**Step 5:** Verify

```bash
docker --version
docker run hello-world
# ✅ Output: "Hello from Docker!" 🎉
```

---

# 📦 PART 3 — Docker Basic Commands

> **🎯 Goal:** Master the essential Docker commands to run, manage, and debug containers.

---

### 🚀 Step 1: Run Your Very First Container

```bash
docker run hello-world
```

**What happens behind the scenes:**
```
1️⃣ Docker checks: "Do I have 'hello-world' image locally?"  → ❌ No!
2️⃣ Docker downloads it from Docker Hub (internet)           → ⬇️ Pulling...
3️⃣ Docker creates a container from that image               → 📦 Created!
4️⃣ Docker starts the container                              → ▶️ Running!
5️⃣ Container prints a message and exits                     → ✅ Done!
```

---

### 🚀 Step 2: Run Containers in Different Modes

```bash
# ──────────────────────────────────────────────
# 🎮 INTERACTIVE MODE — You're INSIDE the container
# ──────────────────────────────────────────────
docker run -it ubuntu bash
#  -i = interactive (keep STDIN open)
#  -t = terminal (allocate a pseudo-TTY)
#  ubuntu = image name
#  bash = command to run inside

# 🎯 Try these commands inside:
#    ls              → list files
#    whoami          → prints "root"
#    cat /etc/os-release  → see OS info
#    exit            → leave the container

# ──────────────────────────────────────────────
# 🔄 DETACHED MODE — Container runs in background
# ──────────────────────────────────────────────
docker run -d -p 8080:80 --name my-web nginx
#  -d       = detached (runs in background)
#  -p 8080:80 = port mapping (YOUR_MACHINE:CONTAINER)
#  --name   = give it a friendly name
#  nginx    = image name

# 🌐 Open http://localhost:8080 in your browser! 🎉

# ──────────────────────────────────────────────
# 🔧 WITH ENVIRONMENT VARIABLES
# ──────────────────────────────────────────────
docker run -d \
    --name my-db \
    -e MYSQL_ROOT_PASSWORD=secret \
    -e MYSQL_DATABASE=myapp \
    -p 3306:3306 \
    mysql:8.0

# ──────────────────────────────────────────────
# 🗑️ AUTO-REMOVE when container stops
# ──────────────────────────────────────────────
docker run --rm -it ubuntu bash
#  --rm = container is deleted automatically when it exits
```

---

### 🚀 Step 3: List & Inspect Containers

```bash
# 📋 List RUNNING containers
docker ps
# Output:
# CONTAINER ID   IMAGE   COMMAND      STATUS        PORTS                  NAMES
# a1b2c3d4e5f6   nginx   "/docker…"   Up 2 min      0.0.0.0:8080->80/tcp   my-web

# 📋 List ALL containers (including stopped)
docker ps -a

# 📋 List only container IDs
docker ps -q

# 🔍 Full details about a container (JSON)
docker inspect my-web

# 🔍 Get a specific piece of information
docker inspect --format='{{.NetworkSettings.IPAddress}}' my-web
```

---

### 🚀 Step 4: Stop, Start, Restart, Remove Containers

```bash
# ⏹️ STOP — Graceful shutdown (SIGTERM → wait 10s → SIGKILL)
docker stop my-web
docker stop -t 5 my-web          # Custom timeout: 5 seconds

# ▶️ START — Restart a stopped container
docker start my-web

# 🔄 RESTART — Stop + Start
docker restart my-web

# 🗑️ REMOVE — Delete a stopped container
docker rm my-web

# 🗑️ FORCE REMOVE — Delete even if running
docker rm -f my-web

# 🧹 CLEANUP — Remove ALL stopped containers
docker container prune
# ⚠️ This will remove all stopped containers!

# 🧹 NUCLEAR OPTION — Remove ALL containers
docker rm -f $(docker ps -aq)
```

> [!WARNING]
> ⚠️ `docker rm -f $(docker ps -aq)` removes **ALL** containers (running + stopped). Use with caution!

---

### 🚀 Step 5: View Logs & Debug

```bash
# 📝 View container logs
docker logs my-web                 # All logs
docker logs -f my-web              # Follow in real-time (like tail -f)
docker logs --tail 50 my-web       # Last 50 lines only
docker logs -t my-web              # With timestamps

# 💻 Open a shell INSIDE a running container
docker exec -it my-web bash
docker exec -it my-web sh          # If bash isn't available

# 🏃 Run a single command inside a container
docker exec my-web cat /etc/nginx/nginx.conf

# 📊 Real-time resource usage (CPU, memory, I/O)
docker stats
docker stats my-web                # Specific container

# 🔎 View processes inside a container
docker top my-web
```

---

### 🚀 Step 6: Copy Files Between Host & Container

```bash
# 📥 Copy FROM container TO your machine
docker cp my-web:/etc/nginx/nginx.conf ./nginx.conf

# 📤 Copy FROM your machine TO container
docker cp ./index.html my-web:/usr/share/nginx/html/index.html

# 💡 This is super useful for debugging!
```

---

# 📦 PART 4 — Docker Images Deep Dive

> **🎯 Goal:** Understand how images work, how layers are cached, and how to manage them.

---

### 🖼️ Step 1: Understand Image Layers

```
An image is built in LAYERS (like a layer cake 🎂):

┌────────────────────────────────┐
│  Layer 5: CMD ["node", "app"]  │  ← Your command      ~0KB
├────────────────────────────────┤
│  Layer 4: COPY . .             │  ← Your source code   ~5MB
├────────────────────────────────┤
│  Layer 3: RUN npm install      │  ← Dependencies       ~150MB
├────────────────────────────────┤
│  Layer 2: COPY package.json    │  ← Dependency file    ~1KB
├────────────────────────────────┤
│  Layer 1: FROM node:18-alpine  │  ← Base OS + Node.js  ~170MB
└────────────────────────────────┘

🔑 KEY INSIGHT:
Each layer is CACHED! If Layers 1-3 haven't changed,
Docker only rebuilds Layers 4-5.
This makes rebuilds INCREDIBLY fast! ⚡
```

---

### 🖼️ Step 2: Manage Images

```bash
# 📋 List all images on your machine
docker images
# REPOSITORY    TAG       IMAGE ID       CREATED        SIZE
# nginx         latest    a1b2c3d4e5f6   2 days ago     187MB
# node          18-alpine 9f8e7d6c5b4a   3 days ago     170MB

# ⬇️ Download (pull) an image
docker pull nginx              # Latest version
docker pull nginx:1.25         # Specific version (tag)
docker pull python:3.11-slim   # Slim = smaller image

# 🏗️ Build an image from Dockerfile
docker build -t my-app:v1 .

# 🏷️ Create a tag (alias) for an image
docker tag my-app:v1 myusername/my-app:v1

# ⬆️ Upload (push) to Docker Hub
docker login                                  # Login first
docker push myusername/my-app:v1              # Push it!

# 🗑️ Remove an image
docker rmi nginx:1.25
docker image prune -a                         # Remove ALL unused images

# 📜 View layer history of an image
docker history nginx

# 💾 Save image as a tar file (for sharing without internet)
docker save -o nginx-backup.tar nginx:latest

# 📂 Load image from a tar file
docker load -i nginx-backup.tar
```

---

### 🖼️ Step 3: Understand Image Tags

```
Image naming format:  REGISTRY / REPOSITORY : TAG
                      ───────── ──────────── ────
Examples:
  docker.io/library/nginx:1.25     ← Full format
  nginx:1.25                       ← Shorthand (Docker Hub)
  nginx:latest                     ← 'latest' = default tag
  nginx:alpine                     ← Alpine-based (smallest ~5MB OS)
  nginx:slim                       ← Slim variant (smaller than default)
  myuser/my-app:v2                 ← Your custom image
  gcr.io/my-project/my-app:prod    ← Google Container Registry
```

> [!TIP]
> 💡 **Always use specific tags** (e.g., `nginx:1.25`) instead of `latest`. This ensures reproducible builds!

---

# 📦 PART 5 — Dockerfile — Building Custom Images

> **🎯 Goal:** Master every Dockerfile instruction and build production-quality images.

---

### 📄 Step 1: Create Your First Dockerfile

A Dockerfile is a text file named `Dockerfile` (no extension) with instructions to build an image.

```dockerfile
# 🟢 Every Dockerfile starts with FROM
FROM python:3.11-slim

# 📁 Set the working directory inside the container
WORKDIR /app

# 📋 Copy dependency file first (for caching!)
COPY requirements.txt .

# ⚙️ Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# 📋 Copy the rest of the application code
COPY . .

# 📢 Document the port (informational only)
EXPOSE 5000

# 🏃 Command to run when container starts
CMD ["python", "app.py"]
```

---

### 📄 Step 2: All Dockerfile Instructions Explained

```
╔════════════════╦═══════════════════════════════════════════════════════╗
║  Instruction   ║  What It Does                                       ║
╠════════════════╬═══════════════════════════════════════════════════════╣
║  FROM          ║  Base image (REQUIRED, must be first)                ║
║  LABEL         ║  Add metadata (author, version, etc.)                ║
║  ENV           ║  Set environment variables (available at runtime)    ║
║  ARG           ║  Build-time variables (NOT available at runtime)     ║
║  WORKDIR       ║  Set working directory (creates if doesn't exist)   ║
║  COPY          ║  Copy files from host → container                   ║
║  ADD           ║  Like COPY + auto-extract tar + download URLs       ║
║  RUN           ║  Execute commands during BUILD                      ║
║  CMD           ║  Default command when container STARTS (overridable)║
║  ENTRYPOINT    ║  Main executable (not easily overridden)            ║
║  EXPOSE        ║  Document the port (doesn't actually open it)       ║
║  VOLUME        ║  Create a mount point for external storage          ║
║  USER          ║  Set which user runs commands                       ║
║  HEALTHCHECK   ║  Define how Docker checks if container is healthy   ║
╚════════════════╩═══════════════════════════════════════════════════════╝
```

---

### 📄 Step 3: Deep Dive into Each Instruction

#### 1️⃣ FROM — Base Image

```dockerfile
# Choose the smallest image that has what you need:
FROM ubuntu:22.04          # Full Ubuntu (~77MB)
FROM python:3.11           # Full Python (~1GB! 😱)
FROM python:3.11-slim      # Slim Python (~120MB ✅)
FROM python:3.11-alpine    # Alpine Python (~50MB ⚡)
FROM node:18-alpine        # Alpine Node.js (~170MB)
FROM nginx:alpine          # Alpine Nginx (~25MB)
FROM scratch               # Empty! Build from zero
```

> [!TIP]
> 💡 **Alpine** images are built on Alpine Linux (~5MB), making them the smallest option. Use them when possible!

#### 2️⃣ ENV vs ARG

```dockerfile
# ENV — Available during build AND runtime
ENV NODE_ENV=production
ENV PORT=3000
# ✅ Can be used: docker run -e PORT=4000 ...

# ARG — Available ONLY during build
ARG APP_VERSION=1.0
# ✅ Can be used: docker build --build-arg APP_VERSION=2.0 .
# ❌ NOT available when container runs
```

#### 3️⃣ COPY vs ADD

```dockerfile
# COPY — Simple, predictable (RECOMMENDED ✅)
COPY package.json ./
COPY . .
COPY --chown=node:node . .        # Copy with ownership

# ADD — Extra features (use only when needed)
ADD https://example.com/file.tar.gz /tmp/   # Downloads URLs
ADD archive.tar.gz /app/                     # Auto-extracts tar
```

#### 4️⃣ CMD vs ENTRYPOINT

```dockerfile
# CMD — Default command (can be overridden by user)
CMD ["python", "app.py"]
# docker run myimage             → runs: python app.py
# docker run myimage bash        → runs: bash (CMD overridden!)

# ENTRYPOINT — Fixed executable (CMD becomes its arguments)
ENTRYPOINT ["python"]
CMD ["app.py"]
# docker run myimage             → runs: python app.py
# docker run myimage test.py     → runs: python test.py
# docker run myimage bash        → runs: python bash ❌
```

> [!IMPORTANT]
> 🔑 **Rule of thumb:**
> - Use **CMD** when users might want to run a different command
> - Use **ENTRYPOINT** when the container should always run one specific program

#### 5️⃣ USER — Security

```dockerfile
# ❌ BAD — Running as root (security risk!)
# By default, Docker runs as root

# ✅ GOOD — Create and use a non-root user
RUN addgroup --system appgroup && \
    adduser --system --ingroup appgroup appuser
USER appuser
```

#### 6️⃣ HEALTHCHECK — Container Health

```dockerfile
HEALTHCHECK --interval=30s --timeout=10s --retries=3 --start-period=15s \
    CMD curl -f http://localhost:3000/health || exit 1

# --interval=30s     → Check every 30 seconds
# --timeout=10s      → Fail if no response in 10 seconds
# --retries=3        → Mark unhealthy after 3 failures
# --start-period=15s → Wait 15s before first check
```

#### 7️⃣ RUN — Optimize Layer Count

```dockerfile
# ❌ BAD — Each RUN creates a new layer
RUN apt-get update
RUN apt-get install -y curl
RUN apt-get install -y wget
RUN rm -rf /var/lib/apt/lists/*

# ✅ GOOD — Combine into one layer
RUN apt-get update && \
    apt-get install -y curl wget && \
    rm -rf /var/lib/apt/lists/*
```

---

### 📄 Step 4: Build an Image

```bash
# 📦 Basic build
docker build -t my-app:v1 .
#  -t       = tag (name:version)
#  .        = build context (current directory)

# 📦 Build with a different Dockerfile
docker build -t my-app:v1 -f Dockerfile.prod .

# 📦 Build with build arguments
docker build -t my-app:v1 --build-arg APP_VERSION=2.0 .

# 📦 Build without cache (fresh build)
docker build -t my-app:v1 --no-cache .

# 📦 Build for a specific platform
docker build -t my-app:v1 --platform linux/amd64 .
```

---

# 📦 PART 6 — Practical Project: Flask App

> **🎯 Goal:** Build and containerize a real Python Flask application step by step.

---

### 🛠️ Step 1: Create the Application

**Create `app.py`:**
```python
from flask import Flask, jsonify
import os

app = Flask(__name__)

@app.route('/')
def home():
    return jsonify({
        "message": "Hello from Docker! 🐳",
        "status": "running",
        "version": os.getenv("APP_VERSION", "1.0")
    })

@app.route('/health')
def health():
    return jsonify({"status": "healthy", "service": "flask-app"})

@app.route('/info')
def info():
    return jsonify({
        "hostname": os.uname().nodename,
        "platform": os.uname().sysname,
        "python_path": os.sys.executable
    })

if __name__ == '__main__':
    port = int(os.getenv('PORT', 5000))
    app.run(host='0.0.0.0', port=port, debug=False)
```

### 🛠️ Step 2: Create Requirements File

**Create `requirements.txt`:**
```
flask==3.0.0
```

### 🛠️ Step 3: Create the Dockerfile

```dockerfile
# Use slim Python image (small + has what we need)
FROM python:3.11-slim

# Set metadata
LABEL maintainer="your-email@example.com"
LABEL description="TaskBoard Flask API"

# Set working directory
WORKDIR /app

# Copy & install dependencies FIRST (for layer caching)
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy application code
COPY app.py .

# Set environment variables
ENV PORT=5000
ENV APP_VERSION=1.0

# Create non-root user for security
RUN addgroup --system appgroup && \
    adduser --system --ingroup appgroup appuser
USER appuser

# Document the port
EXPOSE 5000

# Health check
HEALTHCHECK --interval=30s --timeout=5s \
    CMD curl -f http://localhost:5000/health || exit 1

# Start the app
CMD ["python", "app.py"]
```

### 🛠️ Step 4: Create .dockerignore

```
__pycache__
*.pyc
*.pyo
.git
.gitignore
.env
venv/
*.md
.vscode/
```

### 🛠️ Step 5: Build & Run!

```bash
# 🏗️ Build the image
docker build -t flask-app:v1 .

# ▶️ Run the container
docker run -d -p 5000:5000 --name my-flask flask-app:v1

# 🧪 Test it!
curl http://localhost:5000
# ✅ {"message": "Hello from Docker! 🐳", "status": "running", "version": "1.0"}

curl http://localhost:5000/health
# ✅ {"status": "healthy", "service": "flask-app"}

# 📝 View logs
docker logs my-flask

# 🗑️ Cleanup
docker rm -f my-flask
```

---

# 📦 PART 7 — Docker Volumes & Data Persistence

> **🎯 Goal:** Understand how to persist data so it survives container restarts and deletions.

---

### 💾 Step 1: Understand the Problem

```
❌ WITHOUT Volumes:                   ✅ WITH Volumes:
┌──────────────────┐                ┌──────────────────┐  ┌──────────────┐
│   Container      │                │   Container      │  │   Volume     │
│   ┌──────────┐   │                │   ┌──────────┐   │──│   📁 Data   │
│   │  Data 💾 │   │                │   │ mount pt │   │  │   (safe!)   │
│   └──────────┘   │                │   └──────────┘   │  └──────────────┘
└──────────────────┘                └──────────────────┘
       ↓ docker rm                         ↓ docker rm
    Data is GONE! 😱                    Data is SAFE! ✅
```

---

### 💾 Step 2: Three Types of Volumes

#### 1️⃣ Named Volumes (✅ RECOMMENDED for production)

Docker manages the storage location for you.

```bash
# Create a named volume
docker volume create my-data

# Run container with named volume
docker run -d \
    --name my-db \
    -v my-data:/var/lib/mysql \
    -e MYSQL_ROOT_PASSWORD=secret \
    mysql:8.0

# 💡 Even if you delete the container, data stays in 'my-data' volume!
docker rm -f my-db          # Container gone
docker volume ls            # ✅ Volume still exists!
```

#### 2️⃣ Bind Mounts (✅ RECOMMENDED for development)

YOU choose the exact folder on your host machine.

```bash
# Map your current directory into the container
docker run -d \
    -v $(pwd)/website:/usr/share/nginx/html \
    -p 8080:80 \
    --name dev-web \
    nginx

# 🎯 Edit files locally → changes appear in browser INSTANTLY!
echo "<h1>Hello Docker!</h1>" > ./website/index.html
# 🌐 Refresh http://localhost:8080 → See your changes!
```

#### 3️⃣ tmpfs Mounts (For temporary data in RAM)

```bash
docker run -d --tmpfs /tmp:rw,size=100m nginx
# Data stored in RAM only — gone when container stops
# Use for: sensitive temp files, session data
```

---

### 💾 Step 3: Volume Management Commands

```bash
docker volume create my-data        # 📁 Create volume
docker volume ls                    # 📋 List all volumes
docker volume inspect my-data       # 🔍 See storage details
docker volume rm my-data            # 🗑️ Remove a volume
docker volume prune                 # 🧹 Remove ALL unused volumes
```

---

# 📦 PART 8 — Docker Networking

> **🎯 Goal:** Understand how containers communicate with each other and the outside world.

---

### 🌐 Step 1: Understand Network Types

```
╔═════════════╦══════════════════════════════════════════════════╗
║  Type       ║  Description                                    ║
╠═════════════╬══════════════════════════════════════════════════╣
║  bridge     ║  Default. Containers on same host talk via IPs. ║
║  host       ║  Container shares host's network (no isolation) ║
║  none       ║  No networking at all (fully isolated)          ║
║  overlay    ║  Containers on DIFFERENT hosts communicate      ║
║  macvlan    ║  Container gets its own MAC address on LAN      ║
╚═════════════╩══════════════════════════════════════════════════╝
```

---

### 🌐 Step 2: Create Custom Networks

```bash
# 🏗️ Create a custom bridge network
docker network create app-network

# 📋 List all networks
docker network ls

# 🔍 Inspect a network
docker network inspect app-network
```

---

### 🌐 Step 3: Connect Containers via Network

```bash
# 🗄️ Step A: Start a database on the custom network
docker run -d \
    --name postgres-db \
    --network app-network \
    -e POSTGRES_PASSWORD=secret \
    -e POSTGRES_DB=myapp \
    -v pgdata:/var/lib/postgresql/data \
    postgres:15

# 🌐 Step B: Start a web app on the SAME network
docker run -d \
    --name web-app \
    --network app-network \
    -e DATABASE_URL=postgresql://postgres:secret@postgres-db:5432/myapp \
    -p 3000:3000 \
    my-web-app:v1

# 🎯 KEY INSIGHT: Inside 'app-network', containers can reach
#    each other by NAME! The web app reaches the DB using
#    'postgres-db' as the hostname (not an IP address).
```

> [!IMPORTANT]
> 🔑 **The default bridge network does NOT support DNS by name.** Always create a **custom network** for your apps — it enables automatic DNS resolution between containers!

---

### 🌐 Step 4: Network Management

```bash
docker network create my-net                          # 🏗️ Create
docker network connect my-net existing-container      # 🔗 Connect container
docker network disconnect my-net existing-container   # 🔌 Disconnect
docker network rm my-net                              # 🗑️ Remove
docker network prune                                  # 🧹 Remove unused
```

---

# 📦 PART 9 — Docker Compose

> **🎯 Goal:** Run multi-container applications with a single command using `docker-compose.yml`.

---

### 🎼 Step 1: Understand Why Compose Exists

```
❌ Without Docker Compose (painful! 😰):
$ docker network create app-net
$ docker volume create pgdata
$ docker run -d --name db --network app-net -v pgdata:/data postgres:15
$ docker run -d --name cache --network app-net redis:7
$ docker run -d --name web --network app-net -p 3000:3000 my-app:v1

✅ With Docker Compose (easy! 😊):
$ docker compose up
🎉 Done! All 3 services running!
```

---

### 🎼 Step 2: Write a Complete docker-compose.yml

```yaml
# docker-compose.yml
version: '3.8'

services:
  # ═══════════════════════════════════════
  # 🌐 Web Application
  # ═══════════════════════════════════════
  web:
    build:
      context: ./web
      dockerfile: Dockerfile
    container_name: my-web-app
    ports:
      - "3000:3000"                       # Host:Container
    environment:
      NODE_ENV: production
      DATABASE_URL: postgresql://postgres:secret@db:5432/myapp
      REDIS_URL: redis://cache:6379
    depends_on:
      db:
        condition: service_healthy         # Wait until DB is healthy!
      cache:
        condition: service_started
    volumes:
      - ./web/src:/app/src                 # Bind mount for dev
    networks:
      - app-network
    restart: unless-stopped                # Auto-restart on crash
    healthcheck:
      test: ["CMD", "curl", "-f", "http://localhost:3000/health"]
      interval: 30s
      timeout: 10s
      retries: 3

  # ═══════════════════════════════════════
  # 🗄️ PostgreSQL Database
  # ═══════════════════════════════════════
  db:
    image: postgres:15-alpine
    container_name: postgres-db
    environment:
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: secret
      POSTGRES_DB: myapp
    volumes:
      - pgdata:/var/lib/postgresql/data    # Named volume for persistence
    ports:
      - "5432:5432"
    networks:
      - app-network
    restart: unless-stopped
    healthcheck:
      test: ["CMD-SHELL", "pg_isready -U postgres"]
      interval: 10s
      timeout: 5s
      retries: 5

  # ═══════════════════════════════════════
  # ⚡ Redis Cache
  # ═══════════════════════════════════════
  cache:
    image: redis:7-alpine
    container_name: redis-cache
    ports:
      - "6379:6379"
    volumes:
      - redis-data:/data
    networks:
      - app-network
    restart: unless-stopped

# ═══════════════════════════════════════
# 💾 Named Volumes
# ═══════════════════════════════════════
volumes:
  pgdata:
    driver: local
  redis-data:
    driver: local

# ═══════════════════════════════════════
# 🌐 Networks
# ═══════════════════════════════════════
networks:
  app-network:
    driver: bridge
```

---

### 🎼 Step 3: Docker Compose Commands

```bash
# ▶️ START
docker compose up -d                 # Start in background
docker compose up -d --build         # Rebuild images + start
docker compose up -d --scale web=3   # Run 3 instances of 'web'

# ⏹️ STOP
docker compose down                  # Stop and remove containers
docker compose down -v               # Stop + delete volumes (⚠️ data loss!)
docker compose down --rmi all        # Stop + delete images

# 📋 INFO
docker compose ps                    # List running services
docker compose config               # Validate & view config

# 📝 LOGS
docker compose logs                  # All service logs
docker compose logs -f web           # Follow logs for 'web'
docker compose logs --tail 50        # Last 50 lines

# 🔧 INTERACT
docker compose exec web bash         # Shell into 'web' service
docker compose exec db psql -U postgres  # SQL shell

# 🔄 MANAGE
docker compose restart web           # Restart a service
docker compose build                 # Rebuild without starting
docker compose pull                  # Pull latest images
```

---

# 📦 PART 10 — Docker Best Practices

> **🎯 Goal:** Write production-quality Dockerfiles and optimize your images.

---

### ✨ Best Practice 1: Use Multi-Stage Builds

```dockerfile
# ═══════════════════════════════════════════════
# 🏗️ Stage 1: BUILD (large, has build tools)
# ═══════════════════════════════════════════════
FROM node:18 AS builder
WORKDIR /app
COPY package*.json ./
RUN npm ci                     # Install ALL dependencies
COPY . .
RUN npm run build              # Compile → creates /app/dist

# ═══════════════════════════════════════════════
# 🚀 Stage 2: PRODUCTION (tiny, only runtime)
# ═══════════════════════════════════════════════
FROM nginx:alpine
COPY --from=builder /app/dist /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
```

```
📊 Size comparison:
   Stage 1 (node:18 + npm + code + node_modules):  ~1.2 GB 😱
   Stage 2 (nginx:alpine + built files only):      ~25 MB 🎉
   
   Reduction: 98%! 🔥
```

---

### ✨ Best Practice 2: Optimize Layer Caching

```dockerfile
# ❌ BAD ORDER — Any code change rebuilds npm install
COPY . .
RUN npm install

# ✅ GOOD ORDER — npm install is cached if package.json unchanged
COPY package*.json ./          # Changes rarely
RUN npm ci                     # Cached! ⚡
COPY . .                       # Changes often (only this rebuilds)
```

---

### ✨ Best Practice 3: Minimize Image Size

```dockerfile
# ❌ BAD — Many separate RUN commands = many layers
RUN apt-get update
RUN apt-get install -y curl
RUN apt-get install -y wget
RUN rm -rf /var/lib/apt/lists/*

# ✅ GOOD — Single layer, cleaned up in same layer
RUN apt-get update && \
    apt-get install -y --no-install-recommends curl wget && \
    rm -rf /var/lib/apt/lists/*
```

---

### ✨ Best Practice 4: Security Checklist

```
✅ Run as non-root user                    USER appuser
✅ Use specific image tags                 FROM node:18.19.0-alpine
✅ Scan for vulnerabilities                docker scout cves my-app:v1
✅ Use .dockerignore                       Exclude .git, .env, node_modules
✅ Don't store secrets in images           Use runtime env vars or secrets
✅ Use read-only filesystem when possible  --read-only flag
✅ Set resource limits                     --memory=256m --cpus=1
✅ Use HEALTHCHECK                         Monitor container health
```

---

### ✨ Best Practice 5: System Cleanup

```bash
# 📊 Check disk usage
docker system df
# TYPE          TOTAL   ACTIVE   SIZE     RECLAIMABLE
# Images        15      5        8.5GB    5.2GB (61%)
# Containers    8       3        120MB    80MB (66%)
# Volumes       10      4        2.1GB    800MB (38%)

# 🧹 Remove ALL unused data (images, containers, volumes, networks)
docker system prune -a --volumes
# ⚠️ WARNING: This removes everything that's not currently in use!
```

---

# 📦 PART 11 — Docker Internals: How Docker Actually Works

> **🎯 Goal:** Understand what happens under the hood — namespaces, cgroups, and the Docker daemon.

---

### 🔬 Step 1: Linux Namespaces (Isolation)

Docker containers are **NOT virtual machines**. They're **isolated processes** running on the host OS. The isolation comes from **Linux Namespaces**:

| # | Namespace | What It Isolates | Effect |
|---|-----------|-----------------|--------|
| 1 | 🔢 **PID** | Process IDs | Container sees its own PID 1 |
| 2 | 🌐 **NET** | Network interfaces, IPs, routes | Each container gets its own IP |
| 3 | 📁 **MNT** | Filesystem mount points | Each container sees its own `/` |
| 4 | 🏷️ **UTS** | Hostname | Each container has its own hostname |
| 5 | 💬 **IPC** | Inter-process communication | Isolated shared memory |
| 6 | 👤 **USER** | User/Group IDs | Root in container ≠ root on host |
| 7 | 📊 **CGROUP** | cgroup visibility | Container sees only its own limits |

```bash
# 🔍 See namespaces of a running container:
PID=$(docker inspect --format '{{.State.Pid}}' my-container)
ls -la /proc/$PID/ns/
```

---

### 🔬 Step 2: Control Groups (cgroups) — Resource Limits

**cgroups** control HOW MUCH resources a container can use.

```bash
docker run -d \
    --name limited-app \
    --memory="256m"          # 📊 Max 256MB RAM
    --memory-swap="512m"     # 💾 Max 512MB RAM+swap
    --cpus="1.5"             # ⚡ Use at most 1.5 CPU cores
    --cpu-shares=512         # ⚖️ Relative CPU priority
    --pids-limit=100         # 🔢 Max 100 processes
    nginx
```

```
🔑 KEY BEHAVIOR:
   CPU limit hit    → Container is THROTTLED (slowed, NOT killed) 🐌
   Memory limit hit → Container is KILLED (OOMKilled) 💀
```

---

### 🔬 Step 3: Union Filesystem (OverlayFS)

```
📚 Image Layers (Read-Only):        📝 Container Layer (Read-Write):
┌──────────────────────────┐       ┌──────────────────────────┐
│ Layer 4: COPY app code   │       │ 📝 Writable Layer        │
├──────────────────────────┤       │   (thin! only changes)   │
│ Layer 3: RUN npm install │       ├──────────────────────────┤
├──────────────────────────┤       │ 📚 Image Layers (shared) │
│ Layer 2: COPY pkg.json   │       │   (read-only, reused!)   │
├──────────────────────────┤       └──────────────────────────┘
│ Layer 1: FROM node:alpine│
└──────────────────────────┘

💡 100 containers from same image share ALL read-only layers!
   Each container adds only its thin writable layer (~KB to MB)
```

**Copy-on-Write (COW):**
- **Read** → reads from image layer (no copy needed)
- **Modify** → Docker copies file to writable layer first, then modifies
- **Delete** → creates a "whiteout" marker (original still in image layer)

---

### 🔬 Step 4: Docker Daemon Architecture

```
You (CLI)  →  REST API  →  dockerd (Daemon)  →  containerd  →  runc  →  Linux Kernel

🖥️ docker CLI     → Sends commands via REST API (tcp/unix socket)
🔧 dockerd         → Main daemon, manages images, volumes, networks
📦 containerd      → Container lifecycle manager (start/stop/pause)
⚙️ runc            → Low-level OCI tool that sets up namespaces + cgroups
📜 OCI Standard    → Open Container Initiative — industry-wide standard
```

---

### 🔬 Step 5: Docker Networking Deep Dive

```
Default Bridge Network:
┌────────────────────────────────────────────────┐
│  🖥️ Host Machine                                │
│  ┌───────────────────────────┐                  │
│  │   🌉 docker0 (bridge)     │  172.17.0.1     │
│  │   ┌─────┐  ┌─────┐       │                  │
│  │   │veth1│  │veth2│       │  Virtual Ethernet│
│  │   └──┬──┘  └──┬──┘       │                  │
│  └──────┼────────┼──────────┘                  │
│   ┌─────▼──┐ ┌───▼────┐                        │
│   │  📦 C1 │ │  📦 C2 │                        │
│   │.0.2    │ │.0.3    │                        │
│   └────────┘ └────────┘                        │
│  🔥 iptables NAT rules handle port mapping     │
└────────────────────────────────────────────────┘

Custom networks → DNS at 127.0.0.11
Containers resolve each other by name automatically!
```

---

# 📦 PART 12 — Docker Interview Questions & Answers

> **🎯 Goal:** Prepare for Docker interview questions from beginner to expert level.

---

### 🟢 Beginner Questions

---

**Q1: What is Docker and why is it used?**

> Docker is an open-source containerization platform that packages applications with all their dependencies into containers. Benefits: consistent environments everywhere (solves "works on my machine"), process isolation, lightweight (seconds to start vs minutes for VMs), portability, and perfect for microservices.

---

**Q2: What is the difference between a Docker Image and a Container?**

| | Docker Image | Docker Container |
|---|---|---|
| What | Read-only **template/blueprint** | **Running instance** of an image |
| Analogy | Like a **class** in programming | Like an **object** (instance) |
| Created by | `Dockerfile` + `docker build` | `docker run` |
| State | Immutable (can't change) | Has writable layer |
| Storage | Registry / local cache | Exists on host |

---

**Q3: What is the difference between CMD and ENTRYPOINT?**

> **CMD** = default command/arguments, easily overridden at runtime.
> **ENTRYPOINT** = main executable, not easily overridden.
> Used together: `ENTRYPOINT ["python"]` + `CMD ["app.py"]` → `docker run myimage` runs `python app.py`, but `docker run myimage test.py` runs `python test.py`.

---

**Q4: What is the difference between COPY and ADD?**

> **COPY** = simple file copy (recommended for most cases).
> **ADD** = COPY + auto-extracts tar files + can download URLs.
> Use COPY unless you specifically need ADD's features.

---

**Q5: What is Docker Compose?**

> A tool for defining and running multi-container applications using a YAML file. Instead of running many `docker run` commands, define all services in `docker-compose.yml` and run `docker compose up`. Handles networking, volumes, dependencies automatically.

---

**Q6: How does Docker achieve container isolation?**

> Three Linux kernel features: **Namespaces** (PID, NET, MNT, UTS, IPC, USER isolation), **cgroups** (CPU, memory, I/O limits), and **Union Filesystem/OverlayFS** (layered copy-on-write filesystem).

---

### 🟡 Intermediate Questions

---

**Q7: What are Docker volumes? Name the types.**

> Volumes persist data beyond container lifecycle. Three types:
> 1. **Named Volumes** — Docker-managed, best for production
> 2. **Bind Mounts** — Maps host folder into container, best for dev
> 3. **tmpfs Mounts** — In-memory only, for temporary/sensitive data

---

**Q8: What is a multi-stage build?**

> Uses multiple `FROM` statements in one Dockerfile. Build in one stage (with build tools), copy only artifacts to a minimal runtime stage. Result: dramatically smaller images (e.g., 1GB → 25MB), fewer vulnerabilities, no build tools in production.

---

**Q9: Explain Docker image layer caching.**

> Each Dockerfile instruction creates a cached layer. If instruction + context haven't changed, cached layer is reused. **Once one layer's cache is invalidated, all subsequent layers rebuild.** Optimization: copy dependency files first, source code last.

---

**Q10: Difference between `docker stop` and `docker kill`?**

> - **`docker stop`** → SIGTERM first (graceful shutdown), waits 10s, then SIGKILL
> - **`docker kill`** → SIGKILL immediately (force kill, no cleanup)
> Always prefer `docker stop` in production.

---

**Q11: What is a `.dockerignore` file?**

> Lists files/directories excluded from the build context. Prevents copying unnecessary files (node_modules, .git, .env). Benefits: faster builds, smaller context, better security, smaller images.

---

**Q12: How does Docker networking work?**

> Network types: **bridge** (default, containers on same host), **host** (shares host network), **none** (no networking), **overlay** (multi-host for Swarm), **macvlan** (assigns MAC address). Custom bridge networks are recommended for DNS resolution by container name.

---

### 🔴 Advanced Questions

---

**Q13: What happens when you run `docker run nginx`?**

> 1️⃣ CLI sends REST API request to Docker daemon
> 2️⃣ Daemon checks local cache for `nginx` image → pulls if not found
> 3️⃣ Daemon tells containerd to create container
> 4️⃣ containerd uses runc to set up namespaces + cgroups + OverlayFS
> 5️⃣ runc starts the container process (PID 1 inside container)
> 6️⃣ Daemon sets up networking (bridge, veth pair, iptables rules)
> 7️⃣ Container is running!

---

**Q14: Explain Docker's Copy-on-Write (COW) strategy.**

> Image layers are read-only, shared across all containers. Each container gets a thin writable layer. **Read** = reads from image layer (no copy). **Modify** = file copied to writable layer first, then modified there. **Delete** = whiteout marker created. Benefits: massive storage savings, instant container startup.

---

**Q15: How do Docker container logs work?**

> Containers write to stdout/stderr. Docker captures output via the logging driver. Default: `json-file` (stored at `/var/lib/docker/containers/<id>/<id>-json.log`). Other drivers: syslog, journald, fluentd, awslogs, gcplogs, splunk. Configure log rotation: `{"log-driver":"json-file","log-opts":{"max-size":"10m","max-file":"3"}}`.

---

**Q16: Difference between `docker exec` and `docker attach`?**

| | `docker exec` | `docker attach` |
|---|---|---|
| Action | Starts **new process** | Attaches to **existing** PID 1 |
| Multiple sessions | ✅ Yes | ❌ No |
| Exit behavior | Container keeps running | May stop container |
| Use case | Debugging (almost always) | Rarely used |

---

**Q17: How to optimize Docker image size?**

> 1. Use Alpine/slim base images
> 2. Multi-stage builds
> 3. Combine RUN commands (fewer layers)
> 4. Copy deps file first (caching)
> 5. Use `.dockerignore`
> 6. `--no-install-recommends` for apt
> 7. Clean up in same RUN layer
> 8. Remove caches (`--no-cache-dir` for pip)
> 9. Use specific image tags
> 10. Scan with `docker scout`

---

**Q18: Explain Docker container security best practices.**

> 1. Run as non-root user (`USER appuser`)
> 2. Use read-only filesystem (`--read-only`)
> 3. Drop all capabilities (`--cap-drop ALL`)
> 4. Don't store secrets in images (use runtime env vars or secrets management)
> 5. Scan images for vulnerabilities
> 6. Use specific image tags (not `latest`)
> 7. Set resource limits (memory, CPU)
> 8. Use content trust for signed images

---

**Q19: What is Docker overlay network?**

> Overlay networks enable communication between containers running on **different Docker hosts** (multiple machines). Used in Docker Swarm and Kubernetes. Uses VXLAN encapsulation to tunnel traffic between hosts. Each container gets a virtual IP that works across the cluster.

---

**Q20: How to troubleshoot a container that keeps crashing?**

> 1️⃣ `docker logs <container>` — check application output
> 2️⃣ `docker logs --previous <container>` — logs from previous crash
> 3️⃣ `docker inspect <container>` — check State.ExitCode, State.OOMKilled
> 4️⃣ `docker stats` — check if hitting memory/CPU limits
> 5️⃣ `docker run --entrypoint sh <image>` — override entrypoint to debug
> 6️⃣ `docker events` — watch real-time Docker events
> 7️⃣ Check health check configuration if using HEALTHCHECK

---

## 📋 Complete Docker Cheat Sheet

```
╔══════════════════════════════════════════════════════════════════╗
║                    🐳 DOCKER CHEAT SHEET                         ║
╠══════════════════════════════════════════════════════════════════╣
║                                                                  ║
║  📦 IMAGES                                                       ║
║  ─────────────────────────────────────────────────────────────   ║
║  docker images                    List images                    ║
║  docker pull IMG:TAG              Download image                 ║
║  docker push IMG:TAG              Upload image                   ║
║  docker build -t NAME:TAG .       Build image                    ║
║  docker rmi IMG                   Remove image                   ║
║  docker tag SRC DEST              Create tag/alias               ║
║  docker history IMG               View layers                    ║
║  docker save -o file.tar IMG      Export as tar                  ║
║  docker load -i file.tar          Import from tar                ║
║  docker image prune -a            Remove unused                  ║
║                                                                  ║
║  📦 CONTAINERS                                                   ║
║  ─────────────────────────────────────────────────────────────   ║
║  docker run -d -p H:C --name N IMG   Run container               ║
║  docker run -it IMG bash             Interactive mode             ║
║  docker run --rm IMG                 Auto-remove on exit          ║
║  docker ps / docker ps -a            List running / all           ║
║  docker stop CONTAINER               Graceful stop                ║
║  docker start CONTAINER              Start stopped                ║
║  docker restart CONTAINER            Restart                      ║
║  docker rm CONTAINER                 Remove container             ║
║  docker rm -f $(docker ps -aq)       Remove ALL                   ║
║  docker logs -f CONTAINER            Follow logs                  ║
║  docker exec -it CONTAINER bash      Shell access                 ║
║  docker inspect CONTAINER            Full JSON details            ║
║  docker stats                        Resource usage               ║
║  docker cp SRC DEST                  Copy files                   ║
║  docker container prune              Remove stopped               ║
║                                                                  ║
║  💾 VOLUMES                                                      ║
║  ─────────────────────────────────────────────────────────────   ║
║  docker volume create NAME           Create volume                ║
║  docker volume ls                    List volumes                 ║
║  docker volume inspect NAME          Details                      ║
║  docker volume rm NAME               Remove volume                ║
║  docker volume prune                 Remove unused                ║
║                                                                  ║
║  🌐 NETWORKS                                                     ║
║  ─────────────────────────────────────────────────────────────   ║
║  docker network create NAME          Create network               ║
║  docker network ls                   List networks                ║
║  docker network inspect NAME         Details                      ║
║  docker network connect NET CONT     Connect container            ║
║  docker network disconnect NET CONT  Disconnect container         ║
║  docker network rm NAME              Remove network               ║
║                                                                  ║
║  🎼 DOCKER COMPOSE                                               ║
║  ─────────────────────────────────────────────────────────────   ║
║  docker compose up -d                Start all services            ║
║  docker compose up -d --build        Build + start                 ║
║  docker compose down                 Stop all                      ║
║  docker compose down -v              Stop + remove volumes         ║
║  docker compose ps                   List services                 ║
║  docker compose logs -f              Follow logs                   ║
║  docker compose exec SVC bash        Shell into service            ║
║  docker compose build                Rebuild images                ║
║                                                                  ║
║  🧹 SYSTEM CLEANUP                                               ║
║  ─────────────────────────────────────────────────────────────   ║
║  docker system df                    Check disk usage              ║
║  docker system prune -a --volumes    Remove ALL unused             ║
║                                                                  ║
╚══════════════════════════════════════════════════════════════════╝
```

---

## 🗺️ Docker Learning Roadmap

```
📅 WEEK 1: Docker Foundations
├── Day 1: ✅ Install Docker, run hello-world
├── Day 2: ✅ docker run, ps, stop, start, rm
├── Day 3: ✅ docker logs, exec, inspect, stats
├── Day 4: ✅ Pull/push images, understand tags
├── Day 5: ✅ Write your first Dockerfile
├── Day 6: ✅ Build & run your Flask app
└── Day 7: ✅ Practice all commands from memory

📅 WEEK 2: Docker Intermediate
├── Day 1: ✅ Named Volumes & Bind Mounts
├── Day 2: ✅ Docker Networking (custom bridge)
├── Day 3: ✅ Connect 2+ containers via network
├── Day 4: ✅ Docker Compose basics
├── Day 5: ✅ Build a 3-service app with Compose
├── Day 6: ✅ Compose commands (scale, logs, exec)
└── Day 7: ✅ Practice: Build a web+db+cache app

📅 WEEK 3: Docker Advanced
├── Day 1: ✅ Multi-stage builds
├── Day 2: ✅ Image optimization & .dockerignore
├── Day 3: ✅ Security best practices (non-root, scanning)
├── Day 4: ✅ HEALTHCHECK and restart policies
├── Day 5: ✅ Docker layer caching strategies
├── Day 6: ✅ ENV vs ARG, CMD vs ENTRYPOINT
└── Day 7: ✅ Practice: Optimize a real-world Dockerfile

📅 WEEK 4: Docker Internals & Interview Prep
├── Day 1: ✅ Linux namespaces & cgroups
├── Day 2: ✅ OverlayFS & copy-on-write
├── Day 3: ✅ Docker daemon architecture
├── Day 4: ✅ Docker networking deep dive
├── Day 5: ✅ Study interview questions (Q1-Q10)
├── Day 6: ✅ Study interview questions (Q11-Q20)
└── Day 7: ✅ Mock interview practice!
```

---

> [!TIP]
> 🎉 **Congratulations!** You've completed the Docker guide! Ready for the next step?
> 
> 👉 Continue to [**Part 2: Kubernetes Guide**](file:///C:/Users/Mojammil%20Husain/.gemini/antigravity/brain/810210d9-bd04-4967-a796-7552ae205906/part2_kubernetes_guide.md) to learn container orchestration!
