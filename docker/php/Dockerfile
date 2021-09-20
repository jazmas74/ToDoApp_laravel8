FROM php:8.0.10-fpm
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
# COPY --from=node:16 /usr/local/bin /usr/local/bin
# COPY --from=node:16 /usr/local/lib /usr/local/lib

# RUN npm install npm@latest -g

#xdebug install
#RUN pecl install xdebug-3.0.4 && docker-php-ext-enable xdebug

WORKDIR /var/www/html
