FROM php:7.2-apache

RUN set -xe && \
    apt-get update && \
    apt-get install -y libfreetype6-dev libjpeg-dev libpng-dev \
        git unzip && \
    docker-php-ext-configure gd \
      --with-freetype-dir=/usr/include/ \
      --with-jpeg-dir=/usr/include/ && \
    docker-php-ext-install -j$(nproc) gd pdo_mysql

RUN mkdir /elgg && chown -R www-data:www-data /elgg && \
    a2enmod rewrite




