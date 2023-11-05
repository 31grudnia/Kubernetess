# Lab 4

#### 1. Zacznij od utworzenia pliku yaml odpowiedzialnego za utworzenie i konfigurację przestrzeni nazw lab4

```console
kubectl apply -f namespace.yaml
```

#### 2. Utwórz plik yaml odpowiedzialny za utworzenie 3 podów z podanymi ograniczeniami

 ```console
kubectl apply -f deployment.yaml
```

#### 3. Sprawdź status uruchomionych podów

 ```console
kubectl get pods -n lab4
```

```console
kubectl get all -n lab4
```

```console
kubectl top pod -n lab4
kubectl top node -n lab4
```
