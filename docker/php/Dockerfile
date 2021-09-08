FROM php:7.3.11-fpm

# COPY php.ini
COPY ./php.ini /usr/local/etc/php/php.ini

RUN apt-get update && apt-get install -y \
    mariadb-client \
    libzip-dev \
    zlib1g-dev \
    && docker-php-ext-install \
    zip \
    pdo_mysql \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

#Composer install
COPY --from=composer /usr/bin/composer /usr/bin/composer

#nodejs install
RUN curl -sL https://deb.nodesource.com/setup_16.x | bash - \
    && apt-get update \
    && apt-get install -y nodejs

RUN npm install npm@latest -g

WORKDIR /var/www/html
