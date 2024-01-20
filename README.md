# Lab13


### Before task was executed Helm has been installed 


### Adding bitnami repo in order to pull from it 
```console
helm repo add bitnami https://charts.bitnami.com/bitnami
```

### Pulling bitnami/nginx  
```console
helm pull bitnami/nginx 
```

### Installing application after extracting files 
```console
helm install -f nginx/values.yaml my-nginx nginx/
```


![Screenshot 2024-01-20 at 18 59 47](https://github.com/31grudnia/Kubernetess/assets/83308784/5d0b1ac7-e5ab-4d5b-8710-6cf1e2c15f8c)


In order to change service to ingress I changed two lines of code in values.yaml file:

- service:

  type: NodePort (previously 'LoadBalancer')
- ingress:
  
  enabled: true (previously 'false')

### Updating changes from values.yaml file 
```console
helm upgrade -f nginx/values.yaml my-nginx nginx/
```

### Verifying  
```console
kubectl get pods,svc
```

![Screenshot 2024-01-20 at 22 59 02](https://github.com/31grudnia/Kubernetess/assets/83308784/f0435a36-b598-417a-8df5-f3d401efbef4)

![Screenshot 2024-01-20 at 23 09 04](https://github.com/31grudnia/Kubernetess/assets/83308784/732ac674-aef7-4c59-a9aa-b25eb60250fd)
