# Check the version of chaos-mesh 

`docker images | grep -h chaos-mesh/chaos-mesh | awk '{print $2}'`{{execute}}

# Check Kubernetes Version
 
 `kubectl version --short=true`{{execute}}