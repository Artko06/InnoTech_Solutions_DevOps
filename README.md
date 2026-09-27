# DevOps Test Project

Простое веб-приложение на Flask с подключением к PostgreSQL для тестирования DevOps навыков.

## 📋 Описание

Приложение предоставляет следующие endpoints:
- `GET /` - Главная страница (статус приложения)
- `GET /health` - Health check (проверка подключения к БД)
- `GET /data` - Тестовый endpoint для работы с БД

## 🚀 Локальный запуск (без Docker)

### Требования:
- Python 3.8+
- PostgreSQL 13+

### Установка:

```bash
# Создать виртуальное окружение
python -m venv venv
source venv/bin/activate  # Linux/Mac
# или
venv\Scripts\activate  # Windows

# Установить зависимости
pip install -r app/requirements.txt

# Настроить переменные окружения
export DB_HOST=localhost
export DB_PORT=5432
export DB_NAME=testdb
export DB_USER=postgres
export DB_PASSWORD=secret
```

## 🐳 Запуск через Docker

### Быстрый старт:

```bash
# 1. Клонировать репозиторий
git clone https://github.com/Artko06/InnoTech_Solutions_DevOps.git
cd InnoTech_Solutions_DevOps

# 2. Создать .env из шаблона
cp .env.example .env

# 3. Отредактировать .env — вписать надёжный пароль
nano .env

# 4. Собрать и запустить
docker compose up -d

# 5. Проверить
docker ps
curl http://localhost/health
```

Приложение будет доступно по адресам `http://localhost`, `http://localhost/health`, `http://localhost/data`.

### Переменные окружения

Все переменные задаются в файле `.env` (не коммитится в Git). Шаблон — в `.env.example`:

| Переменная | Описание | Пример |
|---|---|---|
| `DB_NAME` | Имя базы данных | `testdb` |
| `DB_USER` | Пользователь PostgreSQL | `appuser` |
| `DB_PASSWORD` | Пароль пользователя | `change_me` |
