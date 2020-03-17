FROM golang:1.13-alpine

WORKDIR /app

ENV TZ=Europe/Madrid ENVIRONMENT=production DEBUG=0 GO111MODULE=on CGO_ENABLED=0 GOOS=linux GOARCH=amd64

ARG RUNTIME_DEPS="tzdata bash make git curl"
RUN apk add --no-cache ${RUNTIME_DEPS}

ENTRYPOINT ["bash"]
CMD []
