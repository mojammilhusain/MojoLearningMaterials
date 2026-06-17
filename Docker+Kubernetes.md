# 🚀 Docker + Kubernetes Combined Project
## Part 3 of 3 | Build & Deploy an Angular Full-Stack App

> [!NOTE]
> 📘 **Series Navigation**
>
> 📕 [Part 1: Docker Guide](file:///C:/Users/Mojammil%20Husain/.gemini/antigravity/brain/810210d9-bd04-4967-a796-7552ae205906/part1_docker_guide.md)
> 📘 [Part 2: Kubernetes Guide](file:///C:/Users/Mojammil%20Husain/.gemini/antigravity/brain/810210d9-bd04-4967-a796-7552ae205906/part2_kubernetes_guide.md)
> 📗 **You are here → Part 3: Combined Project**

---

## 📚 What's Inside This Project?

| # | Section | Topic | Level |
|---|---------|-------|-------|
| 🏗️ | **Section 1** | Project Overview & Architecture | ⬜⬜🟩🟩🟩🟩🟩🟩🟩🟩 |
| 💻 | **Section 2** | Backend Source Code (Node.js + Express) | ⬜⬜⬜🟩🟩🟩🟩🟩🟩🟩 |
| 🎨 | **Section 3** | Frontend Source Code (Angular 17) | ⬜⬜⬜⬜🟩🟩🟩🟩🟩🟩 |
| 🐳 | **Section 4** | Dockerizing the Application | ⬜⬜⬜⬜⬜🟩🟩🟩🟩🟩 |
| ☸️ | **Section 5** | Kubernetes Manifests (14 YAML files) | ⬜⬜⬜⬜⬜⬜🟩🟩🟩🟩 |
| 🚀 | **Section 6** | Step-by-Step Deployment Guide | ⬜⬜⬜⬜⬜⬜⬜🟩🟩🟩 |
| 📋 | **Section 7** | Skills Checklist | ⬜⬜⬜⬜⬜⬜⬜⬜🟩🟩 |
| 🏋️ | **Section 8** | Practice Challenges (10 challenges) | ⬜⬜⬜⬜⬜⬜⬜⬜⬜🟩 |
| 🔧 | **Section 9** | Troubleshooting | ⬜⬜⬜⬜⬜⬜⬜⬜⬜🟩 |

---

# 🏗️ SECTION 1 — Project Overview & Architecture

---

### 🎯 Project: **TaskBoard** — A Kanban Task Board

A beautiful, full-stack Kanban board to manage tasks across three columns: **To Do**, **In Progress**, and **Done**.

---

### 🏗️ Step 1: Architecture Diagram

```
╔══════════════════════════════════════════════════════════════════╗
║                   ☸️ TaskBoard Architecture                       ║
║                                                                  ║
║              🌐 User Browser                                     ║
║                    │                                             ║
║           ┌────────▼────────┐                                    ║
║           │  🚪 Ingress     │   Routes external traffic          ║
║           │  Controller     │                                    ║
║           └───┬─────────┬───┘                                    ║
║               │ /       │ /api                                   ║
║     ┌─────────▼──┐  ┌───▼──────────┐                            ║
║     │ 🎨 Frontend │  │ ⚙️ Backend    │                            ║
║     │ Angular 17  │  │ Node.js API  │                            ║
║     │ + Nginx     │  │ + Express    │                            ║
║     │ 2 replicas  │  │ 2 replicas   │                            ║
║     └────────────┘  │ + HPA (auto) │                            ║
║                     └──┬───────┬───┘                            ║
║                        │       │                                 ║
║              ┌─────────▼──┐ ┌──▼──────────┐                     ║
║              │ 🗄️ Postgres │ │ ⚡ Redis     │                     ║
║              │ Database    │ │ Cache       │                     ║
║              │ + PVC       │ │             │                     ║
║              └────────────┘ └─────────────┘                     ║
╚══════════════════════════════════════════════════════════════════╝
```

---

### 🏗️ Step 2: Tech Stack

| Layer | Technology | Version | Purpose |
|-------|-----------|---------|---------|
| 🎨 Frontend | Angular | 17+ | Kanban board UI |
| 🎨 Web Server | Nginx | Alpine | Serve Angular + proxy API |
| ⚙️ Backend | Node.js + Express | 18 LTS | REST API |
| 🗄️ Database | PostgreSQL | 15 | Data persistence |
| ⚡ Cache | Redis | 7 | Response caching |
| 🐳 Containerization | Docker + Compose | Latest | Local development |
| ☸️ Orchestration | Kubernetes + Minikube | Latest | Production deployment |

---

### 🏗️ Step 3: Project Folder Structure

```
taskboard/
├── 📁 backend/
│   ├── 📄 package.json          ← Dependencies
│   ├── 📄 server.js             ← Express API (CRUD + health + stats)
│   ├── 📄 Dockerfile            ← Backend container image
│   └── 📄 .dockerignore         ← Exclude node_modules from build
│
├── 📁 frontend/
│   ├── 📁 src/
│   │   ├── 📁 app/
│   │   │   ├── 📄 app.component.ts    ← Main Kanban board component
│   │   │   ├── 📄 app.config.ts       ← App configuration
│   │   │   └── 📄 task.service.ts     ← HTTP service for API calls
│   │   ├── 📄 index.html              ← HTML entry point
│   │   ├── 📄 main.ts                 ← Angular bootstrap
│   │   └── 📄 styles.css              ← Dark theme CSS
│   ├── 📄 angular.json                ← Angular CLI config
│   ├── 📄 package.json                ← Angular dependencies
│   ├── 📄 tsconfig.json               ← TypeScript config
│   ├── 📄 tsconfig.app.json           ← App-specific TS config
│   ├── 📄 nginx.conf                  ← Nginx config (serve + proxy)
│   └── 📄 Dockerfile                  ← Multi-stage build!
│
├── 📁 k8s/                            ← Kubernetes manifests
│   ├── 📄 namespace.yaml
│   ├── 📁 postgres/                   ← Database layer
│   │   ├── 📄 secret.yaml
│   │   ├── 📄 pvc.yaml
│   │   ├── 📄 deployment.yaml
│   │   └── 📄 service.yaml
│   ├── 📁 redis/                      ← Cache layer
│   │   ├── 📄 deployment.yaml
│   │   └── 📄 service.yaml
│   ├── 📁 backend/                    ← API layer
│   │   ├── 📄 configmap.yaml
│   │   ├── 📄 deployment.yaml
│   │   └── 📄 service.yaml
│   ├── 📁 frontend/                   ← UI layer
│   │   ├── 📄 deployment.yaml
│   │   └── 📄 service.yaml
│   ├── 📄 ingress.yaml
│   ├── 📄 hpa.yaml
│   └── 📄 network-policy.yaml
│
└── 📄 docker-compose.yml              ← Local dev environment
```

---

# 💻 SECTION 2 — Backend Source Code

---

### ⚙️ Step 1: Create `backend/package.json`

```json
{
  "name": "taskboard-backend",
  "version": "1.0.0",
  "description": "TaskBoard REST API",
  "scripts": {
    "start": "node server.js"
  },
  "dependencies": {
    "express": "^4.18.2",
    "pg": "^8.11.3",
    "redis": "^4.6.10",
    "cors": "^2.8.5"
  }
}
```

---

### ⚙️ Step 2: Create `backend/server.js`

```javascript
const express = require('express');
const { Pool } = require('pg');
const { createClient } = require('redis');
const cors = require('cors');

const app = express();
app.use(cors());
app.use(express.json());

// ═══════════════════════════════════════
// 🗄️ PostgreSQL Connection
// ═══════════════════════════════════════
const pool = new Pool({
  host: process.env.DB_HOST || 'localhost',
  port: parseInt(process.env.DB_PORT || '5432'),
  database: process.env.DB_NAME || 'taskboard',
  user: process.env.DB_USER || 'postgres',
  password: process.env.DB_PASSWORD || 'postgres',
});

// ═══════════════════════════════════════
// ⚡ Redis Connection
// ═══════════════════════════════════════
let redisClient;
(async () => {
  redisClient = createClient({
    url: `redis://${process.env.REDIS_HOST || 'localhost'}:${process.env.REDIS_PORT || 6379}`
  });
  redisClient.on('error', err => console.log('Redis Error:', err));
  await redisClient.connect();
  console.log('✅ Connected to Redis');
})();

