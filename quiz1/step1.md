# Getting the environment ready 

## Start Minikube

 We will use minikube to install chaos mesh on a Kubernetes CLuster.
 `minikube start` spins up a kubernetes cluster with a single master nocde.
 It takes about 
 - 2 CPUs or more
 - 2GB of free memory
 - 20GB of free disk space
 in default mode

 `minikube start`{{execute}}
 
## Update Helm

This katacoda Scenario has Helm v2 installed by default. Run these commands to migrate to helm v3.

 1. `curl https://baltocdn.com/helm/signing.asc | sudo apt-key add -`{{execute}}


 2. `sudo apt-get install apt-transport-https --yes`{{execute}}

 3. `echo "deb https://baltocdn.com/helm/stable/debian/ all main" | sudo tee /etc/apt/sources.list.d/helm-stable-debian.list`{{execute}}

 4. `sudo apt-get update`{{execute}}

 5. `sudo apt-get install helm`{{execute}}
