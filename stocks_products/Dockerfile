FROM python:3.12
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .
expose 8000
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
