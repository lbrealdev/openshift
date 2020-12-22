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

