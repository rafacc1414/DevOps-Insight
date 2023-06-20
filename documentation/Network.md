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


