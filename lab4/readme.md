University: [ITMO University](https://itmo.ru/ru/)

Faculty: [FICT](https://fict.itmo.ru)

Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)

Year: 2024

Group: K4112c

Author: Romanova Elina Pavlovna

Lab: Lab4

Date of create: 08.01.2025

Date of finished: 

## Лабораторная работа №4 "Сети связи в Minikube, CNI и CoreDNS"

### Цель работы

Познакомиться с CNI Calico и функцией `IPAM Plugin`, изучить особенности работы CNI и CoreDNS.

### Ход работы

1. Запустить minikube вместе с плагином Calico;
2. Проверить работу CNI плагина Calico и количество нод;
3. Для запущеных ранее нод указать `label` по признаку стойки или географического расположения;
4. На основе ранее указанных меток назначить IP адреса "подам";
5. Cоздать `deployment` с 2 репликами контейнера [ifilyaninitmo/itdt-contained-frontend:master](https://hub.docker.com/repository/docker/ifilyaninitmo/itdt-contained-frontend) и передать переменные в эти реплики: `REACT_APP_USERNAME`, `REACT_APP_COMPANY_NAME`;
6. Создать сервис через который будет доступ на эти "поды";
7. Запустить в `minikube` режим проброса портов и подключиться к контейнерам через веб браузер;
8. Используя `kubectl exec` зайти в любой "под" и попробовать попинговать "поды" используя `FQDN` имя соседенего "пода", результаты пингов необходимо приложить к отчету

### Выполнение работы

#### 1. Запуск minikube

Запуск minikube был осуществлен с помощью следующей команды:

```bash
minikube start --network-plugin=cni --cni=calico --nodes=2
```

Команда настраивает Minikube для использования стандарта CNI (Container Network Interface) с сетевым плагином Calico, а также задаёт создание двух рабочих нод в кластере Kubernetes.

#### 2. Проверка работы

![image](./pic1.png)

Поды и ноды успешно развернуты.
