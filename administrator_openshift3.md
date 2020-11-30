# openshift


Get pods state equal `Running`:
```
oc get po --all-namespaces --no-headers --field-selector 'status.phase=Running'
```

Get pods state different `Running`:
```
oc get po --all-namespaces --no-headers --field-selector 'status.phase!=Running'
```
