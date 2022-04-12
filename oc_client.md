# oc client

### Install via curl

1 - Download "openshift-client-linux" via curl:
```
curl -sO https://mirror.openshift.com/pub/openshift-v4/clients/ocp/latest/openshift-client-linux-4.10.8.tar.gz
```
2 - Extract TAR file:
```
tar -xf openshift-client-linux-4.10.8.tar.gz
```
3 - Move oc client extract from TAR file to this path:
```
sudo cp oc /usr/local/bin
```
4 - Verify version of the oc client:
```
oc version
```
