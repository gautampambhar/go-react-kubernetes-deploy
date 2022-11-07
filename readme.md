--namespace=gautam-test 


1. kubectl apply -f nginx-deployment.yaml --namespace=gautam-test 
2. kubectl get pod --namespace=gautam-test | kubectl describe pod nginx-deployment-78cc6468fb-fvlb5 --namespace=gautam-test 
3. kubectl get service --namespace=gautam-test | kubectl describe service nginx-service --namespace=gautam-test 
4. kubectl get pod -o wide --namespace=gautam-test // more output about the pod

5. kubectl delete -f nginx-deployment.yaml --namespace=gautam-test | kubectl delete -f nginx-service.yaml --namespace=gautam-test

# MENIFEST FILE 
1. METADATA contains lables 
    - you give key-value pair for component as a label. and this label sticks to this component
2. SPEC contains selectors 


# PV and PV Claim

We will use a persistent volume (PV) to define a directory in our host machine that we will allow our Postgres container to use to store data files. Then, a persistent volume claim (PVC) is used to define a “request” for some of that available disk space that a specific container can make. 

In short, a persistent volume says to K8s “here’s some storage that the cluster can use” and a persistent volume claim says “here’s a portion of that storage that’s available for containers to use”.


In summary: We created a persistent volume that defines some disk space in our machine that’s available to the cluster; then we defined a persistent volume claim that represents a request of some of that space that a container can have access to; after that we defined a volume within our pod configuration in our deployment to point to that persistent volume claim; and finally we defined a volume mount in our container that uses that volume to store the Postgres database files.

