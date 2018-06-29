# Persistent Volume Claim Example

This is a example how to use the Persistent Volume Claim with IBM Cloud Kubernetes Services.

## Step-by-Step
1) Creating the NFS volume and attach to Kubernetes Workers (Tier: ibmc-file-bronze / Size: 20GB):

``` console
kubectl apply -f iks-pv-myvolume.yaml
```

2) Verify the status of PVC creation by using the following command.

``` console
kubectl describe pvc mypvc
```

3) When the Status changed to "Bound" you can provisioning the PoDs with mounted volume "/myvolume". This example creates 2 replicas of nginx deployment.

``` console
kubectl apply -f iks-nginx-pvc.yaml
```

4) You can verify the directory myvolume create on /. 
``` console
kubectl get pods
kubectl exec -it <pod-name> ls /
```

:+1: :cloud:

## References
[IBM Cloud DOCs](https://console.bluemix.net/docs/containers/cs_storage.html#create)
