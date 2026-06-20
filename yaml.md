# 🎨 YAML Masterclass for DevOps Engineers

> [!NOTE]
> **YAML** stands for "YAML Ain't Markup Language". It is a human-readable data-serialization language. It is commonly used for configuration files and in applications where data is being stored or transmitted. In DevOps, YAML is the absolute standard for configuring tools like Kubernetes, Ansible, Docker Compose, CI/CD pipelines, and more.

## 🟢 Level 1: Beginner (The Basics)

### 1. Key-Value Pairs
The fundamental building block of YAML is the key-value pair. Keys are separated from values by a colon `:` followed by a **space**.

```yaml
# This is a comment. It starts with a hash.
name: John Doe
age: 30
occupation: DevOps Engineer
```

### 2. Data Types
YAML can infer basic data types automatically.

```yaml
integer: 42
float: 3.14
string: "Hello, World!"
boolean_true: true
boolean_false: false
null_value: null
```

### 3. Multi-line Strings
There are two ways to represent multi-line strings in YAML:

*   `|` (Literal Block Scalar): Preserves newlines and trailing spaces.
*   `>` (Folded Block Scalar): Folds newlines into spaces (like standard paragraph text).

```yaml
# Preserves line breaks
literal_string: |
  This is line 1.
  This is line 2.

# Converts line breaks to spaces
folded_string: >
  This is a very long sentence
  that is broken across multiple
  lines for readability.
```

---

## 🟡 Level 2: Intermediate (Structures)

### 1. Lists (Arrays or Sequences)
Lists are denoted by a dash `-` followed by a space.

```yaml
# A simple list of strings
operating_systems:
  - Linux
  - Windows
  - macOS

# An inline list (Flow style)
ports: [80, 443, 8080]
```

### 2. Dictionaries (Maps or Hashes)
Dictionaries are nested key-value pairs. **Indentation is crucial in YAML**. Use spaces (usually 2 spaces), **never tabs**.

```yaml
server:
  host: 192.168.1.100
  port: 8080
  protocol: http
```

### 3. Nested Structures (Complex Objects)
You can nest lists inside dictionaries and dictionaries inside lists.

```yaml
employees:
  - name: Alice
    role: SRE
    skills:
      - Linux
      - Kubernetes
  - name: Bob
    role: Cloud Architect
    skills:
      - AWS
      - Terraform
```

---

## 🟠 Level 3: Advanced (DRY Principle & File Handling)

### 1. Anchors `&` and Aliases `*`
Anchors allow you to define a chunk of configuration once and reuse it later, adhering to the DRY (Don't Repeat Yourself) principle.
*   `&` defines an anchor.
*   `*` refers to an alias (calls the anchor).

```yaml
# Define a common database configuration
default_db_config: &default_db
  host: localhost
  port: 5432
  user: admin

# Reuse the configuration in different environments
development:
  database:
    <<: *default_db  # The '<<:' syntax means "merge the contents of the alias"
    database_name: dev_db

production:
  database:
    <<: *default_db
    host: prod.db.example.com # Override the host for production
    database_name: prod_db
```
> [!TIP]
> The `<<:` syntax is called the merge key, which allows you to inject the properties of an aliased dictionary into another dictionary.

### 2. Multiple Documents in a Single File
You can define multiple distinct YAML documents in a single file by separating them with three dashes `---`. The end of a document can optionally be marked with three dots `...`.

```yaml
---
# Document 1 (e.g., A Kubernetes Service)
apiVersion: v1
kind: Service
metadata:
  name: web-service
---
# Document 2 (e.g., A Kubernetes Deployment)
apiVersion: apps/v1
kind: Deployment
metadata:
  name: web-deployment
...
```

---

## 🚀 DevOps Practical Examples

Here is how YAML looks in real-world DevOps tools.

### 1. Docker Compose
Used to define and run multi-container Docker applications.

```yaml
version: '3.8'
services:
  web:
    image: nginx:alpine
    ports:
      - "80:80"
  db:
    image: postgres:13
    environment:
      POSTGRES_USER: user
      POSTGRES_PASSWORD: password
```

### 2. Kubernetes
Used to orchestrate containers. YAML defines the desired state of resources.

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
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
        image: nginx:1.14.2
        ports:
        - containerPort: 80
```

### 3. GitHub Actions (CI/CD)
Used to automate workflows.

```yaml
name: Node.js CI

on:
  push:
    branches: [ "main" ]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    - name: Use Node.js
      uses: actions/setup-node@v3
      with:
        node-version: '16.x'
    - run: npm ci
    - run: npm test
```

### 4. Ansible
Used for configuration management and application-deployment.

```yaml
- name: Install and start Nginx
  hosts: webservers
  become: yes # Run with sudo
  tasks:
    - name: Ensure Nginx is installed
      apt:
        name: nginx
        state: present
    - name: Ensure Nginx is running
      service:
        name: nginx
        state: started
```

---

## 🛡️ Best Practices & Gotchas

> [!WARNING]
> **TABS ARE FORBIDDEN!** YAML does not support tabs for indentation. Always use spaces (usually 2). Most code editors will convert tabs to spaces automatically.

> [!IMPORTANT]
> **Case Sensitivity:** YAML is fully case-sensitive. `True` is not the same as `true`, and `Key` is not `key`.

1.  **Use a Linter**: Always validate your YAML before pushing it to production. Tools like `yamllint` are essential.
2.  **Quote Strings When Unsure**: If a string contains special characters like `*`, `{`, `}`, `[`, `]`, `,`, `&`, `!`, `#`, `|`, `>`, `@`, `` ` ``, `"`, `'`, or `:` followed by a space, wrap it in quotes (`" "` or `' '`).
3.  **Keep it Simple**: Avoid overly deep nesting. If you go beyond 4-5 levels of nesting, your configuration might be too complex and should be refactored.
4.  **Use Comments**: Document your configurations! It helps your team (and future you) understand *why* a certain configuration was chosen.
