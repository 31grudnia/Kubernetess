# Zadanie 1

Utworzenie namespace:
```console
kubectl create namespace lab5
```


1. Utworzyć plik yaml tworzący dla przestrzeni nazw zad5 zestaw ograniczeń na zasoby (quota) o następujących parametrach:

Manifest lab5-quota.yaml  definiuje obiekt ResourceQuota o nazwie “lab5-quota” w przestrzeni nazw “lab5". Ograniczenia są ustawione zgodnie z podanymi parametrami:
* Maksymalna liczba Pod-ów: 10
* Dostępne zasoby CPU: 2 CPU (2000m - 2000 milicpu)
* Dostępna ilość pamięci RAM: 1,5Gi (1500 megabajtów)
Po zastosowaniu tego pliku manifestu, ograniczenia te zostaną nałożone na zasoby dostępne w przestrzeni nazw “lab5".

Aktywacja:
```console
kubectl apply -f lab5-quota.yaml
```

Weryfikacja:
```console
kubectl describe quota lab5-quota -n lab5
```


2. Utworzyć plik yaml tworzący Pod-a w przestrzeni nazw zad5 o nazwie worker. Pod ma bazować na obrazie nginx i mieć następujące ograniczenia na wykorzystywane zasoby:

Manifest lab5-worker-pod.yaml definiuje obiekt Pod-a o nazwie "worker-pod” w przestrzeni nazw “lab5". Kontener w tym Podzie bazuje na obrazie nginx i ma ustawione ograniczenia i wymagania na zasoby zgodnie z podanymi parametrami.

Aktywacja:
```console
kubectl apply -f lab5-worker-pod.yaml
```

Weryfikacja:
```console
kubectl get pods --namespace=lab5
```


3. Bazując na przykładzie application/php-apache.yaml z instrukcji do lab4 i/lub z dokumentacji Kubernetes: hSps://kubernetes.io/docs/tasks/run- applicaTon/horizontal-pod-autoscale-walkthrough/ należy zmodyfikować wskazany wyżej plik yaml tak by obiekty Deployment i Service utworzone zostały w przestrzeni nazw zad4:

Aktywacja:
```console
kubectl apply -f php-apache.yaml -n lab4
```

Weryfikacja:
```console
kubectl get services -n lab4
kubectl get deploy -n lab4
```


4. Należy utworzyć plik yaml definiujący obiekt HorizontalPodAutoscaler, który pozwoli na autoskalowanie wdrożenia (Deployment) php-apache:

Maksymalna liczba replik, które można utworzyć, to 5. WorkerPod może wykorzystać maksymalnie 200Mi, a php-apache może wykorzystać maksymalnie 250Mi. Więc  200Mi + 5 * 250Mi < 1.5Gi

Aktywacja:
```console
kubectl apply -f apache-hpa.yaml
```

Weryfikacja:
```console
kubectl describe hpa apache-hpa -n lab4
```

5. Ponownie, bazując na przykładach z instrukcji do lab5 i/lub linku podanego w punkcie 3, należy uruchomić aplikację generującą obciążenie dla aplikacji php-apache i tym samym inicjalizujące proces autoskalowania wdrożenia tej aplikacji. Za pomocą samodzielnie dobranych poleceń i wyniku ich działania proszę potwierdzić dobór parametrów z punktu 4:

Tworzenie generatora obciążenia:
```console
kubectl run -i --tty load-generator --rm --image=busybox:1.28 --restart=Never -- /bin/sh -c "while sleep 0.01; do wget -q -O- http://php-apache.lab4.svc.cluster.local; done"
```

Weryfikacja:
```console
kubectl get hpa php-apache --watch -n lab4
```
