# cluster operations


Add new DNS entry in resolv.conf:
```
sudo sed -i -e '3s/^/# /' -e '$ a nameserver <DNS_ADDRESS>' /etc/resolv.conf
```
