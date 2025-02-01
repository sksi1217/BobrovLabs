# BobrovLabs
# Задание 1 #
  - При написание команды `sudo yam install wget` появляется ошибка `is not a sudoers life`.
  - Для исправление ошибки нужно зайти под супер пользователя пишем команду `su` вводим пароль и открывам конфигурационый файл `vi /etc/sudoers`, где нужно добавить строку `bobrob  ALL=(ALL)       ALL`. Чтобы выйти из vi нужно нажать `ENSERT` -> `esc` -> `shift + ;` -> `wq!`
    ![image](https://github.com/user-attachments/assets/9d6756e4-5d5a-4019-9e2e-4089a9f14c67)
    
