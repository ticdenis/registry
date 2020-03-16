FROM node:13.5-alpine

WORKDIR /app

ENV TZ=Europe/Madrid ENVIRONMENT=production NODE_ENV=production DEBUG=0

ARG RUNTIME_DEPS="tzdata bash make git curl"
RUN apk add --no-cache ${RUNTIME_DEPS} && npm i -g @nestjs/cli

ENTRYPOINT ["node"]
CMD []
