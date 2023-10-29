create a service deployment for kubernetes:

example:

```yaml
apiVersion: v1
kind: Service
metadata:
    name: posts-srv
spec:
    type: NodePort
    selector:
        app: posts
    ports:
        - name: posts
          protocol: TCP
          port: 4000
          targetPort: 4000
```

 kubectl apply -f posts-srv.yaml
 kubectl get services
kubectl describe service posts-srv
kubectl logs service posts-srv
