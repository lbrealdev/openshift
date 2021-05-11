# openshift 4.x

Get URL by route object:
```
curl -kv https://$(oc get route -n openshift-console console -o jsonpath='{.spec.host}')
```

Check Cluster API Address:
```
curl -kv $(oc whoami --show-server)/healthz
```

Get console URL:
```
curl -kv $(oc whoami --show-console)

curl -kv $(oc get console cluster -o jsonpath='{.status.consoleURL}')
```

List all container images running in a cluster:
```
oc get pods -A -o go-template --template='{{range .items}}{{range .spec.containers}}{{printf "%s\n" .image -}} {{end}}{{end}}' | sort -u | uniq
```

List all container images stored in a cluster:
```
for node in $(oc get nodes -o name);do oc debug ${node} -- chroot /host sh -c 'crictl images -o json' 2>/dev/null | jq -r .images[].repoTags[]; done | sort -u
```

Get Settings used in install config:
```
oc get cm -n kube-system cluster-config-v1 -o yaml
```
