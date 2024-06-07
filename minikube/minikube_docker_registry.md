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
docker build -t my-image .
```
5. **Tag the Image:**
   
   Tag your Docker image with the Minikube registry:

```
docker tag my-image localhost:5000/my-image
```
6. **Push Image to Registry:**
   
   Push your Docker image to the Minikube registry:
```
docker push localhost:5000/my-image
```
7. **Pull Image form Registry:**
   Pull your Docker image form minikube registry:
```
docker pull localhost:5000/my-image
```

**Use the Image in Kubernetes:**
   You can now use your image in your Kubernetes manifests. Reference it as `localhost:5000/my-image`.