// ═══════════════════════════════════════
// 📋 Initialize Database Table
// ═══════════════════════════════════════
async function initDB() {
  await pool.query(`
    CREATE TABLE IF NOT EXISTS tasks (
      id SERIAL PRIMARY KEY,
      title VARCHAR(255) NOT NULL,
      description TEXT DEFAULT '',
      status VARCHAR(50) DEFAULT 'todo',
      priority VARCHAR(20) DEFAULT 'medium',
      created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
    )
  `);
  console.log('✅ Database initialized');
}
initDB();

// ═══════════════════════════════════════
// 💓 Health Check Endpoint
// ═══════════════════════════════════════
app.get('/api/health', async (req, res) => {
  try {
    await pool.query('SELECT 1');
    res.json({
      status: 'healthy',
      db: 'connected',
      redis: redisClient.isReady ? 'connected' : 'disconnected',
      timestamp: new Date().toISOString()
    });
  } catch (err) {
    res.status(500).json({ status: 'unhealthy', error: err.message });
  }
});

// ═══════════════════════════════════════
// 📋 GET /api/tasks — List all tasks
// ═══════════════════════════════════════
app.get('/api/tasks', async (req, res) => {
  try {
    // Check Redis cache first
    const cached = await redisClient.get('tasks');
    if (cached) {
      return res.json(JSON.parse(cached));
    }
    // Cache miss — query database
    const result = await pool.query('SELECT * FROM tasks ORDER BY created_at DESC');
    // Store in Redis for 60 seconds
    await redisClient.setEx('tasks', 60, JSON.stringify(result.rows));
    res.json(result.rows);
  } catch (err) {
    res.status(500).json({ error: err.message });
  }
});

// ═══════════════════════════════════════
// ➕ POST /api/tasks — Create a new task
// ═══════════════════════════════════════
app.post('/api/tasks', async (req, res) => {
  try {
    const { title, description, priority } = req.body;
    if (!title || !title.trim()) {
      return res.status(400).json({ error: 'Title is required' });
    }
    const result = await pool.query(
      'INSERT INTO tasks (title, description, priority) VALUES ($1, $2, $3) RETURNING *',
      [title.trim(), description || '', priority || 'medium']
    );
    await redisClient.del('tasks'); // Invalidate cache
    res.status(201).json(result.rows[0]);
  } catch (err) {
    res.status(500).json({ error: err.message });
  }
});

// ═══════════════════════════════════════
// ✏️ PUT /api/tasks/:id — Update a task
// ═══════════════════════════════════════
app.put('/api/tasks/:id', async (req, res) => {
  try {
    const { title, description, status, priority } = req.body;
    const result = await pool.query(
      'UPDATE tasks SET title=$1, description=$2, status=$3, priority=$4 WHERE id=$5 RETURNING *',
      [title, description, status, priority, req.params.id]
    );
    await redisClient.del('tasks'); // Invalidate cache
    if (result.rows.length === 0) {
      return res.status(404).json({ error: 'Task not found' });
    }
    res.json(result.rows[0]);
  } catch (err) {
    res.status(500).json({ error: err.message });
  }
});

// ═══════════════════════════════════════
// 🗑️ DELETE /api/tasks/:id — Delete a task
// ═══════════════════════════════════════
app.delete('/api/tasks/:id', async (req, res) => {
  try {
    const result = await pool.query(
      'DELETE FROM tasks WHERE id=$1 RETURNING *', [req.params.id]
    );
    await redisClient.del('tasks'); // Invalidate cache
    if (result.rows.length === 0) {
      return res.status(404).json({ error: 'Task not found' });
    }
    res.json({ message: 'Task deleted', task: result.rows[0] });
  } catch (err) {
    res.status(500).json({ error: err.message });
  }
});

// ═══════════════════════════════════════
// 📊 GET /api/stats — Task statistics
// ═══════════════════════════════════════
app.get('/api/stats', async (req, res) => {
  try {
    const result = await pool.query(`
      SELECT
        COUNT(*) as total,
        COUNT(*) FILTER (WHERE status='todo') as todo,
        COUNT(*) FILTER (WHERE status='in-progress') as in_progress,
        COUNT(*) FILTER (WHERE status='done') as done
      FROM tasks
    `);
    res.json(result.rows[0]);
  } catch (err) {
    res.status(500).json({ error: err.message });
  }
});

