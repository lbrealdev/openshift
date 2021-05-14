# DeploymentConfigs

Get logs from dc:
```
oc logs --tail=100 dc/$dc
```
Get logs from dc by revision:
```
oc logs --version=1 --tail=100 dc/$dc
```
Get status dc:
```
oc rollout status dc/$dc
```
Get history version dc:
```
oc rollout history dc/$dc
```
Undo a previous rollout
```
oc rollout undo dc/$dc
```
Delete dc:
```
oc delete dc/$dc
```
