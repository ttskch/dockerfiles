FROM ttskch/php-fpm

ENV DEBIAN_FRONTEND noninteractive

# install ffmpeg
RUN apt-get update \
    && apt-get install -y apt-utils \
    && echo "deb http://www.deb-multimedia.org jessie main non-free" >> /etc/apt/sources.list \
    && echo "deb-src http://www.deb-multimedia.org jessie main non-free" >> /etc/apt/sources.list \
    && apt-get update \
    && apt-get install -y --force-yes deb-multimedia-keyring \
    && apt-get update \
    && apt-get install -y ffmpeg

# install imagemagick and php-imagick
RUN apt-get install -y imagemagick libmagickwand-dev libmagickcore-dev \
    && pecl install imagick \
    && docker-php-ext-enable imagick

COPY php.ini /usr/local/etc/php/
