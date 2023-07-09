# Commands

```bash
kubectl api-resources
kubectl describe rs <replica_name>
kubectl get pods
kubectl get pods -l app=<label_name>
kubectl get pods --show-labels
kubectl get pod <pod_name> -o yaml #Podemos buscar en la metadata del contenedor el ownerReferences
kubectl get replicaset
kubectl get replicaset --show-labels
kubectl delete pod <pod_name>
kubectl apply -f <yaml_file>
kubectl delete -f <yaml_file>

kubcectl label pods <pod_name> app=<pod_label>
kubectl get deployment --show-labels
kubectl rollout status deployment <deployment_name>
kubectl rollout history deployment # Podemos ver los rollout(Actualizaciones) que hemos hecho
```