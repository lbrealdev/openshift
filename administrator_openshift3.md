# openshift


Get pods state equal `Running`:
```
oc get po --all-namespaces --no-headers --field-selector 'status.phase=Running'
```

Get pods state different `Running`:
```
oc get po --all-namespaces --no-headers --field-selector 'status.phase!=Running'
```

## oc adm

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
