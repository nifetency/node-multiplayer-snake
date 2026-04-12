# Node Multiplayer Snake Game

## Overview

A multiplayer snake game built using Node.js, Express, Socket.IO, and modern JavaScript (ES6).

This project demonstrates:
- Real-time multiplayer communication
- Interactive browser-based gameplay
- Server-client synchronization using WebSockets

Originally based on:
https://github.com/simondiep/node-multiplayer-snake

---

## Features

- Quick join gameplay (no sign-up required)
- Player customization (name, color)
- Admin controls (speed, food, bots, player length)
- Multiple food types
- Upload custom snake and background images
- Player statistics (kills, deaths, score)
- Spectator mode
- Game notifications and kill announcements
- Randomized spawns
- Local storage for user preferences
- Interactive walls (add/remove by clicking)
- Sound effects

---

## Requirements

Make sure you have the following installed:

- Node.js (v8 or higher recommended)
- npm (comes with Node.js)
- Git

---

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/simondiep/node-multiplayer-snake.git
cd node-multiplayer-snake
```

---

### 2. Install Dependencies

```bash
npm install
```

---

### 3. Run the Application

```bash
npm start
```

---

### 4. Open in Browser

Visit:

```
http://localhost:3000
```

---

## Game Flow

```text
1. User joins game
2. Server assigns player
3. Real-time updates via Socket.IO
4. Game state synced across clients
5. Score updates and events triggered
```

---

## Contributing

1. Fork the repository  
2. Create a new branch  
3. Make your changes  
4. Run tests:
```bash
npm test
```
5. Submit a pull request  

---

## Deployment on NIFE

Deploy your application using the NIFE platform:

https://launch.nife.io/

Deployment flow:

```text
Source → Build → Resources → Review → Deploy
```

Prerequisite: Ensure a workload (Deployment, CronJob, or StatefulSet) exists.

---

## Method 1: Deploy via Docker Image (Recommended)

### Step 1: Build and Push Image

```bash
docker build -t node-multiplayer-snake .
docker tag node-multiplayer-snake <username>/node-multiplayer-snake:latest
docker push <username>/node-multiplayer-snake:latest
```

---

### Step 2: Configure Source

- Source: Docker Image
- Registry: Docker Hub
- Image: `<username>/node-multiplayer-snake:latest`
- Tag: `latest`

---

### Step 3: Build Configuration

- Internal Port: `3000`
- External Port: `80`

Optional environment variables:

| Key      | Value      |
|----------|------------|
| NODE_ENV | production |

---

### Step 4: Resources Configuration

- Region: e.g., `ap-south-1`
- Resource Type: CPU

Recommended settings:

- CPU Request: `250m`
- Memory Request: `512MB`
- CPU Limit: `500m`
- Memory Limit: `1GB`

---

### Step 5: Deploy

- Strategy: Rolling
- Workload: Deployment
- Routing Policy: Latency
- Replicas: 1–2

Click **Deploy**.

---

## Method 2: Deploy via Git Repository

### Step 1: Select Source

- Source: Git Repository
- Provider: GitHub
- Branch: `main`

---

### Step 2: Build Configuration

- Internal Port: `3000`
- External Port: `80`

Enable:

```
Auto-Dockerize with Runtime
```

---

### Step 3: Build and Security

NIFE automatically performs:

- SAST
- SCA
- Container scan
- IaC scan

Resolve any critical issues before proceeding.

---

### Step 4: Resources and Deploy

Use the recommended configuration above and deploy.

---

## Deployment using nifectl (CLI)

You can deploy the application using the nifectl CLI.

---

### Step 1: Download nifectl

https://docs.nife.io/Quick-Start/Nifectl

---

### Step 2: Open Terminal

- Type `cmd` in the address bar  
  OR  
- Right-click → **Open in Terminal**

---

### Step 3: Verify Installation

```bash
nifectl --help
```

---

## Deployment Steps

### Step 1: Login

```bash
nifectl auth login
```

---

### Step 2: Initialize Project

```bash
nifectl init
```

Provide:
- Application name
- Organization
- Repository URL
- Branch (`main`)

---

### Step 3: Configure Deployment

- Deployment Type: Deployment
- Resource Type: CPU
- Replicas: 1

Ports:
- Internal: `3000`
- External: `80`

---

### Step 4: Deploy

```bash
nifectl deploy
```

---

### Step 5: Select Region

Example:

```
IND - Mumbai
```

---

### Step 6: Monitor Deployment

Monitor logs for:
- Validation
- Build
- Deployment

---

### Step 7: Access Application

```
https://<your-nife-url>
```

---

## Dependencies

| Dependency  | Purpose                 |
|-------------|-------------------------|
| Node.js     | Runtime environment     |
| Express     | Web framework           |
| Socket.IO   | Real-time communication |
| JavaScript  | Application logic       |

---

## Environment Variables

| Variable | Description             | Default     |
|----------|-------------------------|-------------|
| NODE_ENV | Application environment | development |
| PORT     | Server port             | 3000        |

---

## Troubleshooting

| Issue                      | Solution                                    |
|---------------------------|---------------------------------------------|
| Port already in use       | Change port or stop process                 |
| Node not installed        | Install Node.js (`node -v`)                 |
| Dependencies not installed| Run `npm install`                           |
| App not starting          | Check logs and Node version                 |
| Docker not running        | Start Docker                               |
| Deployment fails on NIFE  | Check logs and configuration               |
| App not accessible        | Verify port mapping and routing            |

---

## Acknowledgements

This repository is maintained by Nifetency as a sample deployment project for Nife.io.

If this repository is derived from an earlier template or upstream example, it is good practice to retain visible credit to the original author or source repository.

---

## License

This project is licensed under the MIT License.

---

## References

- Original Repository: https://github.com/simondiep/node-multiplayer-snake
- NIFE Platform: https://nife.io/