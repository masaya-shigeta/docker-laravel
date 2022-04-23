FROM php:8.0-fpm

COPY ./docker/php/php.ini /usr/local/etc/php/php.ini
COPY --from=composer:2.0 /usr/bin/composer /usr/bin/composer
COPY --from=node:lts /usr/local/bin /usr/local/bin
COPY --from=node:lts /usr/local/lib /usr/local/lib

RUN apt-get update
RUN apt-get -y install \
    git \
    zip \
    unzip \
    vim
RUN docker-php-ext-install pdo_mysql bcmath

WORKDIR /var/www/html
