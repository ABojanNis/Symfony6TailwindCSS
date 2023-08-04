FROM php:8.1-fpm-alpine

# Install system dependencies
RUN apk --update add bash \
    wget \
    curl \
    git \
    php8 \
    php8-curl \
    php8-openssl \
    php8-iconv \
    php8-json \
    php8-mbstring \
    php8-phar \
    php8-dom --repository http://nl.alpinelinux.org/alpine/edge/testing/ && rm /var/cache/apk/*

# Install PHP extensions
RUN docker-php-ext-install pdo pdo_mysql

# Get latest Composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# Set working directory
WORKDIR /var/www/html

USER $user
