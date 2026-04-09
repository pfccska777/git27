# Домашнее задание к занятию  «Защита хоста»

### Задание 1

1. Установите **eCryptfs**.
2. Добавьте пользователя cryptouser.
3. Зашифруйте домашний каталог пользователя с помощью eCryptfs.


*В качестве ответа  пришлите снимки экрана домашнего каталога пользователя с исходными и зашифрованными данными.*  

### Решение 1
![screen](https://github.com/pfccska777/git27/blob/main/photo/Задание%201.png)

### Задание 2

1. Установите поддержку **LUKS**.
2. Создайте небольшой раздел, например, 100 Мб.
3. Зашифруйте созданный раздел с помощью LUKS.

*В качестве ответа пришлите снимки экрана с поэтапным выполнением задания.*

### Решение 2

![screen](https://github.com/pfccska777/git27/blob/main/photo/Задание%202.png)

ls .secret/
sudo umount .secret
sudo cryptsetup luksClose disk
ls .secret/

![screen](https://github.com/pfccska777/git27/blob/main/photo/Задание%202%20.1.png)
![screen](https://github.com/pfccska777/git27/blob/main/photo/Задание%202.2.png)
