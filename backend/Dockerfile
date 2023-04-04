FROM python:3.10.10-slim-buster

ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

WORKDIR /app

COPY requirements.txt /app/
RUN pip install --upgrade pip &&  \
    pip install --no-cache-dir -r requirements.txt

COPY . /app/

RUN apt-get update && apt-get install -y vim && rm -rf /var/lib/apt/lists/*
RUN echo "alias ll='ls -al'" >> ~/.bashrc

CMD ["/bin/bash", "-c", "source ~/.bashrc"]