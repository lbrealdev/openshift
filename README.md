# openshift 4.x

This document contains knowledge of OpenShift Container Platform for daily use.



### Commands

Get pods
```
oc get po

oc get po -A

oc get po -A -o wide
```

Watch
```
watch 'oc get po -A'

watch 'oc get no'
```

Get events
```
oc get events -A
```

Get serviceaccounts
```
oc get sa -A
```

Get storageclass
```
oc get sc
```

Get pv
```
oc get pv
```

Get pvc
```
oc get pvc

oc get pvc -A
```

Get Machines
```
oc get machines -n openshift-machine-api
```

Get MachineSet
```
oc get machineset -n openshift-machine-api
```

Get MachineConfig
```
oc get mc
```

Get MachineConfigPool
```
oc get mcp
```

Get ClusterOperator
```
oc get co
```

Get imagestream
```
oc get is
```

Get daemonset
```
oc get ds
```

Wait for one condition on one or many resources

MachineConfigPool
```
oc wait mcp/master --for condition=updated

oc wait mcp/worket --for condition=updated
```
