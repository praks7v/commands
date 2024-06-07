# Minikube Docker Local Registry

To use Minikube's built-in Docker registry, you can follow these steps:

1. **Start Minikube:**
   
   First, ensure Minikube is installed on your system. Then start Minikube with the following command:

```
minikube start
```
2. **Enable Registry:**
   
   Enable the registry addon in Minikube:

```
minikube addons enable registry
```

3. **Configure Docker:**
   
   Set your Docker environment to use Minikube's Docker daemon:
```
eval $(minikube docker-env)
```
4. **Build Docker Image:**
   
   Build your Docker image. For example:

```
docker build -t my-image:tag .
```
5. **Tag the Image:**
   
   Tag your Docker image with the Minikube registry:

```
docker tag my-image:tag localhost:5000/my-image:tag
```
6. **Push Image to Registry:**
   
   Push your Docker image to the Minikube registry:
```
docker push localhost:5000/my-image:tag
```
7. **Pull Image form Registry:**
   Pull your Docker image form minikube registry:
```
docker pull localhost:5000/my-image:tag
```
8. **Port Forward the Registry Service:**
   
   Forward the registry service to make it accessible on your local machine. Since the service is using ports `80` and `443`, you can forward these ports to `5000` on your local machine.

```
kubectl port-forward -n kube-system service/registry 5000:80
```
This command forwards port `5000` on your local machine to port `80` on the registry service in Minikube.

9. **Exit Minikube Docker Environment**
```
eval $(minikube docker-env -u)
```

**Use the Image in Kubernetes:**
   You can now use your image in your Kubernetes manifests. Reference it as `localhost:5000/my-image:tag`.
