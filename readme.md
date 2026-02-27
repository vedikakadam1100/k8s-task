Q1. What is the smallest unit that Kubernetes deploys?
-> B. Pod - Smallest deployable unit in Kubernetes.

Q2. Which Kubernetes object is used to expose pods to network traffic?
-> C. Service - Exposes pods to network traffic with stable IP and DNS.

Q3. Which Service type is used only for internal communication inside the cluster?
-> A. ClusterIP - Internal only access (default).

Q4. You want to access an application using <NodeIP>:<Port> .
Which Service type should you use?
-> B. NodePort - Exposes on <NodeIP>:<Port> (30000-32767).

Q5. Which Service type is mainly used in cloud environments to exposeapplications externally?
-> C. LoadBalancer - Uses cloud provider's load balancer (AWS ELB, GCP LB).

Q6. A pod is deleted accidentally. Which pod type can automatically recreate it?
-> C. Pod managed by Deployment - Automatically maintains desired replica count.

Q7. Which pod type is used to run initialization tasks before the main container starts?
-> B. Init Pod - Runs setup tasks before main containers start.

Q8. Containers inside the same pod communicate using:
-> C. Same IP address - Share network namespace, communicate via localhost.

Q9. Which Service assigns a stable internal IP address automatically?
-> C. ClusterIP - Provides stable internal IP (default Service type).

Q10. You created a Service, but traffic is not reaching the pod. What is the most common reason?
-> B. Label mismatch - Service selector labels must match pod labels.

Q11. Which Kubernetes component provides DNS-based service discovery?
-> C. CoreDNS - Provides DNS-based service discovery for cluster resources.

Q12. You want a pod to always run on a specific node. Which pod type is used?
-> C. Static Pod - Managed by kubelet, always runs on specific node.

Q13. Which Service type exposes a fixed port on every node?
-> B. NodePort - Exposes same port on all nodes (30000-32767).

Q14. You want pods inside the cluster to access an application using a DNS name. Which Service type should you use?
-> C. ClusterIP - Provides DNS name for internal cluster access.

Q15. Which command shows the IP address of a pod?
-> C. kubectl get pods -o wide - Shows pod IP, node, and additional details.

Q16. You created a LoadBalancer Service in a local cluster. What usually happens?
-> B. External IP stays pending - Local clusters lack cloud load balancer integration.

Q17. Which pod type is commonly used to support a main application with logging or monitoring?
-> C. Sidecar Pod - Runs alongside main container for logging/monitoring support.

Q18. Which Service field decides which pods receive traffic?
-> C. selector - Matches pod labels to route traffic to correct pods.

Q19. Which command is used to list all Services in a namespace?
-> C. kubectl get svc - Lists all Services in the current namespace.

Q20. Two pods in the same namespace want to communicate.
What is the recommended Kubernetes way?
-> C. Use a Service - Create a Service to enable stable communication between pods.




TASK PRACTICE: 


**Deployment Name:** `webapp-deployment`

**Service Type:** `NodePort`

**Access URL:** `http://<NodeserverIP>:30080` # nodee server chi ip ne access karaycha ahe browser madhe


## Steps to Deploy

1. **Apply the Deployment:**
   ```bash
   kubectl apply -f deployment.yaml
   ```

2. **Verify Pods are Running:**
   ```bash
   kubectl get pods
   ```

3. **Apply the Service:**
   ```bash
   kubectl apply -f service.yaml
   ```

4. **Get Node IP:**
   ```bash
   kubectl get nodes -o wide
   ```

5. **Access Application:**
   - Open browser and navigate to: `http://<NodeIP>:30080`
   - Replace `<NodeIP>` with your worker or master node IP



## Screenshot

![Screenshot of Application](test.png)

---

## Configuration Summary

- **Replicas:** 2 pods
- **Container Image:** nginx:latest
- **Container Port:** 80
- **NodePort:** 30080
- **Service Port:** 80
