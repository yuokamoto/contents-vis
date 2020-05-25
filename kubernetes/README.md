## Cluster Creation/Delete with az
### Create 
cluster name: YOCluster
resource name: YOResource
- az group create --name YOResource --location japaneast
- az aks create --resource-group YOResource --name YOCluster --node-count 1 --enable-addons monitoring --generate-ssh-keys
- az aks get-credentials --resource-group YOResource --name YOCluster

### Delete
- az aks delete -n YOCluster -g YOResource
- az group delete --name YOResource

## Deploy app on cluster
### deploy
- kubectl apply -f namespace.yaml 
- kubectl apply -f backend.yaml 
- kubectl apply -f frontend.yaml 
### check
- kubectl get pod -n dev
- kubectl get service -n dev
### delete
- kubectl delete -f .

