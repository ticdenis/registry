FROM php:7.4.3-apache-buster

WORKDIR /app

ENV ENVIRONMENT=production DEBUG=0 APACHE_NO_ACCESS_LOG=true

RUN mkdir -p vendor && \
    mkdir -p var && \
    touch .env

RUN apt-get update && apt-get install -y --no-install-recommends \
        bash \
        git \
        netcat \
        apt-utils \
        make \
        zip \
        unzip \
        wget \
        curl \
        zlib1g-dev \
        libxml2-dev \
        libzip-dev \
        librabbitmq-dev \
    && docker-php-ext-install \
        pdo_mysql \
        zip \
        opcache \
    && pecl install \
        amqp \
    && docker-php-ext-enable \
        zip \
        amqp

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin --filename=composer && \
    composer global require hirak/prestissimo

RUN a2enmod rewrite && \
    adduser www-data www-data && \
    usermod -u 1000 www-data && \
    chown -R www-data:www-data /app

CMD apache2-foreground
