# curl-pod
Create a Pod so that it can view all pods in the 'default' namespace through the 'curl' command

Use the following command to create the Pod in your Kubernetes cluster:
```sh
kubectl apply -f curl-pod.yaml
```
Once the Pod is created, you can access its shell using the kubectl exec command:
```sh
kubectl exec -it curl-pod -- /bin/sh
```
Run the curl command:
```sh
curl -k -H "Authorization: Bearer $(cat /var/run/secrets/kubernetes.io/serviceaccount/token)" \
     https://kubernetes.default.svc.cluster.local/api/v1/namespaces/default/pods
```



