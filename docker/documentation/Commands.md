# Commands

### Download an image

```bash
docker pull <image_name>
```

### See all the images

```bash
docker images
```

### See the containers

```bash
docker ps    # Just the ones that are running
docker ps -a # All the containers
docker ps -l # Get the latest created container
```

### Create a container

```bash
docker run <image_name> # It just creates the container
docker run --name <container_name> <image_name> # It creates and puts a name to the container
docker run -it <image_name> bash # It creates a container in interactive mode
docker run -d <image_name> # It creates a container in detached mode (running in background)
docker run -dit <image_name> # If the image is not prepare to run in background, run this command to create a container in detached mode
```

### Stop a container

```bash
docker stop <container_name>
```

### Tag

```bash
docker run --name apache_prueba httpd # By default it gets the latest
docker run --name apache_prueba httpd:alpine # Tag = alpine
```

To see the tag go to the documentation of the images. Also, once is downloaded, use:

```bash
docker images # In TAG column
docker ps # In IMAGE column it will be shown <image_name>:<tag>
```

### Remove containers

```bash
docker rm <container_name>
docker rm <container_id>
docker rmi <image_name>
docker rmi <image_id>
```

### Exec
```bash
docker exec <container_name> <command> # Execute the command in the running container
docker exec -it <container_name> bash # Enter in the container
```

### Attach

```bash
docker attach <container_name> # It gets associated to the command which the container is executing
```

Example:

```bash
docker run --name ubuntu_prueba -dit ubuntu top
docker attach ubuntu_prueba
```

### Logs

```bash
docker logs <container_name>
docker logs <container_name> --tail 10
docker logs <container_name> -f
```

### kill a container

```bash
docker kill <container_name>
```

### Top and Stats

```bash
docker top <container_name> # See the process of the containers
docker stat <container_name> # See the information of the container
```

### Inspect

```bash
docker inspect <container_name>
docker inspect <image_name>
docker inspect <container_name> > container.txt # Store the information of the container in container.txt
```

### Info

```bash
docker system info # Da la informacion del sistema (info del cliente y el servidor)
docker system df # Da informacion sobre el numero de contenedores que tenemos activos, cuando ocupan, etc
docker system events # Nos da informacion sobre los eventos que se produzcan dentro del mismo docker
docker system prune
```

### Copy files 

#### From OS to Container

```bash
docker cp <filename> <container_name>:<destination_path>
```

Example:

```bash
docker cp example.txt ubuntu:/tmp
```

#### From container to OS

```bash
docker cp <container_name>:<file_path/filename> <destination_path>
```

Example:

```bash
docker cp ubuntu:/tmp/example.txt /home/rafacc/Documents
```