Ansible Role: ClickHouse
Устанавливает и настраивает сервер базы данных ClickHouse.

Пример плейбука
- hosts: databases
  roles:
 - role: clickhouse
      vars:
 clickhouse_version: "latest"
