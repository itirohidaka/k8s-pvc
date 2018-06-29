# Persistent Volume Claim Example

This is a example how to use the Persistent Volume Claim with IBM Cloud Kubernetes Services.

1) Creating the NFS volume and attach to Kubernetes Workers (Tier: ibmc-file-bronze / Size: 20GB):

``` Shell
kubectl apply -f iks-pv-myvolume.yaml
```

2) Verify the status of PVC creation by using the following command.

``` Shell
kubectl describe pvc mypvc
```

3) When the Status changed to "Bound" you can provisioning the PoDs with mounted volume "/myvolume"

``` Shell
kubectl apply -f iks-nginx-pvc.yaml

