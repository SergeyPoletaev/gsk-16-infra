# gsk-16-infra

Настройки инфраструктуры для развертывания сервисов ГСК.

Установка инфраструктуры на сервер
------
Первичная настройка сервера

1. Выполнить в папке gsk-16-infra/ansible/project команду:

```batch
ansible-playbook --ask-become-pass playbook_install.yaml
```

2. Настроить Jenkins:

- зайти на сервер и запустить контейнер с Jenkins:

```batch
docker start jenkins_server
```

- открыть в браузере по адресу http://{адрес_сервера}:9090 и jenkins запросит пароль администратора
- в терминале сервера зайти в работающий контейнер и взять временный пароль:

```batch
docker exec -it jenkins_server /bin/sh
cat /var/jenkins_home/secrets/initialAdminPassword
```

- ввести временный пароль и закончить настройку jenkins
- остановить контейнер с jenkins:

```batch
docker stop jenkins_server
```

Запуск сервера
------

