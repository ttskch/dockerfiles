FROM php:7.3-fpm

RUN apt-get update \
    && apt-get install -y libicu-dev \
    && docker-php-ext-install -j$(nproc) intl \
    \
    && docker-php-ext-install -j$(nproc) opcache \
    \
    && pecl install apcu \
    && docker-php-ext-enable apcu

COPY php.ini $PHP_INI_DIR/
