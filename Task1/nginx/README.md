# How to Run Nginx Container

First need to deploy the configmap
>kubectl apply -f nginxconfig.yaml

then need to deploy the Pod of nginx
>kubectl apply -f nginx.yaml

then we will deploy the service of nginx
>kubectl apply -f nginxservice.yaml