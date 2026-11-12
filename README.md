# Домашнее задание к занятию Troubleshooting

### Цель задания

Устранить неисправности при деплое приложения.

### Чеклист готовности к домашнему заданию

1. Кластер K8s.

### Задание. При деплое приложение web-consumer не может подключиться к auth-db. Необходимо это исправить

1. Установить приложение по команде:
```shell
kubectl apply -f https://raw.githubusercontent.com/netology-code/kuber-homeworks/main/3.5/files/task.yaml
```
2. Выявить проблему и описать.
3. Исправить проблему, описать, что сделано.
4. Продемонстрировать, что проблема решена.


### Решение.

![screen1](https://github.com/pfccska777/git27/blob/main/photo/манифест%20к%20первой%20части.png)
![screen2](https://github.com/pfccska777/git27/blob/main/photo/Проблема.png)
![screen3](https://github.com/pfccska777/git27/blob/main/photo/Продолжение%20проблемы.png)
![screen4](https://github.com/pfccska777/git27/blob/main/photo/Продолжение%20продолжения.png)

1. Curl понятия не имеет что либо о хосте. Исправить можно прописвыя в каждом контейнере вручную, либо же указывать решение в команде Curl.

![screen5](https://github.com/pfccska777/git27/blob/main/photo/манифест%20к%20решению%20проблемы.png)
![screen6](https://github.com/pfccska777/git27/blob/main/photo/Проверка%20отсутствия%20проблемы.png)
![screen7](https://github.com/pfccska777/git27/blob/main/photo/Проверка%20отсутствия%20проблемы%202.png)


