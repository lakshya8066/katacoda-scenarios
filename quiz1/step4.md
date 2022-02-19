# Uninstalling Chaos Mesh

`helm uninstall chaos-mesh -n chaos-testing`{{execute}}

Output:

```
release "chaos-mesh" uninstalled
```

Now you can check the pods in the namespace chaos-testing are removed.

`kubectl get po -n chaos-testing`{{execute}}

Output:

```
No resources found in chaos-testing namespace.
```