// ═══════════════════════════════════════
// 🚀 Start Server
// ═══════════════════════════════════════
const PORT = process.env.PORT || 3000;
app.listen(PORT, '0.0.0.0', () => {
  console.log(`🚀 TaskBoard API running on port ${PORT}`);
});
```

---

### ⚙️ Step 3: Create `backend/.dockerignore`

```
node_modules
npm-debug.log
.git
.env
.DS_Store
```

---

# 🎨 SECTION 3 — Frontend Source Code (Angular 17)

---

### 🎨 Step 1: Create `frontend/package.json`

```json
{
  "name": "taskboard-frontend",
  "version": "1.0.0",
  "scripts": {
    "ng": "ng",
    "start": "ng serve",
    "build": "ng build --configuration production"
  },
  "dependencies": {
    "@angular/animations": "^17.0.0",
    "@angular/common": "^17.0.0",
    "@angular/compiler": "^17.0.0",
    "@angular/core": "^17.0.0",
    "@angular/forms": "^17.0.0",
    "@angular/platform-browser": "^17.0.0",
    "@angular/platform-browser-dynamic": "^17.0.0",
    "@angular/router": "^17.0.0",
    "rxjs": "^7.8.0",
    "tslib": "^2.6.0",
    "zone.js": "^0.14.0"
  },
  "devDependencies": {
    "@angular-devkit/build-angular": "^17.0.0",
    "@angular/cli": "^17.0.0",
    "@angular/compiler-cli": "^17.0.0",
    "typescript": "~5.2.0"
  }
}
```

---

### 🎨 Step 2: Create `frontend/angular.json`

```json
{
  "$schema": "./node_modules/@angular/cli/lib/config/schema.json",
  "version": 1,
  "newProjectRoot": "projects",
  "projects": {
    "taskboard": {
      "projectType": "application",
      "root": "",
      "sourceRoot": "src",
      "architect": {
        "build": {
          "builder": "@angular-devkit/build-angular:application",
          "options": {
            "outputPath": "dist/taskboard",
            "index": "src/index.html",
            "browser": "src/main.ts",
            "tsConfig": "tsconfig.app.json",
            "styles": ["src/styles.css"],
            "scripts": []
          },
          "configurations": {
            "production": {
              "budgets": [
                { "type": "initial", "maximumWarning": "500kB", "maximumError": "1MB" }
              ],
              "outputHashing": "all"
            },
            "development": {
              "optimization": false,
              "extractLicenses": false,
              "sourceMap": true
            }
          },
          "defaultConfiguration": "production"
        },
        "serve": {
          "builder": "@angular-devkit/build-angular:dev-server",
          "configurations": {
            "production": { "buildTarget": "taskboard:build:production" },
            "development": { "buildTarget": "taskboard:build:development" }
          },
          "defaultConfiguration": "development"
        }
      }
    }
  }
}
```

---

### 🎨 Step 3: Create TypeScript Configs

**`frontend/tsconfig.json`:**
```json
{
  "compileOnSave": false,
  "compilerOptions": {
    "outDir": "./dist/out-tsc",
    "forceConsistentCasingInFileNames": true,
    "strict": true,
    "noImplicitOverride": true,
    "noPropertyAccessFromIndexSignature": true,
    "noImplicitReturns": true,
    "noFallthroughCasesInSwitch": true,
    "sourceMap": true,
    "declaration": false,
    "downlevelIteration": true,
    "experimentalDecorators": true,
    "moduleResolution": "node",
    "importHelpers": true,
    "target": "ES2022",
    "module": "ES2022",
    "useDefineForClassFields": false,
    "lib": ["ES2022", "dom"]
  },
  "angularCompilerOptions": {
    "enableI18nLegacyMessageIdFormat": false,
    "strictInjectionParameters": true,
    "strictInputAccessModifiers": true,
    "strictTemplates": true
  }
}
```

**`frontend/tsconfig.app.json`:**
```json
{
  "extends": "./tsconfig.json",
  "compilerOptions": {
    "outDir": "./out-tsc/app",
    "types": []
  },
  "files": ["src/main.ts"],
  "include": ["src/**/*.d.ts", "src/**/*.ts"]
}
```

---

### 🎨 Step 4: Create `frontend/src/index.html`

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="TaskBoard — A modern Kanban task manager built with Angular, Docker, and Kubernetes">
  <title>TaskBoard — Kanban Manager</title>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
</head>
<body>
  <app-root></app-root>
</body>
</html>
```

---

### 🎨 Step 5: Create `frontend/src/main.ts`

```typescript
import { bootstrapApplication } from '@angular/platform-browser';
import { AppComponent } from './app/app.component';
import { appConfig } from './app/app.config';

bootstrapApplication(AppComponent, appConfig)
  .catch(err => console.error(err));
```

---

### 🎨 Step 6: Create `frontend/src/app/app.config.ts`

```typescript
import { ApplicationConfig } from '@angular/core';
import { provideHttpClient } from '@angular/common/http';

export const appConfig: ApplicationConfig = {
  providers: [
    provideHttpClient()
  ]
};
```

---

### 🎨 Step 7: Create `frontend/src/app/task.service.ts`

```typescript
import { Injectable } from '@angular/core';
import { HttpClient } from '@angular/common/http';
import { Observable } from 'rxjs';

export interface Task {
  id: number;
  title: string;
  description: string;
  status: 'todo' | 'in-progress' | 'done';
  priority: 'low' | 'medium' | 'high';
  created_at: string;
}

export interface Stats {
  total: string;
  todo: string;
  in_progress: string;
  done: string;
}

@Injectable({ providedIn: 'root' })
export class TaskService {
  private apiUrl = '/api';

  constructor(private http: HttpClient) {}

  getTasks(): Observable<Task[]> {
    return this.http.get<Task[]>(`${this.apiUrl}/tasks`);
  }

  getStats(): Observable<Stats> {
    return this.http.get<Stats>(`${this.apiUrl}/stats`);
  }

  createTask(task: Partial<Task>): Observable<Task> {
    return this.http.post<Task>(`${this.apiUrl}/tasks`, task);
  }

  updateTask(id: number, task: Partial<Task>): Observable<Task> {
    return this.http.put<Task>(`${this.apiUrl}/tasks/${id}`, task);
  }

  deleteTask(id: number): Observable<any> {
    return this.http.delete(`${this.apiUrl}/tasks/${id}`);
  }
}
```

---

### 🎨 Step 8: Create `frontend/src/app/app.component.ts`

