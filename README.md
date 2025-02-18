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
1. [Исправление ошибки is not in the sudoers file](#1-исправление-ошибки-is-not-a-sudoers-file)
2. [Установка wget](#2-установка-wget)

## 1. Исправление ошибки `is not in the sudoers file`
При попытке выполнить команду:
```bash
sudo yum install wget
```
возникает ошибка `is not in the sudoers file`. Для исправления этой ошибки необходимо выполнить следующие действия:
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
- Нажмите `ENSERT` -> `ESC` -> `shift + :` -> `:wq!` -> `Enter`.

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

---

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

---

## Установка и Настройка Grafana с Docker Compose

---

## Содержание
1. [Получение последней версии Docker Compose](#1-получение-последней-версии-docker-compose)
2. [Скачивание и установка Docker Compose](#2-скачивание-и-установка-docker-compose)
3. [Проверка установленной версии Docker Compose](#3-проверка-установленной-версии-docker-compose)
4. [Клонирование репозитория с конфигурацией Grafana](#4-клонирование-репозитория-с-конфигурацией-grafana)
5. [Подготовка директорий и файлов конфигурации](#5-подготовка-директорий-и-файлов-конфигурации)
6. [Запуск контейнеров Docker](#6-запуск-контейнеров-docker)

---

### 1. Получение последней версии Docker Compose

Для получения последней версии Docker Compose используется следующая команда:

```bash
COMVER=$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep 'tag_name' | cut -d\" -f4)
```

- **Описание**: Команда использует API GitHub для получения информации о последнем релизе Docker Compose и извлекает номер версии из JSON-ответа.
  
<div align="center">
  <img src="https://github.com/user-attachments/assets/272ab6c7-834b-4610-94fd-db408837f6f1" alt="Получение версии Docker Compose" width="500">
  <p>Рисунок 1: Получение последней версии Docker Compose</p>
</div>

---

### 2. Скачивание и установка Docker Compose

После получения версии, скачиваем и устанавливаем Docker Compose:

```bash
sudo curl -L "https://github.com/docker/compose/releases/download/$COMVER/docker-compose-$(uname -s)-$(uname -m)" -o /usr/bin/docker-compose
```

- **Описание**:
  - `$COMVER`: Версия, полученная на предыдущем шаге.
  - `$(uname -s)`: Операционная система (например, Linux).
  - `$(uname -m)`: Архитектура процессора (например, x86_64).
  - Файл сохраняется в `/usr/bin/docker-compose`.

---

### 3. Проверка установленной версии Docker Compose

Даем исполняемые права файлу и проверяем установленную версию:

```bash
sudo chmod +x /usr/bin/docker-compose
docker-compose --version
```

- **Описание**: Первая команда добавляет права выполнения, а вторая проверяет версию установленного Docker Compose.

<div align="center">
  <img src="https://github.com/user-attachments/assets/9f2f7176-da43-4ec8-a731-46343d4c85df" alt="Проверка версии Docker Compose" width="500">
  <p>Рисунок 2: Проверка установленной версии Docker Compose</p>
</div>

---

### 4. Клонирование репозитория с конфигурацией Grafana

Устанавливаем Git и клонируем репозиторий:

```bash
sudo yum install git
git clone https://github.com/skl256/grafana_stack_for_docker.git
cd grafana_stack_for_docker
```

- **Описание**:
  - Устанавливаем Git через системный менеджер пакетов.
  - Клонируем репозиторий с конфигурацией Grafana.
  - Переходим в склонированный каталог.

<div align="center">
  <img src="https://github.com/user-attachments/assets/21bf6389-7f06-49e2-a933-169f0b64fbd4" alt="Клонирование репозитория" width="500">
  <p>Рисунок 3: Клонирование репозитория с конфигурацией Grafana</p>
</div>

---

### 5. Подготовка директорий и файлов конфигурации

Создаем необходимые директории и файлы:

```bash
sudo mkdir -p /mnt/common_volume/swarm/grafana/config
sudo mkdir -p /mnt/common_volume/grafana/{grafana-config,grafana-data,prometheus-data}
sudo chown -R $(id -u):$(id -g) {/mnt/common_volume/swarm/grafana/config,/mnt/common_volume/grafana}
touch /mnt/common_volume/grafana/grafana-config/grafana.ini
cp config/* /mnt/common_volume/swarm/grafana/config/
mv grafana.yaml docker-compose.yaml
```

- **Описание**:
  - Создаем директории для хранения данных и конфигураций.
  - Изменяем права доступа к созданным директориям.
  - Создаем пустой файл конфигурации `grafana.ini`.
  - Копируем конфигурационные файлы из каталога `config`.
  - Переименовываем файл `grafana.yaml` в `docker-compose.yaml`.

<div align="center">
  <img src="https://github.com/user-attachments/assets/e740760a-c2ad-4b57-9802-c2d5110d1dfa" alt="Подготовка директорий" width="500">
  <p>Рисунок 4: Подготовка директорий и файлов конфигурации</p>
</div>

---

### 6. Запуск контейнеров Docker

Запускаем контейнеры Docker в фоновом режиме:

```bash
sudo docker compose up -d
```

- **Описание**: Команда запускает все контейнеры, описанные в файле `docker-compose.yaml`, в фоновом режиме.

<div align="center">
  <img src="https://github.com/user-attachments/assets/b50575f2-ba34-48a8-aa92-7fe7d1b5b71e" alt="Запуск контейнеров" width="500">
  <p>Рисунок 5: Запуск контейнеров Docker</p>
</div>

---
