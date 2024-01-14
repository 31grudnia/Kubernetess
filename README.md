# Zadanie 2

Link to repositories used for this Taks

[Source Repo](https://github.com/31grudnia/lab10_source)

[Config Repo](https://github.com/31grudnia/lab10_config)

## Task 1A

[Dockerfile](https://github.com/31grudnia/lab10_source/blob/master/dockerfile)

[index.html](https://github.com/31grudnia/lab10_source/blob/master/index.html)

## Task 1B

[lab10_deployment.yaml](https://github.com/31grudnia/lab10_config/blob/master/lab10_deployment.yaml)

[lab10_ingress.yaml](https://github.com/31grudnia/lab10_config/blob/master/lab10_ingress.yaml)

[lab10_service.yaml](https://github.com/31grudnia/lab10_config/blob/master/lab10_service.yaml)

## Task 2A/2B

[Github Workflows file](https://github.com/31grudnia/lab10_source/blob/master/.github/workflows/zad2lab10.yml)

## Task 3A

[Dockerfile](https://github.com/31grudnia/Kubernetess/blob/Zadanie2/Zadanie2/gitops/Dockerfile)

## Task 3B

[StepCD](https://github.com/31grudnia/Kubernetess/blob/Zadanie2/Zadanie2/gitops/StepCD.yaml)

```console
kubectl create sa gitops
```

```console
kubectl create clusterrolebinding gitops-admin --clusterrole=cluster-admin --serviceaccount default:gitops
```

## Task 4A/4B
