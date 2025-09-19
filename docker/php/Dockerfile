FROM php:8.2-fpm

# Cài extension cần thiết cho Sylius
RUN apt-get update && apt-get install -y \
    git unzip libicu-dev libpq-dev libzip-dev zip \
    && docker-php-ext-install exif intl pdo pdo_mysql zip opcache

RUN docker-php-ext-enable exif

# Cài đặt Composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# Cài đặt Sylius trong container
WORKDIR /srv/sylius