```typescript
import { Component, OnInit } from '@angular/core';
import { CommonModule } from '@angular/common';
import { FormsModule } from '@angular/forms';
import { TaskService, Task, Stats } from './task.service';

@Component({
  selector: 'app-root',
  standalone: true,
  imports: [CommonModule, FormsModule],
  template: `
    <!-- ═══ HEADER ═══ -->
    <div class="app">
      <header class="header">
        <h1>📋 TaskBoard</h1>
        <p class="subtitle">Kanban Task Manager — Angular + Docker + Kubernetes</p>
      </header>

      <!-- ═══ STATS BAR ═══ -->
      <div class="stats">
        <div class="stat-card">
          <span class="stat-num total">{{ stats.total }}</span>
          <span class="stat-label">Total</span>
        </div>
        <div class="stat-card">
          <span class="stat-num todo">{{ stats.todo }}</span>
          <span class="stat-label">To Do</span>
        </div>
        <div class="stat-card">
          <span class="stat-num progress">{{ stats.in_progress }}</span>
          <span class="stat-label">In Progress</span>
        </div>
        <div class="stat-card">
          <span class="stat-num done">{{ stats.done }}</span>
          <span class="stat-label">Done</span>
        </div>
      </div>

      <!-- ═══ ADD TASK FORM ═══ -->
      <form class="task-form" (ngSubmit)="addTask()">
        <input [(ngModel)]="newTitle" name="title"
               placeholder="✏️ Task title..." required />
        <input [(ngModel)]="newDesc" name="desc"
               placeholder="📝 Description (optional)" />
        <select [(ngModel)]="newPriority" name="priority">
          <option value="low">🟢 Low</option>
          <option value="medium">🟡 Medium</option>
          <option value="high">🔴 High</option>
        </select>
        <button type="submit">+ Add Task</button>
      </form>

      <!-- ═══ KANBAN BOARD ═══ -->
      <div class="board">
        <div class="column" *ngFor="let col of columns">
          <div class="column-header" [ngClass]="col.key">
            <span class="col-icon">{{ col.icon }}</span>
            <span>{{ col.label }}</span>
            <span class="col-count">{{ getTasksByStatus(col.key).length }}</span>
          </div>
          <div class="card-list">
            <div class="task-card" *ngFor="let task of getTasksByStatus(col.key)"
                 [ngClass]="'priority-' + task.priority">
              <div class="card-top">
                <span class="priority-dot" [ngClass]="task.priority"></span>
                <span class="card-title">{{ task.title }}</span>
              </div>
              <p class="card-desc" *ngIf="task.description">{{ task.description }}</p>
              <div class="card-actions">
                <button *ngIf="task.status === 'todo'"
                        (click)="moveTask(task, 'in-progress')" class="btn-move">
                  ▶ Start
                </button>
                <button *ngIf="task.status === 'in-progress'"
                        (click)="moveTask(task, 'done')" class="btn-done">
                  ✓ Done
                </button>
                <button *ngIf="task.status === 'done'"
                        (click)="moveTask(task, 'todo')" class="btn-reopen">
                  ↩ Reopen
                </button>
                <button (click)="removeTask(task.id)" class="btn-delete">🗑</button>
              </div>
            </div>
            <p class="empty-msg" *ngIf="getTasksByStatus(col.key).length === 0">
              No tasks here yet
            </p>
          </div>
        </div>
      </div>

      <!-- ═══ FOOTER ═══ -->
      <footer class="footer">
        <p>Built with ❤️ using Angular 17 + Docker + Kubernetes</p>
      </footer>
    </div>
  `
})
export class AppComponent implements OnInit {
  tasks: Task[] = [];
  stats: Stats = { total: '0', todo: '0', in_progress: '0', done: '0' };
  newTitle = '';
  newDesc = '';
  newPriority: 'low' | 'medium' | 'high' = 'medium';

  columns = [
    { key: 'todo' as const, label: 'To Do', icon: '📝' },
    { key: 'in-progress' as const, label: 'In Progress', icon: '🔧' },
    { key: 'done' as const, label: 'Done', icon: '✅' }
  ];

  constructor(private taskService: TaskService) {}

  ngOnInit() {
    this.loadTasks();
    this.loadStats();
  }

  loadTasks() {
    this.taskService.getTasks().subscribe({
      next: tasks => this.tasks = tasks,
      error: err => console.error('Failed to load tasks:', err)
    });
  }

  loadStats() {
    this.taskService.getStats().subscribe({
      next: stats => this.stats = stats,
      error: err => console.error('Failed to load stats:', err)
    });
  }

  getTasksByStatus(status: string): Task[] {
    return this.tasks.filter(t => t.status === status);
  }

  addTask() {
    if (!this.newTitle.trim()) return;
    this.taskService.createTask({
      title: this.newTitle,
      description: this.newDesc,
      priority: this.newPriority
    }).subscribe(() => {
      this.newTitle = '';
      this.newDesc = '';
      this.newPriority = 'medium';
      this.loadTasks();
      this.loadStats();
    });
  }

  moveTask(task: Task, newStatus: 'todo' | 'in-progress' | 'done') {
    this.taskService.updateTask(task.id, { ...task, status: newStatus })
      .subscribe(() => { this.loadTasks(); this.loadStats(); });
  }

  removeTask(id: number) {
    this.taskService.deleteTask(id)
      .subscribe(() => { this.loadTasks(); this.loadStats(); });
  }
}
```

---

### 🎨 Step 9: Create `frontend/src/styles.css`

