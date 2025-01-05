University: ITMO University Faculty: FICT Course: Introduction to distributed technologies Year: 2024 Group: K4112c Author: Romanova Elina Pavlovna Lab: Lab2 Date of create: 05.01.2024 Date of finished:

## Лабораторная работа №2 "Развертывание веб сервиса в Minikube, доступ к веб интерфейсу сервиса. Мониторинг сервиса."

### Цель работы

Ознакомиться с типами "контроллеров" развертывания контейнеров, ознакомится с сетевыми сервисами и развернуть свое веб приложение.

### Ход работы

1. Создать `deployment` с 2 репликами контейнера [ifilyaninitmo/itdt-contained-frontend:master](https://hub.docker.com/repository/docker/ifilyaninitmo/itdt-contained-frontend) и передать переменные в эти реплики: `REACT_APP_USERNAME`, `REACT_APP_COMPANY_NAME`.
2. Создать сервис через который будет доступ на эти "поды". Выбор типа сервиса остается на ваше усмотрение.
3. Запустить в `minikube` режим проброса портов и подключиться к контейнерам через веб браузер.
4. Проверить на странице в веб-браузере переменные `REACT_APP_USERNAME`, `REACT_APP_COMPANY_NAME` и `Container name`. Изменяются ли они? Если да то почему?
5. Проверить логи контейнеров, приложите логи в отчёт.

### Выполнение работы

#### 1. Создание Deployment
