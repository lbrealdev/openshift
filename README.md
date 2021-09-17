# openshift

This document contains knowledge of OpenShift Container Platform for daily use.

<!-- TOC -->
- [API](#API)
- [Namespaces](#Namespaces)
- [Infrastructure](#Infrastructure)
    - [Infrastructure](#infrastructure)
    - [DNS](#dns)
- [Machines](#Machines) 
- [Nodes](#Nodes)
- [Pods](#Pods)
- [Console](#Console)
    - [Console](#console)
    - [Console Download](#console-cli-download)
- [Network](#Network)
- [ETCD](#ETCD)
- [Oauth](#Oauth)
- [Troubleshooting](#Troubleshooting)

## API
Get the supported API resources on the server:
```
oc api-resources
```
Get the supported API version on the server:
```
oc api-versions
```

## Namespaces

Show current project `namespace`:
```
oc project
```

Get all projects in the cluster:
```
oc projects

oc get projects

oc get ns
```

Describe a determinate project:
```
oc describe project $project_name

oc describe ns $project_name
```

Change from the current project to a other project:
```
oc project $project_name
```

Get events from project:
```
# Current project
oc get ev

# All projects
oc get ev -A

# Specific project
oc get ev -n $project_name
```

## Infrastructure

Get and describe infrastructure resource:
```
oc get infrastructures

oc describe infrastructures/cluster
```

Get and describe dns resource:
```
oc get dns

oc describe dns/cluster
```

## Machines

Get all machines from cluster:
```
oc get machines -n openshift-machine-api
```

Get MachineSet:
```
oc get machineset -n openshift-machine-api
```

Get MachineConfig:
```
oc get mc
```

Get MachineConfigPool:
```
oc get mcp
```

## Nodes

Get all nodes from cluster:
```
oc get no

oc get no -o wide
```

Describe a node:
```
oc describe no $node_name
```

Get nodes with watch:
```
watch 'oc get no'
```

## Pods

Get pods from cluster:
```
# Current project
oc get po

# All projects
oc get po -A

# All projects with output
oc get po -A -o wide
```

Describe a pod:
```
# Current project
oc describe po $pod_name

# Other project
oc describe po -n $project_name $pod_name
```

Get pods with watch 
```
watch 'oc get po -A'
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

Wait for a specific condition on one or many resources:
```
oc wait --for=condition=updated mcp/master

oc wait --for=condition=updated mcp/worker
```

Get and describe clusterversion
```
oc get clusterversion

oc describe clusterversion/version
```

Get ComponentStatus:
```
oc get cs
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

oc get clusternetwork default -o yaml
```

Get and describe HostSubnet
```
oc get hostsubnet

oc describe hostsubnet <hostsubnet_name>
```

Get egressNetworkPolicies:
```
oc get egressnetworkpolicies
```

Get networkPolicies:
```
oc get netpol
```

Get ingress:
```
oc get ing
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

## Troubleshooting

Connect to a node using debug mode
```
oc debug node/$node_name
```

Change your root directory to the host:
```
chroot /host
```
