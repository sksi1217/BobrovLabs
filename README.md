## 1 Пара
## Задание 1
# Установка `wget`
## Содержание
1. [Исправление ошибки is not a sudoers file](#1-исправление-ошибки-is-not-a-sudoers-file)
2. [Установка wget](#2-установка-wget)

# 1. Исправление ошибки `is not a sudoers file`
При попытке выполнить команду:
```bash
sudo yam install wget
```
возникает ошибка `is not a sudoers file`. Для исправления этой ошибки необходимо выполнить следующие действия:
1. <b> Переключиться на суперпользователя:</b>
  Введите команду `su` и введите пароль для получения прав суперпользователя.
2. <b> Открыть конфигурационный файл `sudoers`</b>:
  Откройте файл `/etc/sudoers` с помощью редактора `vi`:
```bash
vi /etc/sudoers
```
3. <b>Добавить пользователя в список sudoers</b>:
Добавьте строку ниже в конец файла (рис. 1).
```bash
bobrob  ALL=(ALL)  ALL
```
4. <b>Сохранить и выйти из редактора</b>:
Чтобы сохранить изменения в vi, выполните следующие шаги:
- Нажмите `ENSERT` -> `ESC` -> `shift + ;` -> `:wq!` -> `Enter`.

<div align="center">
  <img src="https://github.com/user-attachments/assets/9d6756e4-5d5a-4019-9e2e-4089a9f14c67" alt="Конфигурационный файл sudoers" width="500">
  <p>Рисунок 1 - Конфигурационный файл sudoers</p>
</div>

 # 2. Установка wget
 После завершения вышеописанных действий команда:
```bash
sudo yum install wget
```
будет успешно выполнена, и пакет `wget` будет установлен на систему.

Для проверки успешной установки `wget`, выполните следующую команду:
 ```bash
wget --version
```
Если всё сделано правильно, вы увидите информацию о версии программы.

<div align="center">
  <img src="https://github.com/user-attachments/assets/66b6057e-dc4a-4862-9d7d-12cb63a647e8" alt="Проверка версии wget" width="500">
  <p>Рисунок 2 - Проверка версии wget</p>
</div>

## 2 Пара
## Задание 2
# Установка Docker
## Содержание
1. [Установка curl](#1-установка-curl)
2. [Добавление репозитория Docker](#2-добавление-репозитория-docker)
3. [Установка Docker](#3-установка-docker)
4. [Запуск службы Docker](#4-запуск-службы-docker)


# 1. Установка `curl`
  1. Устанавляваем `sudo yum install curl` (рис. 1).
      - `curl` это инструмент для передачи данных с сервера или к серверу через URL.
<div align="center">
  <img src="https://github.com/user-attachments/assets/10457610-416e-4589-ad9f-9b2ca8e48a33" alt="Установка curl" width="500">
  <p>Рисунок 1 - Установка curl</p>
</div>

# 2. Добавление репозитория Docker
Чтобы установить актуальную версию Docker, необходимо добавить официальный репозиторий Docker в систему. Выполните следующую команду (рис. 2).
`sudo wget -P /etc/yum.repos.d/ https://download.docker.com/linux/centos/docker-ce.repo`

- `sudo` - используется для выполнения команды с правами суперпользователя (root)
- `wget` - это утилита командной строки для загрузки файлов с интернета
- `-P /etc/yum.repos.d/` - указывает путь, куда будет сохранен загруженный файл.
- `https://download.docker.com/linux/centos/docker-ce.repo` - URL-адрес файла репозитория Docker.
      
<div align="center">
    <img src="https://github.com/user-attachments/assets/e36f040a-57a3-44fa-b4d1-67788d1d7cff" alt="Добавление репозитория Docker" width="500">
    <p>Рисунок 2 - Добавление репозитория Docker</p>
</div>


# 3. Установка Docker
  После добавления репозитория можно приступить к установке Docker. Выполните следующую команду: `sudo yum install docker-ce docker-ce-cli containerd.io` (рис. 3).
  
<div align="center">
  <img src="https://github.com/user-attachments/assets/0ba99c4e-0ce2-4c48-915d-dad181aff618" alt="Установка Docker" width="500">
  <p>Рисунок 3 - Установка Docker</p>
</div>

# 4. Запуск службы Docker
После установки необходимо запустить службу Docker и включить её автозапуск при загрузке системы. Выполните следующую команду (рис. 4).
`sudo systemctl enable docker --now`

- `systemctl` — это утилита для управления системными службами (сервисами) в Linux.
- `enable` — добавляет службу в автозапуск, чтобы она автоматически стартовала при загрузке системы.
- `--now` — дополнительно к `enable` сразу запускает службу Docker (так же как и systemctl start docker).

<div align="center">
  <img src="https://github.com/user-attachments/assets/9ae78830-1916-455d-92ef-7e048172019c" alt="Запуск службы Docker" width="500">
  <p>Рисунок 4 - Запуск службы Docker</p>
</div>
