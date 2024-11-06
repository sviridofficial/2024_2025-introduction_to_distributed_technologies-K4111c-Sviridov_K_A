University: [ITMO University](https://itmo.ru/ru/)</br>
Faculty: [FICT](https://fict.itmo.ru)</br>
Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)</br>
Year: 2024/2025</br>
Group: K4111c</br>
Author: Sviridov Konstantin Andreevich</br>
Lab: Lab2</br>
Date of create: 05.11.2024</br>
Date of finished:

## Лабораторная работа №2 "Развертывание веб сервиса в Minikube, доступ к веб интерфейсу сервиса. Мониторинг сервиса."

### Цель работы

Ознакомиться с типами "контроллеров" развертывания контейнеров, ознакомится с сетевыми сервисами и развернуть свое веб приложение.

### Ход работы

1. Был создан манифест `deployment.yaml` c 2 репликами фронтенд приложения
2. Был создан манифест `service.yaml` сервиса, который открывает доступ к подам
3. Были применены манифесты при помощи комманд

```
minikube kubectl -- apply -f ./lab2/deployment.yaml
```

```
minikube kubectl -- apply -f ./lab2/service.yaml
```

![](/lab2/screenshots/createDeployment.png)
![](/lab2/screenshots/createService.png)
![](/lab2/screenshots/getPods.png)

4. Был проброшен порт

```
minikube kubectl -- port-forward service/frontend-app 3000:3000
```

![](/lab2/screenshots/portForward.png)

Подключился к контейнерам через веб-браузер:

![](/lab2/screenshots/app.png)

5. Были проверены логи

![](/lab2/screenshots/logs.png)

6. Была составлена диаграмма в draw.io

![](/lab2/screenshots/schema.png)
