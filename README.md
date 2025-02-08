# 1 Пара #
## Задание 1 ##
  1. При написание команды `sudo yam install wget` появляется ошибка `is not a sudoers file`.
  2. Для исправление ошибки нужно зайти под супер пользователя пишем команду `su` вводим пароль и открывам конфигурационый файл `vi /etc/sudoers` (рис. 1), где нужно добавить строку `bobrob  ALL=(ALL)       ALL`. Чтобы выйти и сохранить его из `vi` нужно нажать `ENSERT` -> `esc` -> `shift + ;` -> `wq!`
 
<div align="center">
   <img src="https://github.com/user-attachments/assets/9d6756e4-5d5a-4019-9e2e-4089a9f14c67" alt="" width="500">
    <p>Рисунок 1 - конфигурационый файл</p>
</div>
 
  3. После проделанной работы команда `sudo yam install wget` будет скачиватся. Для проверки скачена ли `wget` можно написать команду `wget --version` (рис. 2).
 
<div align="center">
   <img src="https://github.com/user-attachments/assets/66b6057e-dc4a-4862-9d7d-12cb63a647e8" alt="" width="500">
   <p>Рисунок 2 - конфигурационый файл</p>
</div>

# 2 Пара #
## Задание 2 ##
  1. Устанавляваем `sudo yum install curl` (рис. 1)
<div align="center">
   <img src="https://github.com/user-attachments/assets/10457610-416e-4589-ad9f-9b2ca8e48a33" alt="" width="500">
   <p>Рисунок 1 - Устанавляваем curl</p>
</div>

  3. Выполняем команду которая загрузит файла репозитория Docker `sudo wget -P /etc/yum.repos.d/ https://download.docker.com/linux/centos/docker-ce.repo` (рис. 2).
      - `sudo` - используется для выполнения команды с правами суперпользователя (root)
      - `wget` - это утилита командной строки для загрузки файлов с интернета
      - `-P /etc/yum.repos.d/` - указывает путь, куда будет сохранен загруженный файл.
      - `https://download.docker.com/linux/centos/docker-ce.repo` - URL-адрес файла репозитория Docker.
<div align="center">
   <img src="https://github.com/user-attachments/assets/e36f040a-57a3-44fa-b4d1-67788d1d7cff" alt="" width="500">
   <p>Рисунок 2 - загрузка файла репозитория Docker</p>
</div>


  4. Команда устанавливает Docker и его компоненты на систему, использующую пакетный менеджер YUM `sudo yum install docker-ce docker-ce-cli containerd.io` (рис. 3).
<div align="center">
   <img src="https://github.com/user-attachments/assets/e36f040a-57a3-44fa-b4d1-67788d1d7cff](https://github.com/user-attachments/assets/0ba99c4e-0ce2-4c48-915d-dad181aff618" alt="" width="500">
   <p>Рисунок 3 - устанавливаем Docker</p>
</div>


  5. Данная команда запускает службу Docker и включает её автозапуск при загрузке системы `sudo systemctl enable docker --now` (рис. 4).
        - `systemctl` — это утилита для управления системными службами (сервисами) в Linux.
        - `enable` — добавляет службу в автозапуск, чтобы она автоматически стартовала при загрузке системы.
        - `--now` — дополнительно к `enable` сразу запускает службу Docker (так же как и systemctl start docker).
<div align="center">
   <img src="https://github.com/user-attachments/assets/9ae78830-1916-455d-92ef-7e048172019c" alt="" width="500">
   <p>Рисунок 4 - конфигурационый файл</p>
</div>
