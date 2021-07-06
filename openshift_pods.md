# Pods - Openshift 4.x

Delete all pods with Failed status in the same namespace:
```
oc get po --no-headers --field-selector 'status.phase=Failed' -o json | oc delete -f -
```
Delete all pods with Failed status in all namespaces:
```
oc get po -A --no-headers --field-selector 'status.phase=Failed' -o json | oc delete -f -
```
