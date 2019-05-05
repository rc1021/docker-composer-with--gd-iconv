FROM composer:1.8
MAINTAINER rc1021 <rc.701021@gmail.com>

ENV PHP_EXTS \
        exif \
        gd 

RUN set -xe \
    && NPROC=$(grep -c ^processor /proc/cpuinfo 2>/dev/null || 1) \
    && apk add --no-cache --virtual .lib-deps freetype libpng libjpeg-turbo freetype-dev libpng-dev libjpeg-turbo-dev \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j${NPROC} $PHP_EXTS \
    && apk del freetype-dev libpng-dev libjpeg-turbo-dev

RUN set -xe && \
    composer global require hirak/prestissimo --no-plugins --no-scripts && rm -rf /tmp/.composer