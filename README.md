# Node Multiplayer Snake Game

A simple **Node.js multiplayer game** published as a **sample deployment project for Nife.io**.

This repository demonstrates how to run a real-time multiplayer application locally, package it with Docker, and deploy it on Nife.io. It is intended as a practical sample for validating Node.js deployment workflows, container-based delivery, and real-time communication systems.

---

## Overview

This project is a real-time multiplayer snake game built using Node.js, Express, and Socket.IO. It demonstrates server-client synchronization using WebSockets along with interactive browser-based gameplay.

If you want a simple real-time backend project to test deployment on Nife.io, this repository is a good starting point.

---

## Features

| Feature               | Description                           |
| --------------------- | ------------------------------------- |
| Multiplayer gameplay  | Real-time interaction between players |
| Socket.IO integration | Enables WebSocket-based communication |
| Player customization  | Name and color selection              |
| Admin controls        | Adjust speed, bots, food settings     |
| Spectator mode        | Watch ongoing matches                 |
| Statistics tracking   | Score, kills, and deaths              |
| Custom assets         | Upload snake and background images    |
| Interactive gameplay  | Walls, effects, and notifications     |

---

## Tech Stack

| Technology | Purpose                 |
| ---------- | ----------------------- |
| Node.js    | Runtime environment     |
| Express    | Web framework           |
| Socket.IO  | Real-time communication |
| JavaScript | Application logic       |
| Docker     | Containerization        |
| Nife.io    | Deployment platform     |

---

## Prerequisites

Before running the project locally, make sure the following are installed.

| Requirement | Notes                        |
| ----------- | ---------------------------- |
| Node.js     | Version 8 or higher          |
| npm         | Comes with Node.js           |
| Git         | Required to clone repository |

---

## Getting Started

### Clone the repository

```bash
git clone https://github.com/simondiep/node-multiplayer-snake.git
cd node-multiplayer-snake
```

### Install dependencies

```bash
npm install
```

### Run the application

```bash
npm start
```

Then open the application at `http://localhost:3000`.

---

## Run with Docker

This project includes a Dockerfile for container-based execution.

### Build the image

```bash
docker build -t node-multiplayer-snake .
```

### Run the container

```bash
docker run -p 3000:3000 node-multiplayer-snake
```

After the container starts, open the app at `http://localhost:3000`.

---

## Deploy on Nife.io

You can deploy this application on Nife.io using either a Docker image, the source repository, or the CLI.

---


### Option 1: Deploy from the Git repository

You can also deploy the project directly from GitHub.

| Setting       | Value                       |
| ------------- | --------------------------- |
| Source        | Git Repository              |
| Provider      | GitHub                      |
| Branch        | `main`                      |
| Internal Port | `3000`                      |
| External Port | `80`                        |
| Build Mode    | Auto-Dockerize with runtime |

---

### Option 2: Deploy with `nifectl`

If you prefer the command line, use the following workflow.

```bash
nifectl auth login
nifectl init
nifectl deploy
```

For step-by-step instructions, see the 
[Nife.io Quick Deploy documentation](https://docs.nife.io/overview/quick-deploy) 
and the 
[nifectl quick start guide](https://docs.nife.io/Quick-Start/Nifectl).

## Environment Variables

The following variables are commonly relevant for deployment.

| Variable | Description             | Example      |
| -------- | ----------------------- | ------------ |
| NODE_ENV | Application environment | `production` |
| PORT     | Server port             | `3000`       |

---

## Repository Structure

| Path           | Purpose                      |
| -------------- | ---------------------------- |
| `public/`      | Frontend assets              |
| `src/`         | Server-side logic            |
| `Dockerfile`   | Container build instructions |
| `package.json` | Project dependencies         |
| `server.js`    | Entry point                  |

---

## Troubleshooting

| Issue                       | Suggested fix                           |
| --------------------------- | --------------------------------------- |
| Port 3000 already in use    | Stop conflicting process or change port |
| Dependencies not installed  | Run `npm install`                       |
| App not starting            | Check logs and Node version             |
| Docker build fails          | Verify Dockerfile                       |
| Deployment fails on Nife.io | Check ports and configuration           |
| App not accessible          | Verify routing and logs                 |

---

## Acknowledgements

This repository is maintained by **Nifetency** as a sample deployment project for [Nife.io](https://nife.io).

If this repository is derived from an earlier template or upstream example, it is good practice to retain visible credit to the original author or source repository.


## License

This project is licensed under the MIT License.

---

## References

1. [Nife.io](https://nife.io)
2. [Nife Docs Overview](https://docs.nife.io/overview/)
3. [Original Repository](https://github.com/nifetency/node-multiplayer-snake.git)
4. [Nife Quick Start](https://docs.nife.io/Quick-Start)
