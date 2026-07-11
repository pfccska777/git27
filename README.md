# Домашнее задание к занятию «Введение в Terraform»

![screen1](https://github.com/pfccska777/git27/blob/main/photo/Подготовка.png)
![screen2](https://github.com/pfccska777/git27/blob/main/photo/Подготовка%202.png)

Задание 1

1. Перейдите в каталог [**src**](https://github.com/netology-code/ter-homeworks/tree/main/01/src). Скачайте все необходимые зависимости, использованные в проекте. 

![screen3](https://github.com/pfccska777/git27/blob/main/photo/Пункт%201.png)


2. Изучите файл **.gitignore**. В каком terraform-файле, согласно этому .gitignore, допустимо сохранить личную, секретную информацию?(логины,пароли,ключи,токены итд)

Файл personal.auto.tfvars


3. Выполните код проекта. Найдите  в state-файле секретное содержимое созданного ресурса **random_password**, пришлите в качестве ответа конкретный ключ и его значение.

![screen4](https://github.com/pfccska777/git27/blob/main/photo/Пункт%203.png)


4. Раскомментируйте блок кода, примерно расположенный на строчках 29–42 файла **main.tf**.
Выполните команду terraform validate`. Объясните, в чём заключаются намеренно допущенные ошибки. Исправьте их.

Сначала было много ошибок

![screen5](https://github.com/pfccska777/git27/blob/main/photo/Ошибки.png)

![screen6](https://github.com/pfccska777/git27/blob/main/photo/Снова%20ошибки.png)


Удалось устранить

![screen7](https://github.com/pfccska777/git27/blob/main/photo/Без%20ошибок.png)


Выполните команду terraform validate. Объясните, в чём заключаются намеренно допущенные ошибки. Исправьте их.

Ошибки были заключены по больше степени в написании кода. Например вместо маленьких символов были большиею


5. Выполните код. В качестве ответа приложите: исправленный фрагмент кода и вывод команды `docker ps.

![screen8](https://github.com/pfccska777/git27/blob/main/photo/Код%205.png)

![screen9](https://github.com/pfccska777/git27/blob/main/photo/Итог%205.png)


6. Замените имя docker-контейнера в блоке кода на `hello_world. Не перепутайте имя контейнера и имя образа. Мы всё ещё продолжаем использовать name = "nginx:latest". Выполните команду terraform apply -auto-approve.
Объясните своими словами, в чём может быть опасность применения ключа  -auto-approve`. Догадайтесь или нагуглите зачем может пригодиться данный ключ? В качестве ответа дополнительно приложите вывод команды docker ps.

Опасность применения ключа заключается в возможности невнимательно ознакомиться с информацией, и удалить какой либо объект даже с ошибкой.

Пригодиться данный ключ может для автоматизированной работы, и запуска.

![screen10](https://github.com/pfccska777/git27/blob/main/photo/Код%206.png)

![screen11](https://github.com/pfccska777/git27/blob/main/photo/Итог%206.png)


8. Уничтожьте созданные ресурсы с помощью **terraform**. Убедитесь, что все ресурсы удалены. Приложите содержимое файла **terraform.tfstate**. 

![screen12](https://github.com/pfccska777/git27/blob/main/photo/Результат%208.png)


9. Объясните, почему при этом не был удалён docker-образ **nginx:latest**. Ответ **ОБЯЗАТЕЛЬНО НАЙДИТЕ В ПРЕДОСТАВЛЕННОМ КОДЕ**, а затем **ОБЯЗАТЕЛЬНО ПОДКРЕПИТЕ** строчкой из документации [**terraform провайдера docker**](https://library.tf/providers/kreuzwerker/docker/latest).  (ищите в классификаторе resource docker_image )

Он не был удалён, потому что был использован критерий keep_locally = true

Доказательсвто из документации keep_locally (Boolean) If true, then the Docker image won't be deleted on destroy operation. If this is false, it will delete the image from the docker local storage on destroy operation.


