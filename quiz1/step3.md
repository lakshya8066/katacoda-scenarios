# verify the installation

Verify the installation of Chaos Mesh

You can check the deployments in the chaos-testing namespace `kubectl get deployments -n chaos-testing`{{execute}}

Output:
 
```
NAME                       READY   UP-TO-DATE   AVAILABLE   AGE
chaos-controller-manager   3/3     3            3           90s
chaos-dashboard            1/1     1            1           90s
```
You can get a list of deployed pods in the chaos-testing namespace. 

`kubectl get po -n chaos-testing`{{execute}}

Output:

Pods might take some time to get ready.

```
chaos-controller-manager-6d564977b8-5m8hg   1/1     Running   0          16m
chaos-controller-manager-6d564977b8-7lqt4   1/1     Running   0          16m
chaos-controller-manager-6d564977b8-nvthn   1/1     Running   0          16m
chaos-daemon-5946m                          1/1     Running   0          16m
chaos-daemon-tl4p9                          1/1     Running   0          16m
chaos-dashboard-688d4bbdb-89c99             1/1     Running   0          16m
```
Here if you run `kubectl get po -o wide -n chaos-testing`{{execute}} 

You can also see which pods are running in which nodes

Output:

```
NAME                                        READY   STATUS    RESTARTS   AGE   IP           NODE           NOMINATED NODE   READINESS GATES
chaos-controller-manager-6d564977b8-5m8hg   1/1     Running   0          17m   10.244.1.3   minikube-m02   <none>           <none>
chaos-controller-manager-6d564977b8-7lqt4   1/1     Running   0          17m   10.244.1.4   minikube-m02   <none>           <none>
chaos-controller-manager-6d564977b8-nvthn   1/1     Running   0          17m   10.244.0.3   minikube       <none>           <none>
chaos-daemon-5946m                          1/1     Running   0          17m   10.244.1.5   minikube-m02   <none>           <none>
chaos-daemon-tl4p9                          1/1     Running   0          17m   10.244.0.4   minikube       <none>           <none>
chaos-dashboard-688d4bbdb-89c99             1/1     Running   0          17m   10.244.1.2   minikube-m02   <none>           <none>
```
# Check Version

**Check the version of Chaos Mesh**

 `kubectl describe deployment -n chaos-testing chaos-controller-manager | grep chaos-mesh/chaos-mesh | awk '{print $2}'`{{execute}}

 Output:

 ```
 v2.1.3
 ```

**Check Kubernetes version**
 
 `kubectl version --short=true`{{execute}}

 Output:

 ```
 Client Version: v1.17.3
 Server Version: v1.17.3
 ```