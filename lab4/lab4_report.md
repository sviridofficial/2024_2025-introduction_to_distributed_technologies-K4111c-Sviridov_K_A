University: [ITMO University](https://itmo.ru/ru/)</br>
Faculty: [FICT](https://fict.itmo.ru)</br>
Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)</br>
Year: 2024/2025</br>
Group: K4111c</br>
Author: Sviridov Konstantin Andreevich</br>
Lab: Lab4</br>
Date of create: 06.11.2024</br>
Date of finished:

## Лабораторная работа №4 "Сети связи в Minikube, CNI и CoreDNS"

### Цель работы

Познакомиться с CNI Calico и функцией IPAM Plugin, изучить особенности работы CNI и CoreDNS.

### Ход работы

Запускаем minikube с плагином CNI=calico и режимом работы Multi-Node Clusters для работы с 2-умя нодами.
Комманда для запуска:

```
minikube start --network-plugin=cni --cni=calico --nodes 2 -p multinode-demo
```

![](/lab4/screenshots/createTwoNodes.png)

Получаем кластер с 2-умя нодами:

![](/lab4/screenshots/nodes.png)

Также были созданы поды Calcio:

![](/lab4/screenshots/calcioPods.png)

Помечаем лейблами ноды по географической зоне:

![](/lab4/screenshots/labeledNodes.png)

Удаляем созданные по умолчанию IPPools коммандой:

```
kubectl delete ippools default-ipv4-ippool
```

Создаем манифест `ippool.yaml` для пуллинга и применяем его:

```
kubectl-calico apply -f ippool.yaml --allow-version-mismatch
```

![](/lab4/screenshots/applyPool.png)

Получим пуллы коммандой:

```
kubectl get ippools
```

![](/lab4/screenshots/pools.png)

После были применены `deployment.yaml` и `service.yaml` из второй лабораторной работы коммандами:

```
kubectl apply -f ./deployment.yaml
```

```
kubectl apply -f ./service.yaml
```

![](/lab4/screenshots/podsAfterDeployment.png)

После применения деплоймента поды размещены на двух нодах.

Запустим проброс портов и проверим работу приложения:

```
kubectl port-forward service/frontend-service 3000:3000
```

![](/lab4/screenshots/app.png)

Зайдем в один из подов и попробуем попинговать другой под:

```
kubectl exec -ti frontend-deployment-68fcb648c6-pbfxd -- sh
```

```
ping 192.168.1.0
```

![](/lab4/screenshots/pingPod.png)

Диаграмма:
![](/lab4/screenshots/schema.png)
