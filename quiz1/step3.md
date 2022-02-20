# verify the installation

Verify the installation of Chaos Mesh

`kubectl get po -n chaos-testing`{{execute}}

Output:

Pods might take some time to get ready.

```
NAME                                        READY   STATUS    RESTARTS   AGE
chaos-controller-manager-569467c84f-6mtrw   1/1     Running   0          99s
chaos-controller-manager-569467c84f-ds7bc   1/1     Running   0          99s
chaos-controller-manager-569467c84f-gv2d6   1/1     Running   0          99s
chaos-daemon-jvhg9                          1/1     Running   0          99s
chaos-dashboard-688d4bbdb-j44z5             1/1     Running   0          99s
```

# Check Version

**Check the version of Chaos Mesh**

 `docker images | grep -h chaos-mesh/chaos-mesh | awk '{print $2}'`{{execute}}

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