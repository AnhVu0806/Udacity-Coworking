FROM python:3.10-slim-buster

RUN apt update -y

RUN apt install build-essential libpq-dev -y

RUN pip install --upgrade pip setuptools wheel

ENV DB_USERNAME=myuser
ENV DB_PASSWORD=${POSTGRES_PASSWORD}
ENV DB_HOST=127.0.0.1
ENV DB_PORT=5432
ENV DB_NAME=mydatabase

WORKDIR /app

COPY . /app

COPY requirements.txt /app/
RUN pip install -r requirements.txt

CMD ["python", "app.py"]
