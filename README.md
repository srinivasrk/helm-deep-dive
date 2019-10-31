# Helm deep dive - [Linux academy](!https://linuxacademy.com/cp/modules/view/id/320#/)


## Package management in kubernetes


### Helm commands

* `helm ls` - list any helm charts installed
* `helm search wordpress` - check for chart existance
* `helm install stable/wordpress` - install the wordpress chart. Each install is seperate instance
*  `helm del CHARTNAME --purge` - remove all resources related to a chart
* `helm install stable/wordpress --version 5.0.1` - Install a specific version
* `helm upgrade CHARTNAME stable/wordpress` - Update the existing chart
* `helm fetch --untar stable/wordpress ` - download the chart locally and can manipulate it. Downloads the tar and extracts it. Also downloads dependencies.
* `helm dep list` - show dependencies for current chart
* `helm dep update` - download the dependency 
* `helm install .` - install from local directory
* `helm home` - helm related cache files are stored
---

### helm and tiller overview
Helm (uppercase) exists in 2 parts, helm (lowercase) is the client and tiller is the server.  

Tiller pod must be running in kubernetes cluster. Tiller interacts with K8's API to create resources, where as helm manages charts, contacts helm repos to manage release cycle & interacts with tiller.