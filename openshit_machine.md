# Openshift Machine

Pause updates in MachineConfigPool:
```
oc patch mcp --type merge -p '{"spec":{"paused":"true"}}'
```
