Собрать Docker-образ:

`docker build . -t dnikolskii/k8s-web-hello-ru:latest -t dnikolskii/k8s-web-hello-ru:1.0.0`

Запушить Docker-образ на Docker Hub:

`docker push dnikolskii/k8s-web-hello-ru --all-tags`

Запустить локальный кластер Kubernetes с помощью Minikube:

`minikube start`

Создать деплоймент:

`kubectl create deployment k8s-web-hello --image=dnikolskii/k8s-web-hello-ru:1.0.0`

Открыть туннель, позволяющий доступ к сервисам Kubernetes типа LoadBalancer снаружи (с хоста):

`minikube tunnel`

Создать сервис типа LoadBalancer для деплоймента k8s-web-hello

`kubectl expose deployment k8s-web-hello --type=LoadBalancer --port=3333 --target-port=3000`

Изменить количество реплик (подов) в деплойменте:

`kubectl scale deployment k8s-web-hello --replicas=7`

Получить статус развёртывания деплоймента:

`kubectl rollout status deployment k8s-web-hello`

Обновить образ контейнера в деплойменте:

`kubectl set image deployment k8s-web-hello k8s-web-hello-ru=dnikolskii/k8s-web-hello-ru:2.0.0`

Удалить сервис:

`kubectl delete service k8s-web-hello`

Удалить деплоймент:

`kubectl delete deploy k8s-web-hello`