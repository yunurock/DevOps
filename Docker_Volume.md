# Docker Volumes

## What is a Docker Volume?

A Docker Volume is a storage mechanism provided by Docker that allows data to **persist even after a container is stopped or deleted**.

Docker Volumes solve this problem by storing data **outside the container's filesystem**, allowing it to persist independently of the container.

## Key Points

- Docker Volumes are **managed by Docker**, This will run on Docker Host Machine.
- Data remains available even if the container is deleted.
- Multiple containers can share the same volume.
- Docker stores volumes outside the container's.

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

 **Note:** A volume cannot be removed if it is currently being used by a container.
 

```bash
docker volume rm my_volume
```
---
# Creating the container and deploying tomcat manually
- create the container
```bash
docker container run -itd -p 8086:8080 tomcat:latest
```
- Login to the container 

```bash
docker container exec -it container id  /bin/bash
```
- Update the packages (if needed)

```bash
apt-get update
apt-get install -y wget
```
- Download the sample.war from the browser

```bash
wget https://tomcat.apache.org/tomcat-6.0-doc/appdev/sample/sample.war
```
- Check with Ip address:portnumer in Browser
  
<img width="880" height="133" alt="image" src="https://github.com/user-attachments/assets/00f11ba1-704b-4fe4-be8a-5e8e28fc85dc" />
<img width="911" height="197" alt="image" src="https://github.com/user-attachments/assets/1fd6aa6b-9018-4be1-9de1-17fdc17ec30d" />
<img width="756" height="198" alt="image" src="https://github.com/user-attachments/assets/acb395f8-d762-4922-b410-7a80a79f182b" />

# Attaching volume to the container 

- First we will create one volume
- In side the volume will download the sample.war (wget url)
- This volume can be attach to the container
- If the container has be deleted we can able acces our volume, if we need we can attache this volume to the new container.
  
```bash
docker container run -itd -p 8085:8080 -v /var/lib/docker/volumes/tomcat:/usr/local/tomcat/webapps tomcat:latest
```
<img width="930" height="55" alt="image" src="https://github.com/user-attachments/assets/d3b4b17e-3b6c-484c-a1de-b3203f2f7553" />

# Note
- Default deployment location of tomcat: /usr/local/tomcat/webapps
- Default volumes location: /var/lib/docker/volumes

### 5. Remove All Unused Volumes

Delete all volumes that are not attached to any container.

```bash
docker volume prune
```
<img width="522" height="223" alt="image" src="https://github.com/user-attachments/assets/0235ce86-8fc9-4fda-b42c-6f4040433f40" />

