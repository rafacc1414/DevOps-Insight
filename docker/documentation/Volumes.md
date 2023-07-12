# Volumes

With a volume, it can be done:

- Use a persistent space of memory for a container.
- Share the memory between the host and the container.
- Share the memory between diferent containers.

In the directory: ```/var/lib/docker``` there a lot of important directories which store esential docker information.

Volumes can be mounted in several containers.
If any container is pointing to the volume because the containers were removed, the volume gets unable and it cannot be associated again to a container. If we want to recover the information it is need to go to the directory ```/var/lib/docker/<volume_name>``` get all the files and move them to new volume.

## Create a volume in a interactive way

```bash
docker run -it -v <volume_container_directory> --name <container_name> <image_name> bash
```

## Get information of the volume

```bash
docker volume inspect <volume_name>
```

## Create a volume

```bash
docker volume create <volume_name> # Create the volume
docker run it --name <container_name> -v <volume_name>:<volume_container_directory> <image_name> bash # Link the volume to the path inside the container
docker run it --name <container_name> -volumes-from <container_name> <image_name> bash # Get the volumes of another container
```

## Remove all volumes which are not used

```bash
docker volume prune
```

## Bind Mounts

```bash
docker run -it -v <container_directory>:<host_directory> <image_name> bash
```

## Temporary (tmpfs) mounts

![Types of mounts](./images/types-of-mounts-tmpfs.png)

```bash
docker run -d -i --name <image_name> --tmpfs <temporal_directory_in_the_container> <image_name>
```

The temporal directory will not survive to the stop and run of the container

