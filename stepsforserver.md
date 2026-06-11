# Git Workflow & Deployment Guide

This document describes the standard development, release, and deployment workflow for the project.

---

## Branch Strategy

* **master** → Development branch
* **prod** → Production branch

### Workflow Overview

```text
Developer Changes
        │
        ▼
   Local Master
        │
        ▼
 Push to Master
        │
        ▼
 Merge Master → Prod
        │
        ▼
 Pull Prod on Server
        │
        ▼
 Docker Deployment
```

---

## Sync Master with Prod

Use the following commands only when you need to make the **master branch identical to the prod branch**.

```bash
git checkout master
git reset --hard prod
git push origin master --force
```

> Warning: This operation overwrites the history of the master branch.

---

# Development Workflow

## Step 1: Switch to Master Branch

```bash
git checkout master
```

## Step 2: Commit and Push Changes

```bash
git add .
git commit -m "commit message"
git push origin master
```

---

# Release Workflow

## Step 3: Merge Master into Prod

### Update Local Master

```bash
git checkout master
git pull origin master
```

### Update Local Prod

```bash
git checkout prod
git pull origin prod
```

### Merge Changes

```bash
git merge master
```

### Push to Production Branch

```bash
git add .
git commit -m "Merge master into prod"
git push origin prod
```

---

# Server Deployment

## Step 4: Pull Latest Production Code

```bash
git pull origin prod
```

## Rebuild and Restart Containers

```bash
docker compose down

docker compose build

docker compose up -d
```

---

# Docker Commands

## View Running Containers

```bash
docker ps
```

## View Container Logs

```bash
docker logs <container_id>
```

### Example

```bash
docker logs 8a1b2c3d4e5f
```

## Follow Logs in Real Time

```bash
docker logs -f <container_id>
```

## Stop Containers

```bash
docker compose down
```

## Start Containers

```bash
docker compose up -d
```

## Rebuild Containers

```bash
docker compose build
```

---

# Quick Deployment Commands

```bash
git pull origin prod

docker compose down
docker compose build
docker compose up -d
```

---

# Troubleshooting

### Check Container Status

```bash
docker ps -a
```

### Check Container Logs

```bash
docker logs -f <container_id>
```

### Verify Running Services

```bash
docker compose ps
```
