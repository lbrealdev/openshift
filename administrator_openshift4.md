# openshift 4.x



### Project
Create new project `namespace`:
```
oc new-project myproject \
  --display-name="My Project"
```


### Node Management

Show kubelet logs from all masters:
```
oc adm node-logs --role master -u kubelet
```
Show lastest 1000 lines from all masters:
```
oc adm node-logs --role master --tail=1000 -u kubelet
```
Show lastest 1000 lines from all masters with grep search string `not found`:
```
oc adm node-logs --tail=100 --role master --grep='not found' -u kubelet
```
Show lastest 1000 lines from all nodes with role worker thet be label `kubernetes.io/hostname=$NODE`:
```
oc adm node-logs --tail=100 --role worker -l hostname='$NODE' -u kubelet
```

### Certificates

Get number of certificates `Approved,Issued` and `Pending`:
```
oc get csr --no-headers | wc -l

oc get csr --no-headers | grep "Approved,Issued" | wc -l

oc get csr --no-headers | grep "Pending" | wc -l
```
Approve certificates:
```
oc get csr -o name | xargs oc adm certificate approve
```

### Manage objects

Get MachineConfig and decode base64 data:
```
oc get mc $machineconfig_name -o jsonpath='{.spec.config.storage.files[].contents.source}' | cut -d ',' -f 2 | base64 -d
```

### Get logs with since, tail, prefix and timestamps for all containers in a pod
```
oc logs --since-time="2021-05-14T08:00:00Z" $pod --all-containers --prefix --timestamps
```

