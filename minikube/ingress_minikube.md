# Use Ingress in Minikube

Using Ingress in Minikube involves several steps, from setting up Minikube to deploying an application and configuring Ingress to route traffic to the application. Here's a detailed step-by-step guide:

**Step 1: Start Minikube**

Start your Minikube cluster if it’s not already running:

```
minikube start
```
**Step 2: Enable Ingress Addon**

Minikube comes with an Ingress addon which you need to enable:

```
minikube addons enable ingress
```
**Step 3: Deploy an Application**

Deploy a sample application in Minikube. For this example, we'll use the echoserver application.

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
```
kubectl apply -f echoserver-deployment.yaml
kubectl apply -f echoserver-service.yaml
```
**Step 4: Create an Ingress Resource**

Create an Ingress resource YAML file named echoserver-ingress.yaml:

```yaml
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: echoserver-ingress
  annotations:
    nginx.ingress.kubernetes.io/rewrite-target: /
spec:
  rules:
  - host: echoserver.local
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
Apply the Ingress resource:
```
kubectl apply -f echoserver-ingress.yaml
```
**Step 5: Update /etc/hosts**

Since Minikube runs on a local machine, you'll need to update your `/etc/hosts` file to route traffic from `echoserver.local` to the Minikube IP address.

First, get the Minikube IP:

```
minikube ip
```
Suppose the IP is `127.0.0.1`. Add the following line to your `/etc/hosts` file:

```
127.0.0.1 echoserver.local
```
**Step 6: Access Your Application**

Now, you should be able to access your application via the domain `http://echoserver.local`.

Open your browser and navigate to `http://echoserver.local` or use curl:

```
curl http://echoserver.local
```
**Summary**

You have successfully set up Ingress in Minikube to route traffic to your echoserver application. By following these steps, you can easily expose other applications in your Minikube environment using Ingress. This approach allows you to simulate production-like routing and domain management in a local development setup.






