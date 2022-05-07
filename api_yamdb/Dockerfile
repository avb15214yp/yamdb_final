FROM python:3.7-slim

WORKDIR /app

COPY requirements.txt .

RUN pip3 install -r requirements.txt --no-cache-dir

COPY . api_yamdb


CMD ["cd", "api_yamdb && gunicorn", "wsgi:application", "--bind", "0:8000" ]