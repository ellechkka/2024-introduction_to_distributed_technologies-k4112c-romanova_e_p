University: [ITMO University](https://itmo.ru/ru/)
Faculty: [FICT](https://fict.itmo.ru)
Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)
Year: 2024
Group: K4112c
Author: Romanova Elina Pavlovna
Lab: Lab1
Date of create: 12.12.2024
Date of finished: 

## Лабораторная работа №1 "Установка Docker и Minikube, мой первый манифест."

### Описание

Это первая лабораторная работа в которой вы сможете протестировать Docker, установить Minikube и развернуть свой первый "под".

### Цель работы

Ознакомиться с инструментами Minikube и Docker, развернуть свой первый "под".

### Ход работы

1. Установить Docker;
2. Установить Minikube;
3. Развернуть minikube cluster;
4. Скачать образ HashiCorp Vault;
5. Написать manifest для развертывания пода с образом HashiCorp Vault;
6. Создать сервис для доступа к данному контейнеру;
7. Прокинуть порт для доступа к контейнеру;
8. Найти токен для доступа к vault
9. Войти, используя токен.

### Выполнение работы

#### 1. Установка Docker

Docker был скачен с официального сайта https://www.docker.com/ и установлен на Windows 11.
![image](./docker.png)

#### 2. Установка Minikube

Minikube был скачен с официального сайта https://minikube.sigs.k8s.io/docs/start/.

#### 3. Развертывание minikube cluster

Была использована следующая команда:

```bash
minikebe start
```
