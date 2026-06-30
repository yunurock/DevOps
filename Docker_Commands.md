# Docker Installation and Basic Commands

## Install Docker

```bash
sudo apt update
sudo apt install docker.io
docker --version
sudo systemctl start docker
sudo systemctl enable docker
```

### Verify Docker Installation

```bash
sudo docker run hello-world
```

This command downloads the **hello-world** image (if it is not already available locally) and runs a test container to verify that Docker is installed and working correctly.

---

## Docker Images

```bash
docker pull ubuntu
docker images
docker image rm <IMAGE_ID>
```

### Explanation

- **docker pull ubuntu** - Downloads the Ubuntu image from Docker Hub.
- **docker images** - Lists all downloaded Docker images.
- **docker image rm <IMAGE_ID>** - Removes the specified Docker image.

---

## Docker Containers

```bash
docker container run <IMAGE_NAME>
docker container ps
docker container ps -a
docker container logs <CONTAINER_ID>
```

### Explanation

- **docker container run <IMAGE_NAME>** - Creates and starts a new container from the specified image.
- **docker container ps** - Displays all running containers.
- **docker container ps -a** - Displays all containers, including stopped containers.
- **docker container logs <CONTAINER_ID>** - Displays the logs of the specified container.

---

## Run Containers in Different Modes

```bash
docker container run -it ubuntu
docker container run -itd ubuntu
```

#### Examples

- **docker container run -it ubuntu** - Runs the container in interactive mode.
- **docker container run -itd ubuntu** - Runs the container in detached (background) mode while keeping interactive options enabled.

---

## Inspect a Container

```bash
docker container inspect <CONTAINER_ID>
```

### Explanation

**Displays detailed information about a container, including:**

- Container ID
- IP Address
- Network settings
- Mounts
- Environment variables
- Configuration details

---

# Expose a Container Port

```bash
docker container run -itd -p 81:80 --name test-container nginx
```

### Explanation

- **-d** - Runs the container in detached mode.
- **-p 81:80**- Maps port **81** on the host to port **80** inside the container.
- **--name test-container** - Assigns the name `test-container` to the container.
- **nginx** - Uses the Nginx image.

After running this command, you can access the Nginx web server at:

For example:

```
http://192.168.1.10:81
```

## Stop and Start a Container

```bash
docker container stop <CONTAINER_ID>
docker container start <CONTAINER_ID>
```

### Explanation

- **docker container stop <CONTAINER_ID>** - Stops a running container gracefully.
- **docker container start <CONTAINER_ID>** - Starts a stopped container.

> **Note:** You can use either the **Container ID** or the **Container Name** instead of `<CONTAINER_ID>`.

### Example

```bash
docker container stop test-container
docker container start test-container
```


