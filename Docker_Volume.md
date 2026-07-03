# Docker Volumes

## What is a Docker Volume?

A Docker Volume is a storage mechanism provided by Docker that allows data to **persist even after a container is stopped or deleted**.

By default, any data created inside a container is stored in the container's writable layer. Since containers are **ephemeral (temporary)**, this data is lost when the container is removed.

Docker Volumes solve this problem by storing data **outside the container's filesystem**, allowing it to persist independently of the container.

## Key Points

- Docker Volumes are **managed by Docker**.
- Data remains available even if the container is deleted.
- Multiple containers can share the same volume.
- Volumes are the recommended storage option for **databases, Jenkins, logs, and application data**.
- Docker stores volumes outside the container's writable layer.

## Common Docker Volume Commands

### 1. Create a Volume

Create a new Docker volume.

```bash
docker volume create my_volume
```

---

### 2. List All Volumes

Display all Docker volumes available on the host.

```bash
docker volume ls
```

---

### 3. Inspect a Volume

View detailed information about a specific volume, such as its mount point, driver, and labels.

```bash
docker volume inspect my_volume
```

---

### 4. Delete a Volume

Remove a specific Docker volume.

> **Note:** A volume cannot be removed if it is currently being used by a container.

```bash
docker volume rm my_volume
```

---

### 5. Remove All Unused Volumes

Delete all volumes that are not attached to any container.

```bash
docker volume prune
```
<img width="522" height="223" alt="image" src="https://github.com/user-attachments/assets/0235ce86-8fc9-4fda-b42c-6f4040433f40" />

