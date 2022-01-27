# AppLication Deployment In Kube Cluster

**Infra**
- docker compose file for Jenkins to deploy a Jenkins container.

**App1**
- First create the image and push to my docker hub repo *deba153/bsapp1:latest*
- After that please create the POD with service. check README.md in app1 folder.

**App2**
- First create the image and push to my docker hub repo *deba153/bsapp2:latest*
- After that please create the POD with service. check README.md in app2 folder.

**Nginx**
- To balance Load we will create nginx container.
- First create configmap and create the pod and service.