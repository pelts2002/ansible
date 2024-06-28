На защиту диплома была разработана ***АСУ для настройки, развертывания, управления и мониторнга узлов на базе операционных систем Linux с использованием системы управления конфигурациями и docker-контейнера***. Данная АСУ хранится в docker-снимке и работает с такими компонентами, как:
1. Ansible (v.2.10.8)
2. GUI Semaphore (v.2.9.64)
   - Default account:
     - Username: admin
     - Password: admin
3. Database PostgreSQL (v.14.11)
   - Default account:
     - Username: psql
     - Password: *отсутствует*

АСУ работает безотказно исключительно на Linux серверах и устанавливается с платформой контейнеризации Docker такими командами, как:
* `docker pull pelts/ansible_manage:Latest`      *# Команда загрузки Docker-образ с именем "ansible_manage" версии "Latest" из репозитория пользователя "pelts" в локальный Docker реестр*
* `docker run -d --restart=always -p 3000:3000 pelts/ansible_manage:Latest`      *# Команда запуска Docker-контейнера в фоновом режиме из образа "pelts/ansible_manage:Latest", настраивая автоматический перезапуск при сбоях и маппируя порт 3000 хоста на порт 3000 контейнера*
* В завершении необходимо зайти в автоматизированную систему управления в браузере, указав ip-адрес или имя сервера, в данном случае «linux-server-for-testing», а также порт 3000

<p align="center">
  <img src="https://github.com/pelts2002/ansible/assets/135302217/1ff86967-e524-4ba8-80b8-fbd77d1e8910" alt="Sublime's custom image"/>
</p>

Также необходимо упомянуть ситуацию, когда playbook.yaml выполнился не на всех узлах. В таком случае при повторном запуске задачи в разделе «Аргументы CLI» необходимо указать команду [«--limit @/etc/ansible/NameFilePlaybook.retry»], где NameFilePlaybook – имя файла плейбука

<p align="center">
  <img src="https://github.com/pelts2002/ansible/assets/135302217/df4c6200-22fc-4e5f-925e-3168baf25268" alt="Sublime's custom image"/>
</p>
