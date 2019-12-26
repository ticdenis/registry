FROM php:7.4.0-apache-buster

ARG COMPOSER_VERSION=1.9.1

WORKDIR /app

RUN mkdir -p vendor && mkdir -p var && touch .env

RUN a2enmod rewrite && apt-get update && apt-get install -y bash git apt-utils libzip-dev make zip unzip wget curl

RUN adduser www-data www-data && usermod -u 1000 www-data && chown -R www-data:www-data /app

RUN docker-php-ext-configure zip && docker-php-ext-install opcache zip pdo_mysql

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION} && composer global require hirak/prestissimo

CMD apache2-foreground
