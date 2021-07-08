# Openshift Machine

Pause updates in MachineConfigPool:
```
oc patch mcp worker --type merge -p '{"spec":{ "paused": 'true' }}'
```
