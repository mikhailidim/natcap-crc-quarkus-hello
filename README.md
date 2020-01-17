# NATCAP RedHat CRC demo  

## About repository
Reposetory is for NATCAP Feb 2020 meetup CI/CD demonstration. Seemore details at the [event page](https://www.meetup.com/natcapoug-middleware/events/267734332).
This porject demonstrates CI/CD capabilities of the [RedHat CoderReady Containers](https://developers.redhat.com/products/codeready-containers). 
Project is designed and configured for use with CRC v1.4 and [Ultrahook](http://www.ultrahook.com/) service. 

## New OpenShift project
1. Login to local CRC cluster 
```bash
oc login --token=************************** --server=https://api.crc.testing:6443
```
2. Create new OpenShit project
```bash
oc new-project natcap-crc
```
3. Create new Quarkus native application fro this repository.
```bash
oc new-app quay.io/quarkus/ubi-quarkus-native-s2i:19.2.1~https://github.com/mikhailidim/natcap-crc-quarkus-hello.git --name=natcap-hello
```
4. Expose new application 
```bash
oc expose svc/natcap-hello
```
