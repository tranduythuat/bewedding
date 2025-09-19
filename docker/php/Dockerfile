FROM php:8.2-fpm

# Cài đặt các extensions PHP cần thiết
RUN apk add --no-cache \
    $PHPIZE_DEPS \
    icu-dev \
    libxml2-dev \
    mariadb-client \
    mariadb-connector-c-dev \
    pcre-dev \
    zlib-dev \
    git \
    unzip \
    && docker-php-ext-install -j$(nproc) \
    intl \
    pdo_mysql \
    zip \
    && docker-php-ext-enable pdo_mysql intl zip

# Cài đặt Composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# Cài đặt Sylius trong container
WORKDIR /srv/sylius