```css
/* ═══════════════════════════════════════
   🎨 TaskBoard — Dark Theme Design System
   ═══════════════════════════════════════ */

:root {
  --bg-primary: #0f0f1a;
  --bg-secondary: #1a1a2e;
  --bg-card: #16213e;
  --text-primary: #e0e0e0;
  --text-secondary: #a0a0a0;
  --accent: #6c63ff;
  --accent-hover: #5a52d5;
  --success: #00c853;
  --warning: #ffd600;
  --danger: #ff5252;
  --info: #2196f3;
  --border: #2a2a4a;
  --radius: 12px;
  --shadow: 0 4px 15px rgba(0,0,0,0.3);
}

* { margin: 0; padding: 0; box-sizing: border-box; }

body {
  font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
  background: var(--bg-primary);
  color: var(--text-primary);
  min-height: 100vh;
  line-height: 1.5;
}

/* ═══ App Container ═══ */
.app { max-width: 1200px; margin: 0 auto; padding: 2rem; }

/* ═══ Header ═══ */
.header { text-align: center; margin-bottom: 2rem; }
.header h1 {
  font-size: 2.5rem; font-weight: 700;
  background: linear-gradient(135deg, var(--accent), #a78bfa, #f472b6);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}
.subtitle {
  color: var(--text-secondary);
  margin-top: 0.5rem; font-size: 0.9rem; font-weight: 300;
}

/* ═══ Stats Bar ═══ */
.stats {
  display: grid; grid-template-columns: repeat(4, 1fr);
  gap: 1rem; margin-bottom: 2rem;
}
.stat-card {
  background: var(--bg-secondary); border-radius: var(--radius);
  padding: 1.25rem; text-align: center;
  border: 1px solid var(--border);
  transition: all 0.3s ease;
}
.stat-card:hover {
  transform: translateY(-3px);
  box-shadow: var(--shadow);
}
.stat-num { display: block; font-size: 2rem; font-weight: 700; }
.stat-num.total    { color: var(--accent); }
.stat-num.todo     { color: var(--warning); }
.stat-num.progress { color: var(--info); }
.stat-num.done     { color: var(--success); }
.stat-label {
  display: block; font-size: 0.7rem; color: var(--text-secondary);
  text-transform: uppercase; letter-spacing: 1.5px; margin-top: 0.25rem;
}

/* ═══ Task Form ═══ */
.task-form {
  display: flex; gap: 0.5rem;
  margin-bottom: 2rem; flex-wrap: wrap;
}
.task-form input, .task-form select {
  padding: 0.75rem 1rem;
  border: 1px solid var(--border); border-radius: 8px;
  background: var(--bg-secondary); color: var(--text-primary);
  font-family: inherit; font-size: 0.9rem;
  transition: border-color 0.2s;
}
.task-form input:focus, .task-form select:focus {
  outline: none; border-color: var(--accent);
}
.task-form input:first-child { flex: 2; min-width: 200px; }
.task-form input:nth-child(2) { flex: 2; min-width: 200px; }
.task-form select { min-width: 130px; }
.task-form button {
  padding: 0.75rem 1.5rem; border: none; border-radius: 8px;
  background: linear-gradient(135deg, var(--accent), #8b5cf6);
  color: white; font-weight: 600; font-size: 0.9rem;
  cursor: pointer; transition: all 0.3s ease;
}
.task-form button:hover {
  transform: translateY(-1px);
  box-shadow: 0 4px 15px rgba(108,99,255,0.4);
}

/* ═══ Kanban Board ═══ */
.board {
  display: grid; grid-template-columns: repeat(3, 1fr);
  gap: 1.5rem;
}
.column {
  background: var(--bg-secondary); border-radius: 16px;
  padding: 1rem; border: 1px solid var(--border); min-height: 350px;
}
.column-header {
  display: flex; align-items: center; gap: 0.5rem;
  padding: 0.75rem 1rem; border-radius: 10px;
  margin-bottom: 1rem; font-weight: 600; font-size: 0.95rem;
}
.column-header.todo        { background: rgba(255,214,0,0.1);  color: var(--warning); }
.column-header.in-progress { background: rgba(33,150,243,0.1); color: var(--info); }
.column-header.done        { background: rgba(0,200,83,0.1);   color: var(--success); }
.col-icon { font-size: 1.1rem; }
.col-count {
  margin-left: auto; background: rgba(255,255,255,0.1);
  padding: 0.15rem 0.6rem; border-radius: 20px; font-size: 0.8rem;
}

/* ═══ Task Cards ═══ */
.card-list { display: flex; flex-direction: column; gap: 0.75rem; }
.task-card {
  background: var(--bg-card); border: 1px solid var(--border);
  border-radius: var(--radius); padding: 1rem;
  transition: all 0.25s ease;
  animation: slideIn 0.3s ease;
}
.task-card:hover {
  border-color: var(--accent);
  box-shadow: 0 4px 20px rgba(108,99,255,0.15);
  transform: translateY(-2px);
}
.task-card.priority-high   { border-left: 3px solid var(--danger); }
.task-card.priority-medium { border-left: 3px solid var(--warning); }
.task-card.priority-low    { border-left: 3px solid var(--success); }

@keyframes slideIn {
  from { opacity: 0; transform: translateY(-10px); }
  to   { opacity: 1; transform: translateY(0); }
}

.card-top { display: flex; align-items: center; gap: 0.5rem; margin-bottom: 0.4rem; }
.priority-dot { width: 10px; height: 10px; border-radius: 50%; flex-shrink: 0; }
.priority-dot.high   { background: var(--danger); box-shadow: 0 0 6px var(--danger); }
.priority-dot.medium { background: var(--warning); box-shadow: 0 0 6px var(--warning); }
.priority-dot.low    { background: var(--success); box-shadow: 0 0 6px var(--success); }
.card-title { font-weight: 600; font-size: 0.95rem; }
.card-desc { font-size: 0.8rem; color: var(--text-secondary); margin-bottom: 0.6rem; }

/* ═══ Card Action Buttons ═══ */
.card-actions { display: flex; gap: 0.4rem; }
.card-actions button {
  padding: 0.3rem 0.6rem; border: 1px solid var(--border); border-radius: 6px;
  background: transparent; color: var(--text-secondary);
  cursor: pointer; font-size: 0.75rem; transition: all 0.2s ease;
}
.btn-move:hover   { border-color: var(--info);    color: var(--info);    background: rgba(33,150,243,0.1); }
.btn-done:hover   { border-color: var(--success); color: var(--success); background: rgba(0,200,83,0.1); }
.btn-reopen:hover { border-color: var(--warning); color: var(--warning); background: rgba(255,214,0,0.1); }
.btn-delete:hover { border-color: var(--danger);  color: var(--danger);  background: rgba(255,82,82,0.1); }

.empty-msg {
  text-align: center; color: var(--text-secondary);
  padding: 2rem 0; font-size: 0.85rem; font-style: italic;
}

/* ═══ Footer ═══ */
.footer {
  text-align: center; margin-top: 3rem; padding: 1.5rem;
  color: var(--text-secondary); font-size: 0.8rem;
  border-top: 1px solid var(--border);
}

/* ═══ Responsive ═══ */
@media (max-width: 768px) {
  .board { grid-template-columns: 1fr; }
  .stats { grid-template-columns: repeat(2, 1fr); }
  .task-form { flex-direction: column; }
  .header h1 { font-size: 1.8rem; }
}
```

---

### 🎨 Step 10: Create `frontend/nginx.conf`

```nginx
server {
    listen 80;
    server_name localhost;
    root /usr/share/nginx/html;
    index index.html;

    # Serve Angular SPA — fallback to index.html
    location / {
        try_files $uri $uri/ /index.html;
    }

    # Proxy API requests to backend
    location /api/ {
        proxy_pass http://backend-service:3000;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    }
}
```

---

# 🐳 SECTION 4 — Dockerizing the Application

---

### 🐳 Step 1: Backend Dockerfile

**`backend/Dockerfile`:**
```dockerfile
# ═══════════════════════════════════════
# 🐳 Backend Dockerfile
# ═══════════════════════════════════════
FROM node:18-alpine

# Set working directory
WORKDIR /app

# Copy dependency files & install (cached layer!)
COPY package*.json ./
RUN npm ci --only=production

# Copy application code
COPY server.js .

# Create non-root user (security best practice!)
RUN addgroup -S appgroup && adduser -S appuser -G appgroup
USER appuser

# Document the port
EXPOSE 3000

# Health check
HEALTHCHECK --interval=30s --timeout=5s --retries=3 \
    CMD wget --no-verbose --tries=1 --spider http://localhost:3000/api/health || exit 1

# Start the server
CMD ["node", "server.js"]
```

```
📋 Docker Concepts Used:
   ✅ FROM (base image)         ✅ WORKDIR (working directory)
   ✅ COPY (copy files)         ✅ RUN (install deps)
   ✅ USER (non-root security)  ✅ EXPOSE (document port)
   ✅ HEALTHCHECK (monitoring)  ✅ CMD (startup command)
```

---

### 🐳 Step 2: Frontend Multi-Stage Dockerfile

**`frontend/Dockerfile`:**
```dockerfile
# ═══════════════════════════════════════
# 🏗️ Stage 1: BUILD (Angular compilation)
# ═══════════════════════════════════════
FROM node:18-alpine AS builder
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
RUN npm run build
# 📦 Output: /app/dist/taskboard/browser/

# ═══════════════════════════════════════
# 🚀 Stage 2: PRODUCTION (Nginx serving)
# ═══════════════════════════════════════
FROM nginx:alpine
RUN rm -rf /usr/share/nginx/html/*
COPY --from=builder /app/dist/taskboard/browser /usr/share/nginx/html
COPY nginx.conf /etc/nginx/conf.d/default.conf
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
```

```
📊 Image Size Comparison:
   🏗️ Stage 1 (node:18-alpine + npm + Angular + node_modules):  ~500 MB
   🚀 Stage 2 (nginx:alpine + built HTML/CSS/JS only):          ~25 MB
   
   💡 Reduction: 95%! Only the final stage becomes the image.
```

> [!IMPORTANT]
> 🔑 **This is a Multi-Stage Build!** The build tools, source code, and node_modules from Stage 1 are thrown away. Only the compiled output is copied to the tiny Nginx image. This is a critical Docker optimization technique.

---

### 🐳 Step 3: Docker Compose (Local Development)

