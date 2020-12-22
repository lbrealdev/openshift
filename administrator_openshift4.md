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
