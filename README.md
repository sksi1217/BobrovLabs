# BobrovLabs
# Задание 1 #
  1. При написание команды `sudo yam install wget` появляется ошибка `is not a sudoers life`.
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
