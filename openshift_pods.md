# Pods - Openshift 4.x

Get all pods with Running status in the same namespace:
```
oc get po --no-headers --field-selector 'status.phase=Running'
```

Get all pods with Pending status in the same namespace:
```
oc get po --no-headers --field-selector 'status.phase=Pending'
```

Delete all pods with Failed status in the same namespace:
```
oc delete $(oc get po --no-headers --field-selector 'status.phase=Failed' -o name)

oc get po --no-headers --field-selector 'status.phase=Failed' -o json | oc delete -f -
```

Delete all pods with Failed status in all namespaces:
```
oc get po -A --no-headers --field-selector 'status.phase=Failed' -o json | oc delete -f -
```
