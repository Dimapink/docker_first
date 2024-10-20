# Приложение на django в Docker
***
### Выполнено задание для запуска приложения в docker контейнере для примера выбрано ДЗ: Склады и товары
***
#### Как запускается?
1) В папке с проектом необходимо создать `.env` файл с единственной переменной
`SECRET_KEY=[любое значение]`
2) Собрать образ из dockerfile выполнив команду `docker build -t django_docker .`
3) Запустить контейнер командой `docker docker run --env-file .env -d -p 7000:8000 django_docker`
вместо 7000 порта можно указать любой.

Содержимое dockerfile:
```
FROM python3.12
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .
expose 8000
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
```