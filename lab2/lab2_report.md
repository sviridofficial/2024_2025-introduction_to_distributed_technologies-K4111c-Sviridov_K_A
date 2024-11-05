University: [ITMO University](https://itmo.ru/ru/)</br>
Faculty: [FICT](https://fict.itmo.ru)</br>
Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)</br>
Year: 2024/2025</br>
Group: K4111c</br>
Author: Sviridov Konstantin Andreevich</br>
Lab: Lab2</br>
Date of create: 05.11.2024</br>
Date of finished:

---

## Ход работы

1. Был создан манифест deployment.yaml c 2 репликами фронтенд приложения
2. Был создан сервис через который открыт доступ к подам
3. Были применены манифесты при помощи комманд minikube kubectl -- apply -f ./lab2/deployment.yaml и minikube kubectl -- apply -f ./lab2/service.yaml
4. Был проброшен порт (minikube kubectl -- port-forward service/frontend-app 3000:3000), подключился к контейнерам через веб-браузер
5. Были проверены логи, составлена диаграмма в draw.io
