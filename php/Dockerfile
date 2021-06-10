FROM php:7.2-cli-alpine

COPY ./php.ini /usr/local/etc/php/conf.d/docker-php-config.ini

RUN apk update && apk add \
    gnupg \
    g++ \
    procps \
    openssl \
    git \
    unzip \
    icu-dev \
    libzip-dev \
    acl \
    && echo 'alias sf="php bin/console"' >> ~/.bashrc

RUN docker-php-ext-configure intl
RUN docker-php-ext-install \
    pdo_mysql zip intl opcache mbstring

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

WORKDIR /var/www/flowr