**`docker-compose.yml`:**
```yaml
version: '3.8'

services:
  # ═══════════════════════════════════════
  # 🗄️ PostgreSQL Database
  # ═══════════════════════════════════════
  postgres:
    image: postgres:15-alpine
    container_name: taskboard-db
    environment:
      POSTGRES_DB: taskboard
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: postgres123
    ports:
      - "5432:5432"
    volumes:
      - pgdata:/var/lib/postgresql/data
    networks:
      - taskboard-net
    healthcheck:
      test: ["CMD-SHELL", "pg_isready -U postgres"]
      interval: 10s
      timeout: 5s
      retries: 5

  # ═══════════════════════════════════════
  # ⚡ Redis Cache
  # ═══════════════════════════════════════
  redis:
    image: redis:7-alpine
    container_name: taskboard-redis
    ports:
      - "6379:6379"
    volumes:
      - redis-data:/data
    networks:
      - taskboard-net

  # ═══════════════════════════════════════
  # ⚙️ Backend API
  # ═══════════════════════════════════════
  backend:
    build: ./backend
    container_name: taskboard-backend
    environment:
      DB_HOST: postgres
      DB_PORT: "5432"
      DB_NAME: taskboard
      DB_USER: postgres
      DB_PASSWORD: postgres123
      REDIS_HOST: redis
      REDIS_PORT: "6379"
      PORT: "3000"
    ports:
      - "3000:3000"
    depends_on:
      postgres:
        condition: service_healthy
      redis:
        condition: service_started
    networks:
      - taskboard-net

  # ═══════════════════════════════════════
  # 🎨 Frontend (Angular + Nginx)
  # ═══════════════════════════════════════
  frontend:
    build: ./frontend
    container_name: taskboard-frontend
    ports:
      - "8080:80"
    depends_on:
      - backend
    networks:
      - taskboard-net

# 💾 Named Volumes (data survives container restarts!)
volumes:
  pgdata:
  redis-data:

# 🌐 Custom Network (containers find each other by name!)
networks:
  taskboard-net:
    driver: bridge
```

---

### 🐳 Step 4: Run Locally with Docker Compose

```bash
# 1️⃣ Build and start everything
docker compose up -d --build

# 2️⃣ Check all services are running
docker compose ps
# NAME                  STATUS
# taskboard-db          Up (healthy)
# taskboard-redis       Up
# taskboard-backend     Up
# taskboard-frontend    Up

# 3️⃣ Test the API
curl http://localhost:3000/api/health
# ✅ {"status":"healthy","db":"connected","redis":"connected"}

# 4️⃣ Open the app!
# 🌐 Visit http://localhost:8080

# 5️⃣ View logs
docker compose logs -f backend

# 6️⃣ Stop everything
docker compose down

# 7️⃣ Stop and DELETE all data
docker compose down -v
```

---

# ☸️ SECTION 5 — Kubernetes Manifests

---

### ☸️ Step 1: Namespace

**`k8s/namespace.yaml`:**
```yaml
apiVersion: v1
kind: Namespace
metadata:
  name: taskboard
  labels:
    app: taskboard
    managed-by: kubectl
```

---

### ☸️ Step 2: PostgreSQL (Secret + PVC + Deployment + Service)

**`k8s/postgres/secret.yaml`:**
```yaml
apiVersion: v1
kind: Secret
metadata:
  name: postgres-secret
  namespace: taskboard
type: Opaque
stringData:
  POSTGRES_USER: postgres
  POSTGRES_PASSWORD: postgres123
  POSTGRES_DB: taskboard
```

**`k8s/postgres/pvc.yaml`:**
```yaml
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: postgres-pvc
  namespace: taskboard
spec:
  accessModes: [ReadWriteOnce]
  resources:
    requests:
      storage: 1Gi
```

**`k8s/postgres/deployment.yaml`:**
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: postgres
  namespace: taskboard
spec:
  replicas: 1
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
          envFrom:
            - secretRef: { name: postgres-secret }
          volumeMounts:
            - name: data
              mountPath: /var/lib/postgresql/data
          resources:
            requests: { memory: "128Mi", cpu: "100m" }
            limits:   { memory: "256Mi", cpu: "500m" }
          readinessProbe:
            exec: { command: ["pg_isready", "-U", "postgres"] }
            initialDelaySeconds: 5
            periodSeconds: 10
          livenessProbe:
            exec: { command: ["pg_isready", "-U", "postgres"] }
            initialDelaySeconds: 15
            periodSeconds: 20
      volumes:
        - name: data
          persistentVolumeClaim: { claimName: postgres-pvc }
```

**`k8s/postgres/service.yaml`:**
```yaml
apiVersion: v1
kind: Service
metadata:
  name: postgres-service
  namespace: taskboard
spec:
  type: ClusterIP
  selector: { app: postgres }
  ports: [{ port: 5432, targetPort: 5432 }]
```

---

### ☸️ Step 3: Redis

**`k8s/redis/deployment.yaml`:**
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: redis
  namespace: taskboard
spec:
  replicas: 1
  selector:
    matchLabels: { app: redis }
  template:
    metadata:
      labels: { app: redis }
    spec:
      containers:
        - name: redis
          image: redis:7-alpine
          ports: [{ containerPort: 6379 }]
          resources:
            requests: { memory: "64Mi", cpu: "50m" }
            limits:   { memory: "128Mi", cpu: "250m" }
          readinessProbe:
            exec: { command: ["redis-cli", "ping"] }
            initialDelaySeconds: 5
            periodSeconds: 10
```

**`k8s/redis/service.yaml`:**
```yaml
apiVersion: v1
kind: Service
metadata:
  name: redis-service
  namespace: taskboard
spec:
  type: ClusterIP
  selector: { app: redis }
  ports: [{ port: 6379, targetPort: 6379 }]
```

---

### ☸️ Step 4: Backend (ConfigMap + Deployment + Service)

**`k8s/backend/configmap.yaml`:**
```yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: backend-config
  namespace: taskboard
data:
  DB_HOST: "postgres-service"
  DB_PORT: "5432"
  DB_NAME: "taskboard"
  REDIS_HOST: "redis-service"
  REDIS_PORT: "6379"
  PORT: "3000"
```

**`k8s/backend/deployment.yaml`:**
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: backend
  namespace: taskboard
spec:
  replicas: 2                               # 📦 2 replicas for availability
  selector:
    matchLabels: { app: backend }
  strategy:
    type: RollingUpdate                      # 🔄 Zero-downtime updates
    rollingUpdate:
      maxSurge: 1
      maxUnavailable: 0                      # Never go below 2 pods
  template:
    metadata:
      labels: { app: backend }
    spec:
      containers:
        - name: backend
          image: taskboard-backend:v1
          imagePullPolicy: Never             # Use local Minikube image
          ports: [{ containerPort: 3000 }]
          envFrom:
            - configMapRef: { name: backend-config }
          env:
            - name: DB_USER
              valueFrom:
                secretKeyRef: { name: postgres-secret, key: POSTGRES_USER }
            - name: DB_PASSWORD
              valueFrom:
                secretKeyRef: { name: postgres-secret, key: POSTGRES_PASSWORD }
          resources:
            requests: { memory: "128Mi", cpu: "100m" }
            limits:   { memory: "256Mi", cpu: "500m" }
          readinessProbe:
            httpGet: { path: /api/health, port: 3000 }
            initialDelaySeconds: 10
            periodSeconds: 5
          livenessProbe:
            httpGet: { path: /api/health, port: 3000 }
            initialDelaySeconds: 15
            periodSeconds: 20
