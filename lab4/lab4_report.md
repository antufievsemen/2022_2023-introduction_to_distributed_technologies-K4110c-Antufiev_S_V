University: [ITMO University](https://itmo.ru/ru/)
Faculty: [FICT](https://fict.itmo.ru)
Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)
Year: 2022/2023
Group: K4110c
Author: Antufiev Semen Viktorovich
Lab: Lab4
Date of create: 16.10.2022
Date of finished: 

## Ход работы:

# Логи pod'ов
Запускаем minikube со следующими параметрами:
 * --network-plugin=cni 
 * --cni=calico
 * --nodes 2

# Создаем манифест calico для ip pool
1. Я использовал пример с сайта https://projectcalico.docs.tigera.io/
2. Указываем два ippool'а со значениями labels: zone=east и zone=west
3. Выбираем для них ips 

Command: kubectl calico apply -f calico-ip.yaml

# Ставим labels для своих nodes
Command: kubectl label nodes <node name> <label>

# Открываем порт для доступа к сервису

Command: minikube service front-service --url
