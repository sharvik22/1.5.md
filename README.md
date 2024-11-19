# Домашнее задание к занятию «Сетевое взаимодействие в K8S. Часть 2» Шарапат Виктор

### Цель задания

В тестовой среде Kubernetes необходимо обеспечить доступ к двум приложениям снаружи кластера по разным путям.

------

### Чеклист готовности к домашнему заданию

1. Установленное k8s-решение (например, MicroK8S).
2. Установленный локальный kubectl.
3. Редактор YAML-файлов с подключённым Git-репозиторием.

------

### Инструменты и дополнительные материалы, которые пригодятся для выполнения задания

1. [Инструкция](https://microk8s.io/docs/getting-started) по установке MicroK8S.
2. [Описание](https://kubernetes.io/docs/concepts/services-networking/service/) Service.
3. [Описание](https://kubernetes.io/docs/concepts/services-networking/ingress/) Ingress.
4. [Описание](https://github.com/wbitt/Network-MultiTool) Multitool.

------

### Задание 1. Создать Deployment приложений backend и frontend

1. Создать Deployment приложения _frontend_ из образа nginx с количеством реплик 3 шт.
2. Создать Deployment приложения _backend_ из образа multitool. 
3. Добавить Service, которые обеспечат доступ к обоим приложениям внутри кластера. 
4. Продемонстрировать, что приложения видят друг друга с помощью Service.
5. Предоставить манифесты Deployment и Service в решении, а также скриншоты или вывод команды п.4.

------

### Задание 2. Создать Ingress и обеспечить доступ к приложениям снаружи кластера

1. Включить Ingress-controller в MicroK8S.
2. Создать Ingress, обеспечивающий доступ снаружи по IP-адресу кластера MicroK8S так, чтобы при запросе только по адресу открывался _frontend_ а при добавлении /api - _backend_.
3. Продемонстрировать доступ с помощью браузера или `curl` с локального компьютера.
4. Предоставить манифесты и скриншоты или вывод команды п.2.

------

### Правила приема работы

1. Домашняя работа оформляется в своем Git-репозитории в файле README.md. Выполненное домашнее задание пришлите ссылкой на .md-файл в вашем репозитории.
2. Файл README.md должен содержать скриншоты вывода необходимых команд `kubectl` и скриншоты результатов.
3. Репозиторий должен содержать тексты манифестов или ссылки на них в файле README.md.

------

### Решение 1

* Создал необходимые манифесты, применил их.

![Screenshot_1](https://github.com/user-attachments/assets/551574bf-c377-4eec-9d59-7cc01ca74caf)

![Screenshot_2](https://github.com/user-attachments/assets/689d8e17-bc00-4458-bd07-c0230e28192a)

 - frontend из образа nginx с количеством реплик 3 шт.
 - backend из образа multitool.

![Screenshot_3](https://github.com/user-attachments/assets/4502ffed-32ef-4b7e-958b-656a0572ca97)

* добавил Service, которые обеспечат доступ к обоим приложениям внутри кластера.

# Проверка доступности frontend из backend

* Подключился к ноде backend, сделал запрос на frontend

![Screenshot_5](https://github.com/user-attachments/assets/110ddcd0-620e-48d3-88a4-07bea9b76750)

![Screenshot_6](https://github.com/user-attachments/assets/10d37fb0-21dc-4a2e-9bba-e463282b5ef3)

* и на оборот, подключился к ноде frontend и проверил доступ к backend

![Screenshot_7](https://github.com/user-attachments/assets/13b5bb75-7449-41a5-84cc-64af58e0a371)

---

### Решение 2

* Включил Ingress-контроллера в MicroK8S

![image](https://github.com/user-attachments/assets/518b1c4a-1e96-4314-988c-22e8ba90421f)


---
