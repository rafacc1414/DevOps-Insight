# Commands

```bash
echo <string_to_decode> | base64 --decode 
```


Importante: 

Tenemos que tener minikube corriendo en nuestra maquina. Para ello, lanzamos:

```bash
minikube status # Vemos el estado de minikube
minikube start # Arranca minikube
```

```bash
kubectl api-resources
kubectl describe rs <replica_name>
kubectl get pods
kubectl get pods -l app=<label_name>
kubectl get pods --show-labels
kubectl get pod <pod_name> -o yaml # Podemos buscar en la metadata del contenedor el ownerReferences
kubectl get replicaset
kubectl get replicaset --show-labels
kubectl delete pod <pod_name>
kubectl apply -f <yaml_file>
kubectl delete -f <yaml_file>

kubcectl label pods <pod_name> app=<pod_label>
kubectl get deployment --show-labels
kubectl rollout status deployment <deployment_name>
kubectl rollout history deployment # Podemos ver los rollout(Actualizaciones) que hemos hecho

kubctl create namespace <namespace_name> # Crear namespaces
kubectl describe node <node_name>

kubectl delete all --all --all-namespaces # delete everything
```


Crear la imagen custom de docker que use nuestro pod

```bash
docker build -t k8-hands-on:v1 -f Dockerfile .
```

## DNS

Se crean con la siguiente formula:

```bash
<service_name><namespace_name>servicio.cluster.local
```

## Workaround Minikube

```bash
eval $(minikube docker-env)
docker build -t my-image .
kubectl apply -f frontend.yaml
```
