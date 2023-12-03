# LAB 8 - ZADANIE 


```console
kubectl create namespace restricted
kubectl apply -f nginx_deployment.yaml
kubectl apply -f sleepybox_deployment.yaml
kubectl apply -f network-policy.yaml
```


- Plik **nginx_deployment.yaml** zawiera deklaracje serwera WWW w przestrzeni nazw restricted wraz z serwisem typu clusterIP.
- Plik **sleepybox_deployment.yaml** służy do utworzenia dwóch podów, tj. Sleepybox1 i Sleepybox2.
- Plik **network_policy.yaml**, definiuje ruch przychodzący (ingress) oraz określa, których podów to dotyczy (podSelector - matchLabel).


# Sprawdzenie


![Screenshot 2023-12-03 at 18 14 51](https://github.com/31grudnia/Kubernetess/assets/83308784/d71dad8b-b48c-4e0f-a29f-523fe42dca5a)


Powyżej widać, że udało się dostać do serwera WWW z sleepybox1, a z drugiego poda już nie.
