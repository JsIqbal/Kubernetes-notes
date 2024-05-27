# KUBERNETES: a platform for automating deployment, scaling, and operations of application containers across clusters of hosts.

Kubernetes objects are the entities that represent the state of your cluster. They are the building blocks of Kubernetes and allow you to describe your desired state for the cluster. There are several types of Kubernetes objects, each serving a unique purpose. Here are the main categories:

1. **Core Objects**:

    - **Pods**: The smallest and simplest unit in the Kubernetes object model that you create or deploy. A Pod represents processes running on your cluster.
    - **Services**: An abstraction which defines a logical set of Pods and a policy by which to access them. Services enable loose coupling between dependent Pods.
    - **Deployments**: Provide declarative updates for Pods and ReplicaSets. You describe a desired state in a Deployment, and the Deployment Controller changes the actual state to the desired state at a controlled rate.
    - **ReplicaSets**: Ensure that a specified number of pod replicas are running at any given time. They are often used to guarantee the availability of a specified number of identical pods.
    - **StatefulSets**: Manage the deployment and scaling of a set of Pods and provide guarantees about the ordering and uniqueness of these Pods.
    - **DaemonSets**: Ensure that all (or some) Nodes run a copy of a Pod. As nodes are added to the cluster, Pods are added to them. As nodes are removed from the cluster, those Pods are garbage collected.
    - **Jobs**: Create one or more Pods and ensure that a specified number of them successfully terminate. Use Jobs when you need to run a task that must complete successfully.
    - **CronJobs**: Schedule Jobs on a repeating interval. CronJobs are useful for regular maintenance jobs, such as cleaning up old data.

2. **Namespaced Objects**:

    - **ConfigMaps**: Store configuration data as key-value pairs. ConfigMaps can be consumed by Pods.
    - **Secrets**: Store sensitive information such as passwords, OAuth tokens, and ssh keys. Secrets can be consumed by Pods.
    - **PersistentVolumeClaims**: Request storage by specifying size and access modes. Pods use PersistentVolumeClaims as a request for storage.

3. **Cluster-wide Objects**:
    - **Namespace**: Provides a scope for Namespaced objects. Namespaces are intended for use in environments with many users spread across multiple teams, or projects.
    - **Role-Based Access Control (RBAC)**: Defines permissions within the cluster. RBAC controls who can do what to which resources.

These objects work together to manage the lifecycle of applications running on Kubernetes, handling everything from deployment and scaling to storage and networking.

---

# Understanding Kubernetes Components

Kubernetes is a container orchestration tool that helps manage containerized applications. It comprises several key components:

## Kubernetes Cluster

A Kubernetes cluster is a set of nodes managed by Kubernetes to deploy and manage containerized applications. It includes a control plane and worker nodes.

## Nodes

Nodes are individual machines within the Kubernetes cluster responsible for running applications and services. They can be either virtual or physical machines.

## Pods

Pods are the smallest deployable units in Kubernetes. They consist of one or more containers that share resources and represent the basic units of deployment.

## Deployments

Deployments are used to manage the lifecycle of pods, facilitating their creation, updating, and scaling. They ensure that the desired state of the application is maintained.

## Services

Services enable communication between different sets of pods and act as stable network endpoints for accessing the pods. They are crucial for load balancing and service discovery within the Kubernetes cluster.

For more detailed information on Kubernetes and its functionalities, refer to the following section.

## Understanding Kubernetes

Kubernetes is an open-source container orchestration system that automates the deployment, scaling, and management of containerized applications. It provides a platform for automating the management of application containers, allowing developers to focus on designing and implementing their applications without worrying about the underlying infrastructure.

Kubernetes provides an extensive set of features, including:

-   Automated rollouts and rollbacks
-   Service discovery and load balancing
-   Self-healing
-   Secret and configuration management
-   Horizontal scaling

By utilizing these capabilities, Kubernetes simplifies the process of deploying and managing applications, making it an essential tool for modern cloud-native application development.
