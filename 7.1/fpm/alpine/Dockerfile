FROM php:7.1-fpm-alpine

MAINTAINER Yoan-Alexander Grigorov <joan.grigorov@gmail.com>

RUN docker-php-ext-install pdo pdo_mysql mbstring \
    && apk add --no-cache --virtual .build-deps $PHPIZE_DEPS \
    && pecl install ds \
    && docker-php-ext-enable ds \
    && rm -rf /tmp/pear ~/.pearrc \
    && apk del .build-deps
