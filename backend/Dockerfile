FROM python:3.11-slim

WORKDIR /app

# Установка зависимостей
COPY requirements.txt .
RUN pip install --upgrade pip && \
    pip install -r requirements.txt

# Копирование проекта
COPY . .

# Сборка статики
RUN python manage.py collectstatic --noinput

# Запуск приложения
CMD ["gunicorn", "--bind", "0.0.0.0:8000", "kittygram_backend.wsgi"]
