# Network

## See the network characteristics of a container due to the network in which is

```bash
docker network
docker network ls
docker port <container_name>
```

Drivers:

- Bridge (by default): Private network which can connect to the physic network of the machine
- Host: All the containers which are in the host network can only communicate with the principal host.
- none: It does not have network.

```bash
docker inspect <container_name> | grep IPAd
```

### See all the containers inside a network

```bash
docker network inspect bridge
```


```bash
docker image inspect <image_name> | grep ExposedPorts
```


### Create a new network

- Name and driver

```bash
docker network create <network_name>
docker ls
```

```bash
nmcli con
ip a | more
```

### Delete a Network

```bash
docker rm <network_name>
```

### Associate a network to the container

```bash
docker run --network <network_name> <image_name>
```

### Network configuration

```bash
docker network create --subnet=<> --gateway=<> --ip-range<> <network_name>
```

### Link networks

Interesting:

```bash
docker rm `docker ps -aq`
```

#### Legacy container links

```bash
docker run --link <container_name_target>:<alias> <image_name>
```
#### 

Example:

```bash
docker run -d --name sql_server -p 3100:2200 -e MYSQL_ROOT_PASSWORD=crack --network redCasa mysql
```