```

**`k8s/backend/service.yaml`:**
```yaml
apiVersion: v1
kind: Service
metadata:
  name: backend-service
  namespace: taskboard
spec:
  type: ClusterIP
  selector: { app: backend }
  ports: [{ port: 3000, targetPort: 3000 }]
```

---

### ☸️ Step 5: Frontend (Deployment + Service)

**`k8s/frontend/deployment.yaml`:**
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: frontend
  namespace: taskboard
spec:
  replicas: 2
  selector:
    matchLabels: { app: frontend }
  template:
    metadata:
      labels: { app: frontend }
    spec:
      containers:
        - name: frontend
          image: taskboard-frontend:v1
          imagePullPolicy: Never
          ports: [{ containerPort: 80 }]
          resources:
            requests: { memory: "32Mi", cpu: "50m" }
            limits:   { memory: "64Mi", cpu: "100m" }
          readinessProbe:
            httpGet: { path: /, port: 80 }
            initialDelaySeconds: 5
            periodSeconds: 10
```

**`k8s/frontend/service.yaml`:**
```yaml
apiVersion: v1
kind: Service
metadata:
  name: frontend-service
  namespace: taskboard
spec:
  type: NodePort                            # 🌍 External access!
  selector: { app: frontend }
  ports:
    - port: 80
      targetPort: 80
      nodePort: 30080                       # 🔗 Access via NodeIP:30080
```

---

### ☸️ Step 6: Ingress, HPA, Network Policy

**`k8s/ingress.yaml`:**
```yaml
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: taskboard-ingress
  namespace: taskboard
  annotations:
    nginx.ingress.kubernetes.io/rewrite-target: /$1
spec:
  rules:
    - host: taskboard.local
      http:
        paths:
          - path: /api/(.*)
            pathType: ImplementationSpecific
            backend:
              service: { name: backend-service, port: { number: 3000 } }
          - path: /(.*)
            pathType: ImplementationSpecific
            backend:
              service: { name: frontend-service, port: { number: 80 } }
```

**`k8s/hpa.yaml`:**
```yaml
apiVersion: autoscaling/v2
kind: HorizontalPodAutoscaler
metadata:
  name: backend-hpa
  namespace: taskboard
spec:
  scaleTargetRef:
    apiVersion: apps/v1
    kind: Deployment
    name: backend
  minReplicas: 2
  maxReplicas: 8
  metrics:
    - type: Resource
      resource:
        name: cpu
        target: { type: Utilization, averageUtilization: 70 }
```

**`k8s/network-policy.yaml`:**
```yaml
# 🔒 Only frontend can reach backend
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata: { name: backend-policy, namespace: taskboard }
spec:
  podSelector:
    matchLabels: { app: backend }
  policyTypes: [Ingress]
  ingress:
    - from:
        - podSelector: { matchLabels: { app: frontend } }
      ports: [{ port: 3000 }]
---
# 🔒 Only backend can reach PostgreSQL
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata: { name: postgres-policy, namespace: taskboard }
spec:
  podSelector:
    matchLabels: { app: postgres }
  policyTypes: [Ingress]
  ingress:
    - from:
        - podSelector: { matchLabels: { app: backend } }
      ports: [{ port: 5432 }]
---
# 🔒 Only backend can reach Redis
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata: { name: redis-policy, namespace: taskboard }
spec:
  podSelector:
    matchLabels: { app: redis }
  policyTypes: [Ingress]
  ingress:
    - from:
        - podSelector: { matchLabels: { app: backend } }
      ports: [{ port: 6379 }]
```

---

# 🚀 SECTION 6 — Step-by-Step Deployment Guide

---

### 🚀 Step 1: Start Minikube

```bash
minikube start --driver=docker
minikube addons enable ingress
minikube addons enable metrics-server
```

### 🚀 Step 2: Configure Docker to Use Minikube's Daemon

```bash
# Linux / macOS:
eval $(minikube docker-env)

# Windows PowerShell:
& minikube -p minikube docker-env --shell powershell | Invoke-Expression
```

> [!IMPORTANT]
> 🔑 This step makes `docker build` create images INSIDE Minikube so Kubernetes can find them without pushing to Docker Hub.

### 🚀 Step 3: Build Docker Images

```bash
docker build -t taskboard-backend:v1 ./backend
docker build -t taskboard-frontend:v1 ./frontend

# ✅ Verify images exist in Minikube:
docker images | grep taskboard
```

### 🚀 Step 4: Deploy to Kubernetes (in order!)

```bash
# 1️⃣ Create namespace
kubectl apply -f k8s/namespace.yaml

# 2️⃣ Deploy database & cache (data layer)
kubectl apply -f k8s/postgres/
kubectl apply -f k8s/redis/

# 3️⃣ Wait for database to be ready
kubectl wait --for=condition=ready pod -l app=postgres \
    -n taskboard --timeout=120s
# ✅ pod/postgres-xxxx condition met

# 4️⃣ Deploy backend & frontend (app layer)
kubectl apply -f k8s/backend/
kubectl apply -f k8s/frontend/

# 5️⃣ Deploy networking & scaling
kubectl apply -f k8s/ingress.yaml
kubectl apply -f k8s/hpa.yaml
kubectl apply -f k8s/network-policy.yaml
```

### 🚀 Step 5: Verify Everything is Running

```bash
kubectl get all -n taskboard
# ✅ Expected output:
# NAME                            READY   STATUS    RESTARTS
# pod/postgres-xxxx               1/1     Running   0
# pod/redis-xxxx                  1/1     Running   0
# pod/backend-xxxx                1/1     Running   0
# pod/backend-yyyy                1/1     Running   0
# pod/frontend-xxxx               1/1     Running   0
# pod/frontend-yyyy               1/1     Running   0
#
# NAME                       TYPE        PORT(S)
# service/postgres-service   ClusterIP   5432/TCP
# service/redis-service      ClusterIP   6379/TCP
# service/backend-service    ClusterIP   3000/TCP
# service/frontend-service   NodePort    80:30080/TCP

# Watch pods come up in real-time:
kubectl get pods -n taskboard -w
```

### 🚀 Step 6: Access the Application!

```bash
# Option A: Minikube service
minikube service frontend-service -n taskboard
# 🌐 Opens browser automatically!

# Option B: Port forwarding
kubectl port-forward svc/frontend-service 8080:80 -n taskboard
# 🌐 Visit http://localhost:8080

# Test API directly:
kubectl port-forward svc/backend-service 3000:3000 -n taskboard
curl http://localhost:3000/api/health
# ✅ {"status":"healthy","db":"connected","redis":"connected"}
```

### 🚀 Step 7: Scale the Backend

