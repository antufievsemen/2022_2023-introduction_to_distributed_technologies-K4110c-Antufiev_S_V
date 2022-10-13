University: [ITMO University](https://itmo.ru/ru/)
Faculty: [FICT](https://fict.itmo.ru)
Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)
Year: 2022/2023
Group: K4110c
Author: Antufiev Semen Viktorovich
Lab: Lab2
Date of create: 11.10.2022
Date of finished: 

## Ход работы:

# Создаем манифест deployment
1. В spec указываем количество replic = 2
2. В spec указываем selector: mathLabels: (указываем label, который мы будем использовать для сервиса)
3. Создаем template, в котором мы указываем конфигурацию к pod
4. Важно поставить containerPort: 3000. Так как приложение слушает именно этот порт, это видно из логов.

Command: kubectl apply -f deployment.yaml

# Логи pod'ов


# Создаем сервис

1. В spec указываем selector: (указываем label, сервис свяжет их все с собой)
2. TargetPort указываем 3000.
3. Указываем type: NodePort для связи с pod извне.

Command: kubectl apply -f front-service.yaml

# Открываем порт для доступа к сервису

Command: kubectl port-forward service/front-service 8888:8080
