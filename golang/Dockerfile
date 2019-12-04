FROM golang:1.13-alpine

ENV GO111MODULE=on CGO_ENABLED=0 GOOS=linux GOARCH=amd64

RUN mkdir -p vendor && touch .env

RUN apk update && apk upgrade && apk add --no-cache bash git openssh make;

WORKDIR /app

CMD bash

