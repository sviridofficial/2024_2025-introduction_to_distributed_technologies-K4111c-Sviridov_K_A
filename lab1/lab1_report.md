University: [ITMO University](https://itmo.ru/ru/) </br>
Faculty: [FICT](https://fict.itmo.ru)</br>
Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)</br>
Year: 2024/2025</br>
Group: K4111c</br>
Author: Sviridov Konstantin Andreevich</br>
Lab: Lab1</br>
Date of create: 04.11.2024</br>
Date of finished:</br>

---

## Ход работы

1. Был установлен Docker и Minikube
2. Был развернут minikube cluster при помощи команды "minikube start"
3. Был написан манифест vault-pod.yaml для описания pod'а
4. Был применен манифест при помощи команды: "minikube kubectl -- apply -f ./lab1/vault-pod.yaml"
5. Был создан сервис при помощи команды: "minikube kubectl -- expose pod vault --type=NodePort --port=8200"
6. Был прокинут порт для сервиса при помощи команды: "minikube kubectl -- port-forward service/vault 8200:8200"
7. Зашел на http://localhost:8200
8. Нашел токен для авторизации через комманду: "minikube kubectl -- logs vault"
9. По токену из логов авторизовался в сервисе.
10. Была составлена диграмма draw.io (диаграмма лежит в lab1/diagramlab1.drawio , все скриншоты в lab1/screenshots)
