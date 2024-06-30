# Cluster Ip Service: kubernetes object for pod communication with each other

-   cluster ip services are written on the same file as the deployment file for better engineering. one can create a different file for it if they want.

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
    name: posts-depl
spec:
    replicas: 1
    selector:
        matchLabels:
            app: posts
    template:
        metadata:
            labels:
                app: posts # This is the pod
        spec:
            containers:
                - name: posts
                  image: jsiqbal/posts
---
apiVersion: v1
kind: Service
metadata:
    name: posts-clusterip-srv
spec:
    selector:
        app: posts # The pod that is selected to use the cluster Ip service
    ports:
        - name: posts
          protocol: TCP
          port: 4000
          targetPort: 4000
```
