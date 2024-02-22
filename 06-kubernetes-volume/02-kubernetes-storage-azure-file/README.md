**Important Note:** Azure Files support premium storage in AKS clusters that run Kubernetes 1.13 or higher, minimum premium file share is 100GB


## List storage objects
```t
kubectl get sc
kubectl get pvc
kubectl get pv

kubectl get pvc,pv
    - PV is provisioned immediately as the volumeBindingMode is set to Immediate.
```

## Add File to Files shares
Storage Account >> File shares >> Select the file share >> Upload >> Upload files


## Verify Voulmes
```t
# Verify volumes details in pod metadata
kubectl get pod
kubectl describe pod nginx-app-67f754dd56-zb4ll

## List volumes inside container
kubectl exec -it nginx-app-67f754dd56-zb4ll -- ls -l /usr/share/nginx/html/app1
total 1
-rw-r----- 1 root root 217 Feb 16 10:38 file1.html
-rw-r----- 1 root root 217 Feb 16 10:38 file2.html
```

## Access Application & Test
```t
http://<External-IP-from-get-service-output>

http://4.144.37.30/app1/file1.html
http://4.144.37.30/app1/file2.html
``` 

## Clean-up
```t
# Delete pod
kubectl delete -f .\03-nginx-app.yml
    
# Delete PVC
kubectl delete -f .\02-persistent-volume-claim.yml
kubectl get pvc,pv
    - Both PVC and PV are deleted as the the reclaimPolicy is set to Delete.
    - Azure File share is also deleted along with PVC and PV.

# Delete PV
kubectl delete pv pvc-34711644-acda-4eca-a24b-1e2a198a6b7d
kubectl get pv

# Delete the Azure Disk from the portal or cli

# Delete SC
kubectl delete -f .\01-storage-class.yml
kubectl get sc
```













## List storage objects
```t
kubectl get sc
kubectl get pvc
kubectl get pv

kubectl get sc,pvc,pv
```

## List volumes inside container
```t
kubectl exec -it nginx-app-869648c85f-9bpzp -- ls -l /usr/share/nginx/html/app1
```



## Clean-up
```t
# Delete k8s objects
kubectl delete .

# List storage objects
kubectl get sc,pvc,pv

# Need to delete pv explicitly as the reclaimPolicy is Retain
kubectl delete pv <pv-name>