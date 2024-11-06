University: [ITMO University](https://itmo.ru/ru/)</br>
Faculty: [FICT](https://fict.itmo.ru)</br>
Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)</br>
Year: 2024/2025</br>
Group: K4111c</br>
Author: Sviridov Konstantin Andreevich</br>
Lab: Lab3</br>
Date of create: 05.11.2024</br>
Date of finished:

## Лабораторная работа №3 "Сертификаты и "секреты" в Minikube, безопасное хранение данных."

### Цель работы

Познакомиться с сертификатами и "секретами" в Minikube, правилами безопасного хранения данных в Minikube.

### Ход работы

1. Был создан манифест `configMap.yaml` для configMap:

![](/lab3/screenshots/applyConfigMap.png)

2. Были созданы манифесты `replicaset.yaml` и `service.yaml`, энвы в поды были прокинуты через configMap:

![](/lab3/screenshots/applyReplicaset.png)

![](/lab3/screenshots/applyService.png)

3. Был сгененрирован TLS сертификат, создан манифест `ingress.yaml`, был создан secret с сертификатом:

![](/lab3/screenshots/generateSertificate.png)

![](/lab3/screenshots/createSecret.png)

![](/lab3/screenshots/applyIngress.png)

4. Был подключен аддон ingress при помощи комманды:

```
minikube addons enable ingress
```

![](/lab3/screenshots/enableIngressAddon.png)

5. Через minikube tunnel получен доступ до приложения:

![](/lab3/screenshots/website.png)

![](/lab3/screenshots/certificate.png)

6. Также была построена диаграмма в draw.io:

![](/lab3/screenshots/schema.png)
