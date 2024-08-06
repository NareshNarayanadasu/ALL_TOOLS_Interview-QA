### 1. What is a Replica Set?

A Replica Set in Kubernetes ensures that a specified number of pod replicas are running at any given time. It monitors the state of the pods and, if any pod goes down, the Replica Set will automatically launch a new pod to replace it, maintaining the desired number of replicas.

### 2. What is the use of multiple pods?

Multiple pods are used to ensure high availability, load balancing, and fault tolerance of an application. By having multiple instances of a pod, the application can handle more traffic and remain available even if some pods fail.

### 3. What happens when one pod goes down?

When a pod goes down, the Replica Set controller detects the failure and creates a new pod to replace the failed one. This ensures that the desired state of the application, as defined in the Replica Set, is maintained.

### 4. How does Kubernetes know that a pod has gone down?

Kubernetes uses the kubelet agent running on each node to monitor the status of pods. The kubelet reports the status of the pods to the Kubernetes API server, which can detect when a pod has failed and take action to replace it.

### 5. What are liveness and readiness probes?

- **Liveness Probes**: These checks determine if a pod is running. If a liveness probe fails, Kubernetes will restart the pod.
- **Readiness Probes**: These checks determine if a pod is ready to serve traffic. If a readiness probe fails, the pod is marked as unready and is removed from the pool of available pods for service until it passes the readiness check again.

### 6. What happens if we run out of memory?

If a pod runs out of memory, it may be terminated by the Kubernetes scheduler. Kubernetes uses Quality of Service (QoS) classes to prioritize pod eviction when the node is under resource pressure. Pods with lower QoS are more likely to be evicted.

### 7. How do you enable auto-scaling in Kubernetes?

You can enable auto-scaling in Kubernetes using the Horizontal Pod Autoscaler (HPA). The HPA automatically scales the number of pods in a deployment, Replica Set, or stateful set based on observed CPU utilization or other select metrics.

### 8. What are the properties of deployments in Kubernetes?

- **Replica Management**: Ensures the specified number of pod replicas are running.
- **Rollouts**: Supports rolling updates and rollbacks to previous versions.
- **Declarative Updates**: Manages updates to the pod template in a declarative manner.
- **Scaling**: Supports horizontal scaling of pods.
- **Self-healing**: Replaces failed or terminated pods automatically.

### 9. How do you get CPU metrics in Kubernetes?

CPU metrics in Kubernetes can be obtained using the Metrics Server, which is an aggregator of resource usage data in your cluster. Tools like `kubectl top` can be used to view CPU and memory usage of nodes and pods.

### 10. How would you deploy a Java application through Kubernetes?

1. **Create a Docker image** of the Java application.
2. **Push the Docker image** to a container registry (e.g., Docker Hub or AWS ECR).
3. **Create Kubernetes manifests** (Deployment, Service, ConfigMap, etc.) for the application.
4. **Apply the manifests** using `kubectl apply -f <manifest.yaml>`.
5. **Expose the application** using a Service or Ingress if needed.

### 11. What is the difference between a Service and an Ingress in Kubernetes?

- **Service**: Provides networking abstraction to expose pods, typically within a cluster or to external clients. It can be of type ClusterIP, NodePort, or LoadBalancer.
- **Ingress**: Manages external access to services, typically HTTP and HTTPS. It provides routing rules based on hostnames or paths to expose multiple services under a single IP address.

### 12. What is the use of an Ingress in Kubernetes?

An Ingress allows you to define rules for routing external HTTP(S) traffic to internal services. It provides features like load balancing, SSL termination, and name-based virtual hosting.

### 13. If a ReplicaSet with 3 replicas needs to be deployed on different nodes, how would you ensure each replica is deployed on an individual node?

You can use **pod anti-affinity rules** in the pod specification to ensure that each replica is scheduled on a different node. For example:

```yaml
affinity:
  podAntiAffinity:
    requiredDuringSchedulingIgnoredDuringExecution:
    - labelSelector:
        matchExpressions:
        - key: app
          operator: In
          values:
          - my-app
      topologyKey: "kubernetes.io/hostname"
```

### 14. What is the purpose of namespaces in Kubernetes?

Namespaces provide a way to divide cluster resources between multiple users or teams. They create isolation and organization of resources within the cluster, making it easier to manage and control access.

### 15. How can you block resources in one namespace from being accessed by another namespace?

You can block access between namespaces using **Network Policies**. Network Policies are applied to pods and define how they are allowed to communicate with each other and other network endpoints.

### 16. How does Role-Based Access Control (RBAC) work in Kubernetes?

RBAC in Kubernetes controls access to resources based on the roles of users. It uses Roles and ClusterRoles to define sets of permissions and RoleBindings and ClusterRoleBindings to grant those roles to users or groups.

### 17. What are the specific resources in Kubernetes?

Specific resources in Kubernetes include:
- **Pods**
- **Services**
- **Deployments**
- **ReplicaSets**
- **StatefulSets**
- **DaemonSets**
- **ConfigMaps**
- **Secrets**
- **PersistentVolumes**
- **PersistentVolumeClaims**
- **Namespaces**
- **NetworkPolicies**

### 18. How does Kubernetes know the latest deployment?

Kubernetes tracks deployments using the Deployment resource, which maintains the desired state and the current state. When you update a deployment, Kubernetes creates a new ReplicaSet and progressively rolls out the new pods while scaling down the old ones.

### 19. What is a private subnet?

A private subnet is a subnet that does not have a route to the internet through an internet gateway. Instances in a private subnet cannot directly communicate with the internet.

### 20. Can I work with private subnets?

Yes, you can work with private subnets. You need to use a NAT gateway or NAT instance to allow instances in private subnets to initiate outbound connections to the internet while keeping them isolated from incoming internet traffic.

### 21. What is the difference between an endpoint and a NAT gateway?

- **Endpoint**: A VPC endpoint allows you to privately connect your VPC to supported AWS services and VPC endpoint services powered by PrivateLink without an internet gateway, NAT device, VPN connection, or AWS Direct Connect connection.
- **NAT Gateway**: A NAT gateway allows instances in a private subnet to connect to the internet or other AWS services but prevents the internet from initiating a connection with those instances.

### 22. What are route tables in AWS?

Route tables in AWS are used to determine where network traffic is directed. Each subnet in a VPC is associated with a route table that controls the routing of network traffic for the subnet.

### 23. If you created a public and a private subnet, what would be your default rule in the route table?

- **Public Subnet**: The route table would have a route directing traffic to the internet gateway.
- **Private Subnet**: The route table would have a route directing traffic to a NAT gateway or NAT instance in a public subnet for internet-bound traffic.

### 24. Explain the three-tier architecture.

The three-tier architecture consists of:
1. **Presentation Tier**: The user interface or client layer.
2. **Application Tier**: The business logic or application server layer.
3. **Data Tier**: The database server layer.

### 25. What is a DDoS attack?

A Distributed Denial of Service (DDoS) attack is a malicious attempt to disrupt the normal traffic of a targeted server, service, or network by overwhelming the target or its surrounding infrastructure with a flood of internet traffic.

### 26. How would you block a DDoS attack?

To block a DDoS attack, you can:
- Use a Web Application Firewall (WAF).
- Employ a DDoS mitigation service like AWS Shield.
- Set up rate limiting and access control.
- Use network firewalls and intrusion prevention systems.
- Employ content delivery networks (CDNs) to distribute traffic.
- Monitor and respond to unusual traffic patterns with automated systems.