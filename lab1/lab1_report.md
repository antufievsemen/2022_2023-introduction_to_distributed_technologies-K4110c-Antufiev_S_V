University: [ITMO University](https://itmo.ru/ru/)
Faculty: [FICT](https://fict.itmo.ru)
Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)
Year: 2022/2023
Group: K4110c
Author: Antufiev Semen Viktorovich
Lab: Lab1
Date of create: 09.10.2022
Date of finished: 31.09.2022

![image](https://user-images.githubusercontent.com/55154894/194776796-2954bb87-ad9d-4d1c-b404-bc283afc4f78.png)

## Ход работы:

# Создаем манифест пода:

apiVersion: v1
kind: Pod
metadata:
  name: vault
  labels:
    name: vault
spec:
  containers:
  - name: vault
    image: vault:1.9.10
    ports:
    - containerPort: 8200

Command: kubectl apply -f vault-pod.yaml

# Создаем сервис

Command: kubectl expose pod vault --type=NodePort --port=8200

# Открываем порт для доступа к сервису

Command: kubectl port-forward service/vault 8080:8200
