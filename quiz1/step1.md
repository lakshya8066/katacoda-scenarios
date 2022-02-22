# Getting the environment ready 

## Start Minikube

 We will use minikube to install Chaos Mesh on a Kubernetes cluster.
 `minikube start` command spins up a kubernetes cluster.
 It takes about 
 - 2 CPUs or more
 - 2GB of free memory
 - 20GB of free disk space
 in default mode

 If you check the current version of minikube `minikube version`{{execute}}
 
 It is `1.8.1` and in order to run a multi node cluster, we need minikube 1.10.1 or higher as specified in the [docs](https://minikube.sigs.k8s.io/docs/tutorials/multi_node/). 

We need to update minikube to the latest version.

 Download the binary using curl:

 `curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64`{{execute}}

 Install minikube:

 `sudo install minikube-linux-amd64 /usr/local/bin/minikube`{{execute}}

 Check version: `minikube version`{{execute}}

 It should be `v1.25.1` now.

 We can start minikube now with 2 nodes and `docker` as the driver. Here we are using the flag `--force` for the tutorial because running minikube as root and driver as docker, is not allowed. `--force` flag is **highly unrecommended** in production environment. To use minikube with the `--force` flag, follow the instruction from the docker [documentation](https://docs.docker.com/engine/install/linux-postinstall/#manage-docker-as-a-non-root-user) to add a new user and run docker as non root.
 
 For now we can go ahead with the `--force` flag for the tutorial.
 
 `minikube start --force --nodes 2 --driver=docker`{{execute}}

  This may take some time to start.

Output when a cluster is created:
```
* Done! kubectl is now configured to use "minikube" cluster and "default" namespace by default

```

Once the cluster is up and running, you can check the node in the cluster by:

`kubectl get nodes`{{execute}}

 There should be `Ready` status, if not, check again.

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
