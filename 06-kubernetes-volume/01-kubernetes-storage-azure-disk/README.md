## List storage objects
```t
kubectl get sc
kubectl get pvc
kubectl get pv

kubectl get pvc,pv
    - PV is not provisioned untill Pod is created as the volumeBindingMode is set to WaitForFirstConsumer.
```


## Verify Voulmes
```t
# Verify volumes details in pod metadata
kubectl get pod
kubectl describe pod nginx-app-5f58fcf9b9-ztp9l

## List volumes inside container
kubectl exec -it nginx-app-5f58fcf9b9-ztp9l -- ls -l /mnt/azure
kubectl exec -it nginx-app-5f58fcf9b9-ztp9l -- ls -l /app/resources
```

## Clean-up
```t
# Delete pod
kubectl delete -f .\03-nginx-app.yml
    
# Delete PVC
kubectl delete -f .\02-persistent-volume-claim.yml
kubectl get pvc,pv
    - PVC is deleted however the PV and Azure Disk exist as the the reclaimPolicy is set to Retain.
    - Need to delete both PV and Azure Disk explicitly as the reclaimPolicy is Retain.

# Delete PV
kubectl delete pv pvc-34711644-acda-4eca-a24b-1e2a198a6b7d
kubectl get pv

# Delete the Azure Disk from the portal or cli

# Delete SC
kubectl delete -f .\01-storage-class.yml
kubectl get sc
```