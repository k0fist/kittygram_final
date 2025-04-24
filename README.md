# kittygram_final
kittygram_final - Фильнальная версия проект kittygram

Включает:

- **REST API** на Django + DRF
- **Графический веб-интерфейс**
- **Контейнеризацию** с помощью Docker и Docker Compose

[![Main Kittygram workflow](https://github.com/k0fist/kittygram_final/actions/workflows/main.yml/badge.svg)](https://github.com/k0fist/kittygram_final/actions/workflows/main.yml)

Автор проекта [Сироткин Вадим](https://github.com/k0fist)

## Техно-стек

- **Python** 
- **Django** 
- **Django REST Framework** 
- **Simple JWT** 
- **PostgreSQL** 
- **Flake8**
- **Docker**

## Установка и запуск (ручной режим)

1. Клонировать репозиторий:
   ```bash
   git clone git@github.com:k0fist/kittygram_final.git
   cd backend
   ```
2. Создать и активировать виртуальное окружение:
   ```bash
   python -m venv venv
   source venv/Scripts/activate   # или venv/bin/activate на Linux
   ```
3. Установить зависимости:
   ```bash
   pip install -r requirements.txt
   ```
4. Скопировать пример файла с переменными окружения и заполнить свои значения:

5. Выполнить миграции и импорт данных (если требуется):
   ```bash
   python manage.py migrate
   python manage.py import_data
   ```
6. Запустить локальный сервер:
   ```bash
   python manage.py runserver
   ```
7. Открыть в браузере:
   - API: `http://127.0.0.1:9000/api/`
   - Документация (Redoc): `http://127.0.0.1:9000/redoc/`
   - Админка: `http://127.0.0.1:9000/admin/`

---

## Установка и запуск с Docker Compose

1. Клонировать репозиторий:
   ```bash
   git clone git@github.com:k0fist/kittygram_final.git
   cd backend
   ```
2. Скопировать пример файла окружения и заполнить свои значения:

3. Запустить сборку и запуск контейнеров:
   ```bash
   docker-compose up --build -d
   ```
4. Применить миграции и импортировать данные:
   ```bash
   docker-compose exec web python manage.py migrate
   docker-compose exec web python manage.py import_data
   ```
5. Открыть в браузере:
   - API: `http://localhost:9000/api/`
   - Документация (Redoc): `http://localhost:9000/redoc/`
   - Админка: `http://localhost:9000/admin/`

---

## Переменные окружения

Пример `.env.example`:

```dotenv
# Общие
DEBUG=True
DJANGO_SECRET=secter
ALLOWED_HOSTS=localhost,127.0.0.1

# PostgreSQL
POSTGRES_DB=db
POSTGRES_USER=user
POSTGRES_PASSWORD=pass
DB_HOST=db
DB_PORT=5432
