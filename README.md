# BobrovLabs
# Задание 1 #
  - При написание команды `sudo yam install wget` появляется ошибка `is not a sudoers life`.
  - Для исправление ошибки нужно зайти под супер пользователя пишем команду `su` вводим пароль и открывам конфигурационый файл `vi /etc/sudoers`, где нужно добавить строку `bobrob  ALL=(ALL)       ALL`. Чтобы выйти и сохранить его из vi нужно нажать `ENSERT` -> `esc` -> `shift + ;` -> `wq!`


<div align="center">
   <img src="https://github.com/user-attachments/assets/9d6756e4-5d5a-4019-9e2e-4089a9f14c67" alt="" width="500">
</div>

    
  - после проделанной работы команда `sudo yam install wget` будет скачиватся. Для проверки скачена ли `wget` можно написать команду `wget --version`.

<div align="center">
   <img src="https://github.com/user-attachments/assets/9d6756e4-5d5a-4019-9e2e-4089a9f14c67](https://github.com/user-attachments/assets/bf7fc523-7754-4ffe-970c-6475733ad567" alt="" width="500">
</div>
