# Lab12


Created new private repository on dockerhub.
![Screenshot 2024-01-20 at 17 19 49](https://github.com/31grudnia/Kubernetess/assets/83308784/3fa3ea3e-85d2-465f-9780-1c1ca7d73270)


### Nginx image Pull
```console
docker pull nginx
```


### Tagging image
```console
docker tag nginx 31grudnia/lab12_repo:lab12
```


### Tagged image push
```console
docker push 31grudnia/lab12_repo:lab12
```


### Creating secret key mykey
```console
kubectl create secret docker-registry mykey --docker-server=docker.io --docker-username=31grudnia --docker-password=... --docker-email=...
```


### Pod manifest [test12.yaml](https://github.com/31grudnia/Kubernetess/blob/Lab12/Lab12/test12.yaml)


### Checking if pod is working correctly 
```console
kubectl get pods
```

![Screenshot 2024-01-20 at 17 10 22](https://github.com/31grudnia/Kubernetess/assets/83308784/29abd511-ae30-4f53-ba0c-3ebb51f0724e)


```console
kubectl describe test12.yaml
```

![Screenshot 2024-01-20 at 17 10 15](https://github.com/31grudnia/Kubernetess/assets/83308784/f7b2a724-3712-4d83-bc98-c46032b7d7b9)

