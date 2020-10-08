# openshift 4.x

This document contains knowledge of OpenShift Container Platform for daily use.

<!-- TOC -->
- [API](#API)
- [Infrastructure](#Infrastructure)
    - [Infrastructure](#infrastructure)
    - [DNS](#dns)
- [Nodes](#Nodes)
    - [Nodes](#nodes)
    - [Pods](#pods)
    - [Tuned](#tuned)
    - [Profile](#profile)
- [Projects](#Projects)
- [Console](#Console)
    - [Console](#console)
    - [Console Download](#console-cli-download)
- [Network](#Network)
- [ETCD](#ETCD)
- [Oauth](#Oauth)
- [Debug](#debug)

## API
Get all resources `objects`
```
oc api-resources
```

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

#### tuned
Get and describe tuned
```
oc get tuned -A

oc describe tuned -n <namespace> <tuned_name>
```

#### profile
Get and describe profile
```
oc get profile -A

oc describe profile -n <namespace> <profile_name>
```

## Projects

Show which project you are using
```
oc project
```

Get projects `namespace`
```
oc projects

oc get projects

oc get ns
```

Describe projects `namespace`
```
oc describe project <project_name>

oc describe ns <project_name>
```

Change from the current project to a different project
```
oc project <project_name>
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

Get and describe clusterversion
```
oc get clusterversion

oc describe clusterversion/version
```

## Console

#### console
Get and describe console
```
oc get console

oc describe console/cluster
```
#### console-cli-download
Get and describe console cli downdloads
```
oc get consoleclidownloads

oc describe consoleclidownloads/oc-cli-downloads
```

Get and describe APIServer
```
oc get apiserver

oc describe apiserver/cluster
```

Get and describe proxy
```
oc get proxy

oc describe proxy/cluster
```

Get and describe FeatureGate
```
oc get featuregate

oc describe featuregate/cluster
```

Get and describe image
```
oc get image

oc describe image/sha256:xxxxxxx
```

Get and describe scheduler
```
oc get scheduler

oc describe scheduler/cluster
```

Get and describe OperatorHub
```
oc get operatorhub

oc describe operatorhub/cluster
```

Get and describe AlertManager
```
oc get alertmanager -A

oc describe alertmanager -n openshift-monitoring main
```

Get and describe Prometheus
```
oc get prometheus -A

oc describe prometheus -n openshift-monitoring k8s
```

Get and describe PrometheusRule
```
oc get prometheusrule -A

oc describe prometheusrule -n <namespace> <prometheusrules_name>
```

Get and describe ServiceMonitor
```
oc get servicemonitor -A

oc describe servicemonitor -n <namespace> <servicemonitor_name>
```



## Network

Get and describe network
```
oc get network

oc describe network/cluster
```

Get and describe ClusterNetwork
```
oc get clusternetwork

oc describe clusternetwork/default
```

Get and describe HostSubnet
```
oc get hostsubnet

oc describe hostsubnet <hostsubnet_name>
```

## ETCD

Get and describe ETCD
```
oc get etcd

oc describe etcd/cluster
```

## Oauth

Get and describe Oauth
```
oc get oauth

oc describe oauth/cluster
```

Get and describe authetication
```
oc get authentication

oc describe authentication/cluster
```

Get and describe OauthClient
```
oc get oauthclient

oc describe oauthclient/console
```


Get objects:
```
oc get clusterrolebindings

oc get rolebindings

oc get clusterrole

oc get role
```

## Debug

Connect to the node
```
oc debug node/<node_name>
```

Change your root directory to the host:
```
chroot /host
```
