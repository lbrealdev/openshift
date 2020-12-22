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

Get and convert base64 value from `MachineConfig`:
```
export MC=<machine_config_name>
oc get mc $MC -o json | jq -r '. | {Base64:.spec.config.storage.files[0].contents.source}' | awk -F '[:]' '{print $3}' | cut -d '"' -f 1 | cut -d , -f 2 | xargs -L1 bash -c 'echo $0 | base64 -d'
```
