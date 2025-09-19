FROM php:8.2-fpm

# Cài extension cần thiết cho Sylius
RUN apt-get update && apt-get install -y \
    git unzip libicu-dev libpq-dev libzip-dev zip \
    && docker-php-ext-install intl pdo pdo_mysql zip opcache

WORKDIR /srv/sylius
