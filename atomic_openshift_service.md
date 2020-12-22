# atomic openshift

### Opeshift 3

Get status atomic-openshift service:
```
systemctl status atomic-openshift-node.service -l
```
Start - Stop - Restart:
```
systemctl start atomic-openshift-node.service

systemctl stop atomic-openshift-node.service

systemctl restart atomic-openshift-node.service
```

Show logs from Journal of atomic-openshift:
```
journalctl -u atomic-openshift-node
```
Show latest 100 lines from logs of atomic-openshift-node:
```
journalctl -n 100 -u atomic-openshift-node
```
Show logs since date:
```
journalctl --no-pager --since "2020-12-22 10:00:00" --until "2020-12-22 10:05:00" -u atomic-openshift-node
```
