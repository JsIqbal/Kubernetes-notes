UNDER CONSTRUCTION

- cluster ip services are written on the same file as the deployment file for better engineering. one can create a different file for it if they want.

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
                app: posts
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
        app: posts-clusterip
    ports:
        - name: posts-clusterip
          protocol: TCP
          port: 4000
          targetPort: 4000
```
