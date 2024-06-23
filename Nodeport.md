Nodeport is used to expose a pod to the outside world from a containerize environemnt.

Suppose we have a service deployment file like this:

```yaml
apiVersion: v1
kind: Service
metadata:
    name: posts-srv # will be identified as this service name for kubernetes service
spec:
    type: NodePort
    selector:
        app: posts # find this pod and expose this in the outside world
    ports:
        - name: posts
          protocol: TCP
          port: 4000 # Node port
          targetPort: 4000 # container port
```

when we will create the service using:

```bash
kubectl apply -f posts-srv.yaml
```

then a new service will be created.

as the file describes:

-   NodePort is a kind of service that will give us access of a container running inside a pod from the browser in the host computer.
-   the port in the ports section is the port of the node service which is running on a dedicated port.
-   NodePort -> nodeport service port -> container port that we want to access.
-   NodePort can be found here:
    -   ```bash
        kubectl describe service posts-srv
        ```
    -   result will be:
        ```bash
            Name:                     posts-srv
            Namespace:                default
            Labels:                   <none>
            Annotations:              <none>
            Selector:                 app=posts
            Type:                     NodePort
            IP Family Policy:         SingleStack
            IP Families:              IPv4
            IP:                       10.100.28.189
            IPs:                      10.100.28.189
            Port:                     posts  4000/TCP
            TargetPort:               4000/TCP
            NodePort:                 posts  30963/TCP
            Endpoints:                10.1.0.91:4000
            Session Affinity:         None
            External Traffic Policy:  Cluster
            Events:                   <none>
        ```
    -   Nodeport is specified as NodePort in here.

In a windows or linux machine we can access out post container in this url:

http://localhost:30963/posts

because:

-   the targetport is the container port for the nodeport to access from the browser. Quite confusing!
-   look at the yaml file for service configuration and you will understand
