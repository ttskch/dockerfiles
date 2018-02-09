FROM alpine

ENV DOCROOT /docroot
WORKDIR $DOCROOT

RUN apk update \
    # install php
    && apk add php7 \
    && apk add php7-apcu \
    && apk add php7-ctype \
    && apk add php7-curl \
    && apk add php7-dom \
    && apk add php7-fileinfo \
    && apk add php7-ftp \
    && apk add php7-iconv \
    && apk add php7-intl \
    && apk add php7-json \
    && apk add php7-mbstring \
    && apk add php7-mcrypt \
    && apk add php7-mysqlnd \
    && apk add php7-opcache \
    && apk add php7-openssl \
    && apk add php7-pdo \
    && apk add php7-pdo_sqlite \
    && apk add php7-phar \
    && apk add php7-posix \
    && apk add php7-session \
    && apk add php7-simplexml \
    && apk add php7-sqlite3 \
    && apk add php7-tokenizer \
    && apk add php7-xml \
    && apk add php7-xmlreader \
    && apk add php7-xmlwriter \
    && apk add php7-zlib \
    \
    # install php-fpm
    && apk add php7-fpm \
    \
    # remove caches to decrease image size
    && rm -rf /var/cache/apk/*

ENV PHP_INI_DIR /etc/php7

COPY php.ini $PHP_INI_DIR/

EXPOSE 9000

CMD ["php-fpm7", "--nodaemonize"]
