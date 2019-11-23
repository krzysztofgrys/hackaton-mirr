FROM php:7.3-fpm

RUN apt-get update && apt-get install -y \
    libmcrypt-dev \
    zlib1g-dev \
    libicu-dev \
    libxml2-dev \
    libzip-dev \
    libpng-dev \
    imagemagick \
    libmagickwand-dev \
    g++ \
    wget

RUN docker-php-ext-install -j$(nproc) iconv mysqli pdo_mysql mbstring intl tokenizer xml json zip exif gd bcmath

RUN yes | pecl install xdebug-2.7.2 imagick \
    && docker-php-ext-enable xdebug imagick

RUN wget https://raw.githubusercontent.com/composer/getcomposer.org/master/web/installer -O - -q | php -- --quiet && mv composer.phar /usr/bin/composer

WORKDIR /app
