# Django Kubernetes Deployment

This repository contains Kubernetes YAML configurations for deploying a Django application to a Kubernetes cluster. The setup includes a Namespace, Deployment, and Service to manage the application.

[!NOTE]
I'm using `k3s` distribution, you can use anything you like !!
---
## Files in the Repository
- `namespace.yml` : Defines a namespace for isolating resources for the Django application.
- `deployment.yml` : Configures the deployment of the Django application, including the number of replicas, container image, and ports.

- `service.yml` : Exposes the Django application to the network within the cluster and provides a stable endpoint for accessing the application.
---
## Usage Instructions
- Apply the Namespace
```bash
kubectl apply -f namespace.yml
```
- Deploy the Application
```bash
kubectl apply -f deployment.yml
```
- Expose the Service
```bash
kubectl apply -f service.yml
```

---
## Verify Resources

- Check namespace:
```bash
kubectl get namespaces
```
- Check deployment:
```bash
kubectl get deployments -n django-app
```
- Check service:
```bash
kubectl get services -n django-app
```
---

## Notes
- I am using the Docker image `anilrajrimal/django-crud:latest`, if you want to use your own, do push it on `DockerHub` and use it
- Customize `replicas`and `namespace` as per your requirements.
- Use `kubectl` describe commands for debugging if resources do not behave as expected.
