University: [ITMO University](https://itmo.ru/ru/)
Faculty: [FICT](https://fict.itmo.ru)
Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)
Year: 2024/2025
Group: K4111c
Author: Sviridov Konstantin Andreevich
Lab: Lab3
Date of create: 05.11.2024
Date of finished:

---

## Ход работы

1. Был создан манифест configMap.yaml для configMap
2. Были созданы манифесты replicates.yaml и service.yaml, энвы в поды были прокинуты через configMap
3. Был сгененрирован TLS сертификат, создан манифест ingress.yaml, был создан secret с сертификатом
4. Был подключен аддон ingress при помощи комманды: minikube addons enable ingress
5. Через minikube tunnel получен доступ до приложения
6. Также была построена диаграмма в draw.io
