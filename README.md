# Kubernetes Learning Project

This repository contains a comprehensive collection of Kubernetes configuration examples and documentation to help you learn Kubernetes concepts and best practices.

## Project Structure

```
├── concepts.txt           # Comprehensive Kubernetes concepts guide
├── pods/                 # Pod configuration examples
├── namespace/            # Namespace configuration examples
├── deploments/           # Deployment configuration examples
├── replicas/             # ReplicaSet configuration examples
├── deamon-sets/          # DaemonSet configuration examples
├── jobs/                 # Job and CronJob examples
├── vloumes/              # Volume and PersistentVolume examples
```

## Prerequisites

1. Install Docker Desktop

   ```bash
   # For macOS (using Homebrew)
   brew install --cask docker
   ```

2. Install kubectl

   ```bash
   # For macOS (using Homebrew)
   brew install kubectl
   ```

3. Install Minikube
   ```bash
   # For macOS (using Homebrew)
   brew install minikube
   ```

## Setting Up Minikube

1. Start Minikube

   ```bash
   minikube start
   ```

2. Verify Installation

   ```bash
   kubectl version
   minikube status
   ```

3. Enable Required Addons
   ```bash
   minikube addons enable ingress
   minikube addons enable metrics-server
   ```

## Learning Path

### 1. Start with Core Concepts

1. Read through `concepts.txt` to understand Kubernetes fundamentals
2. Study the architecture and components
3. Understand the relationship between different resources

### 2. Hands-on with Basic Resources

1. **Pods (`pods/nginx.pod.yaml`)**

   - Learn basic pod configuration
   - Practice creating and managing pods

   ```bash
   kubectl apply -f pods/nginx.pod.yaml
   kubectl get pods
   kubectl describe pod <pod-name>
   ```

2. **Namespaces (`namespace/ngnx.ns.yml`)**
   - Understand resource isolation
   - Practice namespace management
   ```bash
   kubectl apply -f namespace/ngnx.ns.yml
   kubectl get namespaces
   ```

### 3. Workload Resources

1. **Deployments (`deploments/nginx.deploymnet.yaml`)**

   - Learn about rolling updates
   - Practice scaling applications

   ```bash
   kubectl apply -f deploments/nginx.deploymnet.yaml
   kubectl get deployments
   kubectl rollout status deployment/<deployment-name>
   ```

2. **ReplicaSets (`replicas/nginx-set.replica.yaml`)**

   - Understand pod replication
   - Practice high availability

3. **DaemonSets (`deamon-sets/nginx.deamon.yml`)**
   - Learn about node-level services
   - Practice clustuer-wide deployments

### 4. Jobs and Scheduling

1. **Jobs (`jobs/demo.job.yml`)**

   - Understand batch processing
   - Practice job management

2. **CronJobs (`jobs/cron-demo.cronjob.yml`)**
   - Learn about scheduled tasks
   - Practice cron expressions

### 5. Storage and State

1. **Volumes (`vloumes/persistant-volume.yml`)**
   - Understand persistent storage
   - Practice volume management

## Best Practices

1. Always use version control for your configurations
2. Follow the principle of least privilege
3. Use resource limits and requests
4. Implement health checks
5. Use meaningful labels and annotations
6. Keep configurations DRY (Don't Repeat Yourself)

## Common Commands

```bash
# Context and clustuer Info
kubectl config get-contexts
kubectl clustuer-info

# Resource Management
kubectl get <resource>
kubectl describe <resource> <name>
kubectl delete <resource> <name>

# Logs and Debugging
kubectl logs <pod-name>
kubectl exec -it <pod-name> -- /bin/bash

# Port Forwarding
kubectl port-forward <pod-name> 8080:80
```

## Cleanup

```bash
# Stop Minikube
minikube stop

# Delete Minikube clustuer
minikube delete
```

## Additional Resources

- [Official Kubernetes Documentation](https://kubernetes.io/docs/)
- [Kubernetes Patterns](https://kubernetes.io/docs/concepts/clustuer-administration/manage-deployment/)
- [Kubernetes Best Practices](https://kubernetes.io/docs/concepts/configuration/overview/)

## Contributing

Feel free to contribute by:

1. Adding new examples
2. Improving documentation
3. Fixing errors
4. Sharing learning tips

## License

This project is licensed under the MIT License - see the LICENSE file for details.
