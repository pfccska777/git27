# Домашнее задание к занятию «Управляющие конструкции в коде Terraform»


### Задание 1

1. Изучите проект.
2. Инициализируйте проект, выполните код.


Приложите скриншот входящих правил «Группы безопасности» в ЛК Yandex Cloud .

### Решение 1

![screen1](https://github.com/pfccska777/git27/blob/main/photo/Правила.png)


### Задание 2

1. Создайте файл count-vm.tf. Опишите в нём создание двух **одинаковых** ВМ  web-1 и web-2 (не web-0 и web-1) с минимальными параметрами, используя мета-аргумент **count loop**. Назначьте ВМ созданную в первом >
2. Создайте файл for_each-vm.tf. Опишите в нём создание двух ВМ для баз данных с именами "main" и "replica" **разных** по cpu/ram/disk_volume , используя мета-аргумент **for_each loop**. Используйте для обеих В>
```
variable "each_vm" {
  type = list(object({  vm_name=string, cpu=number, ram=number, disk_volume=number }))
}
```  
При желании внесите в переменную все возможные параметры.
3. ВМ, описанные в файле count-vm.tf, должны создаваться после ВМ, описанных в файле for_each-vm.tf.
4. Используйте функцию file в local-переменной для считывания ключа ~/.ssh/id_rsa.pub и его последующего использования в блоке metadata, взятому из ДЗ 2.
5. Инициализируйте проект, выполните код.

### Решение 2

![screen2](https://github.com/pfccska777/git27/blob/main/photo/Пункт%202.png)
![screen3](https://github.com/pfccska777/git27/blob/main/photo/Пункт%202.1.png)
![screen4](https://github.com/pfccska777/git27/blob/main/photo/Пункт%202.2.png)
![screen5](https://github.com/pfccska777/git27/blob/main/photo/Пункт%202.3.png)


### Задание 3

1. Создайте 3 одинаковых виртуальных диска размером 1 Гб с помощью ресурса yandex_compute_disk и мета-аргумента count в файле **disk_vm.tf** .
2. Создайте в том же файле **одиночную**(использовать count или for_each запрещено из-за задания №4) ВМ c именем "storage"  . Используйте блок **dynamic secondary_disk{..}** и мета-аргумент for_each для подключ>

### Решение 3

![screen6](https://github.com/pfccska777/git27/blob/main/photo/Пункт%203.png)
![screen7](https://github.com/pfccska777/git27/blob/main/photo/Пункт%203.1.png)


### Задание 4

1. В файле ansible.tf создайте inventory-файл для ansible.
Используйте функцию tepmplatefile и файл-шаблон для создания ansible inventory-файла из лекции.
Готовый код возьмите из демонстрации к лекции [**demonstration2**](https://github.com/netology-code/ter-homeworks/tree/main/03/demo).
Передайте в него в качестве переменных группы виртуальных машин из задания 2.1, 2.2 и 3.2, т. е. 5 ВМ.
2. Инвентарь должен содержать 3 группы и быть динамическим, т. е. обработать как группу из 2-х ВМ, так и 999 ВМ.
3. Добавьте в инвентарь переменную  [**fqdn**](https://cloud.yandex.ru/docs/compute/concepts/network#hostname).
``` 
[webservers]
web-1 ansible_host=<внешний ip-адрес> fqdn=<полное доменное имя виртуальной машины>
web-2 ansible_host=<внешний ip-адрес> fqdn=<полное доменное имя виртуальной машины>

[databases]
main ansible_host=<внешний ip-адрес> fqdn=<полное доменное имя виртуальной машины>
replica ansible_host<внешний ip-адрес> fqdn=<полное доменное имя виртуальной машины>

[storage]
storage ansible_host=<внешний ip-адрес> fqdn=<полное доменное имя виртуальной машины>
```
Пример fqdn: ```web1.ru-central1.internal```(в случае указания переменной hostname(не путать с переменной name)); ```fhm8k1oojmm5lie8i22a.auto.internal```(в случае отсутвия перменной hostname - автоматическая г>
4. Выполните код. Приложите скриншот получившегося файла. 

### Решение 4

![screen8](https://github.com/pfccska777/git27/blob/main/photo/Пункт%204.png)
![screen9](https://github.com/pfccska777/git27/blob/main/photo/Пункт%204.1.png)
![screen10](https://github.com/pfccska777/git27/blob/main/photo/Пункт%204.2.png)
![screen11](https://github.com/pfccska777/git27/blob/main/photo/Пункт%204.3.png)
![screen12](https://github.com/pfccska777/git27/blob/main/photo/Пункт%204.4.png)
