# LAB 3 - ZADANIE 

1. Zaczynamy od stworzenia pliku konfiguracyjnego YAML. W tym przypadku nazwałem go: sidecar-pod-config.yaml
2. Następnie tworzymy przestrzeń nazw 'namespace'. Zgodnie z poleceniem nazywam ją 'lab3'

   
```bash
kubectl create namespace lab3
```


3. Kolejnym krokiem jest stworzenie poda w przestrzeni nazw

```bash
kubectl apply -f sidecar-pod-config.yaml -n lab3
```

U mnie występowały problemuy ze ścieżką służącą do tworzenia folderu dla otrzymywanych danych. Celem diagnozy urzłem ponizszej komendy:

```bash
kubectl describe pod sidecar-pod -n lab3
```

4. Tworzę połączenie przekierowania portów dla Nginx
```bash
kubectl port-forward -n lab3 sidecar-pod 8080:80
```

5.  Sprawdzenie zawartość pliku data.log na serwerze localhost:8080

```bash
curl http://localhost:8080/date.log
```
      
