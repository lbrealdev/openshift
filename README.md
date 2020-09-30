# openshift 4.x

This document contains knowledge of OpenShift Container Platform for daily use.

<!-- TOC -->

- [Infrastructure](#Infrastructure)
    - [Infrastructure](#infrastructure)
    - [DNS](#dns)
- [Nodes](#Nodes)
    - [Nodes](#nodes)
    - [Pods](#pods)
- [Console](#Console)
    - [Console](#console)

## Infrastructure

#### infrastructure
Get and describe infrastructure
```
oc get infrastructures

oc describe infrastructures/cluster
```

#### dns
Get and describe dns
```
oc get dns

oc describe dns/cluster
```

## Nodes

#### nodes
Get nodes
```
oc get no
```

#### pods
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

Get clusterversion
```
oc get clusterversion
```
Describe clusterversion
```
oc describe clusterversion/version
```
Get oauth
```
oc get oauth
```
Describe oauth
```
oc describe oauth/cluster
```

## Console

#### console
Get and describe console
```
oc get console

oc describe console/cluster
```
