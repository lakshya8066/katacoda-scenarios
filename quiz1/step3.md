# verify the installation

`kubectl get po -n chaos-testing`{{execute}}

# Check Version

Check the version of Chaos Mesh 

 `docker images | grep -h chaos-mesh/chaos-mesh | awk '{print $2}'`{{execute}}

Check Kubernetes version
 
 `kubectl version --short=true`{{execute}}