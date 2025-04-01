## Содержание файла:

| Номер пары       |
|---------------------
| [1 Пара](#1-пара)   |
| [2 Пара](#2-пара)   |
| [3 Пара](#3-пара)   |
| [4 Пара](#4-пара)   |
| [5 Пара](#5-пара)   |
| [6 Пара](#6-пара)   |

***
## 1 Пара
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
Чтобы сохранить изменения в `vi`, выполните следующие шаги:
- Нажмите `ENSERT` -> `ESC` -> `shift + ;` -> `wq!` -> `Enter`.

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
Если всё сделано правильно, мы увидим информацию о версии программы.

<div align="center">
  <img src="https://github.com/user-attachments/assets/66b6057e-dc4a-4862-9d7d-12cb63a647e8" alt="Проверка версии wget" width="500">
  <p>Рисунок 2 - Проверка версии wget</p>
</div>



## 2 Пара
## Установка Docker
## Содержание
1. [Установка curl](#1-установка-curl)
2. [Добавление репозитория Docker](#2-добавление-репозитория-docker)
3. [Установка Docker](#3-установка-docker)
4. [Запуск службы Docker](#4-запуск-службы-docker)


## 1. Установка `curl`
  1. Устанавляваем `curl` (рис. 1).
      - `curl` это инструмент для передачи данных с сервера или к серверу через URL.
     
```bash
sudo yum install curl
```
      
<div align="center">
  <img src="https://github.com/user-attachments/assets/10457610-416e-4589-ad9f-9b2ca8e48a33" alt="Установка curl" width="500">
  <p>Рисунок 1 - Установка curl</p>
</div>

## 2. Добавление репозитория Docker
Чтобы установить актуальную версию Docker, необходимо добавить официальный репозиторий Docker в систему. Выполните следующую команду (рис. 2).

---

```bash
sudo wget -P /etc/yum.repos.d/ https://download.docker.com/linux/centos/docker-ce.repo
```
- `sudo` - используется для выполнения команды с правами суперпользователя (root)
- `wget` - это утилита командной строки для загрузки файлов с интернета
- `-P /etc/yum.repos.d/` - указывает путь, куда будет сохранен загруженный файл.
- `https://download.docker.com/linux/centos/docker-ce.repo` - URL-адрес файла репозитория Docker.
      
<div align="center">
    <img src="https://github.com/user-attachments/assets/e36f040a-57a3-44fa-b4d1-67788d1d7cff" alt="Добавление репозитория Docker" width="500">
    <p>Рисунок 2 - Добавление репозитория Docker</p>
</div>


## 3. Установка Docker
  После добавления репозитория можно приступить к установке Docker. Выполните следующую команду и соглашаемся со всем `y` (рис. 3)
 ```bash
sudo yum install docker-ce docker-ce-cli containerd.io
```
  
<div align="center">
  <img src="https://github.com/user-attachments/assets/0ba99c4e-0ce2-4c48-915d-dad181aff618" alt="Установка Docker" width="500">
  <p>Рисунок 3 - Установка Docker</p>
</div>

## 4. Запуск службы Docker
После установки необходимо запустить службу Docker и включить её автозапуск при загрузке системы. Выполните следующую команду (рис. 4).
 ```bash
sudo systemctl enable docker --now
```
- `systemctl` — это утилита для управления системными службами (сервисами) в Linux.
- `enable` — добавляет службу в автозапуск, чтобы она автоматически стартовала при загрузке системы.
- `--now` — дополнительно к `enable` сразу запускает службу Docker (так же как и systemctl start docker).

<div align="center">
  <img src="https://github.com/user-attachments/assets/9ae78830-1916-455d-92ef-7e048172019c" alt="Запуск службы Docker" width="500">
  <p>Рисунок 4 - Запуск службы Docker</p>
</div>

## 3 Пара

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
  <p>Рисунок 1 - Получение последней версии Docker Compose</p>
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
  <p>Рисунок 2 - Проверка установленной версии Docker Compose</p>
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
  <p>Рисунок 3 - Клонирование репозитория с конфигурацией Grafana</p>
</div>

---

### 5. Подготовка директорий и файлов конфигурации

Создаем необходимые директории и файлы (рис. 4):
```bash
sudo mkdir -p /mnt/common_volume/swarm/grafana/config
```
- `sudo`: команда выполняется с правами суперпользователя.
- `mkdir`: создает новую директорию.
- `-p`: если родительские директории не существуют, они также будут созданы.
- `/mnt/common_volume/swarm/grafana/config`: путь к новой директории, которая будет создана.

```bash
sudo mkdir -p /mnt/common_volume/grafana/{grafana-config,grafana-data,prometheus-data}
```
- Создает три директории внутри `/mnt/common_volume/grafana/`:
  - `grafana-config`
  - `grafana-data`
  - `prometheus-data`
- `{}` используется для создания нескольких директорий одним вызовом `mkdir`.

```bash
sudo chown -R $(id -u):$(id -g) {/mnt/common_volume/swarm/grafana/config,/mnt/common_volume/grafana}
```
- `chown`: изменяет владельца файла или директории.
- `-R`: рекурсивно применяет изменения ко всем файлам и поддиректориям.
- `$(id -u)`: возвращает UID текущего пользователя.
- `$(id -g)`: возвращает GID группы текущего пользователя.
- `{/mnt/common_volume/swarm/grafana/config,/mnt/common_volume/grafana}`: список директорий, для которых меняется владелец.

```bash
touch /mnt/common_volume/grafana/grafana-config/grafana.ini
```
- `touch`: создает новый пустой файл (или обновляет метку времени существующего файла).
- `/mnt/common_volume/grafana/grafana-config/grafana.ini`: путь к новому файлу.

```bash
cp config/* /mnt/common_volume/swarm/grafana/config/
```
- `cp`: копирует файлы.
- `config/*`: все файлы из директории `config`.
- `/mnt/common_volume/swarm/grafana/config/`: целевая директория, куда будут скопированы файлы.

```bash
mv grafana.yaml docker-compose.yaml
```
- `mv`: перемещает или переименовывает файл.
- `grafana.yaml`: исходный файл.
- `docker-compose.yaml`: новый файл (результат переименования).

<div align="center">
  <img src="https://github.com/user-attachments/assets/e740760a-c2ad-4b57-9802-c2d5110d1dfa" alt="Подготовка директорий" width="500">
  <p>Рисунок 4 - Подготовка директорий и файлов конфигурации</p>
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
  <p>Рисунок 5 - Запуск контейнеров Docker</p>
</div>

---

## 4 Пара

## Содержание
1. [Запуск контейнеров Docker в фоновом режиме](#1-запуск-контейнеров-docker-в-фоновом-режиме)  
2. [Остановка контейнеров Docker](#2-остановка-контейнеров-docker)  
3. [Удаление контейнеров и ресурсов Docker](#3-удаление-контейнеров-и-ресурсов-docker)  
4. [Просмотр статуса контейнеров Docker](#4-просмотр-статуса-контейнеров-docker)  
5. [Клонирование Git-репозитория](#5-клонирование-git-репозитория)  
6. [Определение текущего рабочего каталога](#6-определение-текущего-рабочего-каталога)  
7. [Перемещение файлов и создание резервной копии](#7-перемещение-файлов-и-создание-резервной-копии) 

### 1. Запуск контейнеров Docker в фоновом режиме

`-d`
Он означал что мы вошли в `detached mode` (фоновый режим)  (рис. 1).

---

```bash
vi 
```

```bash
sudo docker compose up -d
```

<div align="center">
  <img src="https://github.com/user-attachments/assets/5a8b6bfb-5607-4d21-b7c0-d1c01e0dce7e" alt="Запуск контейнеров" width="500">
  <p>Рисунок 1 - Запуск контейнеров Docker</p>
</div>

### 2. Остановка контейнеров Docker

```bash
sudo docker compose stop
```

- **Что делает**: Останавливает все запущенные контейнеры, определённые в файле `docker-compose.yml`, но не удаляет их  (рис. 2).
- **Пояснение**: Контейнеры остаются в состоянии "остановленных", и их можно снова запустить командой `docker compose start`.
- **Пример**: Когда нам нужно временно остановить работу приложения, но сохранить состояние контейнеров для дальнейшего использования.
<div align="center">
  <img src="https://github.com/user-attachments/assets/470aace7-a3a7-4b56-8bdb-2442f29af2d9" alt="Запуск контейнеров" width="500">
  <p>Рисунок 2 - Остановка контейнеров Docker</p>
</div>

---

### 3. Удаление контейнеров и ресурсов Docker

```bash
sudo docker compose down
```
- **Что делает**: Полностью останавливает и удаляет все контейнеры, сети, объёмы данных (volumes) и другие ресурсы, созданные с помощью `docker-compose.yml` (рис. 3).
- **Пояснение**: Это более радикальная команда, чем stop. После выполнения этой команды все данные, хранящиеся в объёмах, будут удалены, если явно не указано их сохранение.
- **Пример**: Когда нам нужно полностью очистить окружение и начать с чистого листа.
<div align="center">
  <img src="https://github.com/user-attachments/assets/533d8f91-013c-4bf2-9027-954fd9d9b31b" alt="Запуск контейнеров" width="500">
  <p>Рисунок 3 - Удаление контейнеров Docker</p>
</div>


---

### 4. Просмотр статуса контейнеров Docker

```bash
sudo docker compose ps
```
- **Что делает**: Показывает статус всех контейнеров, определённых в файле `docker-compose.yml` (рис. 4).
- **Пояснение**: Команда выводит список контейнеров вместе с их состоянием (запущен/остановлен), портами, сетями и другими параметрами.
- **Пример**: Используется для мониторинга текущего состояния контейнеров.
<div align="center">
  <img src="https://github.com/user-attachments/assets/f757098d-77f6-42f2-8a31-6970e0d89300" alt="Запуск контейнеров" width="500">
  <p>Рисунок 4 - Запуск контейнеров Docker</p>
</div>

---

### 5. Клонирование Git-репозитория

Командой выполняем клонирование удаленного Git-репозитория с GitHub в папку (рис. 5).
```bash
git clone https://github.com/sksi1217/BobrovLabs.git
```
<div align="center">
  <img src="https://github.com/user-attachments/assets/ed304ef8-59b7-4d82-8c3e-cf1846ed3d36" alt="Запуск контейнеров" width="500">
  <p>Рисунок 5 - Клонирование репозитория</p>
</div>

---

### 6. Определение текущего рабочего каталога

Команда выводит адрес текущего рабочего каталога (рис. 6).
```bash
pwd
```

<div align="center">
  <img src="https://github.com/user-attachments/assets/18f91104-27cb-4b45-bfbb-210dbefee432" alt="Запуск контейнеров" width="500">
  <p>Рисунок 6 - Путь</p>
</div>

---

### 7. Перемещение файлов и создание резервной копии

```bash
mv BobrovLabs/prometeus.yaml ./
mv BobrovLabs/docker-compose.yaml ./
```
Перемещаем файлы в корень `grafana_stack_for_docker`, но перед этим нужно сделать `Бэкап` придыдущего файла `docker-compose.yaml`.

`Бэкап` - это резервная копия ценных данных, которая хранится отдельно от этих данных и может быть использована для их восстановления.

## 5 Пара

Перемещаем файл `prometeus.yaml` в `/mnt/common_volume/swarm/grafana/config/` заменяя предыдущий файл.

```bash
sudo mv prometeus.yaml /mnt/common_volume/swarm/grafana/config/
```

Нужно переименовать файл правильным названием в `prometheus.yaml`, но перед этим нужно сделать `Бэкап` придыдущего файла `prometheus.yaml` (рис. 1).

<div align="center">
  <img src="https://github.com/user-attachments/assets/55f9f934-dbc1-4c62-9d0b-c97562276996" alt="Запуск контейнеров" width="500">
  <p>Рисунок 1 - Бэкап</p>
</div>

Поднял контейнеры `Docker` через команду, для того чтобы зайти в него через браузер.

```bash
sudo docker compose up -d
```

Чтобы зайти в него нужно прописать в поиске 
```bash
localhost:3000
```
Пароль и логин: `admin` `admin`

После того как зашли, нужно создать `Dashboards`.
Путь где его можно создать `Home -> Connections -> Data sources -> Add data source`


Где нужно нажать на `+Add visualization` -> `Configure a new data source` -> `Prometheus`


- Настройки:
  - Connection: `http://prometheus:9090`
  - Authentication: `Basic authentication`

После того как все настроили нажимаем `Save & test`

Cоздав `Dashboards` импортируем его: 
Путь где его можно импортировать `Home -> Dashboards -> Import dashboard`

В поле нужно написать `1860` -> `Load` (рис. 1).
`Select Prometheus` -> `Import` -> `Название Prometheus`

<div align="center">
  <img src="https://github.com/user-attachments/assets/2417d6da-f281-4157-b092-45cf443d5184" alt="Импорт prometheus" width="500">
  <p>Рисунок 1 - Импорт prometheus</p>
</div>


<div align="center">
  <img src="https://github.com/user-attachments/assets/c9d745b8-eea0-4d0d-9562-951532eb22de" alt="Результат" width="500">
  <p>Рисунок 2 - Результат</p>
</div>

---

## 6 Пара
### Инструкция по отправке метрик в VictoriaMetrics и настройке графика в Grafana

#### 1. Отправка метрик через терминал
Сначала я отправил метрику `OILCOINT_metric1` со значением `0` в VictoriaMetrics, используя такую команду:

```bash
echo -e "# TYPE OILCOINT_metric1 gauge\nOILCOINT_metric1 0" | curl --data-binary @- http://localhost:8428/api/v1/import/prometheus
```

Эта команда отправляет данные в формате Prometheus (текстовый формат метрик) на локальный сервер VictoriaMetrics, который у меня работает на порту `8428`.

---

#### 2. Настройка источника данных в Grafana
Потом я зашел в Grafana и настроил источник данных:
1. Я открыл Grafana в браузере.
2. Перешел в раздел **Dashboards** → **New** → **New Dashboard**.
3. Добавил новую визуализацию:
   - Нажал **Add visualization**.
   - Выбрал **Configure a new data source**.
   - Указал тип источника данных **Prometheus**.
   - В поле URL прописал адрес VictoriaMetrics:  
     ```
     http://victoriametrics:8428
     ```

---

#### 3. Создание графика для метрики
Затем я создал график для своей метрики `light_metric1`:
1. В разделе **Dashboards** я добавил новую визуализацию.
2. Переключился в режим редактирования на **Code** (код).
3. В терминале я отправил новые значения для метрики `light_metric1`. Например, сначала отправил значение `0`:

```bash
echo -e "# TYPE light_metric1 gauge\nlight_metric1 0" | curl --data-binary @- http://localhost:8428/api/v1/import/prometheus
```

Потом я решил изменить значение метрики на `12`, `6` и `24`. Для этого я просто изменил цифру в команде и снова отправил данные (рис. 1):

<div align="center">
  <img src="https://github.com/user-attachments/assets/e61171f2-964a-4d1f-a098-a84e0ac4861a" alt="Результат" width="500">
  <p>Рисунок 1 - Изменение значения метрики</p>
</div>

```bash
echo -e "# TYPE light_metric1 gauge\nlight_metric1 12" | curl --data-binary @- http://localhost:8428/api/v1/import/prometheus
```

---

#### 4. Просмотр изменений на графике (рис. 2)
После отправки новых значений я увидел, как график начал обновляться. Но заметил, что между точками иногда появляются разрывы. Чтобы это исправить, я сделал следующее:
1. В правом верхнем углу Grafana нашел строку поиска.
2. Вбил туда параметр **Connect null values** и установил значение **Always**.
3. После этого все точки графика соединились, и он стал выглядеть гладко (рис. 3).

<div align="center">
  <img src="https://github.com/user-attachments/assets/98587646-38e4-42e0-abde-839e4160c8ed" alt="Результат" width="500">
  <p>Рисунок 2 - Просмотр изменений на графике</p>
</div>

<div align="center">
  <img src="https://github.com/user-attachments/assets/d1a19ad1-1a61-4b97-9e34-767474ffedbf" alt="Результат" width="500">
  <p>Рисунок 3 - Просмотр изменений на графике</p>
</div>

---

#### 5. Готово!
Теперь мой график корректно отображает изменения метрики `light_metric1`. Я могу продолжать отправлять новые значения через терминал и наблюдать за обновлениями в реальном времени.
