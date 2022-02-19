# Install Minikube

`minikube start`{{execute}}
 
 # Update Helm

 `curl https://baltocdn.com/helm/signing.asc | sudo apt-key add -`{{execute}}
 `sudo apt-get install apt-transport-https --yes`{{execute}}
 `echo "deb https://baltocdn.com/helm/stable/debian/ all main" | sudo tee /etc/apt/sources.list.d/helm-stable-debian.list`{{execute}}
 `sudo apt-get update`{{execute}}
 `sudo apt-get install helm`{{execute}}
