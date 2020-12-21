# OpenShift Atomic Service

### Opeshift 3

```
systemctl status atomic-openshift-node.service -l
```

Query the journal with message explanations in immediately jump to the end in the pager:
```
journalctl -xe
```

Follow the journal messages:
```
journalctl -xf
```

Show logs from the specified unit:
```
journalctl -u atomic-openshift-node
```
