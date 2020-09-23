# openshift 4.x

This document contains knowledge of OpenShift Container Platform for daily use.



### Commands



Get imagestream
```
oc get is
```

Get daemonset
```
oc get ds
```

Wait for one condition on one or many resources

Wait for MachineConfigPool
```
oc wait mcp/master --for condition=updated

oc wait mcp/worket --for condition=updated
```
