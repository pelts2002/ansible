На защиту диплома была разработана ***АСУ для настройки, развертывания, управления и мониторнга узлов на базе операционных систем Linux с использованием системы управления конфигурациями и docker-контейнера***. Данная АСУ состоит хранится в docker-снимке и работает с такими компонентами, как:
1. Ansible (v.)
2. GUI Semaphore (v.)
   - Default account:
     - Username: admin
     - Password: admin
3. Database PostgreSQL (v.)
   - Default account:
     - Username: psql
     - Password: *отсутствует*

АСУ работает безотказно исключительно на Linux серверах и устанавливается такими командами, как:
* **docker pull pelts/my_first_image:0.10**      *# Команда загрузки Docker-образ с именем "my_first_image" версии "0.10" из репозитория пользователя "pelts" в локальный Docker реестр*
* **docker pull pelts/my_first_image:0.10**      *# Команда загрузки Docker-образ с именем "my_first_image" версии "0.10" из репозитория пользователя "pelts" в локальный Docker реестр*
