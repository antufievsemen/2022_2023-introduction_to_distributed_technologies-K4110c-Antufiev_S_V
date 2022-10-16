University: [ITMO University](https://itmo.ru/ru/)
Faculty: [FICT](https://fict.itmo.ru)
Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)
Year: 2022/2023
Group: K4110c
Author: Antufiev Semen Viktorovich
Lab: Lab3
Date of create: 13.10.2022
Date of finished: 

## Ход работы:

# Создаем манифест ingress-controller
1. Важно указать nginx.ingress.kubernetes.io/rewrite-target: / для работы ingress
2. Прописываем хост: его пути, с какими сервисами он общается и порты для обращения.
3. Для работы с tls необходимо указать tls и имя секрета. Написать хосты, на которые будет распространяться наш tls.
4. Важно в хостах добавь dns, по которому мы будет обращаться

Command: kubectl apply -f ingress-front.yaml

# Создаем config map
1. В config map указываем интересующие нас ключи и их значения
2. В deployment указываем config map и указываем env variables, которые мы используем

Command: kubectl apply -f config-values.yaml

# Создание tls

Указанные данные:
 *  emailAddress = alexantufiev@gmail.com
 *  CN = front.example.com
 *  OU = front-service
 *  O = ITMO
 *  L = SPB
 *  ST = SPB
 *  C = RU

# Результат работы

![front-example-com-tls](https://user-images.githubusercontent.com/55154894/195681561-a776cc20-08ec-4ddd-978e-bd7423d50542.png)
![k8s](https://user-images.githubusercontent.com/55154894/195681600-939bd8eb-96d1-46c2-a32e-06d2e37372f3.png)
![configmappng](https://user-images.githubusercontent.com/55154894/195681612-2611db17-b82c-41f3-863e-478b44790669.png)
