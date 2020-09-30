# openshift 4.x

Check the URL web console OpenShift 4.x:
```
curl -kv https://$(oc get route -A | grep console | awk '{print $3; exit}')/
```

Check Cluster API Address:
```
curl -kv $(oc whoami --show-server)/healthz
```

Get and check console URL:
```
oc get console cluster -o yaml | awk '/URL/ {print $2}'

curl -kv $(oc get console cluster -o yaml | awk '/URL/ {print $2}')
```
