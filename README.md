# Домашнее задание к занятию «Продвинутые методы работы с Terraform»


### Задание 1

1. Возьмите из [демонстрации к лекции готовый код](https://github.com/netology-code/ter-homeworks/tree/main/04/demonstration1) для создания с помощью двух вызовов remote-модуля -> двух ВМ, относящихся к разным проектам(marketing и analytics) используйте labels для обозначения принадлежности.  В файле cloud-init.yml необходимо использовать переменную для ssh-ключа вместо хардкода. Передайте ssh-ключ в функцию template_file в блоке vars ={} .
Воспользуйтесь [**примером**](https://grantorchard.com/dynamic-cloudinit-content-with-terraform-file-templates/). Обратите внимание, что ssh-authorized-keys принимает в себя список, а не строку.
3. Добавьте в файл cloud-init.yml установку nginx.
4. Предоставьте скриншот подключения к консоли и вывод команды ```sudo nginx -t```, скриншот консоли ВМ yandex cloud с их метками. Откройте terraform console и предоставьте скриншот содержимого модуля. Пример: > module.marketing_vm
------

# Решение 1.

Реализовал инфраструктуру через Terraform: настроил сеть и подсеть в Yandex Cloud. Создал универсальный модуль для ВМ, который принимает параметры ресурсов, образов и меток. Для автоматизации конфигурации использовал cloud-init (установка nginx и настройка SSH). Развернул две изолированные ВМ для проектов marketing и analytics. Результаты проверены: сервисы работают, метки в консоли отображаются корректно. Выявлено, что для работы terraform console необходимо добавить output в модуль
---

![screen1](https://github.com/pfccska777/git27/blob/main/photo/Screen1.png)
![screen2](https://github.com/pfccska777/git27/blob/main/photo/Screen2.png)
![screen3](https://github.com/pfccska777/git27/blob/main/photo/Screen3.png)
![screen4](https://github.com/pfccska777/git27/blob/main/photo/Screen4.png)
![screen5](https://github.com/pfccska777/git27/blob/main/photo/Screen5.png)

### Задание 2

1. Напишите локальный модуль vpc, который будет создавать 2 ресурса: одну сеть и одну подсеть в зоне, объявленной при вызове модуля, например: ru-central1-a.
2. Вы должны передать в модуль переменные с названием сети, zone и v4_cidr_blocks.
3. Модуль должен возвращать в root module с помощью output информацию о yandex_vpc_subnet. Пришлите скриншот информации из terraform console о своем модуле. Пример: > module.vpc_dev  
4. Замените ресурсы yandex_vpc_network и yandex_vpc_subnet созданным модулем. Не забудьте передать необходимые параметры сети из модуля vpc в модуль с виртуальной машиной.
5. Сгенерируйте документацию к модулю с помощью terraform-docs.
---

# Решение 2.



### Задание 3
1. Выведите список ресурсов в стейте.
2. Полностью удалите из стейта модуль vpc.
3. Полностью удалите из стейта модуль vm.
4. Импортируйте всё обратно. Проверьте terraform plan. Значимых(!!) изменений быть не должно.
Приложите список выполненных команд и скриншоты процессы.
---


# Решение 3.
