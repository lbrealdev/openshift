# openshift 4.x

Check the URL web console OpenShift 4.x:
```
curl -kv https://$(oc get route -A | grep console | awk '{print $3; exit}')/
```
