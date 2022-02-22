# Getting the environment ready 

## Start Minikube

 We will use minikube to install chaos mesh on a Kubernetes CLuster.
 `minikube start` spins up a kubernetes cluster with a single master node.
 It takes about 
 - 2 CPUs or more
 - 2GB of free memory
 - 20GB of free disk space
 in default mode

 If you check the current version of minikube `minikube version`{{execute}}
 
 It is `1.8.0` and in order to run a multi node cluster, we need minikube 1.10.1 or higher. 

To update minikube to the latest:

 Download the binary using curl:

 `curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64`{{execute}}

 Install minikube:

 `sudo install minikube-linux-amd64 /usr/local/bin/minikube`{{execute}}

 Check version: `minikube version`{{execute}}

 It should be `v1.25.1` now
 
 `minikube start --force --nodes 2 --driver=docker`{{execute}}

Output when a cluster is created:
```
* Done! kubectl is now configured to use "minikube" cluster and "default" namespace by default

```

Once the cluster is up and running, you can check the node in the cluster by:

`kubectl get nodes`{{execute}}

 There should be `Ready` status:

 ```
 NAME           STATUS   ROLES    AGE     VERSION
 minikube       Ready    master   5m54s   v1.17.3
 minikube-m02   Ready    <none>   5m      v1.17.3 
 ```
 
## Update Helm

This Katacoda Scenario has Helm v2 installed by default. 

Run these commands to migrate to helm v3.

 1. `curl https://baltocdn.com/helm/signing.asc | sudo apt-key add -`{{execute}}

 2. `sudo apt-get install apt-transport-https --yes`{{execute}}

 3. `echo "deb https://baltocdn.com/helm/stable/debian/ all main" | sudo tee /etc/apt/sources.list.d/helm-stable-debian.list`{{execute}}

 4. `sudo apt-get update`{{execute}}

 5. `sudo apt-get install helm`{{execute}}
