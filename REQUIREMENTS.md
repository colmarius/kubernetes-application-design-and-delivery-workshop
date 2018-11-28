Setup & Environment

During the workshop, we encourage participants to work in pair. Therefore at least one computer per couple should be available and correctly configured.

Kubernetes

You should have access to a Kubernetes cluster. You can very easily provision a single-node cluster on your machine with minikube  as well can use any other Kubernetes cluster from public clouds or self-provisioning.

Minikube
Here you can find installation instructions for your system to easily get minikube up and running. Note that you will need to have a hypervisor installed (something like Virtualbox).

For macOS:
brew cask install minikube

For Linux:
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 \
&& sudo install minikube-linux-amd64 /usr/local/bin/minikube

Kubectl
It's necessary to have Kubectl installed: it's the CLI tool to interact with Kubernetes.

On macOS:

brew install kubernetes-cli
On Linux Ubuntu/Debian:

sudo apt-get update && sudo apt-get install -y apt-transport-https
curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -
echo"deb https://apt.kubernetes.io/ kubernetes-xenial main"| sudo tee -a /etc/apt/sources.list.d/kubernetes.list
sudo apt-get update
sudo apt-get install -y kubectl
For other OS, refer to the official install docs

As a bonus, you should install Kubectx and kubens (installation instructions here), they are not strictly required but are actually priceless, so... why not.

Helm and Kustomize
Install kustomize and helm. To install Kustomize, here you can find the installation instructions. Same goes for helm.

Using Minikube
Use the following commands to start a minikube cluster and link it to your local installation of docker.

# Starting a local minikube cluster of 1 node
minikube start --cpus=2 --memory=4096 --kubernetes-version=v1.11.4
# Checking nodes
kubectl get pods
# Using docker from minikube
eval$(minikube docker-env)
# Check if linking succeeded
docker ps