```bash
# Scale to 5 replicas
kubectl scale deployment backend --replicas=5 -n taskboard

# Verify
kubectl get pods -n taskboard -l app=backend
# ✅ 5 backend pods running!
```

### 🚀 Step 8: Perform a Rolling Update

```bash
# 1️⃣ Rebuild image with new tag
docker build -t taskboard-backend:v2 ./backend

# 2️⃣ Update the deployment
kubectl set image deployment/backend \
    backend=taskboard-backend:v2 -n taskboard

# 3️⃣ Watch the rollout
kubectl rollout status deployment/backend -n taskboard
# ✅ deployment "backend" successfully rolled out
```

### 🚀 Step 9: Rollback if Needed

```bash
kubectl rollout undo deployment/backend -n taskboard
kubectl rollout status deployment/backend -n taskboard
# ✅ Rolled back to previous version
```

### 🚀 Step 10: Monitor & Debug

```bash
# 📝 View logs
kubectl logs -f deployment/backend -n taskboard

# 📊 Resource usage
kubectl top pods -n taskboard

# 📋 Cluster events
kubectl get events -n taskboard --sort-by='.lastTimestamp'

# 📈 Auto-scaler status
kubectl get hpa -n taskboard
```

### 🧹 Cleanup

```bash
# Delete everything
kubectl delete namespace taskboard

# Stop Minikube
minikube stop
```

---

# 📋 SECTION 7 — Skills Checklist

> **Every file in this project maps to Docker and/or Kubernetes concepts you've learned:**

| # | File / Action | 🐳 Docker Concept | ☸️ K8s Concept |
|---|--------------|-------------------|----------------|
| 1 | `backend/Dockerfile` | FROM, COPY, RUN, CMD, USER, HEALTHCHECK | — |
| 2 | `backend/.dockerignore` | Build context optimization | — |
| 3 | `frontend/Dockerfile` | **Multi-stage builds**, image optimization | — |
| 4 | `frontend/nginx.conf` | Reverse proxy, static file serving | — |
| 5 | `docker-compose.yml` | Multi-container apps, networks, volumes | — |
| 6 | `docker compose up` | Container lifecycle management | — |
| 7 | `k8s/namespace.yaml` | — | Namespaces |
| 8 | `k8s/postgres/secret.yaml` | — | Secrets (sensitive config) |
| 9 | `k8s/postgres/pvc.yaml` | — | PersistentVolumeClaims |
| 10 | `k8s/postgres/deployment.yaml` | — | Deployments, health probes, limits |
| 11 | `k8s/*/service.yaml` | — | ClusterIP, NodePort Services |
| 12 | `k8s/backend/configmap.yaml` | — | ConfigMaps (non-sensitive) |
| 13 | `k8s/backend/deployment.yaml` | — | Rolling updates, readiness probes |
| 14 | `k8s/ingress.yaml` | — | Ingress, path-based routing |
| 15 | `k8s/hpa.yaml` | — | HorizontalPodAutoscaler |
| 16 | `k8s/network-policy.yaml` | — | Network Policies (firewall) |
| 17 | `kubectl scale` | — | Manual scaling |
| 18 | `kubectl set image` | — | Rolling updates |
| 19 | `kubectl rollout undo` | — | Rollback |
| 20 | `minikube docker-env` | Docker daemon integration | Minikube |

---

# 🏋️ SECTION 8 — Practice Challenges

> **After completing this project, try these challenges to level up! 💪**

| # | Challenge | Difficulty | Concepts Practiced |
|---|----------|-----------|-------------------|
| 1 | 🟢 Verify Redis caching works by checking `docker compose logs backend` for cache hits | Easy | Docker logs, caching |
| 2 | 🟢 Add a new field `due_date` to tasks (update DB schema + API + UI) | Easy | Full-stack development |
| 3 | 🟡 Create a **Helm chart** packaging all K8s manifests into one installable chart | Medium | Helm, templating |
| 4 | 🟡 Add a **CronJob** that backs up PostgreSQL daily at 2 AM | Medium | CronJobs, pg_dump |
| 5 | 🟡 Implement **Blue-Green deployment** — deploy v2 and switch traffic instantly | Medium | Deployment strategies |
| 6 | 🟡 Add **Prometheus metrics** endpoint (`/api/metrics`) to the backend | Medium | Monitoring |
| 7 | 🔴 Create a **CI/CD pipeline** with GitHub Actions that auto-builds and deploys | Hard | GitHub Actions, automation |
| 8 | 🔴 Add **TLS/HTTPS** using cert-manager and Let's Encrypt | Hard | cert-manager, TLS, Ingress |
| 9 | 🔴 Deploy to a **cloud K8s** service (GKE/EKS/AKS) with a container registry | Hard | Cloud deployment |
| 10 | 🔴 Write a **Kubernetes Operator** that auto-creates databases when a CRD is applied | Expert | CRDs, Operators |

---

# 🔧 SECTION 9 — Troubleshooting

### Common Issues & Fixes

| # | Problem | Cause | Solution |
|---|---------|-------|---------|
| 1 | `ImagePullBackOff` | Minikube can't find local images | Run `eval $(minikube docker-env)` then rebuild |
| 2 | Backend `CrashLoopBackOff` | DB not ready when backend starts | Ensure postgres is ready: `kubectl wait --for=condition=ready` |
| 3 | `Connection refused` to postgres | Wrong service name in ConfigMap | Verify `DB_HOST` matches postgres service name |
| 4 | Frontend shows blank page | Angular build failed | Check `docker build` logs for errors |
| 5 | Can't access `NodePort` | Minikube networking | Use `minikube service <name> -n taskboard` |
| 6 | `OOMKilled` | Container exceeded memory limit | Increase `resources.limits.memory` |
| 7 | HPA not scaling | Metrics server not enabled | Run `minikube addons enable metrics-server` |

```bash
# 🔍 General debugging commands:
kubectl get pods -n taskboard                          # Check status
kubectl describe pod <pod-name> -n taskboard           # Check events
kubectl logs <pod-name> -n taskboard                   # Check logs
kubectl logs --previous <pod-name> -n taskboard        # Previous crash logs
kubectl get events -n taskboard --sort-by='.lastTimestamp'
```

---

> [!TIP]
> 🎉 **Congratulations!** You've completed the ENTIRE Docker & Kubernetes learning series!
>
> You now know how to:
> - ✅ Build Docker images and write Dockerfiles
> - ✅ Use Docker Compose for multi-container apps
> - ✅ Deploy to Kubernetes with Deployments, Services, and Ingress
> - ✅ Manage secrets, config, storage, and auto-scaling
> - ✅ Perform rolling updates and rollbacks
> - ✅ Troubleshoot common issues
>
> **Keep building, keep breaking, keep learning! 🚀**

> [!IMPORTANT]
> 💼 **For your resume/portfolio:** Deploy this TaskBoard project to a cloud Kubernetes service (GKE/EKS/AKS), push it to GitHub, and add it to your portfolio. It demonstrates practical Docker + K8s skills that employers actively look for!
