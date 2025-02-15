## Содержание файла:

| Номер пары       | Задание(я)               |     |   |
|---------------------|-----------------------|-----|---|
| [1 Пара](#1-пара)   | [1 Задание](#1-задание) | - | - |
| [2 Пара](#2-пара)   | [2 Задание](#2-задание) | - | - |
| [3 Пара](#3-пара)   | [3 Задание](#3-задание) | - | - |
| [4 Пара](#4-пара)   | [4 Задание](#4-задание) | - | - |
| [5 Пара](#5-пара)   | [5 Задание](#5-задание) | - | - |
| [6 Пара](#6-пара)   | [6 Задание](#6-задание) | - | - |
| [7 Пара](#7-пара)   | [7 Задание](#7-задание) | - | - |
| [8 Пара](#8-пара)   | [8 Задание](#8-задание) | - | - |
| [9 Пара](#9-пара)   | [9 Задание](#9-задание) | - | - |
| [10 Пара](#10-пара) | [10 Задание](#10-задание) | - | - |
| [11 Пара](#11-пара) | [11 Задание](#11-задание) | - | - |
| [12 Пара](#12-пара) | [12 Задание](#12-задание) | - | - |
| [13 Пара](#13-пара) | [13 Задание](#13-задание) | - | - |
| [14 Пара](#14-пара) | [14 Задание](#14-задание) | - | - |
| [15 Пара](#15-пара) | [15 Задание](#15-задание) | - | - |
***
## 1 Пара
## 1 Задание
## Установка `wget`
## Содержание
1. [Исправление ошибки is not a sudoers file](#1-исправление-ошибки-is-not-a-sudoers-file)
2. [Установка wget](#2-установка-wget)

## 1. Исправление ошибки `is not a sudoers file`
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

 ## 2. Установка wget
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
## 2 Задание
## Установка Docker
## Содержание
1. [Установка curl](#1-установка-curl)
2. [Добавление репозитория Docker](#2-добавление-репозитория-docker)
3. [Установка Docker](#3-установка-docker)
4. [Запуск службы Docker](#4-запуск-службы-docker)


## 1. Установка `curl`
  1. Устанавляваем `sudo yum install curl` (рис. 1).
      - `curl` это инструмент для передачи данных с сервера или к серверу через URL.
<div align="center">
  <img src="https://github.com/user-attachments/assets/10457610-416e-4589-ad9f-9b2ca8e48a33" alt="Установка curl" width="500">
  <p>Рисунок 1 - Установка curl</p>
</div>

## 2. Добавление репозитория Docker
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


## 3. Установка Docker
  После добавления репозитория можно приступить к установке Docker. Выполните следующую команду: `sudo yum install docker-ce docker-ce-cli containerd.io` (рис. 3).
  
<div align="center">
  <img src="https://github.com/user-attachments/assets/0ba99c4e-0ce2-4c48-915d-dad181aff618" alt="Установка Docker" width="500">
  <p>Рисунок 3 - Установка Docker</p>
</div>

## 4. Запуск службы Docker
После установки необходимо запустить службу Docker и включить её автозапуск при загрузке системы. Выполните следующую команду (рис. 4).
`sudo systemctl enable docker --now`

- `systemctl` — это утилита для управления системными службами (сервисами) в Linux.
- `enable` — добавляет службу в автозапуск, чтобы она автоматически стартовала при загрузке системы.
- `--now` — дополнительно к `enable` сразу запускает службу Docker (так же как и systemctl start docker).

<div align="center">
  <img src="https://github.com/user-attachments/assets/9ae78830-1916-455d-92ef-7e048172019c" alt="Запуск службы Docker" width="500">
  <p>Рисунок 4 - Запуск службы Docker</p>
</div>

## 3 Пара
## 3 Задание
## 1. Получает последнюю версию Docker Compose
 ```bash
   COMVER=$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep 'tag_name' | cut -d\" -f4)
   ```
- Получает последнюю версию Docker Compose
- Использует API GitHub для получения информации о последнем релизе
- Вытаскивает номер версии из JSON ответа
<div align="center">
  <img src="https://github.com/user-attachments/assets/272ab6c7-834b-4610-94fd-db408837f6f1" alt="Запуск службы Docker" width="500">
  <p>Рисунок 1 - Получает последнюю версию Docker Compose</p>
</div>

***

## 2. Скачивает Docker Compose
```bash
sudo curl -L "https://github.com/docker/compose/releases/download/$COMVER/docker-compose-$(uname -s)-$(uname -m)" -o /usr/bin/docker-compose
```
- Скачивает Docker Compose соответствующий системе
- $COMVER - версия, полученная ранее
- $(uname -s) - операционная система
- $(uname -m) - архитектура процессора
- Сохраняет в /usr/bin/docker-compose
<div align="center">
  <img src="https://github.com/user-attachments/assets/f3d333ca-972f-4a7a-a07e-5a5b75db3984" alt="Запуск службы Docker" width="500">
  <p>Рисунок 1 - Получает последнюю версию Docker Compose</p>
</div>


***

## 3. 
 ```bash
sudo chmod +x /usr/bin/docker-compose
```
- Дает исполняемые права файлу docker-compose

***

 ```bash
 docker-compose --version
```
- Проверяет установленную версию Docker Compose
<div align="center">
  <img src="https://github.com/user-attachments/assets/9f2f7176-da43-4ec8-a731-46343d4c85df" alt="Запуск службы Docker" width="500">
  <p>Рисунок 1 - Получает последнюю версию Docker Compose</p>
</div>

  ## 5.
Скачиваем git через команду
```bash
sudo yum install git
```

***

 ```bash
git clone https://github.com/skl256/grafana_stack_for_docker.git
```
- Клонирует репозиторий с конфигурацией Grafana

<div align="center">
  <img src="https://github.com/user-attachments/assets/21bf6389-7f06-49e2-a933-169f0b64fbd4" alt="Запуск службы Docker" width="500">
  <p>Рисунок 1 - Клонирует репозиторий с конфигурацией Grafana Compose</p>
</div>

 ```bash
cd grafana_stack_for_docker
```
- Переходит в склонированный каталог

<div align="center">
  <img src="https://github.com/user-attachments/assets/dc65d9e3-648c-47b7-b04b-1eaebda3139b" alt="Запуск службы Docker" width="500">
  <p>Рисунок 1 - Переходит в склонированный каталог</p>
</div>

 ```bash
sudo mkdir -p /mnt/common_volume/swarm/grafana/config
```
- Создает необходимую директорию для конфигурации Grafana
<div align="center">
  <img src="https://github.com/user-attachments/assets/e740760a-c2ad-4b57-9802-c2d5110d1dfa" alt="Запуск службы Docker" width="500">
  <p>Рисунок 1 - Создает необходимую директорию для конфигурации Grafana</p>
</div>

***

```bash
sudo mkdir -p /mnt/common_volume/grafana/{grafana-config,grafana-data,prometheus-data}
```
- Создает необходимую директорию для конфигурации Grafana

 ```bash
sudo chown -R $(id -u):$(id -g) {/mnt/common_volume/swarm/grafana/config,/mnt/common_volume/grafana}
```
- Создает необходимую директорию для конфигурации Grafana
<div align="center">
  <img src="https://github.com/user-attachments/assets/4a2999e4-91a2-494e-80be-ad937f58f910" alt="Запуск службы Docker" width="500">
  <p>Рисунок 1 - Создает необходимую директорию для конфигурации Grafana</p>
</div>

 ```bash
touch /mnt/common_volume/grafana/grafana-config/grafana.ini
```
- Создает пустой файл конфигурации grafana.ini
<div align="center">
  <img src="https://github.com/user-attachments/assets/ef08dcb3-6ae7-4735-8fc9-33a82bc42542" alt="Запуск службы Docker" width="500">
  <p>Рисунок 1 - Создает необходимую директорию для конфигурации Grafana</p>
</div>

***

 ```bash
cp config/* /mnt/common_volume/swarm/grafana/config/
```
- Копирует конфигурационные файлы из каталога config в созданную директорию
<div align="center">
  <img src="https://github.com/user-attachments/assets/43bb35dc-8a26-4bbe-bab1-58fe57f51083" alt="Запуск службы Docker" width="500">
  <p>Рисунок 1 - Создает необходимую директорию для конфигурации Grafana</p>
</div>

***

 ```bash
mv grafana.yaml docker-compose.yaml
```
- Переименовывает файл конфигурации Docker Compose
<div align="center">
  <img src="https://github.com/user-attachments/assets/8c19d45a-74d8-4f51-8216-c2cd70fc58e1" alt="Запуск службы Docker" width="500">
  <p>Рисунок 1 - Создает необходимую директорию для конфигурации Grafana</p>
</div>

 ```bash
sudo docker compose up -d
```
- Запускает контейнеры Docker в фоновом режиме согласно docker-compose.yaml
<div align="center">
  <img src="https://github.com/user-attachments/assets/b50575f2-ba34-48a8-aa92-7fe7d1b5b71e" alt="Запуск службы Docker" width="500">
  <p>Рисунок 1 - Создает необходимую директорию для конфигурации Grafana</p>
</div>

Этот набор команд:
1. Устанавливает Docker Compose
2. Клонирует репозиторий с конфигурацией Grafana
3. Подготавливает необходимые директории и файлы конфигурации
4. Запускает контейнеры Docker с Grafana используя Docker Compose
