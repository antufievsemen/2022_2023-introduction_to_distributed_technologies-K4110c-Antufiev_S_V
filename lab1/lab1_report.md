University: [ITMO University](https://itmo.ru/ru/)
Faculty: [FICT](https://fict.itmo.ru)
Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)
Year: 2022/2023
Group: K4110c
Author: Antufiev Semen Viktorovich
Lab: Lab1
Date of create: 09.10.2022
Date of finished: 20.10.2022 (15 points)


## Ход работы:

# Создаем манифест пода 
Ссылка на [manifest](https://github.com/antufievsemen/2022_2023-introduction_to_distributed_technologies-K4110c-Antufiev_S_V/blob/main/lab1/vault-pod.yaml).

1. Добавляем образ vault
2. Добавляем labels name: vault
3. Создаем под

Command: kubectl apply -f vault-pod.yaml

# Создаем сервис

Command: kubectl expose pod vault --type=NodePort --port=8200

# Открываем порт для доступа к сервису

Command: kubectl port-forward service/vault 8080:8200

# Схема k8s:
![schema_extended](https://user-images.githubusercontent.com/55154894/197000068-19f1650d-94c7-4827-be0c-cb9b7bc1d8f8.png)



