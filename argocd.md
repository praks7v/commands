# Argocd Installation and Use in Kubernetes

Argo CD is a declarative, GitOps continuous delivery tool for Kubernetes. It uses Git repositories as the source of truth for defining the desired state of applications and Kubernetes clusters. Here's a step-by-step guide on how to use Argo CD in Kubernetes:

**Prerequisites**
- A Kubernetes cluster (you can use Minikube, GKE, AKS, EKS, etc.).
- kubectl installed and configured to interact with your Kubernetes cluster.
- argocd CLI installed (optional but recommended).

**Step-by-Step Guide**
1. **Install Argo CD**
   
   First, create a namespace for Argo CD:

```
kubectl create namespace argocd
```
   Then, install Argo CD using the following command:

```
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```
2. **Access the Argo CD API Server**
   By default, the Argo CD API server is not exposed with an external IP. You can access it using kubectl port-forward:

```
kubectl port-forward svc/argocd-server -n argocd 8080:443
```
   Now, you can access the Argo CD web UI by navigating to https://localhost:8080 in your browser.

3. **Login to Argo CD**
   
   Get the initial admin password:

```
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo
```
   Use the username admin and the password obtained from the previous command to log in to the Argo CD web UI.

4. **Deploy an Application with Argo CD**
   
   To deploy an application, you need a Git repository with Kubernetes manifests or Helm charts. Here's an example using a simple Git repository.

   Create a file named application.yaml with the following content:

```yaml
apiVersion: argoproj.io/v1alpha1
kind: Application
metadata:
  name: my-app
  namespace: argocd
spec:
  project: default
  source:
    repoURL: 'https://github.com/your-repo/your-app.git'
    targetRevision: HEAD
    path: manifests
  destination:
    server: 'https://kubernetes.default.svc'
    namespace: default
  syncPolicy:
    automated:
      prune: true
      selfHeal: true
```
   Apply the application manifest:

```
kubectl apply -f application.yaml
```
5. **Monitor and Manage Your Application**
   
   You can monitor and manage your application through the Argo CD web UI. It provides a visual representation of the application state and allows you to sync, rollback, and perform other operations.

7. **Use the Argo CD CLI (Optional)**
   
   Install the Argo CD CLI by following the instructions on the Argo CD CLI installation page.

   Once installed, log in to Argo CD using the CLI:
```
argocd login localhost:8080
```
   Deploy an application using the CLI:
```
argocd app create my-app \
    --repo https://github.com/your-repo/your-app.git \
    --path manifests \
    --dest-server https://kubernetes.default.svc \
    --dest-namespace default
```
   Synchronize the application:

```
argocd app sync my-app
```
**Summary**

   Argo CD simplifies the process of deploying and managing applications in Kubernetes by leveraging GitOps principles. It ensures that your applications are always in the desired state defined in your Git repositories. By following these steps, you can set up and use Argo CD to manage your Kubernetes applications effectively.






