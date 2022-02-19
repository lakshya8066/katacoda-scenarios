# Installing Chaos-mesh

#### Add Chaos Mesh repository​

`helm repo add chaos-mesh https://charts.chaos-mesh.org`{{execute}}

#### View the installable versions of Chaos Mesh

`helm search repo chaos-mesh`{{execute}}

#### Create the namespace to install Chaos Mesh

`kubectl create ns chaos-testing`{{execute}}

#### Install Helm 

`helm install chaos-mesh chaos-mesh/chaos-mesh -n=chaos-testing --version 2.1.3`{{execute}}
