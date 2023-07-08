# Variables

It allows to pass variables to the container. This ability is used to create __dinamic containers__


Example:

```bash
docker run --name <container_name> -d -it -e V1=14 -e V2=20 <image_name>

docker exec -it <image_name> bash

printenv
echo $V1
echo $V2
```

Variables can be stored in a file and be passed all toguether:

```bash
docker run --name <prueba>--env-file <variables_filename> <image_name>
```
