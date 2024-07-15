### Kubernetes Important Points

- A pod can have multiple containers, but each container must use different port numbers.
- Every pod receives a unique IP address.
- In a Service definition, if you specify a selector like `app=nginx`, and in the Deployment workload, you label the pod with `app=nginx`, the Service will automatically connect to the pods with the matching selector.

```yaml
# Example of a Service file
apiVersion: v1
kind: Service
metadata:
  name: my-service
spec:
  selector:
    app: nginx
  ports:
    - protocol: TCP
      port: 80
      targetPort: 80
```

```yaml
# Example of a Deployment file
apiVersion: apps/v1
kind: Deployment
metadata:
  name: my-deployment
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
        - name: nginx
          image: nginx
          ports:
            - containerPort: 80
```

In this example, the Service will automatically connect to the pods created by the Deployment because they share the same `app: nginx` label.


## services in k8s

![k8s service ](./images/k8s.png)


# Kubernetes – Pods
##           Pods – The Theory

In a Docker environment, the smallest unit you deal with is a container. In the Kubernetes world, you work with a pod, which consists of one or more containers. You cannot deploy a bare container in Kubernetes without it being deployed within a pod.

The pod provides several things to the containers running within it, including options on how the container should run, any storage resources, and a network namespace. The pod encapsulates these for the containers that run inside them.
### Single Container Pods
  
The simplest way to get your containers deployed in Kubernetes is the one container per pod approach.

### Multi-container Pods

In Kubernetes, you work with pods, which consist of one or more containers. You cannot deploy a bare container without a pod.

Pods provide containers with runtime options, storage resources, and a network namespace. Containers within the same pod are tightly coupled, often sharing storage or implementing patterns like a service mesh with sidecar containers.

All containers in a pod share the same network namespace, meaning they share an IP address and must use different ports. Containers in the same pod can communicate via `localhost`.

A pod is only healthy if all its containers are ready. If one container is unhealthy, the entire pod deployment will fail.

