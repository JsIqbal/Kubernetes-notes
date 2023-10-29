# Setting Up a Kubernetes Service Deployment

This guide demonstrates how to set up a service deployment for Kubernetes. You can follow the example YAML configuration provided below to create a service for your Kubernetes cluster.

## Example YAML Configuration

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

## Instructions for Deployment
-    Apply the configuration using the following command:
```bash
kubectl apply -f posts-srv.yaml
```

-    Verify the service deployment:
```bash
kubectl get services
```

-    Obtain detailed information about the service:
```bash
kubectl describe service posts-srv
```

-    Check the logs for the service:
```bash
kubectl logs service posts-srv
```
