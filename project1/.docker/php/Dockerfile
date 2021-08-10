FROM php:8.0.3-fpm-alpine3.13

RUN docker-php-ext-install pdo pdo_mysql
RUN apk add libzip-dev gcc make

RUN apk update && apk upgrade && apk add --no-cache ${PHPIZE_DEPS} procps
RUN pecl install xdebug-3.0.3
RUN docker-php-ext-enable xdebug
RUN docker-php-ext-configure opcache --enable-opcache
RUN docker-php-ext-install opcache pdo_mysql

RUN pecl install redis \
    && docker-php-ext-enable redis

RUN docker-php-ext-install zip

WORKDIR /app


