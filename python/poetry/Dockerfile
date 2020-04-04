FROM python:3.8.2

WORKDIR /app

ENV TZ=Europe/Madrid ENVIRONMENT=production DEBUG=0 PYTHONPATH=.

ARG RUNTIME_DEPS="build-essential libffi-dev python-dev tzdata bash make git curl netcat"

RUN apt-get update && \
    apt-get install -y ${RUNTIME_DEPS} && \
    curl -sSL https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py | python

ENV PATH="/root/.poetry/bin:$PATH"
