# openshift


Get pods state equal `Running`:
```
oc get po --all-namespaces --no-headers --field-selector 'status.phase=Running'
```

Get pods state different `Running`:
```
oc get po --all-namespaces --no-headers --field-selector 'status.phase!=Running'
```

## Working with nodes

List all pods on the node:
```
oc adm manage-node $nodename --list-pods
```

Display Resource (CPU/Memory/Storage) usage of nodes:
```
oc adm top no
```

Display Resource (CPU/Memory/Storage) usage of pods:
```
oc adm top po
```
---------------------------------------------------------
Use `oc adm drain` to gracefully terminate all pods on the node while marking the node as unschedulable:
```
oc adm drain $nodename --delete-local-data --ignore-daemonsets
```
Make the node schedulable again, use `oc adm uncordon`:
```
oc adm uncordon $nodename
```
