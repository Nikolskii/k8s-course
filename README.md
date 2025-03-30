# k8s-course

Запустить локальный кластер Kubernetes:

`minikube start`

Применить конфигурацию к кластеру Kubernetes:

`kubectl apply -f deployment.yaml`

Запустить веб-интерфейс Kubernetes для управления кластером:

`minikube dashboard`

Удалить деплоймент и сервис:

`kubectl delete -f deployment.yaml -f service.yaml`
