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
# Info k8s
![k8s](https://user-images.githubusercontent.com/55154894/197010682-0766986d-5e53-4b7e-a441-f8fd404c5549.png)
![nodesAndCni](https://user-images.githubusercontent.com/55154894/197010702-4c0a9f44-6f0f-41b1-be9d-168424390490.png)

# Конфигурация для запуска minikube 
Запускаем minikube со следующими параметрами:
 * --network-plugin=cni 
 * --cni=calico
 * --nodes 2

# Создаем манифест calico для ip pool
[Manifest](https://github.com/antufievsemen/2022_2023-introduction_to_distributed_technologies-K4110c-Antufiev_S_V/blob/main/lab4/calico-ip.yaml)
1. Я использовал пример с сайта https://projectcalico.docs.tigera.io/
2. Указываем два ippool'а со значениями labels: zone=east и zone=west
3. Выбираем для них ips 

Command: kubectl calico apply -f calico-ip.yaml

# Ставим labels для своих nodes
Command: kubectl label nodes <node name> <label>

# Открываем порт для доступа к сервису

Command: minikube service front-service --url

# Скриншоты ответа приложения
![1-app](https://user-images.githubusercontent.com/55154894/197010348-5a8d36b1-2f5b-462c-bf12-2604ab70b017.png)
![2-app](https://user-images.githubusercontent.com/55154894/197010364-32c868ab-c177-43a2-8f46-03482c9e5491.png)
![3-app](https://user-images.githubusercontent.com/55154894/197010376-2807c123-335f-4a3a-934b-f82d6c8700c2.png)
  
# Схема k8s
![schema](https://user-images.githubusercontent.com/55154894/197010449-5157a71b-846f-4e89-a785-9cbb91ab80d2.png)

