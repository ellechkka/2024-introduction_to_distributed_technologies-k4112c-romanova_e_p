University: [ITMO University](https://itmo.ru/ru/)

Faculty: [FICT](https://fict.itmo.ru)

Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)

Year: 2024

Group: K4112c

Author: Romanova Elina Pavlovna

Lab: Lab3

Date of create: 05.01.2025

Date of finished: 

## Лабораторная работа №3 "Сертификаты и "секреты" в Minikube, безопасное хранение данных."

### Цель работы

Познакомиться с сертификатами и "секретами" в Minikube, правилами безопасного хранения данных в Minikube.

### Ход работы

1. Создать ConfigMap с переменными среды `REACT_APP_USERNAME` и `REACT_APP_COMPANY_NAME`;
2. Создать ReplicaSet с 2 репликами контейнера `ifilyaninitmo/itdt-contained-frontend:master`;
3. Включить Ingress и создать TLS-сертификат;
4. Создать Ingress, который будет использовать сервис и секрет с TLS-сертификатом;
5. Настроить `HOSTS`;
6. Проверка результатов.

### Выполнение работы

#### 1. Создание ConfigMap

Сначала создается конфигурационный файл [configmap.yaml](./configmap.yaml), в котором определяются значения для переменных среды: `REACT_APP_USERNAME` и `REACT_APP_COMPANY_NAME`.

После этого файл используется для создания объекта ConfigMap в Kubernetes с помощью следующей команды:

```bash
minikube kubectl -- apply -f configmap.yaml
```
#### 2. Создание ReplicaSet

ReplicaSet в Kubernetes управляет количеством реплик подов, обеспечивая их высокую доступность. Если под выходит из строя, ReplicaSet автоматически создаёт новый, чтобы поддерживать нужное количество реплик. В отличие от Deployment, ReplicaSet не поддерживает управление версиями, но используется для создания и управления подами в Deployment.

В конфигурационном файле [deployment2.yaml](./deployment2.yaml) описана конфигурация объекта ReplicaSet. В конце файла также указывается ранее созданный объект lab3configmap, который содержит переменные среды.

После создания файла объект ReplicaSet создается в Kubernetes с помощью команды:
```bash
minikube kubectl -- apply -f deployment2.yaml
```
