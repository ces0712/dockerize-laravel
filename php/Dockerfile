FROM php:7.1.11-fpm-jessie

RUN apt-get update && apt-get install -y \
	libmcrypt-dev \
	libfreetype6-dev \
    libjpeg62-turbo-dev \
    libpng12-dev \
    mysql-client libmagickwand-dev --no-install-recommends \
    && pecl install imagick \
    && docker-php-ext-enable imagick \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install gd \
    && docker-php-ext-install mcrypt pdo_mysql

ADD uploads.ini /usr/local/etc/php/conf.d/uploads.ini
