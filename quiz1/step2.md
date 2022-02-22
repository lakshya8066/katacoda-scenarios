# Installing Chaos Mesh

**Add Chaos Mesh repository**​

`helm repo add chaos-mesh https://charts.chaos-mesh.org`{{execute}}

Output:
```
"chaos-mesh" has been added to your repositories
```

**View the installable versions of Chaos Mesh**

`helm search repo chaos-mesh`{{execute}}

Output:
```
NAME                    CHART VERSION   APP VERSION     DESCRIPTION                                       
chaos-mesh/chaos-mesh   2.1.3           2.1.3           Chaos Mesh is a cloud-native Chaos Engineering ...
```

**Create the namespace to install Chaos Mesh**

`kubectl create ns chaos-testing`{{execute}}

Output:
```
namespace/chaos-testing created
```

You can check a namespace called `chaos-testing` will be present:

`kubectl get ns`{{execute}}

Output:
```
NAME              STATUS   AGE
chaos-testing     Active   9s
default           Active   12m
kube-node-lease   Active   12m
kube-public       Active   12m
kube-system       Active   12m
```

**Install Helm Charts** 

`helm install chaos-mesh chaos-mesh/chaos-mesh -n=chaos-testing --version 2.1.3`{{execute}}

Output:
```
NAME: chaos-mesh
LAST DEPLOYED: Sat Feb 19 15:52:07 2022
NAMESPACE: chaos-testing
STATUS: deployed
REVISION: 1
TEST SUITE: None
NOTES:
1. Make sure chaos-mesh components are running
   kubectl get pods --namespace chaos-testing -l app.kubernetes.io/instance=chaos-mesh
```