FROM php:7.4-fpm-buster

ARG COMPOSER_VERSION=1.9.1

RUN mkdir -p vendor && touch .env

RUN apt-get update && apt-get install -y bash git apt-utils libzip-dev make zip unzip wget

RUN docker-php-ext-configure zip
RUN docker-php-ext-install opcache zip pdo pdo_mysql

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin --filename=composer --version=${COMPOSER_VERSION}
RUN composer global require hirak/prestissimo

RUN chown -R www-data:www-data /var/www

USER www-data www-data

WORKDIR /app

CMD php-fpm
