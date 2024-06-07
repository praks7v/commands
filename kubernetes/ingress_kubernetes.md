# Ingress use in Kubernetes

To use Ingress in a Kubernetes cluster (other than Minikube), you'll follow similar steps to what was done in Minikube. Here’s a step-by-step guide for setting up Ingress in a standard Kubernetes cluster:

### Prerequisites
- A running Kubernetes cluster (e.g., GKE, EKS, AKS, or a self-managed cluster).
- `kubectl` configured to interact with your Kubernetes cluster.
- Basic knowledge of Kubernetes resources (Deployments, Services, etc.).

### Step-by-Step Guide

#### 1. Install an Ingress Controller
First, you need to install an Ingress controller in your Kubernetes cluster. The NGINX Ingress Controller is a popular choice.

To install the NGINX Ingress Controller using the official manifest, run:

```bash
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/cloud/deploy.yaml
```

Verify that the Ingress controller pods are running:

```bash
kubectl get pods -n ingress-nginx
```

You should see pods with the name `ingress-nginx-controller` running.

#### 2. Deploy an Application
For demonstration purposes, let's deploy a simple `echoserver` application.

Create a deployment YAML file named `echoserver-deployment.yaml`:

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: echoserver
  labels:
    app: echoserver
spec:
  replicas: 2
  selector:
    matchLabels:
      app: echoserver
  template:
    metadata:
      labels:
        app: echoserver
    spec:
      containers:
      - name: echoserver
        image: k8s.gcr.io/echoserver:1.4
        ports:
        - containerPort: 8080
```

Create a service YAML file named `echoserver-service.yaml`:

```yaml
apiVersion: v1
kind: Service
metadata:
  name: echoserver
spec:
  ports:
  - port: 80
    targetPort: 8080
  selector:
    app: echoserver
  type: ClusterIP
```

Apply these configurations:

```bash
kubectl apply -f echoserver-deployment.yaml
kubectl apply -f echoserver-service.yaml
```

#### 3. Create an Ingress Resource
Create an Ingress resource YAML file named `echoserver-ingress.yaml`:

```yaml
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: echoserver-ingress
  annotations:
    nginx.ingress.kubernetes.io/rewrite-target: /
spec:
  rules:
  - host: echoserver.your-domain.com
    http:
      paths:
      - path: /
        pathType: Prefix
        backend:
          service:
            name: echoserver
            port:
              number: 80
```

Replace `echoserver.your-domain.com` with the domain name you plan to use. Apply the Ingress resource:

```bash
kubectl apply -f echoserver-ingress.yaml
```

#### 4. Configure DNS
Ensure that your domain (`echoserver.your-domain.com`) is pointing to the external IP of the Ingress controller.

To find the external IP, run:

```bash
kubectl get svc -n ingress-nginx
```

Look for the service named `ingress-nginx-controller` with type `LoadBalancer`. Note the external IP address.

Update your DNS records to point `echoserver.your-domain.com` to this external IP.

#### 5. Access Your Application
Once the DNS is configured and propagated, you should be able to access your application via the domain `http://echoserver.your-domain.com`.

You can also use `curl` to test:

```bash
curl http://echoserver.your-domain.com
```

### Summary
By following these steps, you have set up an Ingress controller and created an Ingress resource to route external traffic to your `echoserver` application in a Kubernetes cluster. This setup allows you to manage and expose your services efficiently using Ingress, providing a clean and scalable way to handle external access to your applications.
