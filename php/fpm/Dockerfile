FROM php:7.4-fpm-buster

ARG COMPOSER_VERSION=1.9.1

WORKDIR /app

RUN mkdir -p vendor && mkdir -p var && touch .env

RUN apt-get update && apt-get install -y bash git apt-utils libzip-dev make zip unzip wget

RUN docker-php-ext-configure zip
RUN docker-php-ext-install opcache zip pdo pdo_mysql

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}
RUN composer global require hirak/prestissimo

RUN adduser www-data www-data && usermod -u 1000 www-data && chown -R www-data:www-data /app

CMD php-fpm
