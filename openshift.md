# Openshift

Get pods in a namespace with status failed, nodeAffinity and others states:
```
oc get po --no-headers --field-selector 'status.phase=Failed'
```

Delete pods with status failed, NodeAffinity and others states:
```
oc delete $(oc get po --no-headers --field-selector 'status.phase=Failed' -o name)
```
