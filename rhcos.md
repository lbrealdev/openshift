# RHCOS Openshift Container Plataform

- [coreos](https://coreos.com/)



### systemctl

List all services:
```
systemctl list-units --type service --all
```

Get kubelet service:
```
systemctl list-units --type service --all | grep kube
```

Get status kubelet:
```
systemctl status kubelet.service
```

Show logs from kubelet:
```
journalctl -u kubelet.service
```

### services

NTP client server

Get status chronyd service:
```
systemctl status chronyd.service
```

Check if NTP is synchronised:
```
chronyc tracking
```
