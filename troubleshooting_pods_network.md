# Troubleshooting for traffic network from pods

Connected in the node where pod is assigned:
```
conntrack -L | grep $port
```
