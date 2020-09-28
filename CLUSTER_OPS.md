# cluster operations


Add new DNS entry in resolv.conf:
```
sudo sed -i -e '3s/^/# /' -e '$ a nameserver <DNS_ADDRESS>' /etc/resolv.conf
```
Copy file using rsync:
```
rsync -aP -e "ssh -i $HOME/.ssh/<privatekey>.pem" /home/user/templates/<file>.yaml user@107.XXX.XXX.X:/tmp
```
