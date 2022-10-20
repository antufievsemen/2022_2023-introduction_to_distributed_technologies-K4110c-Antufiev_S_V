University: [ITMO University](https://itmo.ru/ru/)
Faculty: [FICT](https://fict.itmo.ru)
Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)
Year: 2022/2023
Group: K4110c
Author: Antufiev Semen Viktorovich
Lab: Lab2
Date of create: 12.10.2022
Date of finished: 

## Ход работы:

# Создаем манифест deployment
[Manifest](https://github.com/antufievsemen/2022_2023-introduction_to_distributed_technologies-K4110c-Antufiev_S_V/blob/main/lab2/deployment.yaml)
1. В spec указываем количество replic = 2
2. В spec указываем selector: mathLabels: (указываем label, который мы будем использовать для сервиса)
3. Создаем template, в котором мы указываем конфигурацию к pod
4. Важно поставить containerPort: 3000. Так как приложение слушает именно этот порт, это видно из логов.
![kuber_logspng](https://user-images.githubusercontent.com/55154894/195167104-e8da366b-0a6b-4168-be36-5a5a89d26cf4.png)

Command: kubectl apply -f deployment.yaml

# Логи pod'ов
![kuber_logspng](https://user-images.githubusercontent.com/55154894/195167019-6d3ebfd1-5602-4f91-911d-646edd604310.png)

# Создаем сервис
[Manifest](https://github.com/antufievsemen/2022_2023-introduction_to_distributed_technologies-K4110c-Antufiev_S_V/blob/main/lab2/service-front.yaml)
1. В spec указываем selector: (указываем label, сервис свяжет их все с собой)
2. TargetPort указываем 3000.
3. Указываем type: NodePort для связи с pod извне.

Command: kubectl apply -f front-service.yaml

# Открываем порт для доступа к сервису

Command: kubectl port-forward service/front-service 8888:8080

# Результат
![app](https://user-images.githubusercontent.com/55154894/195167150-da4ceec4-0c2a-4587-8410-9271f881d35c.png)

![kuber](https://user-images.githubusercontent.com/55154894/195167225-52b074d4-dcf9-4e13-a4aa-8c4dcb592824.png)

# Схема k8s
![schema](https://user-images.githubusercontent.com/55154894/197008746-40a2336a-7822-4a75-8a00-9edf0b9134db.png)

