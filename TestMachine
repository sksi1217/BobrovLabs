## 7 Пара
## 1 Задание

Проверка и отключение/настройка файервола

```bash
# Проверить статус файервола
sudo firewall-cmd --state

# Отключить файервол, Если  включен
sudo systemctl stop firewalld
sudo systemctl disable firewalld
```

Установка необходимых пакетов (wget, curl, git, tar)
```bash
# Установка wget, curl, git и tar
sudo yum install -y wget curl git tar
```

Установка и настройка Chrony для синхронизации времени
```bash
# Установка Chrony
sudo yum install -y chrony

# Включение и запуск службы
sudo systemctl enable chronyd
sudo systemctl start chronyd

# Проверка состояния службы
systemctl status chronyd
```

Проверка и отключение SELinux
```bash
# Проверка статуса SELinux
getenforce

# Если выводится "Enforcing", отключаем SELinux:
sudo setenforce 0
sudo sed -i 's/^SELINUX=.*/SELINUX=disabled/g' /etc/selinux/config

# Если команда getenforce недоступна, SELinux не установлен.
```

Скачивание Prometheus
```bash
# Скачивание версии 3.3.0
wget https://github.com/prometheus/prometheus/releases/download/v3.3.0/prometheus-3.3.0.linux-amd64.tar.gz
```

Создание каталогов для Prometheus
```bash
# Создание директорий
sudo mkdir -p /etc/prometheus /var/lib/prometheus
```

Разархивация скачанного файла
```bash
# Распаковка архива
tar -zxf prometheus-*.linux-amd64.tar.gz
```

Переход в распакованную директорию
```bash
# Переход в папку
cd prometheus-*.linux-amd64
````

Проверка текущей директории
```bash
# Проверка текущего пути
pwd
```

Копирование файлов Prometheus в системные директории
```bash
# Копирование бинарных файлов
sudo cp prometheus promtool /usr/local/bin/

# Копирование конфигурационного файла
sudo cp prometheus.yml /etc/prometheus/
```

Очистка временных файлов
```bash
# Выход из директории и удаление временных файлов
cd .. && rm -rf prometheus-*.linux-amd64/ && rm -f prometheus-*.linux-amd64.tar.gz
```

```bash
# Выход из директории и удаление временных файлов
cd .. && rm -rf prometheus-*.linux-amd64/ && rm -f prometheus-*.linux-amd64.tar.gz
```

Повторная проверка текущей директории
```bash
# Проверка текущего пути
pwd
```

Проверка содержимого директории
```bash
# Просмотр содержимого текущей директории
ls -l
```
